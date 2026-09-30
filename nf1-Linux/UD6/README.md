# NF1.UD6. Gestió i Automatització de Servidors amb Scripting en Bash

## Presentació de l'activitat

### El repte: Sistemes Bàsics Consultoria

Com a  tècnics júniors de **EverPia Consulting**, doneu suport als vostres clients, qie no disposen d'un equip d'infraestructura propi, i confien en el vostre servei per mantenir els seus servidors operatius, segurs i actualitzats sense necessitat d'intervenció manual constant.

Fins ara, moltes tasques del dia a dia (comprovacions, altes d'usuaris, còpies de seguretat, neteja de fitxers temporals...) es feien manualment, cosa que consumeix temps i genera errors humans. La direcció de la consultora us encarrega automatitzar aquests processos mitjançant scripting en Bash, per tal de reduir la càrrega operativa de l'equip i oferir un servei més fiable als clients.

Aquest repte es planteja en dues fases:

- **Fase d'aprenentatge**: abans d'atendre cap client, cal que domineu les bases del scripting: control de flux, validació de paràmetres, gestió d'usuaris i grups. Aquests exercicis (Blocs 1 i 2) us serviran per consolidar les competències tècniques que després aplicareu als casos reals.
- **Fase de resolució de casos reals**: un cop dominades les bases, assumireu peticions reals de clients de la consultora relacionades amb l'automatització de tasques de manteniment (còpies de seguretat, neteja de temporals, control d'espai en disc i planificació amb cron), documentant la solució com si l'haguéssiu de lliurar al client.

### Durada de l'activitat

La durada prevista de l'activitat és 8 hores a classe.

### Objectius específics de l'activitat

- Validar requisits d'execució i paràmetres d'entrada en scripts de Bash.
- Crear i administrar usuaris del sistema de forma individual i massiva mitjançant scripts.
- Automatitzar tasques de manteniment del servidor i integrar-les amb planificadors de tasques.

### Competències treballades

h) Mantenir sistemes microinformàtics i xarxes locals, substituint-ne, actualitzant-ne i ajustant-ne els components, per assegurar el rendiment del sistema en condicions de qualitat i seguretat.

n) Mantenir un esperit constant d’innovació i actualització en l’àmbit del sector informàtic.

### Resultats d'aprenentatge i criteris d'avaluació

RA5. Realitza tasques de monitoratge i ús del sistema operatiu en xarxa, descrivint les eines utilitzades i identificant les principals incidències.

5.5 Executa operacions per a l'automatització de tasques del sistema.

### Continguts

- Monitoratge i ús del sistema operatiu en xarxa

### Capacitats clau treballades

- Autonomia
- Organització del treball
- Innovació
- Resolució de problemes
- Responsabilitat

### Semàfor ús de la IA

🟠 Aquesta activitat permet un ús parcial o restringit.

Permès per com a eina de suport en la millora de la redacció dels informes, cerca preliminar d'informació, estructuració d'idees o explicació de conceptes teòrics complexos.

Condicions: Cal processar, entendre i validar sempre els resultats rebuts. Està totalment prohibit copiar l'enunciat d'un exercici directament al xat de la IA i enganxar la resposta generada per al lliurament final sense treball propi ni anàlisi crítica.

## Enunciat de l'activitat

### Requeriments previs

Cal que tingueu un servidor Linux (Ubuntu Server) instal·lat i configurat de l'activitat anterior. Cas que sigui necessari, torneu a desplegar el servidor a partir del fitxer `.OVA` que vau generar.

### Bloc 1: Scripts Bàsics i Control de Flux

#### Exercici 1.1: Control d'entorn i valors de retorn (check_root.sh)

Dissenya un script anomenat `check_root.sh` per verificar si qui l'executa té permisos suficients al servidor.

Requisits:

  1. Comprova si l'script s'executa com a superusuari (root, UID = 0) utilitzant `$(id -u)`.
  2. Si no s'executa com a root, mostra per pantalla: "Error: Aquest script requereix privilegis de superusuari." i finalitza amb el codi de retorn 1.
  3. Si s'executa com a root, mostra per pantalla l'usuari actual i el directori de treball `$PWD`, i finalitza amb el codi de retorn 0.

Exercici 1.2: Validació de paràmetres i càlcul d'espai (check_space.sh)

Crea un script anomenat `check_space.sh` que rebi com a argument la ruta d'un directori del sistema.

Requisits:

  1. Comprova si s'ha passat un argument `$#`. Si no, mostra per pantalla: "Error: Cal indicar un directori." i finalitza amb el codi de retorn 1.
  2. Comprova si l'argument és un directori existent `-d`. Si no, mostra per pantalla: "Error: El directori indicat no existeix." i finalitza amb el codi de retorn 2.
  3. Si tot és correcte, calcula l'espai ocupat pel directori amb la comanda `du -sh [directori]` i mostra per pantalla: "L'espai ocupat pel directori [directori] és de [espai] bytes." i finalitza amb el codi de retorn 0.

### Bloc 2: Gestió d'Usuaris i Grups

#### Exercici 2.1: Creació d'un usuari amb validacions (crea_usuari.sh)

Paràmetres d'entrada:

    - $1:Nom d'usuari
    - $2: Contrasenya de l'usuari

Requisits:

   1. Comprova que l'script s'executi com a `root`. Si no, mostra un missatge i surt amb codi de retorn 1.
   2. Valida que s'hagin rebut exactament 2 arguments `$# -ne 2`. En cas contrari, mostra "Ús: ./crea_usuari.sh \<usuari\> \<contrasenya\>" i surt amb codi 2.
   3. Comprova si l'usuari ja existeix al sistema redirigint tota la sortida i d'errors a /dev/null: `id "$1" &>/dev/null`.
   4. Si l'usuari ja existeix, mostra "L'usuari \<usuari\> ja existeix al sistema." i surt amb codi 3.
   5. Si l'usuari no existeix:
      - Crea l'usuari amb `useradd -m -s /bin/bash "$1"`.
      - Assigna la contrasenya usant una canonada (pipe) amb `echo "$1:$2" | chpasswd`.
      - Mostra el missatge "Usuari \<usuari\> creat correctament." i surt amb codi 0.

#### Exercici 2.2: Alta massiva d'usuaris des de fitxer (alta_massiva.sh)

Crea un script anomenat `alta_massiva.sh` per automatitzar la creació de comptes d'usuari a partir d'un fitxer de text.

Paràmetres d'entrada:

    - $1: Ruta d'un fitxer de text amb el format nom_usuari:contrasenya a cada línia.

Requisits:

  1. Comprova privilegis de `root` i verifica que el fitxer d'entrada existeixi.
  2. Defineix una funció anomenada `processar_usuari` que rebi el nom d'usuari i la contrasenya, apliqui la comprovació d'existència i creï l'usuari si escau.
  3. Utilitza un bucle `while read` per llegir el fitxer línia per línia, extreure els dos camps separats pel caràcter `:` i cridar a la funció `processar_usuari`.
  4. Al finalitzar la lectura, mostra un resum amb el nombre total de línies processades.

### Bloc 3: Automatització d'Accions i Manteniment

#### Exercici 3.1: Backup automatitzat amb data (backup_servidor.sh)

Desenvolupa un script anomenat backup_servidor.sh per realitzar còpies de seguretat de directoris del servidor.

Paràmetres d'entrada:

    - $1: Directori d'origen a copiar ex: `/etc`.
    - $2: Directori de destinació on guardar la còpia ex: `/var/backups`.

Requisits:

  1. Valida que s'hagin entrat els 2 arguments i que el directori origen existeixi.
  2. Si el directori destí no existeix, crea'l fent servir `mkdir -p`.
  3. Genera un nom d'arxiu comprimit amb la data i hora actuals utilitzant la comanda `date`:

    ```bash
    data=$(date +%Y%m%d_%H%M%S)
    nom_backup="backup_${data}.tar.gz"
    ```

#### Exercici 3.2: Manteniment del sistema i tasca programada (manteniment_sistema.sh)

Escriu un script de manteniment automàtic integrat amb registres (logs) i preparat per al dimoni cron.

Requisits:

  1. Fitxer de registre: Redirigeix tota la informació generada per l'script afegint-la (>>) al fitxer /var/log/manteniment_sox.log. Cada línia de log ha de començar amb la data i hora actuals (YYYY-MM-DD HH:MM:SS).
  2. Neteja de fitxers temporals: Esborra els fitxers del directori /tmp que tinguin una antiguitat superior a 7 dies utilitzant la comanda find /tmp -type f -mtime +7 -delete.
  3. Control d'espai en disc:
    - Obtén el percentatge d'ús de la partició arrel (/).
    - Si l'ús és superior al 80%, escriu una línia al log: "[ALERTA] Espai en disc ocupat per sobre del 80% (Ús actual: X%)".
  4. Planificació: **Afegeix com a comentari (#)** al final de l'script la línia exacta que cal afegir al crontab de root per executar aquest script automàticament cada diumenge a les 02:00 hores.

### Guia de bones pràctiques

- Tots els scripts han d'incloure la línia shebang `#!/bin/bash` i una capçalera amb descripció, autoria i data.
- Utilitzeu variables en minuscula i snake_case seguint les bones pràctiques descrites a la guia.

## Què cal lliurar?

- README.md amb la descripció de l'activitat i les instruccions d'ús dels scripts.
- Carpeta al repositori amb tots els scripts desenvolupats.
- Documentació en format Markdown amb la descripció de cada script i mostres de sortida de la seva execució.

## Material de suport

- C. Alonso. *Guia per a la creació d'scripts*. [Repostori de GitHub](https://github.com/carlesalonso/IntroScripting)

- A. Ahmed. *bash guide*. [Repostori de GitHub](https://github.com/Idnan/bash-guide)

- D. Dovhan. *bash handbook*. [Repostori de GitHub](https://github.com/denysdovhan/bash-handbook)
