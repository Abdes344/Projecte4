# T09: Servidor fitxers Linux. NFS (tasca individual)

---

![imatge](/Tasca09/IMG/1.png) 

El primer que haurem de fer serà crear dos grups el grup devs i el grup admins 

---

![imatge](/Tasca09/IMG/2.png) 

Justament després haurem de crear dos usuaris dins dels grups fets anteriorment 

---

![imatge](/Tasca09/IMG/3.png) 

Ara farem un “cd /srv” per entrar com a root per ficar-li contrasenya al nostre usuari dev01 



![imatge](/Tasca09/IMG/4.png) 

Farem el mateix que abans entrar com a root per ficar-li contrasenya al nostre usuari admin01

---


![imatge](/Tasca09/IMG/5.png) 

Ara crearem les carpetes dev_projects i admin_tools amb la comanda “sudo mkdir -p /srv/nfs/…”


---

![imatge](/Tasca09/IMG/6.png) 

Ara farem les següents comandes per configurar els permisos i propietats per tenir un accés segur en el directori.


---

![imatge](/Tasca09/IMG/7.png)

Ara farem el mateix, però el que cambia es la carpeta que ara utilitzarem admin_tools

---


![imatge](/Tasca09/IMG/8.png)

Ara farem un sudo su per tronar a entrar com a root i instal·larem el nfs-kernel-server

---


![imatge](/Tasca09/IMG/9.png)

Ara entrarem a configurar el arxiu entrant amb “sudo nano /etc/exports i afagerimen les dues últimes línies


---


![imatge](/Tasca09/IMG/10.png)

Fent les següents comandes veurem si el arxiu ho hem fet correctament sudo systemctl  start nfs-kernel-server, sudo systemctl reload nfs-kernel-server, sudo exportfs -u 
sudo systemctl enable nfs-kernel-server


---

![imatge](/Tasca09/IMG/11.png)

Ara veurem la informació de la nostrte ip amb “sudo rpcinfo -p 192.168.56.108

---


![imatge](/Tasca09/IMG/12.png)

Ara crearem dos grups en el client amb les comandes “sudo groupadd -g 1001 devs/admins”


![imatge](/Tasca09/IMG/13.png)

Justament després haurem de crear dos usuaris dins dels grups fets anteriorment 

---

![imatge](/Tasca09/IMG/14.png)

I ara li ficarem contrasenya en els dos usuaris 


---

![imatge](/Tasca09/IMG/15.png)

Després de fer tot reiniciarem i ja ens sortiran correctament els dos usuaris 


---

![imatge](/Tasca09/IMG/16.png)

Ara entrarem al client i farem un ping 192.168.56.108 i veurem si es connecta


---

![imatge](/Tasca09/IMG/17.png)

Fem un “sudo apt upgrade” per actualitzar la màquina

---

![imatge](/Tasca09/IMG/18.png)

Ara instal·larem el nfs-common 

---


![imatge](/Tasca09/IMG/19.png)

Ara fem la següent comanda “sudo showmount -e 192.168.56.108” per veure si a la màquina del servidor el arxiu /etc/exports està fet correctament


---

![imatge](/Tasca09/IMG/20.png)

Ara fem un sudo mkdir -p /mnt/admin_tools per crear la carpeta


---


![imatge](/Tasca09/IMG/21.png)

Ara muntarem el recurs NFS al client per entrar al fitxer de forma remota


---


![imatge](/Tasca09/IMG/22.png)

Comprovem que el fitxer s’ha creat al punt de muntatge funciona i respecta els permisos del servidor 


---


![imatge](/Tasca09/IMG/23.png)

Amb “sudo umount /mnt/admin_tools” desmuntem el directori /mnt/admin_tools. Amb “sudo mount -t nfs 192.168.56.108:/srv/nfs/admin_tools /mnt/admin_tools es munta el directori NFS remot al punt de muntatge. Amb “sudo touch /mnt/admin_tools/test2.txt crearem el arxiu test2.txt dins del directori muntat


---

![imatge](/Tasca09/IMG/24.png)
Ara crearem el directori del muntatge i muntarem el recurs NFS al sistem per poder accedir als fitxers


---

![imatge](/Tasca09/IMG/25.png)

Ara entrarem a fitxers ens anirem a otras ubicaciones anirem al primer apartat que serà el del nostre ordinador i buscarem la carpeta mnt on trobarem les dues carpetes que hem creat 


---

![imatge](/Tasca09/IMG/26.png)

Quan entrem a la carpeta admin_tools ens trobarem els dos .txt que hem creat abans i a la carpeta de dev_projects no ens ha de sortir res 


---

![imatge](/Tasca09/IMG/27.png)

En el client entrarem en el arxiu /etc/fstab i tindrem que escriure les dues últimes línies amb la nostre IP per afegir les entrades NFS al fitxer /etc/fstab per muntar automàticament els recursos compartits    



---

![imatge](/Tasca09/IMG/28.png)

Ara fem un “sudo reboot” per reiniciar la màquina 

---

![imatge](/Tasca09/IMG/29.png)

Fem un mount | grep nfs i veurem que tot està correcta 

