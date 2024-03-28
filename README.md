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
