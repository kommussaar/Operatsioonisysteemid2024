Miks andmekandjad vajavad lähtestamist?

Andmekandjate, nagu kõvaketaste ja SSD-de, lähtestamine on vajalik, et neid saaks arvutis ära tunda ja neile faile salvestada. Uus andmekandja on justkui tühi leht, millel puuduvad failide salvestamiseks vajalikud struktuurid ja juhised. Lähtestamisel muudab arvuti ketta äratuntavaks ja valmistab ette selle kasutamiseks.

Lähtestamisel valitakse ka partitsioonitabeli tüüp (näiteks GPT-GUID Partition Table - GUID-partitsioonitabel)  või MBR-Master Boot Record - põhikäivitussektor), mis määrab ära, kuidas kettal olevaid sektsioone ehk partitsioone hallatakse. Ilma lähtestamiseta ei tunne operatsioonisüsteem ketast üldse ära, mistõttu jääks see salvestusruum kasutuskõlbmatuks.

Millised on GPT kasutamise eelised võrreldes MBRiga? 

Toetab suuremaid kettaid: GPT saab hakkama ketastega, mis on suuremad kui 2 TB. MBR-il on 2 TB piir, mis tähendab, et GPT sobib paremini tänapäevaste suure mahutavusega ketaste jaoks.

Rohkem partitsioone: GPT võimaldab luua rohkem sektsioone ehk partitsioone (Windowsis kuni 128) ilma erilahendusteta. MBR aga toetab ainult 4 peamist partitsiooni või nõuab keerulisemat seadistust.

Suurem töökindlus ja turvalisus: GPT hoiab ketta eri osades varukoopiaid olulistest andmetest, mis aitab vältida andmete kaotust, kui ketta teatud osad saavad kahjustada. MBR-il sellist kaitsemehhanismi pole.
