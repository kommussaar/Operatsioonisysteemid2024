# Praktikum 15: Teenused ja optimeerimine

Käesolevas praktikumis uurisin kuidas oma arvutit (operatsioonisüsteemi) optimeerida ja teha ka turvalisemaks. Tutuvusin keskkonnamuutujatega nii Linux Debian-i kui ka Windows-i operatsioonisüsteemis. Uurisin teenuste kohta, tegelesin tarkvara haldusega ning lõpuks analüüsisin pilvetehnoloogia kulusid. Allpool on tulemus. 

***Ülesanne 1***:Tarkvara mis tundub üleliigne olevat: Apache2. ***Mis on Apache2?*** Apache2 on laialdaselt kasutatav avatud lähtekoodiga veebiserveri tarkvara. Selle põhifunktsioon on veebilehtede (HTML-failide, piltide, skriptide jne) teenindamine kasutajatele, kes neid veebibrauseri kaudu küsivad. Apache2 toetab erinevaid mooduleid, mis pakuvad täiendavat funktsionaalsust, nagu SSL, autentimine, URL-i ümberkirjutamine jne. Kasutatakse sageli veebisaitide ja veebirakenduste majutamiseks. ***Miks ta on minu arvates ebavajalik.*** Esiteks, kui süsteem ei vaja veebisaitide või veebirakenduste majutamist (nt isiklik masin või tarkvara, mis ei nõua veebiserverit). Teiseks võivad kasutajad eelistada muid tarkvarasid, mis ei vaja üldse veebiserverit (nt andmebaasiserverid või failide jagamise tarkvara). Lisaks võib Apache2 olla turvaprobleemiks, kui jääb näiteks tööle ilma vajaduseta.
![image](https://github.com/user-attachments/assets/7d87485e-1318-4fb0-b1e7-ae58bb18fec8)
![image](https://github.com/user-attachments/assets/74954ce5-5505-4276-ba77-dcf3d3187085)


***Ülesanne 2***: ![image](https://github.com/user-attachments/assets/7b67d20e-193a-403d-a58e-8e34367759fe)
***Ülesanne 3***: Süsteemi "%Path%" märgitud kaustas olev fail käivitatakse, sest kasutaja keskkonnamuutuja %Path% on nimekirjas süsteemi omast tagapool.
***Ülesanne 4***: Valitud teenus, mille nimi algab minu perenime esitähega (K): ***KtmRm for Distributed Transaction Coordinator (KtmRm-Kernel Transaction Manager Resource Manager)*** ehk KtmRm teenus tuuma tehinguhalduri ressursihaldurile on teenus, mis aitab korraldada ja hallata tehinguid, mis hõlmavad mitut süsteemi või arvuti osa korraga. Näide: Kui programm vajab, et kaks või enam süsteemi töötaksid koos sujuvalt (näiteks andmebaasi värskendamine ja faili salvestamine samal ajal), siis see teenus aitab kõik sünkroonis hoida.
Kas teenuse töötamine on vajalik oma masinas (ja miks) (kas võib teenuse "disabled" määrata)? Ei, seda teenust ei ole tavaliselt vaja tavakasutaja arvutis. Põhjendus: kuna seda kasutatakse peamiselt suurtes ettevõtete süsteemides (nt serverites), kus palju erinevaid komponente peavad koos töötama. Koduarvutites ei kasuta enamik inimesi programme, mis seda teenust vajaksid. Teenuse võib määrata ***Disabled*** olekusse, kui pole spetsiaalset tarkvara, mis seda vajab.
***Ülesanne 5***: ![image](https://github.com/user-attachments/assets/8c077371-6145-423f-87dc-942d4cf2fdda)
***Ülesanne 6***: ![image](https://github.com/user-attachments/assets/d8306e93-518e-4270-8634-5c28412627f7)
