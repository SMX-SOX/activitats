# NF1.UD0. Repàs de comandes Linux

## Presentació de l'activitat

Aquest curs treballarem molt amb servidors Linux. Aquests es caracteritzen per utilitzar una versió del sistema operatiu sense entorn gràfic, tant per motius d'optimització de recursos com de seguretat i fiabilitat.

De fet, en el món real, els servidors no són equips amb els quals interactuem de forma continuada i, molt sovint, ni tan sols hi treballem directament.

Per aquest motiu, és important que dominem algunes de les comandes bàsiques de Linux que ja vam estudiar el curs passat.

![learning tux](./img/learning_tux.png)

Al llarg d'aquest segon curs veurem comandes noves per resoldre accions que, de moment, no han estat necessàries. Però entendre bé com moure's pel sistema d'arxius, interactuar amb arxius i carpetes, gestionar els permisos i la propietat dels objectes, saber administrar usuaris i grups i gestionar aplicacions serà imprescindible al llarg dels diferents projectes.

Per aquest motiu, començarem repassant les comandes i accions bàsiques. Disposeu d'unes activitats que us serviran per repassar aquests continguts.

> **L'objectiu no és lliurar les activitats.** Les solucionarem conjuntament al final de la primera setmana.

### Durada de l'activitat

La durada prevista de l'activitat és 2 hores a classe.

### Objectius específics de l'activitat

- Repassar les comandes bàsiques relacionades amb el sistema d'arxius.
- Repassar la gestió d'usuaris i grups.
- Repassar les accions relacionades amb la propietat i els permisos.

### Competències treballades

g) Realitzar les proves funcionals en sistemes microinformàtics i xarxes locals, localitzant i diagnosticant disfuncions, per comprovar i ajustar el seu funcionament.

o) Utilitzar els mitjans de consulta disponibles, seleccionant-ne el més adequat en cada cas, per resoldre en temps raonable supòsits no coneguts i dubtes professionals.

### Resultats d'aprenentatge i criteris d'avaluació

0222-RA3. Realitza tasques bàsiques de configuració de sistemes operatius, interpretant-ne requeriments i descrivint-ne els procediments seguits.

0222-RA4. Realitza operacions bàsiques d'administració de sistemes operatius, interpretant requeriments i optimitzant el sistema per al seu ús.

0222-RA5. Crea màquines virtuals identificant-ne el camp d'aplicació i instal·lant-hi programari específic.

En ser una activitat de repàs, no hi ha criteris d'avaluació específics. No obstant això, es valorarà la participació i implicació en la resolució de les activitats.

### Continguts

- Realització de tasques bàsiques sobre sistemes operatius lliures i propietaris.
- Administració dels sistemes operatius.
- Configuració de màquines virtuals.

### Capacitats clau treballades

- Autonomia
- Organització del treball
- Responsabilitat

### Semàfor ús de la IA

🟠 Aquesta activitat permet un ús parcial o restringit.

Permès per com a eina de suport en la millora de la redacció dels informes, cerca preliminar d'informació, estructuració d'idees o explicació de conceptes teòrics complexos.

Condicions: Cal processar, entendre i validar sempre els resultats rebuts. Està totalment prohibit copiar l'enunciat d'un exercici directament al xat de la IA i enganxar la resposta generada per al lliurament final sense treball propi ni anàlisi crítica.

## Enunciat de l'activitat

### Indicacions

Executa els següents exercicis en una màquina virtual amb GNU/Linux usant el terminal. Per a cada exercici, escriu la comanda o seqüència de comandes que faries i comprova que el resultat sigui correcte.

Descarrega't l'arxiu ubuntu.ova de la carpeta de xarxa i importa-la a VirtualBox. Inicia la màquina virtual i accedeix-hi amb l'usuari `usuari` i la contrasenya `usuari`.

### Bloc 1: Sistema de fitxers

1. Llista tots els fitxers i carpetes (amb detalls i fitxers ocults) dins del directori `/home`.

2. Copia el fitxer `/etc/passwd` al teu directori personal i canvia el nom de l'arxiu copiat a `users.txt`.

3. Mou el fitxer `users.txt` dins una nova carpeta del teu usuari anomenada documents. Si no existeix, crea-la.

4. Esborra el fitxer `users.txt` dins de documents.

5. Crea tres carpetes noves dins del teu directori personal: `proves`, `proves2` i `proves3` d’una sola comanda.

### Bloc 2: Usuaris i grups

1. Crea dos usuaris nous anomenats `prova1` i `prova2` amb directori personal i shell `/bin/bash`.

2. Crea un grup nou anomenat `alumnes`.

3. Afegeix l’usuari `prova1` al grup `alumnes` i al grup que pot fer sudo (mantenint els grups que ja té).

4. Mostra els grups dels que és membre `prova1`.

5. Elimina l’usuari `prova1` (esborrant el seu directori personal si n’hi hagués).

### Bloc 3: Permisos i propietats

1. Crea un fitxer anomenat `secret.txt` i treu tots els permisos per a “altres”. Comprova resultat amb comanda `ls -l`.

2. Canvia el propietari del fitxer `secret.txt` a l’usuari `prova2`. Comprova resultat amb comanda `ls -l`.

3. Assigna el grup `alumnes` al fitxer `secret.txt`. Comprova resultat amb comanda `ls -l`.

4. Fes que la carpeta `proves2` tingui com a propietari `prova2` i grup propietari `alumnes`. Comprova resultat amb comanda `ls -l`.

5. Dona permisos a la carpeta `proves2` de manera que tant el propietari, com el grup propietari puguin llegir i escriure. La resta d’usuaris no tenen cap permís. Comprova resultat amb comanda `ls -l`.

## Lliurament de l'activitat

No cal fer cap lliurament. L'activitat es realitzarà a classe i es corregirà conjuntament.

## Material de suport

- J. Carrillo. *El Manual de Comandos Linux*. FreeCodeCamp.Novembre 2020. [enllaç](https://www.freecodecamp.org/espanol/news/comandos-de-linux/)

- [Linux Journey](https://labex.io/linuxjourney)
