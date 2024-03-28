# containers05

Numele lucrării de laborator:
Laboratorul 5: Configurarea și Interacțiunea dintre Containere Docker

Scopul lucrării:
Scopul acestei lucrări este de a înțelege și de a aplica conceptele de configurare a containerelor Docker și de a permite interacțiunea între acestea folosind rețele interne.

Sarcina:
Sarcina acestei lucrări constă în crearea și configurarea a două containere Docker, unul pentru serverul web nginx și celălalt pentru un server PHP, și asigurarea interacțiunii între ele în cadrul unei rețele interne. De asemenea, este necesar să se modifice configurarea nginx pentru a servi conținutul PHP.

Descrierea efectuării lucrării cu răspunsuri la întrebări:
Crearea directorului de proiect și configurarea mediului Docker.
Implementarea containerului backend pentru serverul PHP și containerului frontend pentru serverul web nginx.
Configurarea rețelei interne pentru a permite comunicarea între containere.
Configurarea montării volumelor pentru împărtășirea fișierelor între containere.
Configurarea serverului web nginx pentru a servi conținut PHP.
Rularea și testarea interacțiunii dintre containerele Docker.
Concluzii:
În final, veți obține o infrastructură funcțională bazată pe containere Docker, care permite comunicarea între un server web nginx și un server PHP, utilizând o rețea internă și partajând resursele necesare între acestea.

Răspunsuri la întrebări:
În acest exemplu, containerele pot interacționa unul cu celălalt prin intermediul rețelei interne Docker. Această rețea asigură comunicarea privată între containerele care fac parte din aceeași rețea, fără a fi nevoie să expuneți porturi către exterior.

Containerele își văd reciproc prin intermediul numelor lor de container. Atunci când sunt conectate la aceeași rețea internă Docker, acestea pot comunica utilizând numele containerului ca identificator.

A fost necesar să se suprascrie configurarea nginx pentru a configura serverul web pentru a servi conținutul PHP. Prin adăugarea unei noi configurații în fișierul default.conf, serverul nginx este instruit să routeze cererile către serverul PHP pentru procesare, permitând astfel serverului web să ofere conținut dinamico a clientului.




<=====================================Backend container=====================================>

{
	"Id": "ebeb71d14e5542b342e9b6f344391b46b84eae4f0a3a4f89a173a1c72fd20de0",
	"Created": "2024-03-28T18:01:59.072023018Z",
	"Path": "docker-php-entrypoint",
	"Args": [
		"php-fpm"
	],
	"State": {
		"Status": "exited",
		"Running": false,
		"Paused": false,
		"Restarting": false,
		"OOMKilled": false,
		"Dead": false,
		"Pid": 0,
		"ExitCode": 0,
		"Error": "",
		"StartedAt": "2024-03-28T18:11:20.862938676Z",
		"FinishedAt": "2024-03-28T18:48:27.49973309Z"
	},
	"Image": "sha256:38f2b691dcb8c6d4630caa2999173e35be341f2f1264164ae045d9bfb3906c28",
	"ResolvConfPath": "/var/lib/docker/containers/ebeb71d14e5542b342e9b6f344391b46b84eae4f0a3a4f89a173a1c72fd20de0/resolv.conf",
	"HostnamePath": "/var/lib/docker/containers/ebeb71d14e5542b342e9b6f344391b46b84eae4f0a3a4f89a173a1c72fd20de0/hostname",
	"HostsPath": "/var/lib/docker/containers/ebeb71d14e5542b342e9b6f344391b46b84eae4f0a3a4f89a173a1c72fd20de0/hosts",
	"LogPath": "/var/lib/docker/containers/ebeb71d14e5542b342e9b6f344391b46b84eae4f0a3a4f89a173a1c72fd20de0/ebeb71d14e5542b342e9b6f344391b46b84eae4f0a3a4f89a173a1c72fd20de0-json.log",
	"Name": "/backend",
	"RestartCount": 0,
	"Driver": "overlay2",
	"Platform": "linux",
	"MountLabel": "",
	"ProcessLabel": "",
	"AppArmorProfile": "",
	"ExecIDs": null,
	"HostConfig": {
		"Binds": [
			"c:\\Users\\ionca\\Facultate\\Chisinau\\container05/mounts/site:/var/www/html"
		],
		"ContainerIDFile": "",
		"LogConfig": {
			"Type": "json-file",
			"Config": {}
		},
		"NetworkMode": "internal",
		"PortBindings": {},
		"RestartPolicy": {
			"Name": "no",
			"MaximumRetryCount": 0
		},
		"AutoRemove": false,
		"VolumeDriver": "",
		"VolumesFrom": null,
		"ConsoleSize": [
			30,
			120
		],
		"CapAdd": null,
		"CapDrop": null,
		"CgroupnsMode": "host",
		"Dns": [],
		"DnsOptions": [],
		"DnsSearch": [],
		"ExtraHosts": null,
		"GroupAdd": null,
		"IpcMode": "private",
		"Cgroup": "",
		"Links": null,
		"OomScoreAdj": 0,
		"PidMode": "",
		"Privileged": false,
		"PublishAllPorts": false,
		"ReadonlyRootfs": false,
		"SecurityOpt": null,
		"UTSMode": "",
		"UsernsMode": "",
		"ShmSize": 67108864,
		"Runtime": "runc",
		"Isolation": "",
		"CpuShares": 0,
		"Memory": 0,
		"NanoCpus": 0,
		"CgroupParent": "",
		"BlkioWeight": 0,
		"BlkioWeightDevice": [],
		"BlkioDeviceReadBps": [],
		"BlkioDeviceWriteBps": [],
		"BlkioDeviceReadIOps": [],
		"BlkioDeviceWriteIOps": [],
		"CpuPeriod": 0,
		"CpuQuota": 0,
		"CpuRealtimePeriod": 0,
		"CpuRealtimeRuntime": 0,
		"CpusetCpus": "",
		"CpusetMems": "",
		"Devices": [],
		"DeviceCgroupRules": null,
		"DeviceRequests": null,
		"MemoryReservation": 0,
		"MemorySwap": 0,
		"MemorySwappiness": null,
		"OomKillDisable": false,
		"PidsLimit": null,
		"Ulimits": [],
		"CpuCount": 0,
		"CpuPercent": 0,
		"IOMaximumIOps": 0,
		"IOMaximumBandwidth": 0,
		"MaskedPaths": [
			"/proc/asound",
			"/proc/acpi",
			"/proc/kcore",
			"/proc/keys",
			"/proc/latency_stats",
			"/proc/timer_list",
			"/proc/timer_stats",
			"/proc/sched_debug",
			"/proc/scsi",
			"/sys/firmware",
			"/sys/devices/virtual/powercap"
		],
		"ReadonlyPaths": [
			"/proc/bus",
			"/proc/fs",
			"/proc/irq",
			"/proc/sys",
			"/proc/sysrq-trigger"
		]
	},
	"GraphDriver": {
		"Data": {
			"LowerDir": "/var/lib/docker/overlay2/fa41c62713da06b4ce9e1802ece544b34f07605b4ff954d74e053456c0dd7b75-init/diff:/var/lib/docker/overlay2/d9f04f60dbdcb490f38967d12f6c4a8619b7151fe50ccdeda3db24db22ebcf00/diff:/var/lib/docker/overlay2/aae15fb587ff29269199a8474024619bbbc0048e0c4bc46d2bc8918729648c81/diff:/var/lib/docker/overlay2/f90d23cc4dd09cac486c08b241490c26c46ece6a9dfc6229e5b821651420b556/diff:/var/lib/docker/overlay2/14b049a14819d999f0b9103480073ab579890dd55fbe6c3264d6a67ff592f933/diff:/var/lib/docker/overlay2/7dde02af0b8418bb158123c4253237f71db7b7ac25c576a3785f5a46c1f63593/diff:/var/lib/docker/overlay2/0a9cd461f9859c879289b4d83e2053d09528ff00f709d75ed3e897cb93b3adf1/diff:/var/lib/docker/overlay2/3b9e1538406f8799df9ff428ec3d9ce03ccffe2a336d2dd56a40d31f8bd08e66/diff:/var/lib/docker/overlay2/82502d2466527001283072b5d1f3da85c28e5fecbe02d7f17587ff1074768cdd/diff:/var/lib/docker/overlay2/55b06309c481efa6cad90ff6e6a1f2234bff7303fa1635327da8edfacfa9f34f/diff:/var/lib/docker/overlay2/b662568fead4def53c1f38b925663ec52b943e9778e4daf6c894a7f2bcc31cdd/diff",
			"MergedDir": "/var/lib/docker/overlay2/fa41c62713da06b4ce9e1802ece544b34f07605b4ff954d74e053456c0dd7b75/merged",
			"UpperDir": "/var/lib/docker/overlay2/fa41c62713da06b4ce9e1802ece544b34f07605b4ff954d74e053456c0dd7b75/diff",
			"WorkDir": "/var/lib/docker/overlay2/fa41c62713da06b4ce9e1802ece544b34f07605b4ff954d74e053456c0dd7b75/work"
		},
		"Name": "overlay2"
	},
	"Mounts": [
		{
			"Type": "bind",
			"Source": "c:\\Users\\ionca\\Facultate\\Chisinau\\container05/mounts/site",
			"Destination": "/var/www/html",
			"Mode": "",
			"RW": true,
			"Propagation": "rprivate"
		}
	],
	"Config": {
		"Hostname": "ebeb71d14e55",
		"Domainname": "",
		"User": "",
		"AttachStdin": false,
		"AttachStdout": false,
		"AttachStderr": false,
		"ExposedPorts": {
			"9000/tcp": {}
		},
		"Tty": false,
		"OpenStdin": false,
		"StdinOnce": false,
		"Env": [
			"PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
			"PHPIZE_DEPS=autoconf \t\tdpkg-dev \t\tfile \t\tg++ \t\tgcc \t\tlibc-dev \t\tmake \t\tpkg-config \t\tre2c",
			"PHP_INI_DIR=/usr/local/etc/php",
			"PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64",
			"PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2 -D_LARGEFILE_SOURCE -D_FILE_OFFSET_BITS=64",
			"PHP_LDFLAGS=-Wl,-O1 -pie",
			"GPG_KEYS=42670A7FE4D0441C8E4632349E4FDC074A4EF02D 5A52880781F755608BF815FC910DEB46F53EA312",
			"PHP_VERSION=7.4.33",
			"PHP_URL=https://www.php.net/distributions/php-7.4.33.tar.xz",
			"PHP_ASC_URL=https://www.php.net/distributions/php-7.4.33.tar.xz.asc",
			"PHP_SHA256=924846abf93bc613815c55dd3f5809377813ac62a9ec4eb3778675b82a27b927"
		],
		"Cmd": [
			"php-fpm"
		],
		"Image": "php:7.4-fpm",
		"Volumes": null,
		"WorkingDir": "/var/www/html",
		"Entrypoint": [
			"docker-php-entrypoint"
		],
		"OnBuild": null,
		"Labels": {},
		"StopSignal": "SIGQUIT"
	},
	"NetworkSettings": {
		"Bridge": "",
		"SandboxID": "c2578b4c990c3fc57cec0d1336f72465b0353aa63f4b8dc017d6d36bd4674546",
		"SandboxKey": "/var/run/docker/netns/c2578b4c990c",
		"Ports": {},
		"HairpinMode": false,
		"LinkLocalIPv6Address": "",
		"LinkLocalIPv6PrefixLen": 0,
		"SecondaryIPAddresses": null,
		"SecondaryIPv6Addresses": null,
		"EndpointID": "",
		"Gateway": "",
		"GlobalIPv6Address": "",
		"GlobalIPv6PrefixLen": 0,
		"IPAddress": "",
		"IPPrefixLen": 0,
		"IPv6Gateway": "",
		"MacAddress": "",
		"Networks": {
			"internal": {
				"IPAMConfig": null,
				"Links": null,
				"Aliases": [
					"ebeb71d14e55"
				],
				"MacAddress": "",
				"NetworkID": "173d49135c166387a7b04b47742e095930a01cc2a27e4117fe206ba28d8e5bdd",
				"EndpointID": "",
				"Gateway": "",
				"IPAddress": "",
				"IPPrefixLen": 0,
				"IPv6Gateway": "",
				"GlobalIPv6Address": "",
				"GlobalIPv6PrefixLen": 0,
				"DriverOpts": null,
				"DNSNames": [
					"backend",
					"ebeb71d14e55"
				]
			}
		}
	}
}

<=====================================Frontend container=====================================>



{
	"Id": "d0a179c39e14aa8b4f0f273613e1cf2cc6f546100aa8f1b9e5ada51cc0064b4b",
	"Created": "2024-03-28T18:10:38.493770484Z",
	"Path": "/docker-entrypoint.sh",
	"Args": [
		"nginx",
		"-g",
		"daemon off;"
	],
	"State": {
		"Status": "exited",
		"Running": false,
		"Paused": false,
		"Restarting": false,
		"OOMKilled": false,
		"Dead": false,
		"Pid": 0,
		"ExitCode": 0,
		"Error": "",
		"StartedAt": "2024-03-28T18:11:18.56094499Z",
		"FinishedAt": "2024-03-28T18:48:28.409031267Z"
	},
	"Image": "sha256:8e75cbc5b25c8438fcfe2e7c12c98409d5f161cbb668d6c444e02796691ada70",
	"ResolvConfPath": "/var/lib/docker/containers/d0a179c39e14aa8b4f0f273613e1cf2cc6f546100aa8f1b9e5ada51cc0064b4b/resolv.conf",
	"HostnamePath": "/var/lib/docker/containers/d0a179c39e14aa8b4f0f273613e1cf2cc6f546100aa8f1b9e5ada51cc0064b4b/hostname",
	"HostsPath": "/var/lib/docker/containers/d0a179c39e14aa8b4f0f273613e1cf2cc6f546100aa8f1b9e5ada51cc0064b4b/hosts",
	"LogPath": "/var/lib/docker/containers/d0a179c39e14aa8b4f0f273613e1cf2cc6f546100aa8f1b9e5ada51cc0064b4b/d0a179c39e14aa8b4f0f273613e1cf2cc6f546100aa8f1b9e5ada51cc0064b4b-json.log",
	"Name": "/frontend",
	"RestartCount": 0,
	"Driver": "overlay2",
	"Platform": "linux",
	"MountLabel": "",
	"ProcessLabel": "",
	"AppArmorProfile": "",
	"ExecIDs": null,
	"HostConfig": {
		"Binds": [
			"C:\\Users\\ionca\\Facultate\\Chisinau\\container05/mounts/site/simplu_proiect_php:/var/www/simplu_proiect_php",
			"C:\\Users\\ionca\\Facultate\\Chisinau\\container05/nginx/default.conf:/etc/nginx/conf.d/default.conf",
			"C:\\Users\\ionca\\Facultate\\Chisinau\\container05/mounts/site:/var/www/html"
		],
		"ContainerIDFile": "",
		"LogConfig": {
			"Type": "json-file",
			"Config": {}
		},
		"NetworkMode": "internal",
		"PortBindings": {
			"80/tcp": [
				{
					"HostIp": "",
					"HostPort": "80"
				}
			]
		},
		"RestartPolicy": {
			"Name": "no",
			"MaximumRetryCount": 0
		},
		"AutoRemove": false,
		"VolumeDriver": "",
		"VolumesFrom": null,
		"ConsoleSize": [
			30,
			120
		],
		"CapAdd": null,
		"CapDrop": null,
		"CgroupnsMode": "host",
		"Dns": [],
		"DnsOptions": [],
		"DnsSearch": [],
		"ExtraHosts": null,
		"GroupAdd": null,
		"IpcMode": "private",
		"Cgroup": "",
		"Links": null,
		"OomScoreAdj": 0,
		"PidMode": "",
		"Privileged": false,
		"PublishAllPorts": false,
		"ReadonlyRootfs": false,
		"SecurityOpt": null,
		"UTSMode": "",
		"UsernsMode": "",
		"ShmSize": 67108864,
		"Runtime": "runc",
		"Isolation": "",
		"CpuShares": 0,
		"Memory": 0,
		"NanoCpus": 0,
		"CgroupParent": "",
		"BlkioWeight": 0,
		"BlkioWeightDevice": [],
		"BlkioDeviceReadBps": [],
		"BlkioDeviceWriteBps": [],
		"BlkioDeviceReadIOps": [],
		"BlkioDeviceWriteIOps": [],
		"CpuPeriod": 0,
		"CpuQuota": 0,
		"CpuRealtimePeriod": 0,
		"CpuRealtimeRuntime": 0,
		"CpusetCpus": "",
		"CpusetMems": "",
		"Devices": [],
		"DeviceCgroupRules": null,
		"DeviceRequests": null,
		"MemoryReservation": 0,
		"MemorySwap": 0,
		"MemorySwappiness": null,
		"OomKillDisable": false,
		"PidsLimit": null,
		"Ulimits": [],
		"CpuCount": 0,
		"CpuPercent": 0,
		"IOMaximumIOps": 0,
		"IOMaximumBandwidth": 0,
		"MaskedPaths": [
			"/proc/asound",
			"/proc/acpi",
			"/proc/kcore",
			"/proc/keys",
			"/proc/latency_stats",
			"/proc/timer_list",
			"/proc/timer_stats",
			"/proc/sched_debug",
			"/proc/scsi",
			"/sys/firmware",
			"/sys/devices/virtual/powercap"
		],
		"ReadonlyPaths": [
			"/proc/bus",
			"/proc/fs",
			"/proc/irq",
			"/proc/sys",
			"/proc/sysrq-trigger"
		]
	},
	"GraphDriver": {
		"Data": {
			"LowerDir": "/var/lib/docker/overlay2/13cf564eeccb025040e4a86b883fb9582267ba30f5a9495811eeacb84814931b-init/diff:/var/lib/docker/overlay2/19b805483b6aeb600cb458f12764af2c6048b93129440a2eca5462769808d953/diff:/var/lib/docker/overlay2/66ba7e7568ec8f78ae1e695d77cbd636905b6b1dc4478a0ad94c92c9ba6b72d5/diff:/var/lib/docker/overlay2/72d801ab3f3d390a7bae41cb3cec91398ab059f8dfc39137538b9a5622bdad7a/diff:/var/lib/docker/overlay2/f60f7807b5f693b5cda7d1ed1babadadf46fc73b1fb8d03fdce1b35a2b8a566d/diff:/var/lib/docker/overlay2/2c9ad7d35bd487cf83c75029c6fdc68947593244f441d27d26b93048189337c4/diff:/var/lib/docker/overlay2/32d8bf8af078667207e65d6f7315ba1e827dd5ae2f0b7fcc6c6c25aa1f474dc0/diff:/var/lib/docker/overlay2/85c4d75860daeac33c62e5657ee06816d93fa9f1a2eb87d5f0514d7e3e4a6ac0/diff",
			"MergedDir": "/var/lib/docker/overlay2/13cf564eeccb025040e4a86b883fb9582267ba30f5a9495811eeacb84814931b/merged",
			"UpperDir": "/var/lib/docker/overlay2/13cf564eeccb025040e4a86b883fb9582267ba30f5a9495811eeacb84814931b/diff",
			"WorkDir": "/var/lib/docker/overlay2/13cf564eeccb025040e4a86b883fb9582267ba30f5a9495811eeacb84814931b/work"
		},
		"Name": "overlay2"
	},
	"Mounts": [
		{
			"Type": "bind",
			"Source": "C:\\Users\\ionca\\Facultate\\Chisinau\\container05/mounts/site/simplu_proiect_php",
			"Destination": "/var/www/simplu_proiect_php",
			"Mode": "",
			"RW": true,
			"Propagation": "rprivate"
		},
		{
			"Type": "bind",
			"Source": "C:\\Users\\ionca\\Facultate\\Chisinau\\container05/nginx/default.conf",
			"Destination": "/etc/nginx/conf.d/default.conf",
			"Mode": "",
			"RW": true,
			"Propagation": "rprivate"
		},
		{
			"Type": "bind",
			"Source": "C:\\Users\\ionca\\Facultate\\Chisinau\\container05/mounts/site",
			"Destination": "/var/www/html",
			"Mode": "",
			"RW": true,
			"Propagation": "rprivate"
		}
	],
	"Config": {
		"Hostname": "d0a179c39e14",
		"Domainname": "",
		"User": "",
		"AttachStdin": false,
		"AttachStdout": false,
		"AttachStderr": false,
		"ExposedPorts": {
			"80/tcp": {}
		},
		"Tty": false,
		"OpenStdin": false,
		"StdinOnce": false,
		"Env": [
			"PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
			"NGINX_VERSION=1.23.4",
			"PKG_RELEASE=1",
			"NJS_VERSION=0.7.11"
		],
		"Cmd": [
			"nginx",
			"-g",
			"daemon off;"
		],
		"Image": "nginx:1.23-alpine",
		"Volumes": null,
		"WorkingDir": "",
		"Entrypoint": [
			"/docker-entrypoint.sh"
		],
		"OnBuild": null,
		"Labels": {
			"maintainer": "NGINX Docker Maintainers <docker-maint@nginx.com>"
		},
		"StopSignal": "SIGQUIT"
	},
	"NetworkSettings": {
		"Bridge": "",
		"SandboxID": "a4da753e23c9d4f9a6e6eec14fecf7cacbef9a6a92e7600565dd8ea8e66f6eb6",
		"SandboxKey": "/var/run/docker/netns/a4da753e23c9",
		"Ports": {},
		"HairpinMode": false,
		"LinkLocalIPv6Address": "",
		"LinkLocalIPv6PrefixLen": 0,
		"SecondaryIPAddresses": null,
		"SecondaryIPv6Addresses": null,
		"EndpointID": "",
		"Gateway": "",
		"GlobalIPv6Address": "",
		"GlobalIPv6PrefixLen": 0,
		"IPAddress": "",
		"IPPrefixLen": 0,
		"IPv6Gateway": "",
		"MacAddress": "",
		"Networks": {
			"internal": {
				"IPAMConfig": null,
				"Links": null,
				"Aliases": [
					"d0a179c39e14"
				],
				"MacAddress": "",
				"NetworkID": "173d49135c166387a7b04b47742e095930a01cc2a27e4117fe206ba28d8e5bdd",
				"EndpointID": "",
				"Gateway": "",
				"IPAddress": "",
				"IPPrefixLen": 0,
				"IPv6Gateway": "",
				"GlobalIPv6Address": "",
				"GlobalIPv6PrefixLen": 0,
				"DriverOpts": null,
				"DNSNames": [
					"frontend",
					"d0a179c39e14"
				]
			}
		}
	}
}
