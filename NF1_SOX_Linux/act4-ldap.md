# Plec de Condicions Tècniques (PCT)

## Projecte: Implementació del Servei de Directori LDAP per a l'Entorn de Proves Innovatech

| **Dada**                           | **Informació**       |
| ---------------------------------- | -------------------- |
| **Client (Beneficiari)**           | Innovatech (Startup) |
| **Proveïdor (Consultora Tècnica)** | EverPia              |
| **Data de publicació**             | 17 d'octubre de 2026 |

---

## 1. Objecte de l'encàrrec

L'objecte del present **Plec de Condicions Tècniques (PCT)** és la instal·lació, configuració i validació d'un servei **OpenLDAP** en un entorn virtualitzat basat en **Ubuntu Server**.

Aquest servei s'ha de configurar per actuar com a **directori centralitzat d'usuaris i grups** per al domini de proves:

```text
innovatechXX.test
```

> **Nota:** Substituïu `XX` pel número de llista corresponent abans d'iniciar la implementació.

---

# 2. Requeriments d'infraestructura inicial

El consultor ha de verificar la correcta configuració de la infraestructura virtual abans d'iniciar la implementació.

| **ID**       | **Descripció del requeriment**                           | **Configuració requerida**                                                                    |
| ------------ | -------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **R.INF.01** | Configuració de la màquina servidor (*Server Hostname*). | `server.innovatechXX.test`                                                                    |
| **R.INF.02** | Interfície de xarxa pública.                             | **NAT**, per disposar d'accés a Internet i poder descarregar paquets.                         |
| **R.INF.03** | Interfície de xarxa privada.                             | **Host-Only**, per permetre la comunicació privada amb el client virtual i la màquina física. |

---

# 3. Tasques d'implementació i configuració del servidor LDAP

La consultora **EverPia** ha de complir estrictament les tasques següents d'instal·lació i configuració.

## 3.1. Instal·lació i configuració base d'OpenLDAP

| **ID**        | **Descripció de la tasca**                           | **Detalls de la configuració**                                                         |
| ------------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------- |
| **T.LDAP.01** | Instal·lació del servei OpenLDAP.                    | S'ha de mostrar el resultat de la comanda `slapcat` per validar la instal·lació base.  |
| **T.LDAP.02** | Configuració de la base de dades.                    | **Nom del domini:** `innovatechXX.test`                                                |
| **T.LDAP.03** | Configuració de la contrasenya d'administrador.      | **Contrasenya:** `p@ssw0rd`                                                            |
| **T.LDAP.04** | Creació de les Unitats Organitzatives (OU) inicials. | S'han de crear dues OUs: `users` i `groups`, mitjançant un fitxer `.ldif`.             |
| **T.LDAP.05** | Validació de les Unitats Organitzatives.             | Realitzeu una consulta amb `ldapsearch` que mostri totes les OUs creades al directori. |

---

## 3.2. Gestió i administració amb LAM

| **ID**       | **Descripció de la tasca**                    | **Detalls de la configuració**                                                                                |
| ------------ | --------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **T.LAM.01** | Instal·lació del gestor d'usuaris LDAP (LAM). | S'ha de documentar la comanda d'instal·lació utilitzada.                                                      |
| **T.LAM.02** | Accés remot i configuració.                   | Connecteu-vos a LAM des de la màquina física utilitzant l'adreça IP de la interfície **Host-Only**.           |
| **T.LAM.03** | Configuració per defecte.                     | Configureu LAM perquè els nous usuaris s'ubiquin per defecte a l'OU `users` i els nous grups a l'OU `groups`. |
| **T.LAM.04** | Creació de grups.                             | Creeu dos grups de seguretat al directori: `tech` i `manager`.                                                |
| **T.LAM.05** | Creació d'usuaris de prova.                   | Creeu un usuari per a cada grup: `tech01`, membre de `tech`, i `manager01`, membre de `manager`.              |

---

# 4. Integració del client Ubuntu Desktop

| **ID**       | **Descripció de la tasca**          | **Detalls de la configuració**                                                                                                                                                                                              |
| ------------ | ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **T.CLI.01** | Instal·lació del client.            | Instal·leu un client **Ubuntu Desktop** i configureu la interfície de xarxa perquè es pugui comunicar amb el servidor mitjançant la xarxa **Host-Only**.                                                                    |
| **T.CLI.02** | Resolució de noms.                  | Configureu l'arxiu `/etc/hosts` del client perquè resolgui l'adreça IP del servidor com a `server.innovatechXX.test`. Cal proporcionar una **instantània (*snapshot*)** de la màquina client un cop realitzat aquest canvi. |
| **T.CLI.03** | Validació de la connectivitat LDAP. | Comproveu la connectivitat amb el servidor realitzant una consulta `ldapsearch` des del client.                                                                                                                             |
| **T.CLI.04** | Mòduls d'autenticació.              | Instal·leu els mòduls necessaris per permetre l'autenticació dels usuaris mitjançant LDAP.                                                                                                                                  |
| **T.CLI.05** | Configuració del client.            | Modifiqueu els arxius de configuració necessaris del client. S'han de mostrar **clarament els canvis realitzats** en el contingut dels arxius.                                                                              |
| **T.CLI.06** | Comprovació del sistema.            | Reinicieu els serveis necessaris i verifiqueu, mitjançant la comanda `getent passwd`, que els usuaris del directori LDAP són visibles localment.                                                                            |
| **T.CLI.07** | Prova d'accés final.                | Reinicieu el client i inicieu sessió amb l'usuari `tech01`. Cal aportar una captura de pantalla que demostri l'accés correcte i la **creació automàtica de la carpeta personal** de l'usuari.                               |

---

# 5. Validació final

Abans de donar per finalitzat el projecte, cal verificar que:

* [ ] El servidor OpenLDAP està instal·lat i funcionant correctament.
* [ ] El domini LDAP és `innovatechXX.test`.
* [ ] Les OUs `users` i `groups` estan creades.
* [ ] LAM està instal·lat i accessible des de la màquina física.
* [ ] Els grups `tech` i `manager` estan creats.
* [ ] Els usuaris `tech01` i `manager01` existeixen i pertanyen als grups corresponents.
* [ ] El client Ubuntu Desktop pot comunicar-se amb el servidor LDAP.
* [ ] El client resol correctament el nom `server.innovatechXX.test`.
* [ ] Els usuaris LDAP són visibles amb `getent passwd`.
* [ ] És possible iniciar sessió amb l'usuari `tech01`.
* [ ] La carpeta personal de l'usuari es crea automàticament en iniciar sessió.

---

# 6. Acceptació del Plec de Condicions Tècniques (PCT)

| **Per Innovatech (Client)** | **Per EverPia (Consultora)** |
| --------------------------- | ---------------------------- |
| **Nom:**                    | **Nom:**                     |
|                             |                              |
| **Signatura:**              | **Signatura:**               |
|                             |                              |
| **Data:**                   | **Data:**                    |
|                             |                              |

---

> ## 📌 Nota important
>
> Abans de començar la configuració, substituïu **`XX` pel número de llista corresponent** en tots els noms de domini i configuracions on aparegui.
>
> Exemple:
>
> ```text
> innovatech05.test
> server.innovatech05.test
> ```
