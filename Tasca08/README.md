# 🧾 T08: Auditoria de Qualitat i Estandardització de Servidors (SOP)

## 📖 Breu descripció

En aquesta activitat s’ha realitzat una **auditoria interna de qualitat** i una pràctica d’**estandardització de servidors** dins del marc del protocol SOP (Standard Operating Procedure).

L’objectiu és assegurar que qualsevol servidor Ubuntu Server es desplega amb una configuració base correcta, segura i homogènia abans d’afegir serveis avançats.

---

# 🎯 Objectius

* Entendre la importància d’una base sòlida en servidors.
* Aplicar un procediment estàndard de configuració (SOP).
* Desplegar una màquina virtual Ubuntu Server des de zero.
* Verificar configuracions bàsiques de sistema.
* Garantir seguretat, estabilitat i coherència.
* Preparar-se per una certificació pràctica SOP Specialist.

---

# 🧱 Importància de l’estandardització

Un servidor mal configurat pot provocar:

* 🔐 Vulnerabilitats de seguretat
* ⚠️ Errors en serveis crítics
* 📉 Baix rendiment del sistema
* 🔄 Problemes d’escalabilitat
* 💥 Incidències en producció

👉 Per això, l’estandardització és obligatòria en entorns professionals.

---

# 🖥️ FASE 1: Entrenament SOP

## ⚙️ Objectiu de la fase

Practicar la configuració bàsica d’un servidor Ubuntu Server seguint el protocol intern de l’empresa.

---

## 🧾 Tasques realitzades

### 🌐 Configuració de xarxa

* Assignació d’IP estàtica
* Configuració de gateway
* Configuració de DNS

```bash id="net1"
ip a
```

---

### 🔄 Actualització del sistema

```bash id="update"
sudo apt update && sudo apt upgrade -y
```

---

### 👤 Creació d’usuaris

* Creació d’usuaris administratius
* Assignació de permisos
* Configuració de grups

---

### 🔐 Configuració de seguretat

* Revisió de ports oberts
* Configuració de firewall (ufw)
* Actualitzacions de seguretat activades

```bash id="ufw"
sudo ufw enable
sudo ufw status
```

---

### 📦 Instal·lació de paquets base

* net-tools
* curl
* vim
* openssh-server

---

## 🧠 Resultat de l’entrenament

✔️ Sistema configurat segons SOP
✔️ Xarxa funcional i estable
✔️ Sistema actualitzat
✔️ Usuaris configurats correctament
✔️ Seguretat bàsica aplicada

---

# 🏁 FASE 2: Certificació SOP Specialist

## 🧪 Descripció de la prova

Es realitza una prova pràctica individual amb:

* Instal·lació des de zero d’un Ubuntu Server
* Aplicació del protocol SOP complet
* Verificació de configuracions bàsiques

---

## 📌 Restriccions de l’examen

* Només es permet un full manuscrit amb apunts.
* Execució completament pràctica.
* Validació per part del professorat.

---

## 🎯 Competències a demostrar

* Autonomia en la configuració de servidors
* Coneixement de sistemes Linux
* Capacitat d’estandardització
* Bones pràctiques de seguretat
* Resolució d’incidències bàsiques

---

# 🔐 Bones pràctiques SOP

* Utilitzar sempre configuracions consistents
* Mantenir sistemes actualitzats
* Documentar tots els canvis
* Aplicar seguretat per defecte (secure by default)
* Evitar configuracions improvisades en producció

---

# 🧠 Conclusions

El protocol SOP garanteix que tots els servidors desplegats dins l’entorn EverPia segueixen un estàndard comú, segur i escalable.

Aquesta base és essencial abans de desplegar qualsevol servei avançat (LDAP, NFS, CUPS, etc.), assegurant estabilitat i reduint errors crítics.

---

# 🚀 Resultat final

✔️ Configuració base de servidor aplicada
✔️ Protocol SOP entès i practicat
✔️ Sistema preparat per serveis avançats
✔️ Preparació per certificació SOP Specialist

