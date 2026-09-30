# NF1.UD6. Gestió i Automatització de Servidors amb Scripting en Bash

## Presentació de l'activitat

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed non risus. Suspendisse lectus tortor, dignissim sit amet, adipiscing nec, ultricies sed, dolor. Cras elementum ultrices diam. Maecenas ligula massa, varius a, semper congue, euismod non, mi. Proin porttitor, orci nec nonummy molestie, enim est eleifend mi, non fermentum diam nisl sit amet erat. Duis semper. Duis arcu massa, scelerisque vitae, consequat in, pretium a, enim. Pellentesque congue. Ut in risus volutpat libero pharetra tempor. Cras vestibulum bibendum augue. Praesent egestas leo in pede. Praesent blandit odio eu enim. Pellentesque sed dui ut augue blandit sodales. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam nibh. Mauris ac mauris sed pede pellentesque fermentum. Maecenas adipiscing ante non diam sodales hendrerit.

### Durada de l'activitat

La durada prevista de l'activitat és x hores a classe.

### Objectius específics de l'activitat

- Validar requisits d'execució i paràmetres d'entrada en scripts de Bash.
- Crear i administrar usuaris del sistema de forma individual i massiva mitjançant scripts.
- Automatitzar tasques de manteniment del servidor i integrar-les amb planificadors de tasques.

### Competències treballades

a) Competència 1

### Resultats d'aprenentatge i criteris d'avaluació

RA5.

### Continguts

### Capacitats clau treballades

- Autonomia
- Organització del treball
- Treball en equip
- Innovació
- Resolució de problemes
- Responsabilitat
- Relació interpersonal

### Semàfor ús de la IA

🟠 Aquesta activitat permet un ús parcial o restringit.

Permès per com a eina de suport en la millora de la redacció dels informes, cerca preliminar d'informació, estructuració d'idees o explicació de conceptes teòrics complexos.

Condicions: Cal processar, entendre i validar sempre els resultats rebuts. Està totalment prohibit copiar l'enunciat d'un exercici directament al xat de la IA i enganxar la resposta generada per al lliurament final sense treball propi ni anàlisi crítica.

## Enunciat de l'activitat

### Requeriments previs

Cal que tingueu un servidor Linux (Ubuntu Server) instal·lat i configurat de l'activitat anterior. Cas que sigui necessari, torneu a desplegar el servidor a partir del fitxer `.OVA` que vau generar.

### Bloc 1: Scripts Bàsics i Control de Flux

Exercici 1.1: Control d'entorn i valors de retorn (check_root.sh)

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

## Bloc 2: Gestió d'Usuaris i Grups

Exercici 2.1: Creació d'un usuari amb validacions (crea_usuari.sh)

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

Exercici 2.2: Alta massiva d'usuaris des de fitxer (alta_massiva.sh)

Crea un script anomenat `alta_massiva.sh` per automatitzar la creació de comptes d'usuari a partir d'un fitxer de text.

Paràmetres d'entrada:

    - $1: Ruta d'un fitxer de text amb el format nom_usuari:contrasenya a cada línia.

Requisits:

  1. Comprova privilegis de `root` i verifica que el fitxer d'entrada existeixi.
  2. Defineix una funció anomenada `processar_usuari` que rebi el nom d'usuari i la contrasenya, apliqui la comprovació d'existència i creï l'usuari si escau.
  3. Utilitza un bucle `while read` per llegir el fitxer línia per línia, extreure els dos camps separats pel caràcter `:` i cridar a la funció `processar_usuari`.
  4. Al finalitzar la lectura, mostra un resum amb el nombre total de línies processades.

### Bloc 3: Automatització d'Accions i Manteniment

Exercici 3.1: Backup automatitzat amb data (backup_servidor.sh)

Desenvolupa un script anomenat backup_servidor.sh per realitzar còpies de seguretat de directoris del servidor.

Paràmetres d'entrada:

    - $1: Directori d'origen a copiar ex: `/etc`.
    - $2: Directori de destinació on guardar la còpia ex: `/var/backups`.

Requisits:

 1. Valida que s'hagin entrat els 2 arguments i que el directori origen existeixi.
 2. Si el directori destí no existeix, crea'l fent servir `mkdir -p`.
 3. Genera un nom d'arxiu comprimit amb la data i hora actuals utilitzant la comanda `date`:

    ```
    data=$(date +%Y%m%d_%H%M%S)
    nom_backup="backup_${data}.tar.gz"
    ```

## Què cal lliurar?

Lliureu la guia d'instal·lació amb les captures i explicacions necessàries a la tasca del Moodle corresponent.

Per a cada apartat de l'activitat, la documentació hauria d'incloure, sempre que sigui necessari:

1. **L'objectiu de l'acció.**
2. **La comanda o configuració utilitzada.**
3. **Una explicació del funcionament.**
4. **Una captura de pantalla del resultat.**
5. **Una breu conclusió o comprovació**, quan sigui necessari.

> ## 📚 Recordeu
>
> **«Documentar, documentar i documentar.»**

## Material de suport
