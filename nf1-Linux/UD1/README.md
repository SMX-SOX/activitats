# NF1.UD1. Instal·lació Ubuntu Server

## Presentació de l'activitat

Toca posar-s'hi mans a l'obra i començar a muntar el nostre primer servidor Linux. Per què? Bona part de la feina dels administradors de sistemes consisteix a instal·lar i configurar servidors, i en molts casos, caldrà utilitar alguna distribució de GNU/Linux.

Què caldrà fer?

Crear una màquina virtual amb Ubuntu Server. Utilitzarem la versió LTS més recent. Aquesta màquina haurà de seguir estrictament els requeriments que trobareu a continuació. En cas contrari, l'avaluació serà negativa. Aquest és el primer pas per convertir-vos en superherois dels sistemes.

![Ubuntu Server](./img/ud1-img1.png)

### Durada de l'activitat

La durada prevista de l'activitat és 4 hores a classe.

### Objectius específics de l'activitat

- Instal·lar un sistema operatiu sense entorn gràfic.
- Interpretar correctament les instruccions d'instal·lació.

### Competències treballades

a) Determinar la logística associada a les operacions d'instal·lació, configuració i manteniment de sistemes microinformàtics, interpretant-ne la documentació tècnica associada i organitzant els recursos necessaris.

### Resultats d'aprenentatge i criteris d'avaluació

RA1. Instal·la sistemes operatius en xarxa descrivint-ne les característiques i interpretant-ne la documentació tècnica.

1.1 Realitza l'estudi de compatibilitat del sistema informàtic.
1.2 Diferencia els modes d'instal·lació.
1.3 Planifica i realitza el particionat del disc del servidor.
1.4 Selecciona i aplica els sistemes d'arxius.
1.5 Selecciona els components a instal·lar.
1.6 Actualitza el sistema operatiu en xarxa.

### Continguts

1. Instal·lació de sistemes operatius en xarxa
 1.1 Comprovació dels requisits tècnics. Preparació de la instal·lació.
 1.2 Particions i sistema d'arxius. Components i mètodes.
 1.4 Elaboració de la documentació sobre la instal·lació i les incidències.
 1.5 Instal·lació de sistemes operatius en xarxa en màquines virtuals.

### Capacitats clau treballades

- Autonomia
- Organització del treball
- Responsabilitat

### Semàfor ús de la IA

🟠 Aquesta activitat permet un ús parcial o restringit.

Permès per com a eina de suport en la millora de la redacció dels informes, cerca preliminar d'informació, estructuració d'idees o explicació de conceptes teòrics complexos.

Condicions: Cal processar, entendre i validar sempre els resultats rebuts. Està totalment prohibit copiar l'enunciat d'un exercici directament al xat de la IA i enganxar la resposta generada per al lliurament final sense treball propi ni anàlisi crítica.

## Enunciat de l'activitat

Cal que instal·leu un Ubuntu Server 26.04 LTS en una màquina virtual, en el cas de classe serà VirtualBox, si feu l'activitat a casa podeu utilitzar qualsevol altre programari de virtualització.

L'arxiu .ISO del sistema operatiu el trobareu a la unitat de xarxa, dins la carpeta `ISOs`. També el podeu descarregar des de la [pàgina oficial d'Ubuntu](https://ubuntu.com/download/server), tot i que a la classe no es recomana perquè pot trigar força temps.

### Requisits de la màquina virtual

La màquina virtual haurà de complir obligatòriament els requisits següents:

- Memòria RAM: 4 GB.
- Processador: 4 nuclis.
- Disc dur: 20 GB.
- Dos adaptadors de xarxa:
  - Xarxa NAT.
  - host-only (per poder accedir a la màquina virtual des de l'ordinador host).
- Usuari i contrasenya: `usuari` / `usuari` (sense cometes).
- Instal·la el servei SSH durant la instal·lació del sistema operatiu. Això ens permetrà connectar-nos a la màquina virtual des de l'ordinador host des del terminal.

### Documentació de la instal·lació

A més de crear la màquina virtual, haureu d'elaborar una guia d'instal·lació en què documentareu correctament les diferents accions, configuracions i decisions preses durant el procés.

Penseu que documentar correctament una instal·lació és fonamental per evitar errors i facilitar posteriors desplegaments o configuracions.

> ### 📚 El lema d'aquest curs és
>
> ***«Documentar, documentar i documentar.»***

### Què cal lliurar?

Lliureu la guia d'instal·lació amb les captures i explicacions necessàries a la tasca del Moodle corresponent.

## Material de suport

- [NF1.UD1. Instal·lació Ubuntu Server](https://smx-sox.github.io/Materials/NF1_SOX_Linux/UD1-Instal%C2%B7laci%C3%B3/)

- [Documentació oficial d'Ubuntu Server](https://ubuntu.com/server/docs)
