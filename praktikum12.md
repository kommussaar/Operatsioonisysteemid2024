Ül 3 kood:  ```#!/bin/sh
echo "Tere, mis on teie nimi?:"
read kasutaja_nimi
echo "Tere $kasutaja_nimi!"
echo "Mis on teie eriala?"
read eriala
echo "Teie eriala on $eriala"
echo "Mis on teie matriklinumber?"
read matriklinumber
echo "Teie matriklinumber on $matriklinumber"``` 

Ül 3 ekraanivaade: ![image](https://github.com/user-attachments/assets/41c3f904-3d95-404f-be46-a43e6712f93f)

Ül 4 kood: ```#!/bin/bash

for i in *.$1; do
if [ -f "$i" ]; then
mv "$i" "${i/$1/$2}"
fi
done```

ül 4 ekraanivaade: ![image](https://github.com/user-attachments/assets/503d59ce-682b-4487-ab54-2945380c8ffb)


ül 6 kood: ```#!/bin/bash

eksponendi_fuktsioon() {
    baas=$1
    eksponent=$2
    tulemus=1

    while [ $eksponent -gt 0 ]; do
        tulemus=$((tulemus*baas))
        eksponent=$((eksponent-1))
    done

    echo "Tulemus: $tulemus"
}



eksponendi_fuktsioon 9 5```

ül 6 ekraanivaade: ![image](https://github.com/user-attachments/assets/dc168a92-fdca-43bb-89dd-bf65a58238fe)
