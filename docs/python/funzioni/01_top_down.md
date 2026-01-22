# Approccio top-down e scomposizione dei problemi


## 🎯 Obiettivi di apprendimento
- descrivere l’approccio top-down con parole proprie
- scomporre un problema in sottoproblemi ordinati
- scrivere un semplice pseudocodice
- identificare input e output di una funzione vista come scatola nera


## 🧠 Introduzione concettuale
Devi calcolare il prezzo finale di un prodotto applicando uno sconto e poi l’IVA.  
Se scrivi tutto in una volta, in un’unica espressione, rischi di confondere i passaggi e di non sapere dove intervenire quando qualcosa non funziona.  

Immagina, ad esempio, che:
- oggi l’IVA sia al 22%
- domani venga portata al 24%
- oppure che lo sconto non sia più percentuale, ma fisso

Se il calcolo è scritto tutto insieme, dovrai rileggerlo attentamente ogni volta e rischierai di sbagliare.  
Questo rende il programma **difficile da mantenere**.  

> **Definizione**  
> La **manutenibilità** è la facilità con cui un programma può essere modificato nel tempo senza introdurre errori e senza dover riscrivere tutto.  

L’approccio top-down parte dal risultato finale e scende nei dettagli: prima il quadro generale, poi i pezzi più piccoli.  
Non è una regola rigida, ma un modo pratico per non perdersi quando i problemi crescono.  


## 🧩 Spiegazione guidata
Con il top-down si inizia da una descrizione generale del problema:
- “calcolare il prezzo finale”

Poi si scompone il problema in passi più semplici e comprensibili:
- calcolare lo sconto
- applicare lo sconto al prezzo base
- aggiungere l’IVA
- ottenere il prezzo finale

Ogni passo può diventare una **funzione**, cioè una *scatola nera*:  
non ci interessa come funziona internamente, ma solo:
- quali dati riceve (input)
- quale risultato restituisce (output)

Prima di scrivere codice conviene chiarire le idee con un piano o uno pseudocodice.  
Lo pseudocodice non è Python: è una descrizione logica dei passi, utile per controllare l’ordine delle operazioni e il significato di ciascuna.  


## 🧪 Esempi

### Piano dei passi (in linguaggio naturale)
- ricevi prezzo base, sconto percentuale e IVA
- calcola l’importo dello sconto
- sottrai lo sconto al prezzo base
- applica l’IVA al prezzo scontato
- ottieni il prezzo finale

### Pseudocodice
```text
input: prezzo_base, sconto_percento, iva_percento
calcola importo_sconto
calcola prezzo_scontato
calcola prezzo_finale
restituisci prezzo_finale
````

### Traduzione in funzioni Python

```python
def calcola_sconto(prezzo_base, sconto_percento):
    # restituisce l'importo dello sconto
    return prezzo_base * (sconto_percento / 100)


def aggiungi_iva(prezzo, iva_percento):
    # restituisce il prezzo con IVA
    return prezzo * (1 + iva_percento / 100)


def prezzo_finale(prezzo_base, sconto_percento, iva_percento):
    # usa le funzioni come scatole nere
    sconto = calcola_sconto(prezzo_base, sconto_percento)
    prezzo_scontato = prezzo_base - sconto
    return aggiungi_iva(prezzo_scontato, iva_percento)


# esempio di utilizzo
base = 100
finale = prezzo_finale(base, 10, 22)
print(finale)
```

> **Nota**  
> La funzione `prezzo_finale` non ricalcola tutto da sola: coordina altre funzioni più semplici.  
> Questo rende il codice più leggibile e più facile da modificare.

## ⚠️ Errori comuni

```python
# Calcolo corretto ma scritto tutto in una sola espressione
base = 100
finale = (base - base * 10 / 100) * 1.22
print(finale)
```

* **Cosa ci si aspetta:**
  Un codice più breve, quindi migliore.

* **Cosa succede davvero:**
  Il calcolo è difficile da leggere e da verificare.
  Se cambia l’IVA o lo sconto, bisogna analizzare attentamente tutta l’espressione.

* **Perché succede:**
  La mancanza di scomposizione nasconde il significato dei singoli passaggi e rende il codice fragile.

> **Errore comune**  
> Pensare che “meno righe” significhi automaticamente “codice migliore”.  
> La leggibilità è spesso più importante della brevità.

## ✅ Check rapido (autoverifica)

1. Prevedi l’output:

```python
base = 50
print(prezzo_finale(base, 20, 10))
```

Spiega passo per passo come si arriva al risultato.

2. Prevedi l’output:

```python
print(calcola_sconto(80, 25))
```

Perché il risultato ha proprio quel valore?

3. Indica input e output della funzione `aggiungi_iva`.

## 🧩 Esercizi (autonomia)

### Base

* Scomponi il problema “calcolare la media di tre voti e dire se è sufficiente” in 2–3 sottoproblemi ordinati.

### Intermedio

* Scrivi un breve pseudocodice per calcolare il prezzo di una pizza con ingredienti extra.

### Sfida

* Progetta in top-down un programma che, dati i minuti di chiamata, calcoli il costo finale applicando:

  * uno scatto iniziale
  * un costo al minuto
  * l’IVA

**Suggerimenti:**

* Parti sempre dal risultato finale.
* Chiediti: “da quali pezzi dipende questo risultato?”
* Dai un nome chiaro a ogni sottoproblema.

## ✅ Checklist finale

* So spiegare cos’è l’approccio top-down.
* So scomporre un problema in pochi passi significativi.
* So scrivere pseudocodice semplice e leggibile.
* So riconoscere una funzione come scatola nera con input e output chiari.

## 🧠 Trappola comune

Confondere la scomposizione con il dettaglio eccessivo.
L’approccio top-down non richiede subito tutti i dettagli, ma prima l’**ossatura logica** del problema.

> **Idea chiave**  
> Prima chiarisci *cosa* deve fare il programma, poi *come* lo farà.
