# Parametri e argomenti: nomi e oggetti


## 🎯 Obiettivi di apprendimento
- distinguere parametri e argomenti in esempi reali
- spiegare il modello mentale “nomi e oggetti”
- prevedere l’effetto del passaggio di parametri
- riconoscere comportamenti diversi con oggetti mutabili e immutabili
- correggere aspettative errate sui cambiamenti dei dati


## 🧠 Introduzione concettuale

Una funzione modifica una lista di voti. Ti aspetti che la lista cambi anche fuori dalla funzione, ma non succede. Oppure succede quando non lo vuoi. Senza un modello mentale chiaro, questi comportamenti sembrano casuali e difficili da prevedere. In realtà seguono regole precise.

Le funzioni diventano affidabili quando sai:
- cosa entra nella funzione
- cosa esce dalla funzione
- cosa può essere modificato e cosa no  


## 🧩 Spiegazione guidata

Il **parametro** è il nome usato nella definizione della funzione.  
L’**argomento** è il valore passato quando la funzione viene chiamata.

Quando chiami una funzione in Python, non viene fatta una copia dell’oggetto passato. Viene creato un **nuovo nome** che fa riferimento allo **stesso oggetto**.  

> **Idea chiave**  
> In Python i **nomi** sono etichette e gli **oggetti** sono i dati veri e propri.  
> Passare un argomento significa creare un nuovo nome che punta allo stesso oggetto.

Questo spiega perché:
- alcune modifiche sono visibili anche fuori dalla funzione
- altre modifiche non hanno alcun effetto esterno


## 🧪 Esempi

### Oggetto immutabile (stringa)

```python
def aggiungi_punto(testo):
    testo = testo + "."  # crea un nuovo oggetto stringa
    return testo

frase = "Ciao"
nuova = aggiungi_punto(frase)

print(frase)
print(nuova)
````

La stringa originale non cambia.  
La funzione crea una **nuova stringa** e ricollega il nome locale `testo`.


### Oggetto mutabile (lista)

```python
def aggiungi_voto(voti, nuovo):
    voti.append(nuovo)  # modifica l'oggetto lista

lista = [6, 7]
aggiungi_voto(lista, 8)

print(lista)
```

La lista viene modificata direttamente.  
Il cambiamento è visibile anche fuori dalla funzione.


## ⚠️ Errori comuni

```python
def incrementa(n):
    n = n + 1

x = 5
incrementa(x)
print(x)
```

* **Cosa ci si aspetta:**
  Che `x` diventi 6.

* **Cosa succede davvero:**
  `x` resta 5.

* **Perché succede:**
  `n` è un nome locale che viene ricollegato a un nuovo oggetto.
  La `x` esterna non viene mai modificata.


```python
def svuota(lista):
    lista = []

valori = [1, 2, 3]
svuota(valori)
print(valori)
```

* **Cosa ci si aspetta:**
  Una lista vuota.

* **Cosa succede davvero:**
  `[1, 2, 3]`

* **Perché succede:**
  Il nome `lista` viene ricollegato a una nuova lista locale.
  L’oggetto originale non viene modificato.

> **Errore comune**  
> Pensare che assegnare un nuovo valore a un parametro modifichi automaticamente l’oggetto originale.


## ✅ Check rapido (autoverifica)

1. Prevedi l’output:

```python
def raddoppia(n):
    n = n * 2
    return n

x = 4
print(raddoppia(x))
print(x)
```

Spiega perché `x` mantiene o non mantiene il valore.

2. Prevedi l’output:

```python
def aggiungi(lista):
    lista.append(99)

dati = [1, 2]
aggiungi(dati)
print(dati)
```

Spiega perché l’output cambia o non cambia.


## 🧩 Esercizi (autonomia)

### Base

* Scrivi una funzione `raddoppia(n)` e verifica se cambia la variabile esterna.

### Intermedio

* Scrivi una funzione `aggiungi_zero(lista)` che aggiunga `0` alla lista passata.

### Sfida

* Scrivi una funzione `normalizza(nome)` che restituisca il nome con la prima lettera maiuscola senza modificare la stringa originale.

**Suggerimenti:**

* Ricorda: i parametri sono nomi locali.
* Con liste e dizionari, le modifiche possono essere visibili anche fuori dalla funzione.


## ✅ Checklist finale

* So distinguere parametri e argomenti.
* So spiegare il modello “nomi e oggetti” con un esempio.
* So prevedere l’effetto del passaggio di parametri.
* So evitare aspettative errate con mutabili e immutabili.


## 🧠 Trappola comune

Pensare che “passare una variabile” significhi copiarla.
In realtà si passa un riferimento all’oggetto e si creano nuovi nomi.

> **Idea chiave**  
> I nomi possono cambiare, gli oggetti no.  
> A meno che l’oggetto sia mutabile e venga modificato direttamente.
