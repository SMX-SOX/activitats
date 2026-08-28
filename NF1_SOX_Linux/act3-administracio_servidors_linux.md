# Administració Servidors Linux

# Instruccions

* L'activitat s'ha de realitzar de manera **individual**.
* Cal documentar les accions sol·licitades, **comentant i explicant** els aspectes necessaris.
* Compartiu el document elaborat a **Google Drive**.

---

# Configuracions prèvies

Partim d'una màquina amb **Ubuntu Server** instal·lada durant el projecte anterior.

Si l'heu esborrat, haureu d'importar l'arxiu **OVA** que vau crear amb aquesta màquina virtual.

Abans d'arrencar la màquina virtual, configureu una **tercera interfície de xarxa**, que en aquesta ocasió haurà d'estar configurada en mode **només-amfitrió**.

---

# Configuració del servidor

## 1. Configuració de la tercera interfície

Arrenqueu la màquina virtual i editeu l'arxiu de configuració de **Netplan** perquè aquesta tercera interfície es configuri mitjançant **DHCP (`dhcp4`)**, igual que la primera interfície configurada en mode **NAT**.

---

## 2. Nom de la màquina i domini

Canvieu el nom de la màquina perquè segueixi el format següent:

```text
serverXX
```

Configureu també el domini:

```text
soxXX.test
```

Substituïu `XX` pel número que correspongui segons les indicacions del professorat.

---

## 3. Comprovació del nom complet de la màquina

Mostreu el nom complet de la màquina utilitzant la comanda:

```bash
hostname -f
```

Expliqueu les diferències entre les comandes:

```bash
hostname
```

i:

```bash
hostname -f
```

---

## 4. Actualització del sistema

Actualitzeu el sistema operatiu perquè disposi de les últimes actualitzacions disponibles.

Documenteu les comandes utilitzades.

---

## 5. Instal·lació de `duf`

Instal·leu l'eina:

```text
duf
```

Aquesta eina s'utilitzarà posteriorment per consultar la informació relacionada amb l'espai disponible als sistemes d'arxius.

---

## 6. Creació d'un grup

Creeu un grup anomenat:

```text
usuaris
```

---

## 7. Creació d'un usuari

Creeu un segon usuari anomenat:

```text
user1
```

Aquest usuari haurà de complir els requisits següents:

* Disposar d'una **carpeta personal**.
* Utilitzar **Bash** com a shell per defecte.

---

## 8. Assignació d'usuaris al grup

Afegiu l'usuari inicial del sistema i l'usuari:

```text
user1
```

com a membres del grup:

```text
usuaris
```

---

## 9. Informació dels usuaris

Obriu l'arxiu:

```text
/etc/passwd
```

Utilitzeu la comanda `grep` per mostrar únicament les línies corresponents als dos usuaris creats o configurats anteriorment.

Documenteu:

* La comanda utilitzada.
* La informació que apareix a cada línia.
* El significat de cadascun dels camps mostrats.

---

## 10. Emmagatzematge de les contrasenyes

Responeu les preguntes següents:

* On s'emmagatzemen les contrasenyes dels usuaris?
* En quin format s'emmagatzemen?

Documenteu breument la diferència entre els arxius relacionats amb la informació dels usuaris i les contrasenyes.

---

## 11. Configuració de la zona horària

Configureu correctament la **zona horària** del sistema.

Comproveu posteriorment que la configuració s'ha aplicat correctament.

---

## 12. Configuració de mDNS

Configureu l'equip perquè funcioni amb **mDNS**.

Instal·leu i configureu el servei o dimoni necessari perquè:

* El sistema pugui resoldre noms d'equips mitjançant mDNS.
* El servei s'iniciï automàticament en arrencar el sistema.

---

## 13. Comprovació de la resolució de noms

Comproveu que podeu identificar els equips dels companys o companyes del grup utilitzant únicament el seu nom d'amfitrió.

Per exemple:

```bash
ping nom_host
```

No haureu d'indicar directament l'adreça IP.

Documenteu el resultat de la prova.

---

# Gestors gràfics

## 1. Instal·lació de Webmin

Instal·leu **Webmin** al servidor.

Documenteu el procés d'instal·lació i l'accés a la seva interfície web.

---

## 2. Informació del servidor

Analitzeu la informació que mostra Webmin sobre el servidor.

Indiqueu quina informació podeu consultar, com ara:

* Informació del sistema.
* Sistema operatiu.
* Processador.
* Memòria.
* Espai d'emmagatzematge.
* Xarxa.
* Serveis en execució.

---

## 3. Menús principals

Mostreu i documenteu els principals menús disponibles a Webmin.

Afegiu captures de pantalla i indiqueu breument la funció de cada apartat principal.

---

## 4. Gestió d'usuaris i grups

Comproveu com es poden crear i gestionar **usuaris i grups** des de Webmin.

Per documentar aquesta acció:

* Creeu un usuari.
* Creeu un grup.
* Documenteu el procés mitjançant captures de pantalla.

---

## 5. Mòduls de Webmin

Una de les característiques principals de Webmin és la seva **modularitat**.

Webmin permet afegir o activar mòduls per gestionar diferents serveis, com ara:

* DNS.
* Correu electrònic.
* FTP.
* LDAP.

Observeu els mòduls disponibles però no activats a l'apartat **Un-used modules**.

Activeu el mòdul corresponent a la gestió d'un servidor **FTP**.

> **Nota:** No patiu si el servidor FTP no està instal·lat. L'objectiu és localitzar i activar el mòdul corresponent.

---

# Monitorització

## 1. Processos en funcionament

Mostreu els processos que s'estan executant actualment al sistema.

Documenteu la comanda o eina utilitzada i expliqueu breument la informació mostrada.

---

## 2. Monitorització amb `vmstat`

Investigueu les diferents opcions disponibles de la comanda:

```bash
vmstat
```

Realitzeu alguna captura en què es pugui observar detalladament:

* L'ús de la memòria física.
* L'ús de la memòria virtual.

Expliqueu breument la informació mostrada.

---

## 3. Espai disponible amb `duf`

Utilitzeu l'eina:

```bash
duf
```

per determinar:

* L'espai de disc utilitzat.
* L'espai de disc disponible.
* Els diferents sistemes d'arxius muntats al sistema.

Documenteu el resultat.

---

## 4. Informació del maquinari

Mostreu la relació del **maquinari del sistema**.

Documenteu l'eina o comanda utilitzada i la informació obtinguda sobre els principals components del servidor.

---

## 5. Registre dels inicis de sessió

Inicieu sessió amb els usuaris creats anteriorment.

Posteriorment, mostreu els registres dels inicis de sessió:

* Des del terminal.
* Utilitzant Webmin.

Documenteu els resultats obtinguts.

---

## 6. Informació dels darrers reinicis i apagades

Mostreu la informació corresponent als darrers:

* Reinicis del sistema.
* Apagades del sistema.

Documenteu les comandes utilitzades i la informació mostrada.

---

# Documentació

Per a cada apartat de l'activitat, la documentació hauria d'incloure, sempre que sigui necessari:

1. **L'objectiu de l'acció.**
2. **La comanda o configuració utilitzada.**
3. **Una explicació del funcionament.**
4. **Una captura de pantalla del resultat.**
5. **Una breu conclusió o comprovació**, quan sigui necessari.

> ## 📚 Recordeu
>
> **«Documentar, documentar i documentar.»**
>
> Una bona documentació permet reproduir una instal·lació, detectar errors i facilitar les tasques de manteniment posteriors.
