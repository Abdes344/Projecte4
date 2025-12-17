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

Ara Tornarem a fer el mateix procediment de abans i al arribar aqui triarem l'opció de Google Drive

---


![imatge](/Tasca02/IMG/14.png)

En aquest apartat li donarem on ens diu AuthID i ens demanara que fiquem un compte de Google Drive


---


![imatge](/Tasca02/IMG/15.png)

I ara ficarem de temporització que es faci cada dia a les 18:00 


---


![imatge](/Tasca02/IMG/16.png)

I Aquí veiem que ja la tenim creada 


---

![imatge](/Tasca02/IMG/17.png)

I aquí veiem que ja estaria tot correctament 

---


![imatge](/Tasca02/IMG/18.png)

Aquí veiem que en explorador de arxius tenim tot creat correctament 


---

![imatge](/Tasca02/IMG/19.png)

I en el Drive també o tenim creat correctament 


---


![imatge](/Tasca02/IMG/20.png)

Ara li donarem els tres punts i triarem l'opció de restore 


---


![imatge](/Tasca02/IMG/21.png)

Aquí li donarem a continuar 


---


![imatge](/Tasca02/IMG/22.png)

En aquest apartat de aquí li tornarem a donar a continuar 


---


![imatge](/Tasca02/IMG/23.png)

i aquí veiem que el restore està ben fet 


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

