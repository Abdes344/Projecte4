# Introducció 🚀

La primera hora el vostre responsable de seguretat us presenta el tema de les còpies de seguretat a partir d’un material didàctic. A continuació, caldrà que treballeu els aspectes del tema i ho fareu mitjançant una dinàmica cooperativa.

---

## Presentació del cas client 🏢

**"Muntatges i Serveis Tècnics SL"** és una petita empresa dedicada a la instal·lació i manteniment d'equips industrials.

### Infraestructura Tècnica:
- **Servidor de Fitxers (Ubuntu Server):** Conté tota la documentació crítica:
  - **Documents de Projectes:** Plànols, especificacions tècniques (300 GB, creixement moderat).
  - **Bases de Dades (Comptabilitat i Clients):** Crítiques i d'ús diari (20 GB, canvi constant).
  - **Carpetes Personals dels Usuaris:** Per a la feina diària (100 GB).
- **10 Equips Clients (Windows 10/11):** Els usuaris treballen majoritàriament amb fitxers del servidor, però alguns tècnics guarden de forma temporal informes i altres arxius importants a la carpeta Documents.
- **Connexió a Internet:** Fibra òptica de 600 Mbps (simètrica).

### Requisits de Recuperació:
- **Temps de Recuperació (RTO):** Les dades de Comptabilitat/Clients han d'estar disponibles en menys de 4 hores.
- **Pèrdua de Dades Admesa (RPO):** Es pot admetre una pèrdua màxima de 24 hores per a la majoria de dades, però les dades de Comptabilitat/Clients no poden perdre més de 4 hores de treball.
- **Retenció:** Cal guardar les dades amb un historial d'almenys un mes.

---

## Fase 1: Treball individual 🧑‍💻

De forma individual, heu de donar resposta a les següents preguntes basant-se en el cas pràctic:

1. **Què copiar? (Priorització):**
   - Quines són les dades més crítiques del servidor? 
   - Cal fer còpia dels 10 equips clients? Justifica-ho.
   
2. **Periodicitat i Tipus de Còpia:**
   - Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual).
   - Quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques?
   
3. **Mitjans i Ubicació:**
   - Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)?
   - On s'hauria de guardar físicament la còpia més recent? (Regla 3-2-1).

---

## Fase 2: Treball per parelles 👥

1. **Discussió i Consens:**
   - Comparen les seves respostes individuals (Fase 1).
   
2. **Elaboració d'una Proposta Unificada:**
   - Consensuar i dissenyar el vostre propi Esquema 3-2-1 de Còpies (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas.

### Exemple d'Esquema de la Parella:

| Element               | Proposta de la Parella | Justificació  |
|-----------------------|------------------------|---------------|
| **Dades Crítiques**    |                      |               |
| **Periodicitat (BD)**  |                      |               |
| **Tipus de Còpia (BD)**|                      |               |
| **Mitjà 1 (Local)**    |                      |               |
| **Mitjà 2 (Extern)**   |                      |               |

---

## Fase 3: Treball en grup 🤝

1. **Debat i Selecció:**
   - Cada parella presenta el seu esquema.
   - El grup debat els pros i contres de cada proposta (cost, temps de recuperació, seguretat, simplicitat).

2. **Disseny de la Política Final:**
   - El grup ha de redactar la Política de Còpies de Seguretat Definitiva que presentaran a l'empresa "Muntatges i Serveis Tècnics SL".

---

## Document Final (Fase 3) 📑

El grup ha de generar un document amb els següents punts resolts:

1. **Dades Objecte de Còpia:**
   - Quines dades es copien i amb quina freqüència (separant Servidor/Clients i crítiques/no crítiques).
   
2. **Cronograma Setmanal Detallat:**
   | Dia        | Dades (Ex: BD)   | Tipus de còpia  | Mitjà         |
   |------------|------------------|-----------------|---------------|
   | Dilluns    |                  |                 |               |
   | Dimarts    |                  |                 |               |
   | ...        |                  |                 |               |
   | Diumenge   |                  |                 |               |

3. **Elecció de Mitjans i Ubicació (Regla 3-2-1):**
   - **Mitjà 1 (Local):** Quin mitjà concret (p. ex., Disc dur USB, NAS) s'utilitza.
   - **Mitjà 2 (Extern):** Quin mitjà (p. ex., Cloud, LTO) i el proveïdor proposat (p. ex., Azure, Google Cloud, servei local).
   - **Ubicació Fora de Lloc:** On es guarda la còpia externa (física o lògica) i qui és el responsable de la seva gestió.

4. **Estratègia de Recuperació (RTO/RPO):**
   - Com es garanteix que les dades de Comptabilitat/Clients compleixen amb el requisit de RPO (4 hores) i RTO (4 hores).

---

## Materials i Links de Suport 🔗

- [Moodle 0226 Seguretat Informàtica. RA2.AA3Còpies](https://moodle.example.com)
- [INCIBE. Copias de seguridad. Una guía de aproximación para el empresario](https://www.incibe.es)
- [Xataka. Backup 3 - 2 - 1, el método definitivo para mantener a salvo tus datos (YouTube)](https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8)
