# Funzioni in Python (approccio top-down)


## Scopo della dispensa

Questa dispensa introduce le basi delle **funzioni e procedure in Python**, utilizzando l’**approccio top-down** per progettare programmi chiari, prevedibili e modificabili nel tempo.

L’obiettivo non è solo “scrivere codice che funziona”, ma **imparare a ragionare sul codice**, a scomporre i problemi e a costruire soluzioni comprensibili anche dopo settimane o mesi.


## Filosofia didattica

Il percorso è **pratico e motivato**.  
Ogni concetto nasce da un problema reale e da una necessità concreta, non da una regola astratta.

Le scelte proposte non sono dogmi, ma **strumenti di ragionamento**:
- servono a ridurre gli errori
- rendono il comportamento del programma prevedibile
- aiutano a capire *perché* il codice fa ciò che fa

L’attenzione è posta sui **modelli mentali** (top-down, nomi e oggetti, scope, mutabilità), perché sono questi che permettono di affrontare problemi nuovi in autonomia.


## Obiettivi di apprendimento globali

1) Analizzare un problema e scomporlo in sottoproblemi.
2) Applicare l’approccio top-down nella progettazione di programmi.
3) Scrivere e chiamare funzioni con parametri e valore di ritorno.
4) Comprendere e spiegare il flusso di esecuzione con le funzioni.
5) Distinguere parametri e argomenti.
6) Comprendere lo scope delle variabili e prevederne la visibilità.
7) Prevedere gli effetti del passaggio di parametri mutabili e immutabili.
8) Evitare bug comuni legati a scope, aliasing e modifiche inattese.
9) Progettare funzioni con responsabilità singola e interfaccia chiara.
10) Scrivere codice più leggibile, testabile e manutenibile.


## Struttura dei file

La dispensa è organizzata in moduli progressivi.  
Ogni file introduce pochi concetti ben definiti e li collega a quelli precedenti.

- `README.md`  
  Guida generale, filosofia didattica, obiettivi e struttura del percorso.

- `01_top_down.md`  
  Approccio top-down, scomposizione dei problemi e pseudocodice.

- `02_prime_funzioni.md`  
  Prime funzioni: `def`, `return`, flusso di esecuzione.

- `03_parametri_argomenti.md`  
  Parametri e argomenti, modello mentale “nomi e oggetti”.

- `04_scope_variabili.md`  
  Scope delle variabili, locali e globali, errori tipici (`UnboundLocalError`).

- `05_mutabili_immutabili.md`  
  Mutabilità, identità degli oggetti, aliasing, copie, uso di `id()`.

- `06_progettazione_funzioni.md`  
  Progettare funzioni chiare, responsabilità singola, separazione calcolo/stampa.

- `07_parametri_default.md`  
  Parametri opzionali, valori di default e bug dei default mutabili.

- `08_riepilogo.md`  
  Riepilogo concettuale, mappa dei concetti chiave e domande di ripasso.

- `09_esercizi_finali.md`  
  Esercizi complessivi e mini-progetti per consolidare le competenze.


## Come studiare il materiale

Per ottenere il massimo beneficio dalla dispensa:

1) Leggi **un file per volta**, senza saltare i moduli.
2) Copia gli esempi e provali in un editor o notebook Python.
3) Rispondi ai **Check rapidi** senza guardare il codice prima di eseguire.
4) Svolgi gli esercizi **Base** prima di passare a Intermedio e Sfida.
5) Torna spesso alla sezione **Errori comuni** quando qualcosa non funziona.
6) Usa il **Riepilogo** come mappa di orientamento, non come semplice riassunto.

> L’obiettivo non è memorizzare il codice, ma **imparare a prevedere cosa succederà prima di eseguirlo**.


## Licenza

Questo materiale è distribuito sotto licenza  
Creative Commons Attribution 4.0 International (CC BY 4.0).

È consentito usare, modificare e condividere il materiale,
anche per scopi commerciali, **a condizione che venga sempre
attribuita la paternità dell’opera originale**.