# Scope (contesto) delle variabili


## 🎯 Obiettivi di apprendimento
- distinguere variabili locali e globali
- prevedere la visibilità di una variabile
- interpretare un errore di tipo `UnboundLocalError`
- spiegare perché le variabili globali sono rischiose


## 🧠 Introduzione concettuale

Una funzione usa una variabile `totale` senza definirla.
Il programma funziona?
Dipende da dove è definita quella variabile.
Senza una regola chiara sullo scope, l’esecuzione del programma diventa imprevedibile.
Lo stesso codice può funzionare o fallire a seconda del contesto.

Le funzioni devono poter lavorare in modo isolato.
Per questo è fondamentale capire quali variabili sono visibili dentro una funzione e quali no.


## 🧩 Spiegazione guidata

Le variabili create **dentro** una funzione sono **locali**.
Esistono solo durante l’esecuzione di quella funzione e non sono accessibili dall’esterno.

Le variabili create **fuori** dalle funzioni sono **globali**.
Sono visibili ovunque nel programma, ma possono creare dipendenze nascoste e comportamenti difficili da prevedere.

> **Idea chiave**  
> Se in una funzione assegni un valore a un nome, Python lo considera **locale**.  
> Questo vale anche se esiste una variabile globale con lo stesso nome.

Questa regola spiega molti errori legati allo scope, incluso `UnboundLocalError`.


## 🧪 Esempi

```python
# Variabile locale

def mostra():
    messaggio = "Ciao"
    print(messaggio)

mostra()
# print(messaggio)  # errore: messaggio non esiste fuori
```

```python
# Variabile globale letta
contatore = 0

def mostra_contatore():
    print(contatore)

mostra_contatore()
```

```python
# Variabile globale modificata (sconsigliata)
contatore = 0

def incrementa():
    global contatore
    contatore = contatore + 1

incrementa()
print(contatore)
```


## ⚠️ Errori comuni

```python
x = 10

def cambia():
    x = x + 1

cambia()
```

* **Cosa ci si aspetta:**  
  Che `x` diventi 11.

* **Cosa succede davvero:**  
  Python genera un errore `UnboundLocalError`.

* **Perché succede:**  
  Python vede un’assegnazione a `x` dentro la funzione e lo considera locale.
  Il nome `x` locale viene usato prima di essere inizializzato.

> **Errore comune**  
> Pensare che Python “cerchi automaticamente” la variabile globale.  
> In realtà, l’assegnazione rende il nome locale.


## ✅ Check rapido (autoverifica)

1. Prevedi l’output o l’errore:

```python
val = 3

def f():
    print(val)

f()
```

Spiega perché il codice funziona o meno.

2. Prevedi l’output o l’errore:

```python
val = 3

def g():
    val = val + 1
    return val

print(g())
```

Spiega perché compare quell’errore o quel valore.


## 🧩 Esercizi (autonomia)


### Base
- Scrivi una funzione che usa una variabile locale e prova a stamparla fuori dalla funzione.

### Intermedio
- Crea una variabile globale `saldo` e una funzione che la legga senza modificarla.

### Sfida
- Riscrivi una funzione che usa `global` in modo da non usarla, passando i dati come parametri.

**Suggerimenti:**
- Preferisci passare valori tramite parametri.
- Se vedi `global`, chiediti se esiste una soluzione più chiara.


## ✅ Checklist finale

- So distinguere variabili locali e globali.
- So prevedere la visibilità e la durata di una variabile.
- So spiegare perché compare `UnboundLocalError`.
- So motivare perché le variabili globali sono rischiose.


## 🧠 Trappola comune

Usare variabili globali per comodità.
All’inizio sembra funzionare, ma rende il programma fragile e difficile da testare.

> **Idea chiave**  
> Una funzione dovrebbe ricevere tutto ciò che le serve tramite parametri
> e restituire un risultato esplicito.
