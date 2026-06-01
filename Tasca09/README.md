# 📁 T09: Servidor de Fitxers Linux – NFS (Network File System)

## 📖 Breu descripció

En aquesta activitat s’ha implementat un **servidor de fitxers Linux utilitzant NFSv3**, amb l’objectiu de centralitzar l’emmagatzematge de dades en un entorn de desenvolupament simulat.

El cas pràctic representa l’empresa **DevOptimize Solutions**, que necessita un sistema per evitar la dispersió de fitxers entre desenvolupadors i millorar el control de versions i l’eficiència del treball.

---

# 🎯 Objectius

* Entendre el funcionament de NFS en entorns Linux.
* Configurar un servidor NFSv3.
* Configurar un client Linux per muntar recursos compartits.
* Gestionar permisos amb usuaris, grups i sistema de fitxers.
* Controlar accessos mitjançant `/etc/exports`.
* Simular un entorn real de compartició de fitxers.

---

# 🧱 Escenari del client

## 🏢 DevOptimize Solutions

* Startup de desenvolupament de programari.
* Entorn 100% Linux.
* Problema: dispersió de fitxers i versions duplicades.
* Necessitat: centralitzar recursos en un servidor únic.

---

# 🖥️ FASE 1: Configuració del servidor NFS

## 📦 Instal·lació del servei

```bash id="nfs1"
sudo apt update
sudo apt install nfs-kernel-server -y
```

---

## 📂 Creació del directori compartit

```bash id="dir1"
sudo mkdir -p /srv/nfs/projectes
sudo chown nobody:nogroup /srv/nfs/projectes
sudo chmod 777 /srv/nfs/projectes
```

---

## ⚙️ Configuració d’exportacions

Fitxer:

```bash id="exports"
sudo nano /etc/exports
```

### Contingut:

```text id="exportsfile"
/srv/nfs/projectes 192.168.1.0/24(rw,sync,no_subtree_check)
```

---

## 🔄 Aplicació de configuració

```bash id="exportfs"
sudo exportfs -a
sudo systemctl restart nfs-kernel-server
```

---

## 📸 Estat del servidor

![Servidor NFS configurat](./img/nfs-server.png)

---

# 👥 Gestió d’usuaris i permisos

## 👤 Creació d’usuaris simulats

```bash id="users"
sudo adduser dev1
sudo adduser dev2
```

## 🔐 Assignació de grups

```bash id="groups"
sudo groupadd developers
sudo usermod -aG developers dev1
sudo usermod -aG developers dev2
```

---

## 📂 Control d’accés

* Permisos gestionats amb `chmod`
* Propietat gestionada amb `chown`
* Accés controlat via `/etc/exports`

---

# 💻 FASE 2: Configuració del client NFS

## 📦 Instal·lació del client

```bash id="client"
sudo apt install nfs-common -y
```

---

## 📂 Creació del punt de muntatge

```bash id="mount"
sudo mkdir -p /mnt/nfs
```

---

## 🔗 Muntatge del recurs compartit

```bash id="mountcmd"
sudo mount 192.168.1.10:/srv/nfs/projectes /mnt/nfs
```

---

## 📸 Client connectat

![Client NFS muntat](./img/nfs-client.png)

---

# 🧪 Proves de funcionament

## 📄 Creació de fitxers

* S’han creat fitxers des del client.
* Verificació de sincronització amb el servidor.

## 🔁 Resultat

✔️ Fitxers visibles en ambdós sistemes
✔️ Permisos aplicats correctament
✔️ Compartició funcional

---

# ⚠️ Limitacions detectades

* NFSv3 no inclou autenticació forta.
* Seguretat basada en IP i permisos locals.
* No hi ha control centralitzat d’usuaris (sense LDAP).

---

# 🔐 Bones pràctiques

* Limitar rangs IP a `/etc/exports`
* Evitar permisos 777 en producció
* Utilitzar firewalls per restringir accés
* Migrar a NFSv4 en entorns crítics
* Integrar amb autenticació centralitzada (LDAP) si escau

---

# 📚 Materials consultats

* Projecte04-NFS (GitHub):
  https://github.com/SMX2n/Projecte04-NFS

* Ubuntu NFS documentation:
  https://documentation.ubuntu.com/server/how-to/networking/install-nfs/

* SomeBooks NFS tutorials:

  * https://somebooks.es/nfs-parte-1-instalacion-en-un-servidor-ubuntu-20-04-lts/
  * https://somebooks.es/nfs-parte-2-instalacion-en-un-cliente-ubuntu-20-04-lts/

---

# 🧠 Conclusions

La implementació de NFS permet centralitzar fitxers en entorns Linux de manera eficient i senzilla.

Tot i les seves limitacions en seguretat, és una solució molt utilitzada en entorns controlats o interns, especialment en equips de desenvolupament com el cas de DevOptimize Solutions.

---

# 🚀 Resultat final

✔️ Servidor NFS configurat
✔️ Client NFS connectat
✔️ Compartició de fitxers funcional
✔️ Gestió bàsica d’usuaris i permisos
✔️ Entorn de proves complet

