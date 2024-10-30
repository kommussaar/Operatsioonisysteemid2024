Ülesanne 1: ![image](https://github.com/user-attachments/assets/0f27e552-c084-46bb-84da-75a48a951fea)
Ülesanne 2: ![image](https://github.com/user-attachments/assets/bdbd0adb-c6aa-461c-9ee5-574545416e30)
Ülesanne 3: Käsk teksti kujul: ps -axu | grep daemon | grep -v 'grep' | awk '{for(i=11;i<=NF;i++) printf "%s ", $i; print ""}' | tr -s ' ' | sed -E 's#.*/##; s/^@//' | grep -v '^\s*bus\s*$'
![image](https://github.com/user-attachments/assets/7a2b0d3a-140f-4cea-bfcb-d3c49d545290)
Ülesanne 4: Käsk teksi kujul: ip a | grep -oP 'inet \K[\d.]+' | grep -v '^127' | head -n 1 > ipaddress.txt
![image](https://github.com/user-attachments/assets/1c282216-9c84-4122-a623-1e8b6e3ba3f6)



