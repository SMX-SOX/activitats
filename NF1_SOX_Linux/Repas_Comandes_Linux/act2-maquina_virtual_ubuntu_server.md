## Breu descripció

Aquest curs treballarem sovint amb servidors i, en aquest sector, **Linux és força predominant**, sobretot si parlem de serveis de xarxa.

Per això, en aquest primer projecte crearem una **màquina virtual Linux**, que ens haurà de servir com a base per a la resta del curs.

Tot i que, per practicar, crearem de tant en tant servidors des de zero, és una bona idea disposar d'una **OVA** que ens permeti desplegar ràpidament una màquina virtual sense perdre temps en les configuracions inicials.

De fet, la virtualització va permetre canviar la manera com es treballa en el món de l'administració de servidors.

### Què caldrà fer?

Caldrà que creeu una **màquina virtual amb Ubuntu Server**. Utilitzarem la versió **LTS més recent**.

Aquesta màquina haurà de **seguir estrictament** els requeriments que trobareu a continuació. En cas contrari, l'avaluació serà negativa.

Aquest és el primer pas per convertir-vos en **superherois dels sistemes**. 🦸‍♂️🦸‍♀️

> **[Imatge / element visual]**

Un cop tingueu la màquina creada i correctament avaluada, creareu una **OVA** per tal de poder desplegar aquesta màquina virtual ràpidament quan la necessiteu.

---

## Requisits de la màquina virtual

La màquina virtual haurà de complir **obligatòriament** els requisits següents:

* **Memòria RAM:** 4 GB.

* **Disc dur:** 20 GB.

* **Dos adaptadors de xarxa:**

  * Xarxa **NAT**.
  * Xarxa en mode **pont**, amb una adreça IP de la forma:

    `192.168.c.x/24`

    On:

    * `c = 2` per als alumnes de **2n A**.
    * `c = 4` per als alumnes de **2n B**.
    * `x` correspon al **número de llista de l'alumne**.

* **Usuari inicial:** `usuari`

* **Contrasenya:** `usuari`

> ⚠️ **No podeu utilitzar un altre nom d'usuari ni una altra contrasenya.**

* Instal·lar i configurar el servei **SSH**.

---

## Documentació

A més de crear la màquina virtual, haureu d'elaborar una **guia d'instal·lació** en què documentareu correctament les diferents accions, configuracions i decisions preses durant el procés.

Penseu que **documentar correctament una instal·lació és fonamental** per evitar errors i facilitar posteriors desplegaments o configuracions.

> ### 📚 El lema d'aquest curs és:
>
> ***«Documentar, documentar i documentar.»***

---

## Material de suport

Com a material de suport, disposeu de la guia corresponent a la **UD2 del mòdul AA1 – Instal·lació**.

## Objectius específics de la tasca / Finalitat de la tasca

* Instal·lar un sistema operatiu sense entorn gràfic.
* Interpretar correctament les instruccions d'instal·lació.
* Configurar interfícies de xarxa mitjançant **Netplan**.
* Exportar màquines virtuals a arxius en format **OVA**.

---

## Competències treballades

1. Determinar la logística associada a les operacions d'instal·lació, configuració i manteniment de sistemes microinformàtics, interpretant-ne la documentació tècnica associada i organitzant els recursos necessaris.

---

## Resultats d'aprenentatge i criteris d'avaluació

### RA(s) de la tasca

**0224 RA1.** Instal·la sistemes operatius en xarxa descrivint-ne les característiques i interpretant-ne la documentació tècnica.

### CA(s) de la tasca

1. Realitza l'estudi de compatibilitat del sistema informàtic.
2. Diferencia els modes d'instal·lació.
3. Planifica i realitza el particionat del disc del servidor.
4. Selecciona i aplica els sistemes d'arxius.
5. Selecciona els components a instal·lar.
6. Actualitza el sistema operatiu en xarxa.

---

## Continguts de la tasca

### 1. Instal·lació de sistemes operatius en xarxa

* **1.1** Comprovació dels requisits tècnics. Preparació de la instal·lació.
* **1.2** Particions i sistema d'arxius. Components i mètodes.
* **1.4** Elaboració de la documentació sobre la instal·lació i les incidències.
* **1.5** Instal·lació de sistemes operatius en xarxa en màquines virtuals.

---

## Capacitats clau treballades

* Autonomia
* Innovació
* Relació interpersonal
* Organització del treball
* Responsabilitat
* Treball en equip
* Resolució de problemes

## Mòduls i resultats d'aprenentatge treballats

| Mòdul professional                                | Resultat d'aprenentatge |       Hores |
| ------------------------------------------------- | ----------------------- | ----------: |
| **0224 – Sistemes Operatius en Xarxa**            | **RA1**                 |       **4** |
| 0226 – Seguretat Informàtica                      | —                       |           — |
| 0227 – Serveis de Xarxa                           | —                       |           — |
| 0228 – Aplicacions Web                            | —                       |           — |
| 1708 – Sostenibilitat                             | —                       |           — |
| 1710 – Itinerari Personal per a l'Ocupabilitat II | —                       |           — |
| 1713 – Projecte Intermodular                      | —                       |           — |
| Tutoria                                           | —                       |           — |
| **Total d'hores**                                 |                         | **4 hores** |

---

## Quan es necessita, termini i forma de lliurament

### Producte final

El producte final serà:

> **Una màquina virtual Ubuntu Server correctament instal·lada i configurada segons els requisits indicats a la tasca.**

### Termini de lliurament

* **Termini:** *pendent d'indicar.*

### Forma de lliurament

Caldrà lliurar a la tasca corresponent del **Moodle**:

* La **guia d'instal·lació**, correctament documentada.
* La **màquina virtual**, correctament configurada, segons les indicacions del professorat.

