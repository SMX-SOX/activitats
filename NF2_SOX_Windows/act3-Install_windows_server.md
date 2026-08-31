# T0X: Instal·lació de Windows Server 2025

## Tasca individual

# Breu descripció

## Introducció al cas

Després del nostre assessorament a **TransLògic S.A.**, l'empresa ens encarrega el desplegament dels seus servidors basats en **Windows Server 2025**.

En aquest projecte treballarem amb **Windows Server 2025 Essentials**, una solució orientada a petites i mitjanes empreses.

Per aquest motiu, haurem de desplegar diverses màquines virtuals. Amb l'objectiu de treballar de manera eficient i seguint les bones pràctiques, realitzarem primer una **instal·lació de prova**.

Aquesta instal·lació servirà per:

* Aprendre el procediment d'instal·lació de Windows Server 2025.
* Comprovar la configuració de la màquina virtual.
* Elaborar una guia d'instal·lació.
* Disposar d'una documentació de referència per a la posterior implantació dels sistemes del client.

---

# Procediment

## 1. Creació de la màquina virtual

Creeu una màquina virtual amb les característiques següents:

* **8 GB de memòria RAM**.
* **2 processadors**.
* **Dos discos durs:**

  * Un disc principal de **32 GB**, on s'instal·larà el sistema operatiu.
  * Un disc secundari de **10 GB**.
* **Dues interfícies de xarxa:**

  * Una interfície en mode **NAT**.
  * Una interfície en mode **Host-Only**.

---

## 2. Instal·lació del sistema operatiu

Instal·leu **Windows Server 2025** amb les característiques següents:

* Instal·lació en mode **GUI**.
* Idioma del sistema: **English (US)**.
* Configuració regional: **Espanyol**.
* Teclat: **Espanyol**.

---

## 3. Configuració inicial

Realitzeu les accions següents:

1. Canvieu el nom de l'equip a:

```text
DCxx
```

> **Nota:** `xx` correspon al vostre número de llista.

2. Actualitzeu la màquina virtual.

3. Un cop finalitzades les actualitzacions, pauseu-les durant el màxim temps possible.

---

# Contingut de la guia

La guia d'instal·lació haurà d'incloure els apartats següents.

## Comparació amb els requisits de Microsoft

Compareu la configuració de la màquina virtual definida anteriorment amb els requisits indicats per Microsoft.

Cal respondre a la pregunta següent:

> **La configuració proposada és coherent amb els requisits oficials de Windows Server 2025?**

Justifiqueu la resposta.

---

## Documentació de la instal·lació

Documenteu els diferents procediments realitzats durant la instal·lació.

La documentació ha d'incloure:

* Les diferents fases de la instal·lació.
* La configuració de la màquina virtual.
* Les captures de pantalla necessàries.
* Observacions sobre les decisions preses.
* La configuració final del servidor.

> **Recordeu:** la documentació s'ha de realitzar en format **Markdown**.

---

# Materials i enllaços de suport

* **UD6. AA2 — Instal·lació de Windows Server 2025**
  Disponible al Moodle del mòdul **0224 — Sistemes Operatius en Xarxa**.

* [Requisits de maquinari per a Windows Server — Microsoft Learn](https://learn.microsoft.com/es-es/windows-server/get-started/hardware-requirements?tabs=cpu%26pivots%3Dwindows-server-2025&utm_source=chatgpt.com)

---

# Objectius específics de la tasca / Finalitat

La finalitat de la tasca és realitzar la **instal·lació d'un servidor Windows Server 2025** i documentar correctament tot el procediment.

---

# Competències treballades

* **a)** Determinar la logística associada a les operacions d'instal·lació, configuració i manteniment de sistemes microinformàtics, interpretant-ne la documentació tècnica associada i organitzant els recursos necessaris.

* **c)** Instal·lar i configurar programari bàsic i d'aplicació, assegurant-ne el funcionament en condicions de qualitat i seguretat.

---

# Resultats d'aprenentatge i criteris d'avaluació

## RA(s) de la tasca

### 0224 — Sistemes Operatius en Xarxa

**RA1.** Instal·la sistemes operatius en xarxa descrivint-ne les característiques i interpretant-ne la documentació tècnica.

---

## CA(s) de la tasca

* **1.1** Realitza l'estudi de compatibilitat del sistema informàtic.
* **1.2** Diferencia els modes d'instal·lació.
* **1.3** Planifica i realitza el particionat del disc del servidor.
* **1.4** Selecciona i aplica els sistemes d'arxius.
* **1.5** Selecciona els components a instal·lar.
* **1.6** Aplica procediments per a l'automatització d'instal·lacions.
* **1.7** Aplica preferències en la configuració de l'entorn personal.
* **1.8** Actualitza el sistema operatiu en xarxa.
* **1.9** Comprova la connectivitat del servidor amb els equips client.

---

# Continguts

## 1. Instal·lació de sistemes operatius en xarxa

* **1.1** Comprovació dels requisits tècnics i preparació de la instal·lació.
* **1.2** Particions i sistemes d'arxius. Components i mètodes.
* **1.3** Automatització.
* **1.4** Elaboració de la documentació sobre la instal·lació i les incidències.
* **1.5** Instal·lació de sistemes operatius en xarxa en màquines virtuals.

---

# Capacitats clau treballades

* Autonomia
* Innovació
* Relació interpersonal
* Organització del treball
* Responsabilitat
* Treball en equip
* Resolució de problemes

---

# Mòdul i resultat d'aprenentatge treballat

| Mòdul professional                     | Resultat d'aprenentatge |       Hores |
| -------------------------------------- | ----------------------- | ----------: |
| **0224 — Sistemes Operatius en Xarxa** | **RA1**                 |       **2** |
| **Total**                              |                         | **2 hores** |

---

# Quan es necessita, termini i forma de lliurament

## Producte final a lliurar

> **Guia d'instal·lació de Windows Server 2025 en format Markdown.**

---

## Termini de lliurament

* Consultar la **temporització del mòdul**.

---

## Forma de lliurament

Caldrà lliurar:

* Una **carpeta al repositori** amb la documentació de la tasca.
* L'**enllaç al repositori** mitjançant la tasca corresponent del **Moodle**.

---

> ## 📌 Recordatori
>
> La documentació ha de ser clara, ordenada i incloure les captures de pantalla necessàries per demostrar totes les configuracions realitzades.
>
> El format obligatori de la guia és **Markdown (`.md`)**.
