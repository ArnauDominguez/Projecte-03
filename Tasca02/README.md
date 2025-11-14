# T02: Gestió emmagatzematge

La informació és un dels béns més valuosos per a qualsevol organització. A **EverPia** ens esforcem perquè els nostres clients tinguin la seguretat que les seves dades estan protegides i segures. Per aquest motiu, i dins de la vostra formació al departament de seguretat informàtica, rebreu una **formació bàsica** sobre la gestió d’emmagatzematge per poder afrontar els reptes que els nostres clients ens proposen.

Un bufet d'advocats amb dades altament sensibles ens ha contractat per revisar i optimitzar el seu sistema d'emmagatzematge de dades, ja que l'actual és vulnerable a fallades i pèrdua d'informació.

Abans d'accedir a les seves instal·lacions i dissenyar la solució física, necessitem garantir que tot l'equip tècnic tingui un **domini absolut dels fonaments teòrics** de la gestió d'emmagatzematge des de la perspectiva de la seguretat i la protecció de la informació.

Per aquest motiu, rebreu una formació sobre els pilars de la **gestió segura de l’emmagatzematge**, per garantir que la informació dels nostres clients estigui sempre **disponible, íntegra i protegida**. Així que toca estar atent i no perdre’s cap detall de les explicacions.

---

## Àrees d'estudi

### 1. Gestió de la informació de forma segura
- Principis bàsics: **Confidencialitat**, **Integritat** i **Disponibilitat** (CIA).
- Polítiques d'accés i control: autenticació, autorització i registre d'activitat.
- Còpies de seguretat i estratègies de recuperació davant desastres.
- Xifrat d'emmagatzematge (at-rest) i xifrat en trànsit (in-transit).

### 2. Tecnologies de Redundància (RAID)
- Què és RAID i per què s'utilitza.
- **Nivells clau**:
  - **RAID 0** — striping: millora rendiment, **sense redundància**.
  - **RAID 1** — mirroring: duplicació per alta disponibilitat.
  - **RAID 5** — striping amb paritat: equilibri espai/seguretat.
  - **RAID 6** — striping amb doble paritat: tolerància a dues fallades.
  - **RAID 10 (1+0)** — combinació mirror + stripe: alt rendiment i redundància.
- Consideracions pràctiques: temps de reconstrucció, degradació de rendiment i impacte en la seguretat de les dades.

### 3. Models d’emmagatzematge
Descripció, característiques, avantatges i desavantatges dels principals models en xarxa:

- **DAS (Direct Attached Storage)**  
  - Connexió directa a un servidor.  
  - Avantatges: senzillesa, baix cost i alt rendiment local.  
  - Desavantatges: escalabilitat limitada i gestió compartida deficitària.

- **NAS (Network Attached Storage)**  
  - Emmagatzematge accessible per la xarxa (nivell fitxer).  
  - Avantatges: fàcil compartició de fitxers i gestió centralitzada.  
  - Desavantatges: dependència de la xarxa; pot esdevenir coll d’ampolla.

- **SAN (Storage Area Network)**  
  - Xarxa d'emmagatzematge a nivell bloc (Fibre Channel o iSCSI).  
  - Avantatges: alt rendiment i escalabilitat per aplicacions crítiques.  
  - Desavantatges: cost elevat i complexitat d'administració.

- **Avaluació comparativa**  
  - Analitzar rendiment vs cost vs seguretat.  
  - Recomanacions segons cas d'ús (petita oficina vs entorn crític).

---

## Avaluació final

Un cop finalitzada la formació, hauràs de respondre un **qüestionari** per avaluar el teu grau d’assoliment. **Supera’l — el teu progrés dins d’EverPia en depèn!**

[Solucio](Solucio.md)

[Tornar pàgina projecte](../README.md)
