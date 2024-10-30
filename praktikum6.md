Ülesanne 1: ![image](https://github.com/user-attachments/assets/0f27e552-c084-46bb-84da-75a48a951fea)
Ülesanne 2: ![image](https://github.com/user-attachments/assets/bdbd0adb-c6aa-461c-9ee5-574545416e30)
Ülesanne 3: Käsk teksti kujul: ps -axu | grep daemon | grep -v 'grep' | awk '{for(i=11;i<=NF;i++) printf "%s ", $i; print ""}' | tr -s ' ' | sed -E 's#.*/##; s/^@//' | grep -v '^\s*bus\s*$' (millegipärast on hetke viimane | viltu)
![image](https://github.com/user-attachments/assets/7a2b0d3a-140f-4cea-bfcb-d3c49d545290)


