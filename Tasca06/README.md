# 🧠 Auditoria del Servei DNS — Consultora EverPia

## Context
Com a membres cada cop més integrats de l’equip tècnic de la consultora **EverPia**, teniu davant un nou repte.  
El vostre client, una empresa de màrqueting digital (**DigiCore**), experimenta de tant en tant errors de connectivitat a certes aplicacions.  
El seu equip tècnic creu que la causa principal podria ser una **resolució de noms (DNS)** incorrecta o lenta.

Se us ha encarregat **realitzar una auditoria teòrica i pràctica del servei DNS** per formar el personal del client i oferir **eines de diagnosi ràpides**.

---

## 🧩 Fase Teòrica: Sessió Formativa

Com a part d’aquesta formació, cal elaborar un **material formatiu** pel personal del client.  
Per assegurar la màxima qualitat en els continguts, els directors tècnics han preparat unes sessions prèvies per dominar els conceptes que després haureu d’explicar.

### 📘 Conceptes a explicar

1. **Jerarquia i Estructura**  
   - Explicació de l'estructura en arbre del DNS  
   - (Root > TLDs > Segon Nivell)

2. **Procés de Resolució**  
   - Consulta iterativa i recursiva  
   - Què és un servidor d’arrel (*Root Server*)  
   - Què és un servidor autoritatiu

3. **Tipus de Zones**  
   - Zona directa i inversa  
   - Zona primària i secundària

4. **Tipus de Registres Clau (Records)**  
   - A, CNAME, MX, NS i SRV

5. **Conceptes Essencials**
   - **Resposta Autoritativa:** què significa i com identificar-la  
   - **TTL (Time To Live):** funció i impacte en la propagació i rendiment  
   - **SOA (Start of Authority):** informació essencial i importància

6. **Reenviadors**
   - Condicionals i incondicionals

7. **Resolució Local**
   - Mecanismes de resolució sense servidor entre equips clients  
   - Protocol **mDNS**

---

### 🎥 Activitat de la Fase Teòrica
Un cop domineu aquests conceptes, caldrà preparar una **píndola formativa en vídeo** (durada entre **10 i 15 minuts**) que expliqui de forma breu però clara aquests conceptes.

---

## 🧰 Fase Pràctica: Diagnosi de Noms (Auditoria amb CLI)

Heu de demostrar l'ús de les principals **utilitats de diagnosi DNS** en diferents sistemes operatius utilitzats pel client (**Linux/macOS i Windows**).

Per a cada eina, executeu les comandes indicades a continuació contra el domini especificat i **captureu i analitzeu els resultats**.

🖥️ Per fer aquesta demostració, caldrà utilitzar un equip **Zorin** amb dues interfícies:
- La primera en **NAT**
- La segona en **adaptador pont**, amb la IP correctament configurada segons les indicacions dels responsables.

---

### 🔍 A. Diagnosi Avançada amb `dig` (Linux / macOS)

#### **Comanda 1: Consulta Bàsica de Registre A**
dig xtec.cat A

**Anàlisi:**  
Identifica la IP de resposta, el valor **TTL** i el servidor que ha respost a la consulta.

---

#### **Comanda 2: Consulta de Servidors de Noms (NS)**
dig tecnocampus.cat NS

**Anàlisi:**  
Quins són els servidors de noms autoritatius per a aquest domini?

---

#### **Comanda 3: Consulta Detallada SOA**
dig escolapia.cat SOA

**Anàlisi:**  
Quina és la informació del correu de l'administrador i el número de sèrie del domini?

---

#### **Comanda 4: Consulta de Resolució Inversa**
dig -x 147.83.2.135

**Anàlisi:**  
Quina informació sobre els registres s’obté?

---

### 💡 Comprovació de Resolució amb `nslookup` (Multiplataforma)

L’eina `nslookup` està disponible en pràcticament qualsevol sistema operatiu.  
Es pot usar de forma similar a `dig` o en **mode interactiu**, que mostra un *prompt* (`>`).

---

### 🧾 Comandes principals en mode interactiu

- `set type=` → per indicar el tipus de consulta: A, AAAA, MX, NS, SOA, TXT o ALL  
- `server IP` → per indicar el servidor DNS que es vol utilitzar (es pot posar també el nom)  
- `exit` → per sortir de la comanda  

---

#### **Comanda 1: Consulta Bàsica no Autoritativa**
set type=A
tecnocampus.cat

**Anàlisi:**  
Per què indica que la resposta és **no autoritativa**?

---

#### **Comanda 2: Consultes Autoritatives**
server IP del primer servidor de noms del domini tecnocampus.cat
set type=A
tecnocampus.cat

**Anàlisi:**  
Quines diferències s’observen respecte a la resposta de la Comanda 1?

---

## 🌐 Resolucions Locals

Finalment, es vol comprovar el funcionament de la **resolució local**, útil per a entorns on **no es disposa d’un servidor DNS propi** i que evita haver d’accedir als equips o recursos per la seva IP.

---

### 🧩 Activitat de la Fase Pràctica
Crea un fitxer **`guia.md`** que inclogui:

- Les **captures de pantalla** de les 6 comandes anteriors  
- Les **explicacions i anàlisis** corresponents  
- Les **proves de resolució local**

---

📄 **Resultat final esperat:**  
Un document complet amb **totes les proves, captures i anàlisis**, servint com a guia formativa i tècnica per al personal de **DigiCore**.

[Solucio](Solucio.md)

[Tornar pàgina projecte](../README.md)
