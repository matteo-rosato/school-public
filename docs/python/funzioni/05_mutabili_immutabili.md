# Mutabili e immutabili


## 🎯 Obiettivi di apprendimento
- distinguere oggetti mutabili e immutabili
- usare `id()` per osservare l’identità di un oggetto
- spiegare l’aliasing con esempi semplici
- prevedere l’output dopo una modifica in-place
- usare `.copy()` per evitare modifiche indesiderate


## 🧠 Introduzione concettuale

Due variabili sembrano due liste diverse.  
Modifichi una lista e cambia anche l’altra: sorpresa.

Per capire questi effetti servono due idee fondamentali:
- mutabilità
- identità degli oggetti

La funzione `id()` permette di osservare l’identità di un oggetto.  
Se due nomi hanno lo stesso `id()`, allora puntano allo stesso oggetto.


## 🧩 Spiegazione guidata

Gli oggetti **immutabili** (`int`, `float`, `str`, `tuple`) non possono essere modificati.  
Ogni “modifica” crea in realtà un nuovo oggetto con un nuovo `id()`.

Gli oggetti **mutabili** (`list`, `dict`, `set`) possono essere modificati **in-place**.  
Il contenuto cambia, ma l’`id()` dell’oggetto resta lo stesso.

Quando due nomi puntano allo stesso oggetto mutabile, si parla di **aliasing**.  
In questo caso una modifica fatta tramite un nome è visibile anche tramite l’altro.

Per evitare effetti collaterali indesiderati, si può creare una **copia superficiale**
usando il metodo `.copy()`.


## 🧪 Esempi

```python
# Immutabile: l'identità cambia dopo una modifica
x = 10
print(id(x))
x = x + 1
print(id(x))
```

```python
# Mutabile: l'identità resta uguale dopo una modifica in-place
lista = [1, 2]
print(id(lista))
lista.append(3)
print(id(lista))
```

```python
# Stesso oggetto, nomi diversi (aliasing)
lista1 = [5, 6]
lista2 = lista1
print(id(lista1), id(lista2))
lista1.append(7)
print(lista1)
print(lista2)
```

```python
# Oggetti diversi con stesso valore
a = [1, 2]
b = [1, 2]
print(a == b)
print(id(a), id(b))
```

```python
# Copia superficiale
originale = [10, 20]
copia = originale.copy()
print(id(originale), id(copia))
originale.append(30)
print(originale)
print(copia)
```

```python
# id() e passaggio dei parametri

def aggiungi_elemento(lista):
    print("dentro:", id(lista))
    lista.append(99)

numeri = [1, 2]
print("fuori:", id(numeri))
aggiungi_elemento(numeri)
print(numeri)
```


## ⚠️ Errori comuni

```python
numeri = [1, 2, 3]
altro = numeri
altro.pop()
print(numeri)
```

* **Cosa ci si aspetta:**  
  Che `numeri` resti invariata.

* **Cosa succede davvero:**  
  Anche `numeri` viene modificata.

* **Perché succede:**  
  `altro` e `numeri` sono alias dello stesso oggetto.
  Condividono lo stesso `id()`.


```python
def aggiungi_zero(lista):
    lista.append(0)
    return lista

base = [5, 6]
nuova = aggiungi_zero(base)
print(base)
```

* **Cosa ci si aspetta:**  
  Che `base` resti `[5, 6]`.

* **Cosa succede davvero:**  
  `base` diventa `[5, 6, 0]`.

* **Perché succede:**  
  La funzione modifica l’oggetto originale in-place.

> **Errore comune**  
> Pensare che una funzione “lavori su una copia” della lista.  
> In realtà lavora sull’oggetto originale, se non viene creata una copia.


## ✅ Check rapido (autoverifica)

1. Prevedi l’output:

```python
x = 7
prima = id(x)
x = x + 1
print(prima == id(x))
```

Spiega perché l’identità cambia o non cambia.

2. Prevedi l’output:

```python
lista = [1]
prima = id(lista)
lista.append(2)
print(prima == id(lista))
```

Spiega perché l’identità cambia o non cambia.

3. Prevedi l’output:

```python
a = [1, 2]
b = a.copy()
print(id(a) == id(b))
```

Spiega perché il risultato è `True` o `False`.


## 🧩 Esercizi (autonomia)


### Base
- Prevedi l’output di un programma con due variabili che puntano alla stessa lista e stampa `id()`.

### Intermedio
- Scrivi una funzione che riceve una lista e restituisce una nuova lista con un elemento in più, senza modificare l’originale.
  Usa `id()` per verificare.

### Sfida
- Crea un esempio con dizionari che mostra aliasing e poi risolvilo con `.copy()`.
  Mostra gli `id()`.

**Suggerimenti:**
- Verifica se stai creando un nuovo oggetto o modificando uno esistente.
- Usa `id()` per controllare l’identità.


## ✅ Checklist finale

- So distinguere oggetti mutabili e immutabili.
- So usare `id()` per riconoscere l’identità.
- So spiegare l’aliasing.
- So prevedere l’output con modifiche in-place.
- So usare `.copy()` per evitare effetti collaterali.


## 🧠 Trappola comune

Pensare che l’operatore `=` crei sempre una copia.  
In Python, `=` crea solo un nuovo nome o riassegna un nome a un oggetto esistente.

> **Idea chiave**  
> Per copiare un oggetto mutabile serve una copia esplicita.
