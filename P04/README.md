# P04: Documentació servidor DNS

Benvinguts, consultors!

Com a membres de l'equip de sistemes d'EverPia, heu configurat un servidor DNS com a prova de concepte per al client **Digicore**. Actualment, totes les configuracions es troben dins la vostra màquina virtual Ubuntu Server.

L’objectiu d’aquesta tasca és **publicar aquestes configuracions a GitHub**, per tal que en un futur es pugui replicar el servidor simplement descarregant els arxius i reiniciant el servei, sense necessitat de reconfigurar-ho tot manualment.

---

## **Fase 1: Preparació de la Connectivitat i Extracció dels Arxius**

### **Pas 1.1: Configuració de la Interfície Host-Only**

1. A la configuració de la vostra màquina virtual Ubuntu Server:
   - Afegiu una **segona interfície de xarxa**.
   - Assigneu-li el mode **Host-Only**.
2. Configureu-la i activeu-la dins Ubuntu.
3. Comproveu que hi ha connectivitat entre la màquina física (host) i la màquina virtual (VM).

---

### **Pas 1.2: Còpia Segura dels Fitxers Clau amb SCP**

Un cop teniu connectivitat, utilitzareu **SCP (Secure Copy Protocol)**, inclòs a SSH, per copiar els fitxers al vostre PC.

Els fitxers que heu de copiar són:

- `/etc/bind/named.conf.options`
- `/etc/bind/named.conf.local`
- Tots els arxius de zones ubicats a:  
  `/etc/bind/zones`

**Exemple de comanda SCP (executada des del PC físic):**

scp usuari@IP_de_la_VM:/etc/bind/named.conf.options .

El **punt (.)** final indica que els arxius es copiaran al directori actual del PC.

---

## **Fase 2: Integració a GitHub**

### **Pas 2.1: Crear carpeta i README.md**

1. Al vostre repositori de GitHub, creeu la carpeta:

producte04/

2. Creeu l’arxiu:

producte04/README.md

3. Dins el README.md heu d’incloure:
   - Títol del producte.
   - Explicació del contingut.
   - Informació breu sobre la configuració o estructura dels arxius.

---

### **Pas 2.2: Pujar els arxius**

1. Pugeu els fitxers del servidor DNS.
2. Creeu la carpeta:

producte04/zones/

3. Si GitHub no us deixa crear una carpeta buida, utilitzeu el truc:
   - Crear un fitxer temporal:  
     `producte04/zones/esborrar`
   - Pujar els arxius de zona.
   - Esborrar el fitxer `esborrar`.

---

Els arxius quedaran organitzats així:

producte04/
├── README.md
├── named.conf.options
├── named.conf.local
└── zones/
├── zona_forward.db
├── zona_reverse.db
└── ...

Això garantirà una estructura clara i fàcil de replicar en qualsevol servidor Linux que utilitzi **Bind9**.


[Arxiu named.conf.local](named.conf.local)

[Arxiu named.conf.options](named.conf.options)

[Arxiu de zones](zones)

[Tornar pàgina projecte](../README.md)
