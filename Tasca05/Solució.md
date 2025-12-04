# **T05: Accés Remot. Connexió via SSH**

![imatge](/Tasca05/ServeiSSH/1.png) 

Primer el que farem serà deixar el primer adaptador en NAT i el segon el ficarem en adaptador només amfitrió 

---

![imatge](/Tasca05/ServeiSSH/2.png) 
Amb la comanda “sudo apt install ssh” instal·larem el servei ssh  

---

![imatge](/Tasca05/ServeiSSH/3.png)   
Ara configurarem el arxiu del netplan afegint l’enp0s8 per entrar el que farem sera ficar la següent comanda “sudo nano /etc/netplan/50-cloud-init.yaml”

---

![imatge](/Tasca05/ServeiSSH/4.png)   
Després de configurar l’arxiu farem un “sudo netplan apply” per aplicar els canvis que acabem de fer

---

![imatge](/Tasca05/ServeiSSH/5.png)   
Després farem un ip per veure que en el enp0s8 tenim la ip   

---

![imatge](/Tasca05/ServeiSSH/6.png)   
Entrem a la terminal i connectem el ssh i fem un hostname  

---

![imatge](/Tasca05/ServeiSSH/7.png)   
Entrem al arxiu “sudo nano /etc/ssh/sshd\_config” i afegirem AllowUsers usuari 

---

![imatge](/Tasca05/ServeiSSH/8.png)   
Ara farem un “sudo sshd \-t” per veure que el arxiu esta fet correctament just després farem un “sudo systemctl restart sshd”, “sudo systemctl start sshd” i “sudo systemctl status sshd” i veurem que en el status estara tot correcte  

---

![imatge](/Tasca05/ServeiSSH/9.png)   
Ara crearem un usuari que es diu usuari2 i farem que no es pugui connectar a ssh 

---

![imatge](/Tasca05/ServeiSSH/10.png)   
Aquí veiem que el usuari2 no es pot connectar  

---

![imatge](/Tasca05/ServeiSSH/11.png)   
Ara a la terminal farem un “ssh \-D 9876 usuari@192.168.56.107” per configurar el tunel

---

![imatge](/Tasca05/ServeiSSH/12.png) 

![imatge](/Tasca05/ServeiSSH/13.png) 

![imatge](/Tasca05/ServeiSSH/14.png) 
El primer que farem sera entrar al client Windows i entrarem en el panel de control. després entrarem a redes e internet. i per últim entrarem a opcions de internet i anirem a connexions. Abaix en sortirà configuracion de LAN i entrarem. Habilitarem el servidor proxy i entrarem a opciones avanzadas. I per últim en el apartat de socks en ficarem 127.0.0.1 i en el apartat de puerto 9876\.

---

![imatge](/Tasca05/ServeiSSH/15.png)   
Ara instal·larem el Wireshark

---

![imatge](/Tasca05/ServeiSSH/16.png)   
Aquí ja estaria dins del Wireshark   

---

![imatge](/Tasca05/ServeiSSH/17.png)  
Li donarem dos clicks a Ethernet i ens portara en aquest apartat. 

---

![imatge](/Tasca05/ServeiSSH/18.png)   
Ara fem un Ping 192.168.56.107 en la terminal del client 

---

![imatge](/Tasca05/ServeiSSH/19.png)   
Després de posar ssh al buscador veure que tot ens surt correctament

---

![imatge](/Tasca05/ServeiSSH/20.png)   
Tornem a entrar a la terminal del client per ficar la següent comanda “ssh-keygen \-t rsa” 

---

![imatge](/Tasca05/ServeiSSH/21.png)   
Just despres ficarem un altre comanda “scp .\\.ssh\\id\_rsa.pub usuari@192.168.56.107:

---

![imatge](/Tasca05/ServeiSSH/22.png)   
I per finalitzar en el servidor Linux ficarem el que veiem a pantalla 

---

![imatge](/Tasca05/ServeiSSH/23.png)   
I per últim entrem a la terminal de Windows i ens connectarem i per saber si esta tot correcte no ens demanara contrasenya 
