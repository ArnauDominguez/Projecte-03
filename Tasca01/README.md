# 🛑 Alerta de Seguretat: EverPia sota atac

**Alerta!!**  
EverPia ha estat atacada per ciberdelinqüents. La consultora on esteu de becaris ha patit una **fuita d’informació (data breach)**, i informació confidencial sobre un projecte en desenvolupament està ara en mans de delinqüents que amenacen amb publicar-la si no es paga un rescat.

Aquesta situació ha causat **una gran alarma dins la companyia**, i s’ha creat un **comitè de crisi** per gestionar-la.  
La investigació interna ha revelat que **un dels comptes tècnics va ser compromès a causa de l'ús d'una contrasenya feble o reutilitzada.**

---

## 🎯 Objectiu

Com a resposta a aquesta crisi, la **Direcció Tècnica** ha emès una directriu:

> Tot el personal tècnic ha de començar a utilitzar un **gestor de contrasenyes validat** per garantir l'ús de credencials úniques i robustes.

Se us encarrega la tasca d’**avaluar les opcions i crear la documentació necessària per a la formació del personal.**

---

## 🧩 Fase 1: Anàlisi i Justificació (Document d'Informe)

Heu de redactar un **informe tècnic** que justifiqui la decisió de la Direcció i compari les opcions disponibles.

### Contingut de l'informe

#### 🔹 Introducció i Justificació
- Explicació de **per què les contrasenyes febles o reutilitzades** són un risc crític per a l'empresa (atacs de diccionari, *credential stuffing*, etc.).  
- La **funció crucial d’un gestor de contrasenyes** per mitigar aquests riscos.

#### 🔹 Comparativa Tècnica
Realitzeu una **taula comparativa** entre dues opcions:

| Eina | Tipus | Característiques principals |
|------|--------|-----------------------------|
| **Bitwarden** | Online / Núvol | Sincronització entre dispositius, xifratge *end-to-end*, model freemium, accés multiplataforma. |
| **KeePassX / KeePassXC** | Offline / Escriptori | Emmagatzematge local (fitxer `.kdbx`), independència del núvol, codi obert (*open source*), portabilitat. |

#### 🔹 Avantatges i Inconvenients
Resumiu els **pros i contres** de cada model (*online vs. offline*) des del punt de vista de:
- Seguretat  
- Usabilitat  
- Continuïtat del negoci  

#### 🔹 Recomanació
Concloeu l’informe **escollint l’eina més adequada** per al personal tècnic de l’empresa i **justifiqueu la vostra elecció.**

---

## 🧠 Fase 2: Guia d’Ús Tècnica (Manual Operatiu)

Utilitzant l’eina seleccionada a la Fase 1 (*Bitwarden*, *KeePassX*, o similar*), creeu una **Guia d’Ús per a l’Equip Tècnic**.

### Contingut de la guia

#### 🔹 Instal·lació i Configuració Inicial
- Descàrrega, instal·lació i creació de la base de dades principal o compte mestre.

#### 🔹 Generació de Contrasenyes Segures
- Ús del **generador de contrasenyes** de l’eina: paràmetres, longitud i caràcters especials.

#### 🔹 Exemples d’Ús i Emplenament Automàtic
- Desar credencials d’un **compte de correu electrònic.**  
- Desar credencials d’una **aplicació o servei web.**  
- Utilitzar l’**extensió del navegador** per emplenar automàticament les dades.

#### 🔹 Gestió de Còpies de Seguretat (Backup)
- Explicació detallada de **com fer una còpia de seguretat** de l’arxiu de contrasenyes:
  - `.kdbx` en *KeePass*  
  - Exportació en *Bitwarden*  
- Recomanació de la **millor pràctica per guardar la còpia de seguretat** de manera segura:
  - Clau USB xifrada  
  - Emmagatzematge xifrat al núvol  

---

- [Informe](informe.md)
- [Guia d'ús](guia.md)

[Tornar pàgina projecte](../README.md)


