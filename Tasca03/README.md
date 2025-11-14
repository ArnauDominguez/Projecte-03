# T03: Gestió flexible de discos (LVM i Espais d’emmagatzematge)

Un cop superada la fase de formació, ja esteu preparats per afrontar el repte dels nostres clients. Com ja es va explicar, tenim un nou i important client: **el bufet d’advocats Garriga i Associats**, un dels més prestigiosos de la ciutat, que ha requerit els serveis de la nostra consultora. Gestiona una gran quantitat d'informació legal sensible, per la qual cosa la integritat, la disponibilitat (alta redundància) i la facilitat de gestió del seu emmagatzematge són d'importància crítica.

La direcció de *Garriga i Associats* ha expressat la necessitat urgent de renovar els sistemes de servidors per garantir que la informació estigui protegida contra fallades de disc i que l'espai pugui ser ampliat sense interrupcions.

Com a tècnics d'Everpia, teniu l'encàrrec de dissenyar i documentar les solucions d'emmagatzematge que compliran aquests requisits tant en entorns Linux com Windows. Aquest disseny permetrà presentar al client una proposta de solució.

L'objectiu principal és dissenyar i documentar **dues solucions d'emmagatzematge** (una per servidors Linux i una per servidors Windows) que compleixin els principis d'alta disponibilitat, redundància i escalabilitat. Com que ha de ser una prova de concepte, s’utilitzaran màquines virtuals en lloc de servidors reals.

---

## 1. Part Linux: LVM amb Zorin OS

S'ha d'utilitzar la distribució **Zorin OS** (o una alternativa Linux compatible) per demostrar la utilitat del **Logical Volume Manager (LVM)**.

### Requisits de la Implementació i Demostració

#### **1. Configuració Inicial**
- Crear un **grup de volums (VG)** i un **volum lògic (LV)** utilitzant inicialment **dos discs de 10 GB**.
- Formatar i muntar el volum.
- Fer que el muntatge sigui automàtic mitjançant l’arxiu `/etc/fstab`.

#### **2. Alta Disponibilitat**
- Implementar un **mirall (lvm_mirror)** per protegir la informació davant la fallada d'un disc.

#### **3. Instantànies (snapshots)**
1. Afegir **dos discos de 10 GB** al grup de volums.
2. Crear un volum **lvm_dades** amb el primer disc, formatar-lo i muntar-lo.
3. Afegir arxius al volum (per exemple, imatges).
4. Amb el segon disc afegit, crear un **snapshot (lv_snapshot)**.
5. Documentar com **restaurar** el snapshot en cas que el volum original es danyi.

#### **4. Escalabilitat**
- Utilitzar l'espai disponible al grup de volums per **ampliar el volum `lv_dades`**.

---

## 2. Part Windows: Espais d'Emmagatzematge (Storage Spaces)

S'ha d'utilitzar **Windows 11** per demostrar les configuracions possibles amb **Storage Spaces**.

### Requisits de la Implementació i Demostració

#### **1. Configuració Inicial**
- Crear un **Storage Pool** amb **tres discos de 10 GB**.

#### **2. Estudi de Configuracions**
Documentar la creació de diferents tipus de resiliència:

- **Mirroring (2 discos)**  
  Proporciona alta disponibilitat.
  
- **Parity (3 discos)**  
  Explicar la seva eficiència d'espai comparada amb el mirall.

- **Triple Mirror**  
  Afegir els discos de 10 GB necessaris.

#### **3. Demostració de Gestió**
- Mostrar l'estat dels discos i del pool des de la consola de gestió de Windows.
- Simular la facilitat de manteniment d’aquest sistema.

---

## Com treballareu i què lliurareu?

- El treball és en grup.
- Us dividireu en dos equips:
  - Equip Linux → LVM
  - Equip Windows → Storage Spaces
- Individualment:
  - Preparareu el **guió de la tasca**, cercareu comandes, documentació, etc.
- En parelles:
  - Realitzareu la demostració assignada.
- En grup:
  - Revisareu la documentació i **cada membre la pujarà al seu repositori**.

La documentació s’ha de guardar en format **Markdown** dins una carpeta:


