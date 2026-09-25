# NF1.UD2. Configuració bàsica servidor GNU/Linux

## Presentació de l'activitat

En aquesta primera activitat ens centrarem a l'administració bàsica d'un servidor Linux. Començarem amb un canvi respecte a com heu estat treballant amb màquines virtuals fins ara, ja no hi accedirem a la màquina a través de l'entorn virtual, sinó que ho farem a través d'una connexió remota amb SSH.

El motiu, és doble, d'una banda, poder treballar des del terminal de l'equip Windows facilita la feina, i fa que accions com copiar i enganxar siguin més senzilles, i d'altra banda, ens acostuma a la manera de treballar amb servidors reals, que normalment són virtuals i es troben a centres de dades no accessibles físicament.

![sox-ud2](./img/sox-ud2.png)

Veurem les accions bàsiques d'administració: gestió paquets, actualització del sistema i les configuracions bàsiques: xarxa, hora, teclat, etc.

Finalment, exportarem la nostra màquina virtual a un fitxer que podrem importar en altres equips, i que ens permetrà tenir una còpia de seguretat del nostre treball.

### Durada de l'activitat

La durada prevista de l'activitat és 4 hores a classe.

### Objectius específics de l'activitat

- Configuració bàsica d'un servidor GNU/Linux.
- Gestió de màquines virtuals.

### Competències treballades

c) Instal·lar i configurar programari bàsic i d’aplicació, assegurant-ne el funcionament en condicions de qualitat i seguretat.

### Resultats d'aprenentatge i criteris d'avaluació

RA1. Instal·la sistemes operatius en xarxa descrivint-ne les característiques i interpretant-ne la documentació tècnica.

- 1.5 Selecciona els components a instal·lar.
- 1.7 Aplica preferències en la configuració de l'entorn personal.
- 1.8 Actualitza el sistema operatiu en xarxa.
- 1.9 Comprova la connectivitat del servidor amb els equips client

### Continguts

1. Instal·lació de sistemes operatius en xarxa

### Capacitats clau treballades

- Autonomia
- Organització del treball
- Responsabilitat

### Semàfor ús de la IA

🟠 Aquesta activitat permet un ús parcial o restringit.

Permès per com a eina de suport en la millora de la redacció dels informes, cerca preliminar d'informació, estructuració d'idees o explicació de conceptes teòrics complexos.

Condicions: Cal processar, entendre i validar sempre els resultats rebuts. Està totalment prohibit copiar l'enunciat d'un exercici directament al xat de la IA i enganxar la resposta generada per al lliurament final sense treball propi ni anàlisi crítica.

## Enunciat de l'activitat

### Requisits previs

Necessitem la màquina virtual amb Ubuntu Server 26.04 LTS que hem creat a l'activitat anterior. Si la màquina virtual no té el servei SSH instal·lat, caldrà instal·lar-lo amb la comanda `sudo apt install ssh`.

### Descripció de l'activitat

Documenta amb captures de pantalla i explicacions els següents passos:

1. Connexió remota amb SSH a la màquina virtual Ubuntu Server 26.04 LTS.

   - Executa la comanda `ip a` per obtenir les adreces IP de la màquina virtual. Identifica la segona, que correspon a la interfície `host-only` i que és la que utilitzarem per connectar-nos a la màquina virtual des de l'equip Windows.

   - Obre `Terminal`a l'equip Windows i executa la comanda `ssh usuari@adreça_ip`, on `nom_usuari` és el nom d'usuari que has creat a la màquina virtual i `adreça_ip` és l'adreça IP que has identificat a l'apartat anterior.

   - Observa com apareix un missatge d'advertència indicant que la clau de l'equip no és coneguda. Accepta-la i introdueix la contrasenya de l'usuari. Aquest missatge només apareixerà la primera vegada que et connectis a la màquina virtual.

   > ⚠️Si més endanvant, una nova màquina virtual té la mateixa adreça IP, et donarà un error de clau no vàlida. En aquest cas, caldrà eliminar la clau antiga amb la comanda `ssh-keygen -R adreça_ip` i tornar a connectar-se.

2. Actualitzacions del sistema

   - Comprova si el sistema té actualitzacions disponibles. Mostra la comanda que has utilitzat i el resultat obtingut (no cal mostrar la totalitat dels paquets).

   - Simula el resultat d'una actualització amb `apt -s upgrade`. Indica si mostra algun tipus de conflicte o dependència que caldria resoldre abans d'actualitzar.

   - Actualitza el sistema.

   > ⚠️ Tot i que és molt important mantenir els sistemes actualitzats, en entorns de producció, sobretot si tenen serveis crítics, caldrà planificar les actualitzacions per assegurar-se que no es trenqui cap dependència i que els serveis continuïn funcionant correctament. Es recomana la lectura de l'article de G. Garcia "Hay paquetes pendientes de actualizar: ¿actualizo o no?" que teniu accessible a la secció de Materials de suport.

3. Canviant el nom de l'equip

   - Executa la comanda `hostnamectl` i observa la informació que mostra. Fixa't en el camp `Static hostname`, que és el nom actual de l'equip.

   - Anem a canviar el nom de l'equip (static hostname) amb la comanda `sudo hostnamectl set-hostname nom_equip`. Mostra les captures de pantalla i explica els passos que has seguit. Tria un com a nom sox-\<abc>, on \<abc> són les inicials del teu nom. Així per exemple, si el teu nom és Joan Garcia Martí, el nom de l'equip serà sox-jgm.

   - Canviem el "icon name" o nom descriptiu de l'equip amb la comanda `sudo hostnamectl set-icon-name nom_descriptiu`. Mostra les captures de pantalla i explica els passos que has seguit. Tria un nom descriptiu que representi el teu equip, per exemple "Servidor de Joan Garcia Martí".

   - Comprova el canvi amb la comanda `hostnamectl` i mostra el resultat.

   - Comprova quin resultat et mostra la comanda `hostname` i explica la diferència amb el resultat de la comanda `hostnamectl`.

   - Tot i que la comanda `hostnamectl` canvia el nom de l'equip de manera permanent, cal actualitzar el fitxer `/etc/hosts` per assegurar que el nom de l'equip es resol correctament. Edita el fitxer amb la comanda `sudo nano /etc/hosts` per actualitzar la informació del nom de l'equip, afegint també un nom de domini (la resta de l'arxiu s'ha deixar com està).

    ```linux
    127.0.0.1 localhost
    127.0.1.1 server-abc.sox.text server-abc
    ```

   - Comprova quin resultat et mostra la comanda `hostname -f` i explica la diferència amb el resultat de la comanda `hostname`.

4. Canvi de la contrasenya usuari actual (administrador)

   - Executa la comanda `passwd` i canvia la contrasenya de l'usuari `usuari` que has creat a la màquina virtual, posa un triat per tu.

5. Gestió de la instal·lació d'aplicacions

   - Mostra la informació disponible de l'aplicació `htop` amb la comanda `apt show htop`. Explica què és i per a què serveix.

   - Instal·la l'aplicació `htop` amb la comanda `sudo apt install htop`. Mostra les captures de pantalla i explica els passos que has seguit.

6. Configuracions hora, teclat i idioma

   - Configura la zona horària amb la comanda `sudo timedatectl set-timezone Europe/Madrid`. Mostra les captures de pantalla i explica els passos que has seguit.

   - Configura el teclat amb la comanda `sudo dpkg-reconfigure keyboard-configuration`. Mostra les captures de pantalla i explica els passos que has seguit.

   - Configura l'idioma amb la comanda `sudo dpkg-reconfigure locales`. Mostra les captures de pantalla i explica els passos que has seguit.

7. Explorant arxius de configuració

8. Exportar la màquina virtual

   - Exporta la màquina virtual a un fitxer amb extensió `.ova`. Mostra les captures de pantalla i explica els passos que has seguit. Una vegada finalitzat el procés, copia't el fitxer al teu disc extraïble.

### Què cal lliurar?

Lliureu la guia d'instal·lació amb les captures i explicacions necessàries a la tasca del Moodle corresponent.

## Materials de suport

- [Material de l'assignatura. NF1.UD2. Configuració bàsica servidor GNU/Linux](https://smx-sox.github.io/Materials/NF1_SOX_Linux/UD2-Configuraci%C3%B3/)

- G. García, "Hay paquetes pendientes de actualizar: ¿actualizo o no?". Linkedin, setembre 2026.[enllaç a la publicació](https://www.linkedin.com/pulse/hay-paquetes-pendientes-de-actualizar-actualizo-o-garc%C3%ADa-urtiaga-tnkaf/)