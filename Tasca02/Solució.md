# T02: DPR: còpies de seguretat. Cas pràctic

---

![imatge](/Tasca02/IMG/1.png)

El primer que farem serà crear un nou disc de 10 GB com ens diu a la tasca 

---

![imatge](/Tasca02/IMG/2.png)

Després ja entrarem al Windows i el que tindrem que fera serà instal·lar el duplicati

---

![imatge](/Tasca02/IMG/3.png)

Al entrar al duplicati tindrem que donar-li a la primera opció que es la de crear una nova backup

---


![imatge](/Tasca02/IMG/4.png)

Ens portara en aquest apartat que el únic que tindrem que fer serà donar-li un altre cop a la primera opció la de crear una nova backup

---

![imatge](/Tasca02/IMG/5.png)

Aquí el que farem serà ficar el nom del nostre backup i després ficar-li una contrasenya 

---

![imatge](/Tasca02/IMG/6.png)

Aquí triarem l'opció de “file system” i triarem el disc que vam crear al principi abans de entrar a la màquina.

---

![imatge](/Tasca02/IMG/7.png) 

Aquí triarem la ruta de la carpeta en el meu cas he triat la de HOME

---

![imatge](/Tasca02/IMG/8.png)

Aquí o configurarem com ens diu a la tasca que ha cada hora es vagi actualitzant 

---

![imatge](/Tasca02/IMG/9.png)

Aquí no tocarem res i continuarem i ja hauríem acabat

---

![imatge](/Tasca02/IMG/10.png)

Aquí veiem que tenim la backup creada

---


![imatge](/Tasca02/IMG/11.png)

Després de donar-li a start veiem que tenim una versió nova  

---

![imatge](/Tasca02/IMG/12.png)

Ara Tornarem a fer el mateix procediment de abans i al arribar aqui triarem l'opció de Google Drive

---


![imatge](/Tasca02/IMG/13.png)

En aquest apartat li donarem on ens diu AuthID i ens demanara que fiquem un compte de Google Drive

---

![imatge](/Tasca02/IMG/14.png)

I ara ficarem de temporització que es faci cada dia a les 18:00 


---

![imatge](/Tasca02/IMG/15.png)

I Aquí veiem que ja la tenim creada 

---

![imatge](/Tasca02/IMG/16.png)

I aquí veiem que ja estaria tot correctament 


---

![imatge](/Tasca02/IMG/17.png)

Aquí veiem que en explorador de arxius tenim tot creat correctament 


![imatge](/Tasca02/IMG/18.png)

I en el Drive també o tenim creat correctament 


---

![imatge](/Tasca02/IMG/19.png)

Ara li donarem els tres punts i triarem l'opció de restore 

---

![imatge](/Tasca02/IMG/20.png)

Aquí li donarem a continuar 

---


![imatge](/Tasca02/IMG/21.png)

En aquest apartat de aquí li tornarem a donar a continuar 

---


![imatge](/Tasca02/IMG/22.png)

i aquí veiem que el restore està ben fet 


---

![imatge](/Tasca02/IMG/23.png)

Farem el mateix amb la backup de Google Drive i li donarem a restore  

---

![imatge](/Tasca02/IMG/24.png)

Aqui li donarem a continuar sense tocar res


---


![imatge](/Tasca02/IMG/25.png)

tornarem a donar-li a continuar

---


![imatge](/Tasca02/IMG/26.png)

i aquí veiem que el restore l’hem fet correctament 


---


![imatge](/Tasca02/IMG/27.png)

Ara crearem un nou disc de 10 GB per a la maquina de zorin


---

![imatge](/Tasca02/IMG/28.png)

Entrem a la terminal i farem un “lsblk -o NAME,SIZE,TYPE,MOUNTPOINT


---

![imatge](/Tasca02/IMG/29.png)

Ara fem una partició i crearem una partició XFS en un disc usant el parted 


---

![imatge](/Tasca02/IMG/30.png)

Amb la comanda “lsblk -f” mostrarem el llistat i discos i particions del sistema 


---


![imatge](/Tasca02/IMG/31.png)

Amb “sudo apt install xfsprogs” el instalarem 

---


![imatge](/Tasca02/IMG/32.png)

Ara formatem la partició /dev/sdb1 amb el sistema de arxius XFS

---


![imatge](/Tasca02/IMG/33.png)

Aqui crearem el punt de muntatge i després el muntarem


---


![imatge](/Tasca02/IMG/34.png)

Aquí instalarem el duplicity 


---

![imatge](/Tasca02/IMG/35.png)

Aqui crearem un usuari que es dirà usuari1 i fitxers de prova 

---


![imatge](/Tasca02/IMG/36.png)

Farem el mateix, però amb un altre usuari que es dirà usuari2 

---

![imatge](/Tasca02/IMG/37.png)

Ara crearem fitxers de 10 MB en el teu home 


---


![imatge](/Tasca02/IMG/38.png)

Ara el que tindrem que fer serà un export PASSPHRASE=”contrasenya_forta”

---

![imatge](/Tasca02/IMG/39.png)

Ara ficarem la següent comanda “sudo duplicity /home file:///media/backup/duplicity” per crear el backup en el arxiu 


---


![imatge](/Tasca02/IMG/40.png)

Ara mostrarem l’estat del backup en duplicity amb la comanda “duplicity collection-status file:///media/backup/duplicity

---


![imatge](/Tasca02/IMG/41.png)

Fem un “sudo umount /media/backup” per desmuntar la carpeta

---


![imatge](/Tasca02/IMG/42.png)

Ara entrem amb sudo nano /usr/local/bin/fullbackup.sh per completar el arxiu amb tot el que hi ha a la captura 


---

![imatge](/Tasca02/IMG/43.png)

Després de escriure el arxiu el que farem serà fer un “sudo chmod +x /usr/local/bin/fullbackup.sh” 

---


![imatge](/Tasca02/IMG/44.png)

Fiquem la comanda “sudo crontab -e” i triarem la primera opció i ens portara a un arxiu nano


---


![imatge](/Tasca02/IMG/45.png)

Quan entrem en aquest arxiu afegim una línia per programar el cron  i per fer un backup cada dia a les 23:00


---


![imatge](/Tasca02/IMG/46.png)

Entrem en un altre arxiu nano i tornarem a escriure tot l’arxiu 


---


![imatge](/Tasca02/IMG/47.png)

Després de escriure tot l’arxiu tornem a escriure la comanda  “sudo chmod +x /usr/local/bin/fullbackup.sh” 


---


![imatge](/Tasca02/IMG/48.png)

Tornem a programar el crontab, però ara ho farem de dilluns a dissabte a les 23:00


---



![imatge](/Tasca02/IMG/49.png)

Ara anem al explorador de arxius anem a “other Locations” i entrem en el disc creat anteriorment i ens tindria que sortir la carpeta duplicity 


---


![imatge](/Tasca02/IMG/50.png)

Al entrar ens tindrien que sortir uns quants fitxers 

---


![imatge](/Tasca02/IMG/51.png)

Tornem a entrar a la terminal i fem un “sudo mount /dev/sdb1 /media/backup” i després un ls i veiem tots els fitxers ensenyats anteriorment 


---


![imatge](/Tasca02/IMG/52.png)

Aquí tornem a veure del duplicity collection


---

