# T09: Servidor de fitxers Linux — NFS

## Tasca individual

### Breu descripció

### Introducció

Molt bé, equip de **consultors júniors**. En aquest projecte ens trobem davant d'un requisit tècnic molt habitual per part dels clients: la **centralització de dades en entorns Linux**.

### El cas client: DevOptimize Solutions

El nostre client, **DevOptimize Solutions**, és una petita *startup* de desenvolupament de programari que treballa exclusivament amb Linux.

Actualment tenen un problema crític: el seu codi font i els seus actius —documents de disseny, scripts, etc.— estan descontrolats. Cada desenvolupador disposa de còpies locals, fet que provoca constants errors de versions i una important pèrdua d'eficiència.

Ens han contractat per implementar un **servidor de fitxers centralitzat**.

Atès que tot l'entorn és Linux, la solució nativa proposada és **NFS (*Network File System*)**.

El client ha insistit que actualment treballa **sense un entorn d'autenticació centralitzada** i que, de moment, no té previst implementar-ne cap.

Per mostrar al client com funcionaria la solució proposada i també les seves limitacions, se us encarrega la realització d'una **demostració del sistema**.

Haureu de:

* Crear un **servidor NFS (NFSv3)**.
* Configurar un **client Linux** que consumeixi els recursos compartits.
* Crear usuaris i grups per **simular** l'entorn del client.
* Demostrar el control d'accés utilitzant:

  * Les opcions d'exportació de `/etc/exports`.
  * Els permisos del sistema de fitxers mitjançant `chmod` i `chown`.

En aquest repositori trobareu la descripció de la tasca:

[Projecte04-NFS](https://github.com/SMX2n/Projecte04-NFS?utm_source=chatgpt.com)

### Materials i enllaços de suport

* **Material propi:** UD5. AA1. NFS, disponible al Moodle del mòdul de **Sistemes Operatius en Xarxa**.
* Ruiz, P. (2021, 22 de novembre). *NFS (parte 1): Instalación en un servidor Ubuntu 20.04 LTS*. SomeBooks.es.
* Ruiz, P. (2021, 2 de desembre). *NFS (parte 2): Instalación en un cliente Ubuntu 20.04 LTS*. SomeBooks.es.
* [Documentació oficial d'Ubuntu sobre NFS](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/?utm_source=chatgpt.com)

---

## Objectius específics de la tasca / Finalitat

La finalitat de la tasca és que l'alumnat configuri un **servidor de fitxers NFS amb diversos nivells d'accés** i prepari un **client Linux per accedir automàticament als recursos compartits**. 

---

## Competències treballades

* **f)** Instal·lar, configurar i mantenir serveis multiusuari, aplicacions i dispositius compartits en un entorn de xarxa local, atenent les necessitats i els requeriments especificats.
* **g)** Realitzar proves funcionals en sistemes microinformàtics i xarxes locals, localitzant i diagnosticant disfuncions per comprovar-ne i ajustar-ne el funcionament.
* **o)** Utilitzar els mitjans de consulta disponibles, seleccionant el més adequat en cada cas, per resoldre en un temps raonable supòsits no coneguts i dubtes professionals. 

---

## Resultats d'aprenentatge i criteris d'avaluació

### RA(s) de la tasca

**0224. RA4 — Gestiona els recursos compartits del sistema, interpretant especificacions i determinant nivells de seguretat.**

### CA(s) de la tasca

* **4.1** Reconeix la diferència entre permís i dret.
* **4.2** Identifica els recursos del sistema que es compartiran i en quines condicions.
* **4.3** Assigna permisos als recursos del sistema que es compartiran.
* **4.5** Utilitza l'entorn gràfic per compartir recursos.
* **4.6** Estableix nivells de seguretat per controlar l'accés del client als recursos compartits en xarxa.

### Continguts

* **4.1** Permisos i drets.
* **4.2** Compartir arxius i directoris a través de la xarxa.
* **4.3** Configuració dels permisos dels recursos compartits. 

---

## Capacitats clau treballades

* Autonomia
* Innovació
* Relació interpersonal
* Organització del treball
* Responsabilitat
* Treball en equip
* Resolució de problemes

---

## Mòdul i resultat d'aprenentatge treballat

| Mòdul professional                     | Resultat d'aprenentatge |       Hores |
| -------------------------------------- | ----------------------- | ----------: |
| **0224 — Sistemes Operatius en Xarxa** | **RA4**                 |       **4** |
| **Total**                              |                         | **4 hores** |



---

## Quan es necessita, termini i forma de lliurament

### Producte final a lliurar

Caldrà lliurar una **carpeta al repositori** que inclogui:

* **`README.md`** amb l'enunciat de la tasca.
* **`Guia.md`** amb la documentació de la **prova de concepte**.

### Forma de lliurament

La tasca es lliurarà mitjançant un **enllaç al repositori**, a través de la tasca corresponent del **Moodle**. 
