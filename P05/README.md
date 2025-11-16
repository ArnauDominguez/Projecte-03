# P05: Presentació sistemes emmagatzematge

En el vostre camí per tal d’arribar un dia a ser consultors d'infraestructura sènior, teniu assignada una tasca de màxima prioritat per al nostre client, una empresa de disseny que necessita modernitzar els seus servidors de fitxers.

La vostra missió en aquesta activitat és **preparar i defensar una presentació comparativa exhaustiva** davant el client. L'objectiu és educar la direcció i els tècnics d'aquesta empresa sobre les dues tecnologies líders proposades per a la seva infraestructura de servidors de fitxers:

- **LVM (Logical Volume Manager)**: solució estàndard per a la gestió dinàmica de l'emmagatzematge en entorns **Linux**.  
- **Storage Spaces (Espais d'Emmagatzematge)**: eina nativa de **Microsoft** per a la virtualització d'emmagatzematge en servidors **Windows**.

Aquesta presentació serà l'eina clau per justificar la nostra elecció tecnològica. No només heu d'explicar com funcionen, sinó també posicionar les dues tecnologies segons l'entorn i les necessitats del client.

---

## Contingut que ha d'incloure la presentació

### 1. Introducció
- Context del client (empresa de disseny) i necessitat de modernització.
- Objectiu de la presentació: comparar LVM i Storage Spaces per recomanar la millor opció.

### 2. Característiques principals
**LVM (Linux)**  
- Arquitectura bàsica: Physical Volumes (PV), Volume Groups (VG), Logical Volumes (LV).  
- Funcions clau: redimensionament online, snapshot, striping, mirroring (amb configuracions addicionals).  
- Beneficis: flexibilitat, administració granular, integració amb eines Linux.

**Storage Spaces (Windows)**  
- Arquitectura bàsica: Storage Pool, Virtual Disks, Resiliency (Mirror/Parity).  
- Funcions clau: discos agrupats, formats virtuals, tiers, integració amb Windows Server i Hyper-V.  
- Beneficis: integració nativa, gestió centralitzada amb GUI i PowerShell, opcions de resiliència per a entorns Windows.

### 3. Terminologia equivalent (paral·lelismes)
- **PV (LVM)** ⇄ **Physical disks in Pool (Storage Spaces)**  
- **VG (LVM)** ⇄ **Storage Pool (Storage Spaces)**  
- **LV (LVM)** ⇄ **Virtual Disk / VDisk (Storage Spaces)**  
- **snapshot (LVM)** ⇄ **Checkpoint / Snapshot mechanisms (Windows / ReFS/Storage Spaces integration)**

### 4. Semblances i Diferències
- **Semblances**
  - Ambdós virtualitzen l'emmagatzematge físic i permeten redimensionar i gestionar l'espai lògic.
  - Suport per a configuracions amb redundància (mirrors, paritat, etc.).
- **Diferències**
  - **Escalabilitat:** Storage Spaces tendeix a integrar funcions d'escalat i tiers més enfocades a entorns Windows i infraestructura Microsoft; LVM és extremadament modular i flexible en entorns Linux.
  - **Rendiment:** Depèn de l'implementació (RAID software vs hardware, tipus de paritat). Storage Spaces Parity pot tenir penalització d'escriptura en certs escenaris; LVM amb striping pot oferir millor rendiment seqüencial si està ben configurat.
  - **Cost i ecosistema:** LVM és gratuït i àmpliament suportat en sistemes Linux; Storage Spaces és part de l'ecosistema Microsoft (llicències, integració Windows Server, suport de vendor).
  - **Gestió:** Storage Spaces ofereix GUI (Server Manager, Windows Admin Center) i PowerShell; LVM es gestiona principalment per CLI (pvcreate, vgcreate, lvcreate) i eines gràfiques disponibles addicionals.

### 5. Avantatges per tipus d'entorn
- **Entorn Linux (LVM)**
  - Organitzacions que ja utilitzen Linux/containers.
  - Necessitat d'eines CLI, scripts i integració amb backups Linux.
  - Baix cost i alta flexibilitat.
- **Entorn Windows (Storage Spaces)**
  - Organitzacions amb infraestructura Microsoft (Active Directory, Hyper-V).
  - Necessitat d'administració centralitzada amb interfícies gràfiques.
  - Buena integració amb característiques nadiues (deduplicació, ReFS en funcions específiques).

### 6. Recomanacions pràctiques i criteris de decisió
- Avaluar:
  - **Ecosistema tecnològic existent** (Linux vs Windows).
  - **Requisits de disponibilitat i tolerància a falles.**
  - **Budget i cost de manteniment.**
  - **Necessitats de rendiment** (tipus de càrrega: IOPS vs throughput seqüencial).
  - **Facilitat d'administració** i competències internes.

### 7. Proposta concreta per al client (exemples)
- Opció A — **Total Linux (LVM)**: si el parc de servidors i les aplicacions ja utilitzen Linux (baixa despesa de llicències, alta flexibilitat).
- Opció B — **Total Windows (Storage Spaces)**: si el client treballa principalment amb Windows Server / Hyper-V i vol gestió amb GUI.
- Opció C — **Híbrid**: Servidors de fitxers centrals en Storage Spaces per a flux de treball d'oficina i servidors específics en LVM per a procesos de render/compute sobre Linux.

### 8. Riscos i consideracions
- Temps de reconstrucció després de fallades.
- Impacte en el rendiment durant operacions de manteniment.
- Estratègies de còpia de seguretat i recuperació d’emergència.
- Monitoratge i alertes.

### 9. Conclusions
- Resum de punts forts i febles de cada solució.
- Reiterar la recomanació segons l’anàlisi del client.
- Proposta de següents passos: prova pilot, pla de migració, pressupost estimat.

---

## Suggeriment d'estructura de la presentació (slides)
1. Títol i objectiu
2. Context del client
3. Què són LVM i Storage Spaces (resum)
4. Arquitectura i terminologia (taula comparativa)
5. Funcionalitats clau (LVM)
6. Funcionalitats clau (Storage Spaces)
7. Similituds i diferències (gràfic/taula)
8. Casos d’ús i avantatges per l’entorn del client
9. Riscos i mesures de mitigació
10. Proposta i justificació
11. Pla de migració / prova pilot
12. Pressupost estimat i ROI (opcional)
13. Preguntes i tancament

---

## Consells per l’exposició
- Sigueu tècnics però accessibles: evita l’excés de jerga per la direcció.
- Porteu exemples reals i mesures (benchmarks simples) si és possible.
- Prepareu una demo curta o captures de pantalla de gestió (LVM CLI i Storage Spaces GUI).
- Acabeu amb una recomanació clara i passos següents.
[Solucio](Solucio.md)

[Tornar pàgina projecte](../README.md)
