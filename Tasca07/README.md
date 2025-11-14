# T07: Instal·lant un servidor de noms

Després de l’exitosa experiència a nivell de formació, els nostres clients de Digicore estan tan satisfets amb la nostra feina que ens encarreguen la implantació des de zero dels seus serveis de DNS interns.  
Actualment, l'agència fa servir adreces IP per accedir als seus servidors de desenvolupament, bases de dades i eines de gestió interna. Aquest mètode és ineficient i propens a errors:

- **Usabilitat deficient:** Els empleats han de memoritzar o buscar constantment adreces IP complexes (p. ex., `192.168.10.25`).
- **Manteniment feixuc:** Si un servidor canvia la seva IP, cal actualitzar manualment la configuració a tots els equips i aplicacions.
- **Manca de professionalitat:** En un entorn professional, tots els serveis haurien d’estar accessibles amb noms fàcils de recordar.

Per tant, la nostra missió és implementar un **Sistema de Noms de Domini (DNS) intern robust**, perquè els serveis de l’empresa siguin accessibles amb noms amigables (p. ex., `bbdd.digicore.lan` o `wiki.digicore.lan`).

---

## 🎯 El vostre repte

La recomanació és utilitzar **BIND9**, l'estàndard de facto en servidors DNS a Linux per la seva fiabilitat i flexibilitat.

La vostra missió serà:

- Instal·lar i configurar un **servidor DNS primari (màster)** amb BIND9 en Linux.
- Crear una **Zona Directa (Forward Zone)** i una **Zona Inversa (Reverse Zone)** per al domini privat.
- Treballar amb el domini **`digicore-XX.test`**, on `XX` és el vostre número de llista.

---

## 🖥️ Pas previ: Preparació del servidor

Configurar una màquina virtual **Ubuntu Server** amb:
- 4 GB de RAM  
- 20 GB de disc  
- Una interfície *adaptador pont* (configurada segons indicacions)
- Una interfície *host-only*  
- Instal·lar `bind9` i `ssh` per poder exportar els arxius al vostre GitHub.

---

## 🔧 Accions a realitzar

### 1. Configurar `named.conf.options`
- Permetre consultes recursives des de la xarxa local.
- Afegir com a reenviador: `8.8.8.8`.
- Mostrar captura.
- Reiniciar el servei i mostrar l’estat.

---

### 2. Comprovació amb un client
- Utilitzar Zorin com a client amb *adaptador pont*.
- El DNS del client ha de ser la IP del servidor.
- Comprovar resolució a Internet (`dig google.com` o navegador).

---

### 3. Definir zones a `named.conf.local`
Afegir:
- **Zona directa:** `digicore-XX.test`
- **Zona inversa:** xarxa local especificada al repte.

---

### 4. Crear la Zona Directa
Crear carpeta `/etc/bind/zones` i copiar `db.local`.

Configurar:
- **SOA** correctament
- **NS** apuntant al servidor
- Registre **A** `server` → IP del servidor
- Registre **A** `dbserver` → IP del client
- Registre **CNAME** `data` → `dbserver`

---

### 5. Crear la Zona Inversa
Crear arxiu a `/etc/bind/zones` copiant `db.127`.

Configurar:
- **SOA** i **NS**
- Registres **PTR** per `server` i `dbserver`

---

### 6. Reiniciar i fer comprovacions
Des del client:
- Consultes directes (`dig server.digicore-XX.test`)
- Consultes inverses (`dig -x IP`)

---

### 7. Permetre transferència de zona
A `named.conf.local`, afegir permisos perquè els companys puguin rebre la zona directa.

---

### 8. Configurar una Zona Secundària
- Rebre i configurar una zona secundària d’un company.
- Forçar la transferència.
- Comprovar funcionament des del client.

---

## 📝 Activitat d’avaluació final
Al final passareu una **avaluació pràctica**, on només podreu utilitzar **un full manuscrit** amb anotacions pròpies, que es lliurarà al final.

```markdown

[Solucio](Solucio.md)

[Tornar pàgina projecte](../README.md)
