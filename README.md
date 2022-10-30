# Tillståndsmaskin - ATmega328P
Implementering av en tillståndsmaskin för multipla lysdioder, som kan blinka, tändas och släckas. 
Interrupts används för att direkt uppdatera lysdiodernas tillstånd via tryckknappar. Pekare används i samband med 
blinkhastighet för att direkt kunna avbryta eventuell blinkning vid byte av tillstånd 
(blinkhastighetem som refereras till av pekaren nollställs närtillståndet övergår från blinkande till något annat).

I filen "header.h" implementeras deklarationer, enumerationer och definitioner för implementering av tillståndsmaskinen. 
I filen "main.c" åstadkommes initiering av mikrodatorn, följt av att tillståndsmaskinen utsignaler uppdateras kontinuerligt. 
I filen "setup.c" sker initiering av mikrodatorn (I/O-portarna konfigureras och avbrott aktiveras på tryckknapparnas pinnar). 
I filen "interrupts.c" placeras avbrottsrutiner för att uppdatera tillståndsmaskinens tillstånd vid nedtryckning av någon av tryckknapparna. 
I filen "fsm.c" definieras funktioner för att realisera tillståndsmaskinen.

Se video tutorial här (först demonstreras icke flankstyrda avbrott, sedan implementeras tillståndsmaskinen):
https://youtu.be/_ZN9jcZ_Zqk
