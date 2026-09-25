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

   - Cerca el paquet `btop` per verificar que existeix als repositoris.

   - Mostra la informació del paquet `btop` amb la comanda `apt show btop`. Documenta la informació que mostra la comanda.

   - Instal·la l'aplicació `btop` amb la comanda `sudo apt install btop`. Un cop finalitzada la instal·lació, obre el programa per comprovar que funciona correctament.

   - Cerca la informació relativa al paquet `lsd`. Instal·la el paquet `lsd` i comprova el seu funcionament com alternativa a la comanda `ls`.

   - Instal·la el paquet `apache2` amb la comanda `sudo apt install apache2`. Un cop finalitzada la instal·lació, comprova que el servei està actiu amb la comanda `systemctl status apache2`.

   - Desinstal·la el paquet netejant també els fitxers de configuració (opció purge) amb la comanda `sudo apt purge apache2`. Comprova que el servei ja no està actiu amb la comanda `systemctl status apache2`.

   - Provem ara a instal·lar un paquet de tipus `snap`. Instal·la el paquet `micro` amb la comanda `sudo snap install micro --classic`. Un cop finalitzada la instal·lació, comprova que el servei està instal·lat amb la comanda `snap list`. Obre el programa i comprova que el programa funciona correctament.

   > ⚠️ El paràmetre `--classic` és necessari per a alguns paquets que necessiten accedir a parts del sistema que no estan disponibles amb el confinament de seguretat que utilitza `snap`. Per això, caldrà afegir aquest paràmetre a la comanda d'instal·lació.

   - Actualitza el paquet `micro` amb la comanda `sudo snap refresh micro`. Com just l'acabes d'instal·lar, no farà res, però és important conèixer la comanda.

   - Desinstal·la el paquet `micro` amb la comanda `sudo snap remove micro`. Comprova que el servei ja no està actiu amb la comanda `snap list`.

   › 💡 Tot i que per l'activitat cal desinstal·lar l'editor `micro`si veus que t'agrada més que el tradicional `nano`, pots tornar a instal·lar-lo per fer-lo servir al llarg de les activitats.

6. Configuracions hora, teclat i idioma

   - Observa la configuració actual de la zona horària amb la comanda `timedatectl`.

   - Configura la zona horària amb la comanda `sudo timedatectl set-timezone Europe/Madrid`. Assegura't que la sincronització horària estigui activa. Mostra les captures de pantalla i explica els passos que has seguit.

   - Configura el teclat amb la comanda `sudo dpkg-reconfigure keyboard-configuration`. I assegura't que la configuració sigui correcta. Mostra les captures de pantalla i explica els passos que has seguit.

   - Mostra la configuració actual de l'idioma amb la comanda `locale`. Documenta com es configura l'idioma amb la comanda `sudo dpkg-reconfigure locales`. Mostra les captures de pantalla i explica els passos que has seguit.

7. Explorant arxius de configuració

   La carpeta `/etc` conté els fitxers de configuració del sistema i està ple de subcarpetes. Començarem buscant fitxers per nom, extensió i mida.

   - Troba la ruta exacta dels fitxers de configuració que tinguin extensió `.yaml` amb la comanda `find /etc -type f -name "*.yaml"`. Mostra la comanda i el resultat obtingut.

   - Ara buscarem les carpetes que continguin la paraula "ssh" dins de /etc amb la comanda `find /etc -type d -name "*ssh*"`. Mostra la comanda i el resultat obtingut.

   - Localitza fitxers grans: Busca quins fitxers de configuració o logs dins de /var/log ocupen més de 10 Megabytes (útil per quan un servidor es queda sense espai):

   ```linux
      find /var/log -type f -size +10M
   ```

   - Mostra el fitxer de configuració del servei SSH, però omet totes les línies que siguin comentaris (#) o estiguin buides:

   ```linux
      grep -vE '^\s*#|^\s*$' /etc/ssh/sshd_config
   ```

   › El paràmetre -v inverteix la cerca —mostra el que NO coincideix— i -E activa les expressions regulars per detectar el símbol # a l'inici de línia ^ o línies buides ^$. A l'article "Guía completa del comando grep en Linux" teniu més informació sobre com utilitzar aquesta comanda.

8. Configuracions de xarxa

   Fins ara la nostra màquina virtual està usant adreces IP de forma automàtica (DHCP). En el cas dels servidors reals, l'habitual és tenir una adreça IP fixa.

   - Canvia la configuració de la primera interfície de `xarxa NAT` a `Adaptador pont`. Mostra clarament que has canviat la configuració.

   - Edita l'arxiu de `netplan`per configurar la interfície de xarxa amb una adreça IP fixa. Seguint el següent criteri:

      - Adreça IP: 192.168.c.x, on c identifica la classe (2 per 2n A i 4 per 2n B) i x correspon al teu número de llista.
      - Màscara de subxarxa: 255.255.255.0
      - Passarel·la: 192.168.c.254 (òbviament c ha de ser coherent amb l'adreça IP que has triat).
      - Servidor de noms: 8.8.8.8

   - Aplica els canvis amb la comanda `sudo netplan apply` i comprova que la configuració és correcta amb la comanda `ip a`.

   › 💡 Els arxius `yaml` s'han d'identar de forma similar a Python i no admet tabuladors.

   - Comprova que la màquina virtual té connectivitat amb la xarxa i amb Internet.

9. Gestió de serveis

   Un servidor es caracteritza per oferir diversos serveis a la xarxa. Aquests serveis s'executen com a processos en segon pla i es poden gestionar amb la comanda `systemctl`.

   - Comprova l'estat del servei SSH amb la comanda `systemctl status ssh`. Mostra el resultat obtingut.

   - Atura el servei SSH amb la comanda `sudo systemctl stop ssh`. Observa com  has perdut la connexió amb la màquina virtual i no pots tornar a connectar-te fins que no tornis a iniciar el servei (des de la màquina virtual, no des de l'equip Windows).

   - Inicia el servei SSH amb la comanda `sudo systemctl start ssh`. Torna a connectar-te a la màquina virtual des de l'equip Windows i comprova que el servei està actiu amb la comanda `systemctl status ssh`.

10. Acabar i exportar la màquina virtual

    - Arribem al final de l'activitat. El primer que farem serà posar l'adaptador de xarxa de la màquina virtual a `xarxa NAT` i editar la configuració de netplan perquè torni a obtenir una adreça IP automàticament (DHCP). Actualitza el netplan i comprova les adreces IP.

    - Exporta la màquina virtual a un fitxer amb extensió `.ova`. Mostra les captures de pantalla i explica els passos que has seguit. Una vegada finalitzat el procés, copia't el fitxer al teu disc extraïble.

### Què cal lliurar?

Lliureu la guia d'instal·lació amb les captures i explicacions necessàries a la tasca del Moodle corresponent.

## Materials de suport

- [Material de l'assignatura. NF1.UD2. Configuració bàsica servidor GNU/Linux](https://smx-sox.github.io/Materials/NF1_SOX_Linux/UD2-Configuraci%C3%B3/)

- G. García, "Hay paquetes pendientes de actualizar: ¿actualizo o no?". Linkedin, setembre 2026.[enllaç a la publicació](https://www.linkedin.com/pulse/hay-paquetes-pendientes-de-actualizar-actualizo-o-garc%C3%ADa-urtiaga-tnkaf/)

- C. Lead, "Guía Completa del Comando grep en Linux: De lo Básico a lo Avanzado". cesarlead, juliol 2020. [enllaç a la publicació](https://cesarlead.com/posts/guia-completa-grep-linux/).
