# Riepilogo


## 🎯 Obiettivi di apprendimento
- riassumere i concetti chiave sulle funzioni
- collegare approccio top-down, parametri e scope
- usare una mappa concettuale testuale
- rispondere a domande di ripasso usando esempi concreti


## 🧠 Introduzione concettuale

Dopo aver studiato funzioni, parametri, scope e mutabilità, è importante fermarsi e costruire un quadro d’insieme. Un riepilogo serve a collegare le idee. Serve soprattutto a usarle insieme quando si progetta un programma reale.


## 🧩 Spiegazione guidata

> L’approccio top-down porta a scomporre un problema in sottoproblemi.  
> Ogni sottoproblema può diventare una funzione con input e output.  
> I parametri permettono di passare dati.  
> Lo scope stabilisce dove i nomi sono visibili.  
> La mutabilità spiega quando una funzione modifica i dati originali.  
> I valori di default migliorano la flessibilità, ma richiedono attenzione.  


## 🧪 Esempi

```python
# Schema minimo di programma top-down

def calcola():
    return 10


def mostra(valore):
    print("Risultato:", valore)


def main():
    risultato = calcola()
    mostra(risultato)


main()
```


## ⚠️ Errori comuni

```python
valori = [1, 2, 3]
media = (valori[0] + valori[1] + valori[2]) / 3
print("Media:", media)
```

* **Cosa ci si aspetta:**  
  Codice semplice e veloce.

* **Cosa succede davvero:**  
  Difficile da riusare o modificare.

* **Perché succede:**  
  Mancano funzioni e separazione dei compiti.


## ✅ Check rapido (autoverifica)

1. Prevedi l’output:

```python
print(calcola())
```

Spiega perché quel valore è corretto.

2. Prevedi l’output:

```python
val = calcola()
mostra(val)
```

Spiega perché la stampa è separata dal calcolo.


## 🧩 Esercizi (autonomia)


### Base
- Scrivi una lista di 5 concetti chiave e spiega ognuno in una frase.

### Intermedio
- Trasforma un piccolo script monolitico in 2–3 funzioni.

### Sfida
- Progetta una funzione che usa parametri opzionali e restituisce un risultato
  senza effetti collaterali.

**Suggerimenti:**
- Usa la checklist globale per verificare cosa ti manca.


## ✅ Checklist finale

- So spiegare il legame tra top-down e funzioni.
- So distinguere parametri e argomenti.
- So prevedere lo scope delle variabili.
- So riconoscere problemi di mutabilità e aliasing.
- So evitare default mutabili.


## 🧠 Trappola comune

Studiare i concetti separatamente e poi non saperli usare insieme.
Ogni concetto serve a prendere decisioni durante la progettazione di un programma.


## 🧠 Schema concettuale

- Problema complesso

  - approccio top-down
    - parto dal risultato finale
    - scompongo in sottoproblemi
    - ogni sottoproblema diventa una funzione

  - funzioni
    - scatole nere
      - non mi interessa come funzionano dentro
      - mi interessa cosa ricevono e cosa restituiscono
    - responsabilità singola
      - una funzione = un compito chiaro
      - evita funzioni che fanno "tutto"

  - parametri e argomenti
    - parametri
      - nomi usati nella definizione della funzione
    - argomenti
      - valori passati nella chiamata
    - passaggio dei dati
      - i parametri diventano nuovi nomi
      - i nomi puntano a oggetti esistenti

  - return
    - output della funzione
    - restituisce un valore al codice chiamante
    - return implicito
      - se manca, la funzione restituisce None
    - separazione dei ruoli
      - return per il codice
      - print per l’utente

  - scope (contesto dei nomi)
    - scope locale
      - nomi definiti dentro una funzione
      - esistono solo durante l’esecuzione della funzione
    - scope globale
      - nomi definiti fuori dalle funzioni
      - visibili ovunque
      - rischiosi: dipendenze nascoste
    - regola chiave
      - assegnare a un nome lo rende locale
      - può causare UnboundLocalError

  - mutabilità e identità degli oggetti
    - identità
      - osservabile con id()
      - stesso id() = stesso oggetto
    - oggetti mutabili
      - list, dict, set
      - modificabili in-place
      - l’id() resta uguale
    - oggetti immutabili
      - int, float, str, tuple
      - ogni modifica crea un nuovo oggetto
      - l’id() cambia
    - aliasing
      - più nomi per lo stesso oggetto
      - una modifica tramite un nome si vede anche dagli altri
    - copia
      - .copy()
      - crea un nuovo oggetto indipendente
      - evita effetti collaterali

  - parametri opzionali e default
    - valori di default
      - usati se l’argomento non è passato
      - valutati una sola volta, alla definizione
    - default immutabili
      - sicuri
    - default mutabili
      - pericolosi
      - condivisi tra chiamate
    - soluzione corretta
      - usare None come sentinella
      - creare l’oggetto dentro la funzione

  - obiettivo finale
    - codice leggibile
    - codice prevedibile
    - codice facile da testare
    - codice facile da modificare


## 📝 10 domande di ripasso

1) Cos’è l’approccio top-down?
2) Perché lo pseudocodice è utile?
3) Qual è la differenza tra parametro e argomento?
4) Che cosa restituisce una funzione senza `return`?
5) Che cosa significa “variabile locale”?
6) Perché le variabili globali sono rischiose?
7) Che cosa significa aliasing?
8) Quando serve `.copy()`?
9) Perché un default mutabile è pericoloso?
10) Che cosa significa “responsabilità singola”?
