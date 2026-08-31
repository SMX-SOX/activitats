# P0X: Llicenciament Windows Server 2025

## Breu descripció

Mentre inicieu la vostra aventura emprenedora, cal seguir pagant factures.

Gràcies a la gran feina que vau desenvolupar a **EverPia**, els responsables de la consultora han decidit continuar donant-vos suport i passar-vos encàrrecs de clients que, actualment, no estan en condicions d'assumir directament.

---

## Introducció al client

L'empresa **TransLògic S.A.**, dedicada a la logística regional, vol renovar la seva infraestructura de servidors a **Windows Server 2025**.

Actualment disposen d'un servidor físic antic que ha quedat obsolet i volen **virtualitzar tota la seva càrrega de treball** per millorar la disponibilitat i facilitar la gestió de la infraestructura.

### Detalls de la infraestructura

#### Servidor físic (*Host*)

* **1 servidor físic**.
* **2 processadors (CPU)**.
* **12 nuclis físics per processador**.
* **Total: 24 nuclis físics**.

#### Càrrega de treball

La infraestructura prevista inclou les màquines virtuals següents:

* **1 VM** per al Controlador de Domini (**Active Directory**).
* **1 VM** per al Servidor de Fitxers.
* **1 VM** per al Servidor d'Impressores i Gestió Documental.
* **1 VM** per a **SQL Server**, destinada a la base de dades de l'ERP.
* **8 VMs de suport** per a aplicacions de logística i terminals de magatzem.

> **Total: 12 màquines virtuals amb Windows Server.**

#### Usuaris i dispositius

L'empresa disposa de:

* **45 empleats en total**.
* **30 treballadors d'oficina**, cadascun amb:

  * Un ordinador.
  * Un ordinador portàtil.
* **15 treballadors de magatzem**, que comparteixen:

  * **5 tauletes robustes** per realitzar tasques d'inventari.
  * Les tauletes s'utilitzen durant **3 torns de treball**.

---

# Encàrrec del client

Com a consultors informàtics, haureu de realitzar una anàlisi de la infraestructura i proposar la solució de llicenciament més adequada.

## 1. Analitzar el model de llicenciament

Analitzeu el model de llicenciament **per nucli (*core*)** de **Windows Server 2025**.

Cal tenir en compte les característiques del servidor físic:

```text
2 CPU × 12 nuclis = 24 nuclis físics
```

---

## 2. Calcular el cost de les diferents opcions

Calculeu el cost total de la infraestructura comparant les dues edicions principals:

* **Windows Server 2025 Standard**
* **Windows Server 2025 Datacenter**

---

## 3. Determinar el tipus de CAL més adequat

Analitzeu quin tipus de **Client Access License (CAL)** és més econòmic per a l'empresa:

* **User CAL**
* **Device CAL**

La decisió s'ha de justificar tenint en compte:

* El nombre d'usuaris.
* El nombre de dispositius.
* Els treballadors que comparteixen dispositius.
* Els diferents torns de treball.

---

## 4. Proposta final

Justifiqueu la decisió final tenint en compte els aspectes següents:

* 💰 **Cost inicial**.
* 📈 **Escalabilitat futura**.
* 🖥️ **Nombre de màquines virtuals**.
* ⚙️ Funcionalitats disponibles segons l'edició.

També cal tenir en compte funcionalitats avançades com:

* **Storage Spaces Direct (S2D)**.
* **Software-Defined Networking (SDN)**.
* Altres funcionalitats relacionades amb la virtualització i la infraestructura de centres de dades.

---

# Presentació al client

Prepareu una presentació dirigida al gerent de **TransLògic S.A.**

La presentació ha de tenir una durada aproximada de:

> **Entre 5 i 10 minuts**

L'objectiu és explicar la proposta de manera:

* Clara.
* Ordenada.
* Entenedora.
* Adaptada a un **perfil no tècnic**.

La presentació hauria d'incloure:

1. La situació inicial del client.
2. Les característiques de la infraestructura.
3. L'explicació del model de llicenciament.
4. La comparació entre **Standard i Datacenter**.
5. La comparació entre **User CAL i Device CAL**.
6. Els costos calculats.
7. La proposta final.
8. La justificació de la decisió.

---

# Materials i recursos de suport

* **UD6. AA1 — Introducció a Windows Server**
  Disponible al Moodle del mòdul **0224 — Sistemes Operatius en Xarxa**.

* [Microsoft — Windows Server: preus i llicències](https://www.microsoft.com/es-es/windows-server/pricing?utm_source=chatgpt.com)

* [Windows Server 2025: llicències, novetats i requisits](https://license-partners.com/windows-server-2025-licencias-novedades-requisitos/?utm_source=chatgpt.com)

* [Calculadora de llicenciament per nuclis](https://www.lenovosalesportal.com/windows-server-2025-core-licensing-calculator.aspx?utm_source=chatgpt.com)

* [Consulta de preus de Windows Server](https://www.senetic.es/category/microsoft-windows-server-13134/?utm_source=chatgpt.com)

---

# Objectius específics de la tasca / Finalitat

L'objectiu específic de la tasca és seleccionar **quina versió del sistema operatiu s'adapta millor a les necessitats del client**, tenint en compte:

* Els requisits tècnics.
* Les necessitats de la infraestructura.
* Els aspectes econòmics.

Com a objectius secundaris, també es treballa:

* L'elaboració de presentacions.
* L'exposició oral. 

---

# Competències treballades

* **k)** Elaborar pressupostos de sistemes a mida complint els requeriments del client.
* **l)** Assessorar i assistir el client, canalitzant a un nivell superior els supòsits que ho requereixin per trobar solucions adequades a les seves necessitats.
* **o)** Utilitzar els mitjans de consulta disponibles, seleccionant-ne el més adequat en cada cas, per resoldre en un temps raonable supòsits no coneguts i dubtes professionals. 

---

# Resultats d'aprenentatge i criteris d'avaluació

## RA(s) de la tasca

### 0224 — Sistemes Operatius en Xarxa

**RA1.** Instal·la sistemes operatius en xarxa descrivint-ne les característiques i interpretant-ne la documentació tècnica.

### 1713 — Projecte Intermodular

**RA2.** Planteja solucions a les necessitats del sector tenint en compte la seva viabilitat, els costos associats i elaborant un petit projecte.

**RA5.** Transmet informació amb claredat, de manera ordenada i estructurada.

---

## CA(s) de la tasca

* **1.1** Realitza l'estudi de compatibilitat del sistema informàtic.
* **2.1** Identifica les necessitats.
* **5.1** Manté una actitud ordenada i metòdica en la transmissió de la informació.
* **5.2** Transmet informació verbal tant horitzontalment com verticalment.

---

## Continguts

* Sistemes operatius en xarxa propietaris.
* Elaboració de presentacions. 

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

# Mòduls i resultats d'aprenentatge treballats

| Mòdul professional                     | Resultat d'aprenentatge |       Hores |
| -------------------------------------- | ----------------------- | ----------: |
| **0224 — Sistemes Operatius en Xarxa** | **RA1**                 |       **2** |
| **1713 — Projecte Intermodular**       | **RA2 / RA5**           |       **2** |
| **Total**                              |                         | **4 hores** |



---

# Quan es necessita, termini i forma de lliurament

## Producte final a lliurar

> **Una presentació dirigida al client amb l'anàlisi i la proposta final de llicenciament.**

## Termini de lliurament

* Consultar la **temporització del mòdul**.

## Forma de lliurament

Caldrà lliurar, a través de la tasca corresponent del **Moodle**, un:

* **Enllaç a la presentació**. 
