Una utility 100% rinnovabile può comunque essere schiacciata dagli shock. 


# Tesi concettuale

> “se anche le rinnovabili non bastano, allora **da cosa dipende davvero la resilienza ai shock energetici?**”  

> “le rinnovabili riducono il rischio SOLO se accompagnate da strumenti di mercato (hedging, PPA, ecc.)”

> “Analisi driver della resilienza ai shock nei mercati elettrici, mostrando che la stabilità non dipende solo dal mix energetico ma anche dalla struttura di copertura e contrattualizzazione dell’energia”

La volatilità non proviene solo dal mix energetico, ma anche da:

1. **Prezzo di mercato (TTF, PUN, ecc.)**
2. **Struttura del mercato (hedging, contratti, PPA)**
3. **Esposizione finanziaria (come sei coperto)**

**Domanda di ricerca**:  
* Le rinnovabili riducono il rischio di prezzo, o la resilienza ai shock dipende principalmente dalla struttura di copertura finanziaria e contrattuale?  
* Perché le utility rinnovabili sono ancora esposte alla volatilità dei mercati energetici?

---

# Analisi del RISCHIO

## Leve di riduzione della volatilità (business-grade)

### 1. Hedging finanziario (FONDAMENTALE)
<!--
![Image](https://images.openai.com/static-rsc-4/1WuppMWM3wWJ-x8eLTpSs_-XovKNlF4WU4E32AjD1nB4jPrIcUaaRBxLnDQjTzk6_qEXGc0odatvxaNwXqrODMAfny3vOJfY14U99_K5YNuXEa-U3aKPUvrKkejzcI937Zx1RZeoGCfr3koQR85j-5_xyq7t4LVn0VEkRpE6sRKZ91I5a0w-4Ky_m2dcegWM?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/nSUHDEq9AMRuePwxso-ZUZafR_Rrw4RBbvKmtqmQaWG1iwrSosNegj4fa53AJvEWSRSXcAuYYWfF1f1HunsCrFhLdEx-D-PLGVJfSyqpLcMhZabkFnoJdml0UrOPOVIIjpDfLttyxXTNiDwkiC_mS_Jkgucgn0RU9l8vo9531CT8zjFHA2nH2AJB0B4zSVNq?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/p7a98DWmju72IqpNP2EriHZzGClTDap3F_2H574GA5pnxeRFOcF1UmO-eqlZh8Y0VZsnTXPo4IcxsF2DwnCo0fqZRDTRNGSUCgbhyj6pl406BLM1wYcgybzJ1NwED8ClFU4YV3NJ450E1BBdcesngbkxum2jM9VXPm6Emxoft6v0cr4WlELIh5nxRBH49A8A?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/sFCNiyutanMvllMBwtsqPiUGcGZWNvy0X4q8VIzxAwtXZwKW42Mosa29sVKRW_dgr1IcbAVzEd2j_3fXsj5RkZwsNdut2Y8iFy6LCFNLx8-66J5qQYHd21OD6kkQ1cwEiWV5clszOBdfQ5tVv6HrErTjxebVmhaeYV7bJ18DuT_UShGAdkN134zL9Hbbx8ww?purpose=fullsize)
-->

* futures
* forward
* PPA

### 2. Contratti PPA (qui c’è oro per la tua tesi)
<!--
![Image](https://images.openai.com/static-rsc-4/v70wwXTn_mLJMMATQLds3ZVkqOpV7WJxc8_qmb7aK_4kBTON3tTo458RwzUFG9SmK6vNVmK44_umSI-rkC9HyhCNBjdhdg4CaPsVq2OZ-rZkzTxrwDNVSg716IjiNKTW4UmM9ru9psqaZFGNhNCLeaEbd3gljMlHhvbb5jcAEhJn8nnDOF6FZm-YEM_Gyjfd?purpose=fullsize)
-->

* bloccano il prezzo
* eliminano volatilità

Insight:
> la stabilità non viene dal “green”, ma dal “contratto”

### 3. Diversificazione e portfolio energetico
<!--
![Image](https://images.openai.com/static-rsc-4/9zWMuuWhXQaz7QEwVL9uVoA3HwUwOIdE-XplQ9T2TVUbwlhBpAr5c5J01-Ndqt1WGbnR0t1iGHLDVnfBB-BhQ-jFNGovZSf6x0GOL2aik6S5Mx95hh4gJA-eRWGv4KopANlkRdwAh8jiDrxsqjJMOnHb4Z7z27upcOAWkPO6Oucp_5frWKcgq-rkIV3_pCYR?purpose=fullsize)
-->

* solo solare = instabile
* mix + storage = stabile

## Framework e modello conettuale
Non:
>Prezzo elettrico = f(GAS)

Ma:

> Risk = f(Renewables, Hedging, Contracts, Market_Shocks)

rischio elettrico = funzione di:
* mercato
* contratti
* struttura energetica

##  Versione econometrica realistica

Vol_{PUN,t} = \beta_0 + \beta_1 Renewable_t + \beta_2 TTF_t + \beta_3 Hedging_t + \beta_4 (Renewable_t \times Hedging_t) + \epsilon_t


# 1. Le variabili 

## Volatilità PUN (Y)
Vol_{PUN,t} = \text{RollingStd}(PUN_t, k)
* dati PUN orari/giornalieri
* rolling window (7, 14 o 30 giorni)

## TTF (X1)
* prezzo gas europeo
* dataset pubblico (ICE / EEX / aggregatori energia)

## Renewable (X2)
* <code>% produzione rinnovabile sul totale</code>

    oppure:

* wind + solar generation (più granulare ma più sporco)

## Hedging (X3)

### STRATEGIA A - Proxy aziendale (più realistica)

Hedging = PPA coverage ratio

* % energia venduta tramite contratti a lungo termine (PPA)  
    oppure 
* proxy semplificato:
    * dummy “pre vs post contratto PPA”
    * oppure “azienda ha hedging policy: sì/no”

### STRATEGIA B - Proxy di mercato (più econometrica)

Hedging = volatilità implicita del mercato o indicatori  
perché più il mercato è volatile, meno è efficace l'hedging

* spread forward vs spot
* volatilità TTF o PUN stesso
* VIX-like energetico (esiste?)

### STRATEGIA C - Dummy strutturale
```
Hedging_t = 1 se periodo post-implementazione strategia PPA
           0 altrimenti

```
(per regressioni con interazione)


# Regressione 
Vol_{PUN,t} = \beta_0 + \beta_1 TTF_t + \beta_2 Renewable_t + \beta_3 Hedging_t + \beta_4 (Renewable_t \times Hedging_t) + \epsilon_t

## Interpretazione 
* **β1** → shock gas aumenta volatilità
* **β2** → rinnovabili riducono volatilità (forse)
* **β3** → hedging riduce volatilità (atteso negativo)
* **β4** → interazione  

Se β4 < 0   hedging + rinnovabili = sistema super stabile  
Se β4 = 0   hedging domina, rinnovabili marginali  
Se β4 > 0   interazione complessa

# Limite
L'hedging non riduce volatilità direttamente

* hedging riduce **esposizione aziendale**
* non sempre **prezzo di mercato**

---
> “la stabilità energetica non dipende solo dalla generazione, ma dalla struttura contrattuale del mercato”

---
Hedging è **proxy + interpretazione economica intelligente**
