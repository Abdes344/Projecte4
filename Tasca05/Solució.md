# **T05: Accés Remot. Connexió via SSH**

![ServeiSSH][image1]

Primer el que farem serà deixar el primer adaptador en NAT i el segon el ficarem en adaptador només amfitrió 

![][image2]  
Amb la comanda “sudo apt install ssh” instal·larem el servei ssh  


![][image3]  
Ara configurarem el arxiu del netplan afegint l’enp0s8 per entrar el que farem sera ficar la següent comanda “sudo nano /etc/netplan/50-cloud-init.yaml”

![][image4]  
Després de configurar l’arxiu farem un “sudo netplan apply” per aplicar els canvis que acabem de fer

![][image5]  
Després farem un ip per veure que en el enp0s8 tenim la ip   

![][image6]  
Entrem a la terminal i connectem el ssh i fem un hostname  

![][image7]  
Entrem al arxiu “sudo nano /etc/ssh/sshd\_config” i afegirem AllowUsers usuari 

![][image8]  
Ara farem un “sudo sshd \-t” per veure que el arxiu esta fet correctament just després farem un “sudo systemctl restart sshd”, “sudo systemctl start sshd” i “sudo systemctl status sshd” i veurem que en el status estara tot correcte  

![][image9]  
Ara crearem un usuari que es diu usuari2 i farem que no es pugui connectar a ssh 

![][image10]  
Aquí veiem que el usuari2 no es pot connectar  

![][image11]  
Ara a la terminal farem un “ssh \-D 9876 usuari@192.168.56.107” per configurar el tunel

![][image12]

![][image13]

![][image14]
El primer que farem sera entrar al client Windows i entrarem en el panel de control. després entrarem a redes e internet. i per últim entrarem a opcions de internet i anirem a connexions. Abaix en sortirà configuracion de LAN i entrarem. Habilitarem el servidor proxy i entrarem a opciones avanzadas. I per últim en el apartat de socks en ficarem 127.0.0.1 i en el apartat de puerto 9876\.

![][image15]  
Ara instal·larem el Wireshark

![][image16]  
Aquí ja estaria dins del Wireshark    
![][image17]  
Li donarem dos clicks a Ethernet i ens portara en aquest apartat.  
![][image18]  
Ara fem un Ping 192.168.56.107 en la terminal del client   
![][image19]  
Després de posar ssh al buscador veure que tot ens surt correctament 

![][image20]  
Tornem a entrar a la terminal del client per ficar la següent comanda “ssh-keygen \-t rsa”   
![][image21]  
Just despres ficarem un altre comanda “scp .\\.ssh\\id\_rsa.pub usuari@192.168.56.107:

![][image22]  
I per finalitzar en el servidor Linux ficarem el que veiem a pantalla 

![][image23]  
I per últim entrem a la terminal de Windows i ens connectarem i per saber si esta tot correcte no ens demanara contrasenya 
