# 🖨️ T10: Servidor d’Impressió Linux – CUPS (Prova de Concepte)

## 📖 Breu descripció

En aquesta activitat s’ha implementat un **servidor d’impressió centralitzat utilitzant CUPS (Common UNIX Printing System)** per a l’empresa fictícia **DevOptimize Solutions**.

L’objectiu és demostrar que un servidor Linux pot gestionar impressores de xarxa i permetre que clients Linux enviïn treballs d’impressió de manera remota i transparent.

Per a la prova de concepte s’ha utilitzat la impressora virtual **cups-pdf**, que genera fitxers PDF en lloc d’impressió física.

---

# 🎯 Objectius

* Instal·lar i configurar CUPS en un servidor Linux.
* Configurar una impressora virtual (cups-pdf).
* Activar l’administració web de CUPS.
* Compartir la impressora per xarxa.
* Connectar un client Linux (Zorin OS).
* Validar el funcionament amb impressions reals (PDF).
* Documentar tot el procés amb proves.

---

# 🧱 Escenari de treball

## 🖥️ Infraestructura

* **Servidor:** Ubuntu Server
* **Client:** Zorin OS Desktop
* **Xarxa:** NAT + Host-Only
* **Impressora:** cups-pdf (virtual)

---

# 🖨️ FASE 1: Instal·lació del servidor CUPS

## 📦 Instal·lació del servei

```bash id="cups1"
sudo apt update
sudo apt install cups -y
```

---

## 🔄 Activació del servei

```bash id="cups2"
sudo systemctl enable cups
sudo systemctl start cups
sudo systemctl status cups
```

---

# 🌐 Configuració d’accés remot

## ⚙️ Permetre connexions externes

Edició del fitxer:

```bash id="cupsconf"
sudo nano /etc/cups/cupsd.conf
```

### Modificacions clau:

* `Listen 0.0.0.0:631`
* Permetre accés a xarxa local
* Obrir administració remota

---

## 🔁 Reinici del servei

```bash id="restartcups"
sudo systemctl restart cups
```

---

## 🌍 Accés web CUPS

URL d’administració:

```
http://IP_DEL_SERVIDOR:631
```

📸 Panell web CUPS:

![CUPS Web Interface](./img/cups-web.png)

---

# 🖨️ FASE 2: Instal·lació impressora virtual

## 📦 Instal·lació cups-pdf

```bash id="cups-pdf"
sudo apt install cups-pdf -y
```

---

## 🧾 Verificació impressora

```bash id="lp"
lpstat -p -d
```

---

# 🔧 FASE 3: Configuració de la impressora

## 🌐 Des del panell web

1. Accedir a CUPS (631)
2. Anar a **Administration**
3. Afegir impressora “PDF Printer”
4. Compartir impressora en xarxa

---

## 📸 Impressora configurada

![Impressora CUPS PDF](./img/cups-printer.png)

---

# 💻 FASE 4: Configuració del client (Zorin OS)

## 🔎 Descobriment de la impressora

* Accedir a configuració d’impressores
* Detectar impressora de xarxa CUPS
* Afegir dispositiu remot

---

## 🖨️ Impressió de prova

* Document de text
* PDF
* Fitxer d’imatge

📸 Impressió des del client:

![Client imprimint](./img/cups-client.png)

---

# 📂 FASE 5: Validació al servidor

## 📁 Fitxers generats

Els documents impresos es generen automàticament a:

```
/var/spool/cups-pdf/
```

---

## 🧾 Resultat

✔️ PDF generats correctament
✔️ Recepció de treballs des del client
✔️ Comunicació servidor-client funcional

---

# ⚠️ Problemes i solucions

* 🔥 Firewall bloquejant port 631 → obert manualment
* 🌐 Accés remot desactivat → modificació de cupsd.conf
* 🖨️ Impressora no visible → reinici de servei CUPS

---

# 🔐 Bones pràctiques

* Limitar accés al port 631
* No exposar CUPS a internet públic
* Utilitzar autenticació per administració
* Monitoritzar cues d’impressió
* Fer backups de configuració

---

# 📚 Fonts consultades

* Canonical – Ubuntu CUPS documentation
  https://documentation.ubuntu.com/server/how-to/networking/install-nfs/

* Idroot – Install CUPS on Ubuntu 24.04
  https://idroot.us/install-cups-print-server-ubuntu-24-04/

* YouTube – CUPS server tutorial
  https://www.youtube.com/watch?v=FNwSTrOSgZQ

---

# 🧠 Conclusions

La implementació de CUPS permet centralitzar i gestionar la impressió en entorns Linux de manera eficient, reduint costos i simplificant la gestió de dispositius.

La prova de concepte amb cups-pdf demostra que és possible crear un sistema complet de impressió en xarxa sense necessitat de hardware físic.

---

# 🚀 Resultat final

✔️ Servidor CUPS operatiu
✔️ Impressora virtual configurada
✔️ Client connectat correctament
✔️ Impressió remota funcional
✔️ Validació completa de la PoC

