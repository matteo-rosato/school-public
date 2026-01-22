# Progettare funzioni chiare


## 🎯 Obiettivi di apprendimento
- progettare funzioni con una sola responsabilità
- definire input e output in modo esplicito
- separare calcolo e stampa
- rifattorizzare un programma monolitico


## 🧠 Introduzione concettuale

Un programma che legge dati, calcola risultati e stampa tutto in un unico blocco può funzionare. Tuttavia è difficile da **riusare** e da **testare**.

Quando devi modificare una sola parte del programma, rischi di rompere le altre.
Questo rende il codice fragile e poco flessibile.

Le funzioni rendono il codice più leggibile.
Soprattutto permettono di isolare le responsabilità e individuare più facilmente gli errori.


## 🧩 Spiegazione guidata

Una buona funzione ha una **responsabilità singola**.  
Deve svolgere un compito chiaro e limitato, non “un po’ di tutto”.

L’interfaccia della funzione è definita da:
- parametri di ingresso (input)
- valore di ritorno (output)

Separare **calcolo** e **stampa** è una pratica fondamentale.  
Una funzione dovrebbe calcolare un risultato, un’altra dovrebbe occuparsi di mostrarlo.

> **Definizione**  
> Il **refactoring** è il processo di trasformazione di un codice funzionante ma disordinato
in un codice più chiaro e strutturato, senza cambiarne il comportamento. È una pratica essenziale per mantenere il codice sano e facile da gestire.


## 🧪 Esempi

```python
# Versione monolitica
ore = 5
paga_oraria = 12
paga = ore * paga_oraria
print("Paga:", paga)
```

```python
# Versione con funzioni

def calcola_paga(ore, paga_oraria):
    return ore * paga_oraria


def stampa_paga(paga):
    print("Paga:", paga)


def main():
    ore = 5
    paga_oraria = 12
    paga = calcola_paga(ore, paga_oraria)
    stampa_paga(paga)


main()
```


## ⚠️ Errori comuni

```python
def gestisci_paga(ore, paga_oraria):
    paga = ore * paga_oraria
    print("Paga:", paga)
    # qui magari salva su file, manda email, ecc.
```

* **Cosa ci si aspetta:**  
  Comodità: tutto in un unico punto.

* **Cosa succede davvero:**  
  La funzione diventa difficile da testare e da riusare.

* **Perché succede:**  
  La funzione ha troppe responsabilità e un’interfaccia poco chiara.

> **Errore comune**  
> Pensare che “mettere tutto in una funzione” renda il codice automaticamente migliore.


## ✅ Check rapido (autoverifica)

1. Prevedi l’output:

```python
print(calcola_paga(4, 10))
```

Spiega perché quel valore è corretto.

2. Prevedi l’output:

```python
valore = calcola_paga(3, 8)
stampa_paga(valore)
```

Spiega perché la stampa è separata dal calcolo.


## 🧩 Esercizi (autonomia)


### Base
- Spezza un programma che calcola l’area di un triangolo in due funzioni:
  una per il calcolo e una per la stampa.

### Intermedio
- Scrivi un programma che calcola il totale della spesa e poi lo stampa.
  Usa due funzioni con responsabilità distinte.

### Sfida
- Ristruttura uno script che legge tre numeri, calcola la media e stampa un messaggio.
  Progetta almeno tre funzioni.

**Suggerimenti:**
- Dai nomi chiari e coerenti alle funzioni.
- Chiediti sempre: “questa funzione fa una sola cosa?”.


## ✅ Checklist finale

- So progettare funzioni con una responsabilità singola.
- So separare calcolo e stampa.
- So definire input e output in modo chiaro.
- So rifattorizzare uno script monolitico.


## 🧠 Trappola comune

Pensare che più codice dentro una funzione significhi più ordine.
In realtà una funzione troppo grande diventa un mini-programma difficile da capire.

> **Idea chiave**  
> Piccoli blocchi, responsabilità precise.
