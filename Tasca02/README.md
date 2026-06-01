# 💾 T02: DPR – Còpies de Seguretat (Cas pràctic)

## 📖 Breu descripció

En aquesta activitat s'ha posat en pràctica una **política de còpies de seguretat (DPR)** per al client *“Muntatges i Serveis Tècnics SL”*.

L’objectiu és dissenyar, implementar i validar un sistema real de backups tant en **Windows (client)** com en **Linux (servidor)** utilitzant eines professionals com **Duplicati** i **Duplicity**.

---

# 🎯 Objectius

* Implementar una política de còpies 3-2-1.
* Configurar backups locals i al núvol.
* Aprendre a restaurar informació en cas de pèrdua.
* Automatitzar còpies amb cron.
* Treballar amb eines reals de backup professional.
* Validar la recuperació de dades.

---

# 🪟 PART 1: Còpies de seguretat en Windows (Duplicati)

## 🧱 Escenari

* Màquina virtual amb Windows 11.
* 2 discs:

  * Disc principal (SO)
  * Disc secundari (10 GB per backups)
* Núvol: Google Drive (compte extern)

---

## ⚙️ Instal·lació de Duplicati

### Passos realitzats

1. Descàrrega de Duplicati.
2. Instal·lació al sistema Windows.
3. Inici del servei web local.
4. Accés al panell de configuració.

### 📸 Instal·lació

![Instal·lació Duplicati](./img/duplicati-install.png)

---

## ☁️ Configuració del backup

### Política aplicada (3-2-1)

* 1 còpia local (disc secundari)
* 1 còpia al cloud (Google Drive)
* 1 còpia original (equip usuari)

---

## ⏱️ Programació de còpies

| Tipus de còpia | Destí          | Freqüència |
| -------------- | -------------- | ---------- |
| Incremental    | Disc secundari | Cada hora  |
| Completa       | Google Drive   | 18:00      |

---

### 📸 Configuració backup

![Configuració backup Duplicati](./img/duplicati-config.png)

---

## 📂 Prova de funcionament

* S’han afegit fitxers a Documents.
* S’ha executat backup automàtic.
* S’han verificat còpies generades.

### 📸 Fitxers d’exemple

![Fitxers Documents](./img/documents.png)

---

## ♻️ Restauració de dades

### Procés realitzat

1. Eliminació del contingut de Documents.
2. Restauració des del disc local.
3. Restauració des del cloud (Google Drive).

### 📸 Restauració

![Restauració Duplicati](./img/restore.png)

---

## ✅ Resultat Windows

✔️ Backups locals funcionant
✔️ Backups cloud operatius
✔️ Restauració validada
✔️ Política 3-2-1 implementada

---

# 🐧 PART 2: Còpies de seguretat en Linux (Duplicity)

## 🧱 Escenari

* Ubuntu Server
* Disc secundari de 10 GB
* Punt de muntatge: `/media/backup`

---

## 💽 Preparació del disc

### Formateig i muntatge

```bash id="mkfs"
mkfs.xfs /dev/sdb1
mkdir -p /media/backup
mount /dev/sdb1 /media/backup
```

### 📸 Muntatge disc

![Disc muntat Linux](./img/mount.png)

---

## 📦 Instal·lació de Duplicity

```bash id="install"
sudo apt update
sudo apt install duplicity -y
```

---

## 👥 Creació d’usuaris i dades

* S’han creat usuaris addicionals.
* S’han generat fitxers de prova (10 MB).
* Carpeta objectiu: `/home`

---

## 💾 Còpia de seguretat completa

```bash id="full"
duplicity full /home file:///media/backup
```

---

## ♻️ Restauració

* Eliminació de fitxers de `/home`
* Restauració amb duplicity
* Verificació de dades recuperades

---

## 📈 Còpia incremental

* S’ha afegit un fitxer de 4 MB.
* Nova còpia executada.
* S’ha confirmat mode incremental.

---

## 🧹 Desmuntatge

```bash id="umount"
umount /media/backup
```

---

# 🤖 Automatització amb cron

## 📝 Script FULL backup

```bash id="fullscript"
#!/bin/bash
export PASSPHRASE="contrasenya"

mount /dev/sdb1 /media/backup

duplicity full /home file:///media/backup

umount /media/backup
```

---

## 🕒 Cron FULL (diumenges 23:00)

```bash id="cron1"
0 23 * * 0 /ruta/fullbackup.sh
```

---

## 📝 Script incremental

```bash id="incscript"
#!/bin/bash
export PASSPHRASE="contrasenya"

mount /dev/sdb1 /media/backup

duplicity incremental /home file:///media/backup

umount /media/backup
```

---

## 🕒 Cron incremental (dilluns a dissabte)

```bash id="cron2"
0 23 * * 1-6 /ruta/incrementalbackup.sh
```

---

# 🔐 Bones pràctiques aplicades

* 🔒 Unitats de backup desmuntades per defecte.
* 🧪 Proves de restauració reals.
* ⏱️ Automatització amb cron.
* ☁️ Backup extern per redundància.
* 📊 Separació de còpies completes i incrementals.

---

# 📚 Materials utilitzats

* Duplicati: https://duplicati.com/
* Documentació Duplicity (man pages)
* Cron scheduling guides
* Apunts de sistemes operatius i backups

---

# 🧠 Conclusions

Aquesta pràctica ha permès implementar un sistema complet de còpies de seguretat en entorns Windows i Linux, seguint una arquitectura professional basada en la regla **3-2-1**.

També s’ha practicat la restauració de dades i l’automatització de processos crítics, essencials en entorns reals de producció.

---

# 🚀 Resultat final

✔️ Backup Windows amb Duplicati
✔️ Backup Linux amb Duplicity
✔️ Restauració validada
✔️ Incrementals funcionals
✔️ Automatització amb cron
✔️ Política 3-2-1 aplicada

