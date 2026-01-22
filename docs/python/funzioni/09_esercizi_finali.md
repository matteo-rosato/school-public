# Esercizi finali


## 🎯 Obiettivi di apprendimento
- consolidare l’uso delle funzioni in problemi realistici
- applicare l’approccio top-down nella progettazione
- evitare errori legati a scope e mutabilità
- progettare soluzioni con input e output chiari


## 🧠 Introduzione concettuale

Gli esercizi finali uniscono tutti i concetti della dispensa.  
Scomposizione, funzioni, parametri, scope e mutabilità vengono usati insieme.

Ogni esercizio richiede prima di **progettare** e poi di **implementare**.  
Non serve correre. Serve ragionare e verificare passo dopo passo.


## 🧩 Spiegazione guidata

Per ogni esercizio segui questo schema:
1. scomponi il problema in sottoproblemi
2. decidi quali funzioni servono
3. implementa il codice
4. verifica il comportamento con esempi

I criteri indicati in ogni esercizio ti aiutano a capire se la soluzione è corretta e ben progettata.


## 🧩 Esercizi

### Base

**1) Media di voti**
- Consegna: leggi tre voti e calcola la media.
- Il programma deve:
  - usare una funzione `media_tre(a, b, c)`
  - restituire la media con `return`

**2) Sconto e IVA**
- Consegna: calcola il prezzo finale dato prezzo base, sconto e IVA.
- Il programma deve:
  - usare una funzione per lo sconto
  - usare una funzione per l’IVA

**3) Conta lettere**
- Consegna: data una stringa, conta quante vocali contiene.
- Il programma deve:
  - separare il calcolo dalla stampa

### Intermedio

**4) Registro spese**
- Consegna: data una lista di spese, calcola totale e media.
- Il programma deve:
  - usare una funzione per il totale
  - usare una funzione per la media

**5) Convertitore di temperatura**
- Consegna: data una lista di temperature in Celsius,
  crea una lista in Fahrenheit.
- Il programma deve:
  - restituire una nuova lista
  - non modificare la lista originale

**6) Gestione punteggi**
- Consegna: aggiungi punteggi a una lista e calcola il massimo.
- Il programma deve:
  - evitare effetti collaterali non voluti

### Sfida

**7) Mini-progetto: bollette**
- Consegna: calcola il costo totale di una bolletta con
  quota fissa, consumo e IVA.
- Il programma deve:
  - avere almeno 3 funzioni con responsabilità singola
- Suggerimenti progressivi:
  1. definisci le funzioni `quota_fissa`, `costo_consumo`, `totale`
  2. separa calcolo e stampa

**8) Mini-progetto: pagella**
- Consegna: data una lista di voti, calcola media, massimo e minimo.
- Il programma deve:
  - usare funzioni separate
  - stampare un riepilogo finale
- Suggerimenti progressivi:
  1. una funzione per la media
  2. una funzione per massimo e una per minimo
  3. non modificare la lista originale

**9) Analisi testo**
- Consegna: dato un testo, conta parole, caratteri e righe.
- Il programma deve:
  - usare funzioni separate
  - restituire i risultati come valori di ritorno

**10) Bilancio familiare**
- Consegna: dato un dizionario di entrate e uscite, calcola il saldo.
- Il programma deve:
  - evitare variabili globali
  - restituire il risultato da una funzione


## ✅ Checklist finale

- So progettare con top-down prima di scrivere codice.
- So separare calcolo e stampa.
- So prevedere effetti collaterali con oggetti mutabili.
- So verificare un programma con criteri chiari.


## 🧠 Trappola comune

Saltare la fase di progettazione e scrivere subito il codice.
Questo porta a soluzioni difficili da correggere e da estendere.

> **Idea chiave**  
> Prima scomponi, poi codifichi e infine testi.
