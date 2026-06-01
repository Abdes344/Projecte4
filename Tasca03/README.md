# 🆘 T03: Pla de Recuperació davant Desastres (DRP) – Imatges del sistema

## 📖 Breu descripció

En aquesta activitat s’ha treballat el disseny i la implementació d’un **Pla de Recuperació davant Desastres (DRP)** per a una organització fictícia.

L’objectiu principal és garantir que, en cas de fallada greu, robatori o corrupció del sistema, es pugui recuperar ràpidament l’estat complet dels equips utilitzant **imatges del sistema**.

Per a la prova de concepte s’ha utilitzat **Zorin OS 18** i l’eina **Rescuezilla**.

---

# 🎯 Objectius

* Entendre el concepte de DRP (Disaster Recovery Plan).
* Analitzar eines de clonació i imatge de disc.
* Comparar solucions comercials i open source.
* Crear una imatge completa del sistema.
* Restaurar un sistema des d’una imatge.
* Documentar el procediment de forma tècnica.

---

# 🔍 FASE 1: Anàlisi i justificació de la solució

## 🧠 Necessitat del client

L’empresa necessita:

* Recuperació ràpida d’equips
* Eliminació de temps d’instal·lació manual
* Conservació de configuracions i aplicacions
* Reducció del temps d’inactivitat (downtime)

---

## ⚖️ Comparativa d’eines de clonació

### 🏢 Eines comercials

| Eina                  | Característiques                       | Preu                  |
| --------------------- | -------------------------------------- | --------------------- |
| Acronis Cyber Protect | Backup + imatge + protecció ransomware | Subscripció (alta)    |
| Macrium Reflect       | Clonació avançada, entorn empresarial  | Llicència de pagament |

---

### 🧰 Eines de comunitat (open source)

| Eina        | Característiques                               | Preu    |
| ----------- | ---------------------------------------------- | ------- |
| Clonezilla  | Clonació completa de discs, molt eficient      | Gratuït |
| Rescuezilla | Interfície gràfica de Clonezilla, fàcil d’usar | Gratuït |

---

## 🏆 Solució proposada

### ✔️ Rescuezilla

### 💡 Justificació

* Interfície gràfica senzilla (ideal per tècnics no experts).
* Basat en Clonezilla (fiabilitat provada).
* Compatible amb Linux.
* Permet crear i restaurar imatges completes.
* Gratuït i de codi obert.

👉 Es considera la millor opció per a entorns educatius i petites/mitjanes empreses.

---

# 🖥️ FASE 2: Guia tècnica amb Rescuezilla

## 🧱 Escenari

* Sistema original: Zorin OS 18
* Màquina virtual amb configuració completa
* Sistema net per a restauració (sense SO instal·lat)
* Eina utilitzada: Rescuezilla Live USB

---

# 💾 1. Creació de la imatge del sistema

## ⚙️ Procés

1. Arrencar la màquina amb **Rescuezilla Live**.
2. Seleccionar opció:

   * 🟢 “Backup”
3. Triar disc origen (Zorin OS).
4. Seleccionar destinació (disc extern o carpeta).
5. Iniciar procés de clonació.

### 📸 Creació d’imatge

![Creació imatge Rescuezilla](./img/rescuezilla-backup.png)

---

## ⏳ Resultat

* Imatge completa del sistema creada amb èxit.
* Inclou:

  * Sistema operatiu
  * Aplicacions
  * Configuracions d’usuari

---

# ♻️ 2. Restauració del sistema

## ⚙️ Procés

1. Arrencar la màquina buida amb Rescuezilla.
2. Seleccionar:

   * 🟡 “Restore”
3. Triar la imatge creada.
4. Seleccionar disc destí.
5. Confirmar restauració.

### 📸 Restauració

![Restauració sistema Rescuezilla](./img/rescuezilla-restore.png)

---

## 🖥️ Resultat

* Sistema restaurat completament.
* Mateixa configuració que l’original.
* Aplicacions i usuaris intactes.

---

# ⚡ Avantatges del sistema DRP

* 🕒 Recuperació molt ràpida del sistema.
* 💾 Clonació completa del disc.
* 🔁 Restauració idèntica (bare-metal restore).
* 🧑‍💻 No cal reinstal·lació manual.
* 🧩 Reducció del temps d’inactivitat.

---

# ⚠️ Limitacions

* 📦 Les imatges ocupen molt espai.
* 🔄 Cal actualitzar imatges periòdicament.
* 💽 Dependència d’emmagatzematge extern.
* 🧪 Pot requerir compatibilitat exacta de hardware.

---

# 🔐 Bones pràctiques DRP

* Fer còpies periòdiques del sistema.
* Emmagatzemar imatges en lloc segur.
* Provar restauracions regularment.
* Documentar versions del sistema.
* Automatitzar backups quan sigui possible.

---

# 📚 Fonts consultades

* INCIBE – Pla de Recuperació davant Desastres
  https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres

* Documentació oficial Rescuezilla
  https://rescuezilla.com/

---

# 🧠 Conclusions

La implementació d’un sistema de recuperació basat en imatges permet garantir una **continuïtat del negoci ràpida i eficient**.

Rescuezilla es presenta com una solució òptima per la seva simplicitat, potència i naturalesa open source, permetent restaurar sistemes complets en pocs minuts.

---

# 🚀 Resultat final

✔️ Comparativa d’eines realitzada
✔️ Solució seleccionada i justificada
✔️ Imatge del sistema creada
✔️ Sistema restaurat correctament
✔️ Guia tècnica documentada

