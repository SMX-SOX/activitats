# TXX: Servidor d'impressió Linux — CUPS

## Tasca individual

## Breu descripció

### Introducció

Molt bé, equip. A la nostra consultora, **EverPia**, busquem constantment optimitzar els recursos dels nostres clients per reduir costos i simplificar la gestió.

Un dels punts més caòtics en qualsevol oficina és la **gestió d'impressores**: controladors incompatibles, costos de tòner descontrolats i equips que no saben a quina impressora estan enviant els treballs.

La solució professional és implementar un **servidor d'impressió centralitzat**.

### El cas client: DevOptimize Solutions

**DevOptimize Solutions** ens ha demanat una proposta per centralitzar la impressió en tots els seus departaments.

L'empresa utilitza una combinació de:

* Clients Linux amb **Zorin OS**.
* Servidors basats en **Ubuntu Server**.

---

## La vostra missió: la prova de concepte (PoC)

Abans d'invertir en impressores de xarxa, el client vol veure una **Prova de Concepte (*Proof of Concept*, PoC)** que demostri que un servidor Linux pot gestionar una impressora i compartir-la de manera transparent amb els clients Zorin OS.

Per simular una impressora de xarxa sense necessitat d'adquirir maquinari físic, utilitzarem la impressora virtual **`cups-pdf`**.

Aquesta eina funciona com una impressora convencional, però, en lloc d'imprimir el document en paper, genera un **fitxer PDF** que es desa al servidor.

L'objectiu és configurar aquest escenari i demostrar que un client pot enviar correctament un treball d'impressió al servidor. 

---

# Escenari de treball

Utilitzareu el mateix escenari configurat durant la **PoC de NFS**, de manera que podeu continuar treballant amb les mateixes màquines virtuals.

### Màquina 1 — Servidor

**Ubuntu Server** configurat amb:

* Una interfície de xarxa en mode **NAT**.
* Una segona interfície de xarxa en mode **Host-Only**.

### Màquina 2 — Client

**Zorin OS Desktop**, amb una configuració de xarxa compatible amb la del servidor per permetre la comunicació entre ambdues màquines.

---

# PoC: Servidor d'impressió CUPS

Haureu de realitzar les accions següents:

## 1. Instal·lació de CUPS

Instal·leu el servei **CUPS** al servidor.

Documenteu les comandes utilitzades durant la instal·lació.

---

## 2. Instal·lació de la impressora virtual

Instal·leu i configureu la impressora virtual:

```text
cups-pdf
```

Aquesta impressora permetrà generar documents PDF en lloc d'imprimir-los físicament.

---

## 3. Configuració de l'administració de CUPS

Configureu el servei CUPS per:

* Permetre l'administració del servei.
* Permetre que CUPS escolti les connexions a través de totes les interfícies de xarxa necessàries.

Documenteu els canvis realitzats en la configuració.

---

## 4. Compartició de la impressora

Utilitzeu:

* El navegador web.
* La interfície web de CUPS.

Configureu la impressora perquè pugui ser **compartida a través de la xarxa**.

---

## 5. Configuració del client Zorin OS

Des de la màquina client amb **Zorin OS**, afegiu la impressora compartida pel servidor.

Comproveu que el client pot localitzar i utilitzar correctament la impressora.

---

## 6. Proves d'impressió

Realitzeu proves d'impressió de diversos documents des del client.

Comproveu que els treballs són enviats correctament al servidor d'impressió.

---

## 7. Comprovació dels documents generats

Des del servidor, verifiqueu que s'han generat correctament els fitxers **PDF** corresponents als treballs enviats des del client.

Documenteu:

* La ubicació dels fitxers generats.
* Els documents creats.
* Les proves realitzades.

---

# Documentació de la prova

Cal documentar:

* Les comandes utilitzades.
* Els canvis de configuració realitzats.
* Les proves efectuades.
* Les captures de pantalla necessàries per demostrar el correcte funcionament de la prova de concepte.

La documentació s'ha de realitzar seguint el mateix criteri explicat a la tasca relacionada amb la generació de documents en PDF. 

---

# Materials i enllaços de suport

* **Material propi:** UD5. AA1. CUPS, disponible al Moodle del mòdul de **Sistemes Operatius en Xarxa**.
* J. B. Alex Mantich (2024, 15 de febrer). *Instalación de servidor de impresión en CUPS para Linux* [Vídeo]. YouTube.
* R00t (2025, 25 d'abril). *How To Install CUPS Print Server on Ubuntu 24.04 LTS*. Idroot.
* Documentació oficial d'Ubuntu Server.

---

# Objectius específics de la tasca / Finalitat

La finalitat de la tasca és que l'alumnat configuri un **servidor d'impressió utilitzant el protocol CUPS**. 

---

# Competències treballades

* **f)** Instal·lar, configurar i mantenir serveis multiusuari, aplicacions i dispositius compartits en un entorn de xarxa local, atenent les necessitats i els requeriments especificats.

* **g)** Realitzar proves funcionals en sistemes microinformàtics i xarxes locals, localitzant i diagnosticant disfuncions per comprovar-ne i ajustar-ne el funcionament.

* **o)** Utilitzar els mitjans de consulta disponibles, seleccionant-ne el més adequat en cada cas, per resoldre en un temps raonable supòsits no coneguts i dubtes professionals. 

---

# Resultats d'aprenentatge i criteris d'avaluació

## RA(s) de la tasca

**0224. RA4 — Gestiona els recursos compartits del sistema, interpretant especificacions i determinant nivells de seguretat.**

## CA(s) de la tasca

* **4.4** Comparteix impressores en xarxa.

## Continguts

* **4.4** Configuració d'impressores compartides en xarxa. 

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
| **0224 — Sistemes Operatius en Xarxa** | **RA4**                 |       **4** |
| **Total**                              |                         | **4 hores** |



---

# Quan es necessita, termini i forma de lliurament

## Producte final a lliurar

Caldrà lliurar una **carpeta al repositori** que inclogui:

* **`README.md`** amb l'enunciat de la tasca.
* **`Guia.md`** amb la documentació de la **prova de concepte**.

## Forma de lliurament

La tasca es lliurarà mitjançant un **enllaç al repositori**, a través de la tasca corresponent del **Moodle**. 
