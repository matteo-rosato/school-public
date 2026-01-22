# Parametri opzionali e valori di default


## 🎯 Obiettivi di apprendimento
- usare parametri opzionali con valori di default
- prevedere il comportamento dei default mutabili
- correggere il bug del default mutabile usando `None`
- spiegare perché il valore di default viene valutato una sola volta


## 🧠 Introduzione concettuale

Vuoi una funzione che aggiunga un elemento a una lista.  
Vuoi anche poterla usare senza passare esplicitamente la lista vuota alla prima chiamata.

Usi quindi un parametro con valore di default. Se non conosci bene il meccanismo, rischi un bug sottile: la lista cresce da sola tra una chiamata e l’altra.

Questo comportamento non è casuale.  
Dipende da **quando** Python valuta il valore di default.


## 🧩 Spiegazione guidata

Un parametro è **opzionale** quando ha un valore di default nella definizione della funzione.
Se l’argomento non viene passato, Python usa automaticamente quel valore.

I valori di default **non vengono creati a ogni chiamata**.
Vengono valutati **una sola volta**, nel momento in cui la funzione viene definita.

Se il valore di default è un oggetto **mutabile**, lo stesso oggetto viene riusato
in tutte le chiamate successive.

> **Idea chiave**  
> Il valore di default vive quanto la funzione, non quanto la chiamata.

Per questo motivo, la pratica più sicura è usare `None` come default
e creare l’oggetto mutabile **dentro** la funzione.


## 🧪 Esempi

```python
# Parametro opzionale con default immutabile

def saluta(nome, prefisso="Ciao"):
    return prefisso + " " + nome

print(saluta("Luca"))
print(saluta("Luca", "Buongiorno"))
```

```python
# Default mutabile: comportamento inatteso

def aggiungi(valore, lista=[]):
    lista.append(valore)
    return lista

print(aggiungi(1))
print(aggiungi(2))  # sorpresa
```

```python
# Soluzione corretta con None

def aggiungi_sicuro(valore, lista=None):
    if lista is None:
        lista = []
    lista.append(valore)
    return lista

print(aggiungi_sicuro(1))
print(aggiungi_sicuro(2))
```


## ⚠️ Errori comuni

```python
def accumula(x, dati=[]):
    dati.append(x)
    return dati

print(accumula("a"))
print(accumula("b"))
```

* **Cosa ci si aspetta:**  
  `["a"]` e poi `["b"]`.

* **Cosa succede davvero:**  
  `["a", "b"]`.

* **Perché succede:**  
  La lista di default è la stessa per tutte le chiamate.
  Non viene ricreata automaticamente.

> **Errore comune**  
> Pensare che il valore di default sia una copia nuova a ogni chiamata.


## ✅ Check rapido (autoverifica)

1. Prevedi l’output:

```python
print(saluta("Marta"))
print(saluta("Marta", "Ciao"))
```

Spiega perché i due risultati sono uguali o diversi.

2. Prevedi l’output:

```python
print(aggiungi(10))
print(aggiungi(20))
```

Spiega perché la seconda chiamata contiene il valore precedente.


## 🧩 Esercizi (autonomia)


### Base
- Scrivi una funzione `saluta(nome, lingua="it")` che cambi il saluto in base alla lingua.

### Intermedio
- Crea una funzione `aggiungi_tag(testo, tag=None)` che aggiunga un tag solo se passato.

### Sfida
- Progetta una funzione `registra_punteggio(nome, punteggio, archivio=None)`
  che salvi i dati in un dizionario senza bug di default mutabile.

**Suggerimenti:**
- Usa `if lista is None` per creare l’oggetto.
- Esegui chiamate consecutive per verificare il comportamento.


## ✅ Checklist finale

- So usare parametri opzionali con valori di default.
- So spiegare perché il default viene valutato una sola volta.
- So evitare default mutabili.
- So applicare correttamente la soluzione con `None`.


## 🧠 Trappola comune

Pensare che il default sia un “modello” copiato a ogni chiamata.
In realtà è un oggetto unico creato alla definizione della funzione.

> **Idea chiave**  
> Default immutabili: sicuri.  
> Default mutabili: da evitare.