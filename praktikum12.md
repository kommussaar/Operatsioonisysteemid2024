12. praktikumis õppisin põhilist skriptimist Linuxis. Tulemus on näha allpool





Ül 3 kood:  #!/bin/sh
echo "Tere, mis on teie nimi?:"
read kasutaja_nimi
echo "Tere $kasutaja_nimi!"
echo "Mis on teie eriala?"
read eriala
echo "Teie eriala on $eriala"
echo "Mis on teie matriklinumber?"
read matriklinumber
echo "Teie matriklinumber on $matriklinumber"

Ül 3 ekraanivaade: ![image](https://github.com/user-attachments/assets/41c3f904-3d95-404f-be46-a43e6712f93f)

Ül 4 kood:
#!/bin/bash

for i in *.$1; do
    if [ -f "$i" ]; then
        mv "$i" "${i/$1/$2}"
    fi
done

ül 4 ekraanivaade: ![image](https://github.com/user-attachments/assets/503d59ce-682b-4487-ab54-2945380c8ffb)


ül 6 kood: #!/bin/bash

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



eksponendi_fuktsioon 9 5

ül 5 kood: #!/bin/bash

# Kontrollime, kas on antud argument (protsessi nimi)
if [ -z "$1" ]; then
  echo "Palun sisestage protsessi nimi!"
  exit 1
fi

# Käivitame ps -A ja filtreerime otsitava protsessi nime grep abil
ps -A | while read line
do
    # Eemaldame liigsed tühikud
    processed_line=$(echo "$line" | tr -s ' ')

    # Eraldame PID ja ülejäänud osa (protsessi nimi)
    pid=$(echo "$processed_line" | cut -d ' ' -f1)
    process_name=$(echo "$processed_line" | cut -d ' ' -f4-)

    # Kui protsessi nimi sisaldab otsitavat nime, siis väljastame PID ja nime
    if [[ "$process_name" == *"$1"* ]]; then
        echo "PID: $pid, Protsessi nimi: $process_name"
    fi
done

ül 5 ekraanivaade: ![image](https://github.com/user-attachments/assets/8c24e974-2c6d-4fe9-8f94-0f374de54aed)


ül 6 ekraanivaade: ![image](https://github.com/user-attachments/assets/dc168a92-fdca-43bb-89dd-bf65a58238fe)

ül 7 ekraanivaade: ![image](https://github.com/user-attachments/assets/b9bcd710-648b-4bc2-82b6-c687ef383672)
![image](https://github.com/user-attachments/assets/e45ef06f-492b-4981-bfc8-37729a6e2ff1)
![image](https://github.com/user-attachments/assets/f15052f6-5172-4d78-b9cf-69b13861ed59)




