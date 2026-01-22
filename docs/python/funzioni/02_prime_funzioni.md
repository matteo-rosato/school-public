# Prime funzioni in Python


## 🎯 Obiettivi di apprendimento
- riconoscere la sintassi `def` e l’indentazione corretta
- scrivere una funzione semplice e chiamarla
- spiegare il flusso di esecuzione di un programma con funzioni
- distinguere tra `return` esplicito e `return` implicito
- descrivere la differenza concettuale tra funzione e procedura


## 🧠 Introduzione concettuale
Immagina di dover stampare lo stesso messaggio di benvenuto in cinque punti diversi del programma.  
Senza funzioni, sei costretto a riscrivere lo stesso testo più volte.  

```python
print("Benvenuto nel corso")
# ... altro codice
print("Benvenuto nel corso")
# ... altro codice
print("Benvenuto nel corso")
# ... altro codice
print("Benvenuto nel corso")
# ... altro codice
print("Benvenuto nel corso")
```

Se domani devi cambiare il messaggio, devi ricordarti di modificarlo in tutti i punti. Se ne dimentichi uno, il programma diventa incoerente.

Questo è un problema di **manutenibilità**, cioè della facilità con cui un programma può essere modificato nel tempo senza introdurre errori o incongruenze.

Le funzioni risolvono il problema: scrivi il codice una sola volta e lo riusi ovunque.


## 🧩 Spiegazione guidata

Una funzione in Python si definisce usando:

* la parola chiave `def`
* un nome significativo
* le parentesi tonde `()`
* un corpo indentato

Quando il programma incontra una **chiamata di funzione**, interrompe temporaneamente il flusso principale, esegue il corpo della funzione e poi torna al punto da cui era partito.

Il comando `return` termina l’esecuzione della funzione e restituisce un valore al punto di chiamata. Se una funzione non contiene alcun `return`, Python restituisce automaticamente il valore `None`.

> **Definizione**  
> In ambito didattico si usa spesso il termine **procedura** per indicare una funzione che non restituisce un valore utile, ma produce solo un effetto (per esempio, stampare un messaggio).


## 🧪 Esempi

```python
def saluta(nome):
    # stampa un saluto, non restituisce un valore utile
    print("Ciao", nome)


def somma(a, b):
    # restituisce un risultato
    return a + b


saluta("Luca")
ris = somma(3, 5)
print(ris)
```

Esempio di `return` implicito:

```python
def stampa_titolo(testo):
    print("===", testo, "===")


valore = stampa_titolo("Report")
print(valore)
```

> **Nota**  
> Anche se `stampa_titolo` non contiene `return`, la funzione restituisce comunque `None`.
> Questo comportamento è automatico in Python.


## ⚠️ Errori comuni

```python
def somma(a, b):
return a + b
```

* **Cosa ci si aspetta:**
  Che la funzione funzioni comunque.

* **Cosa succede davvero:**
  Python genera un errore di indentazione.

* **Perché succede:**
  In Python l’indentazione definisce i blocchi di codice ed è parte della sintassi.


```python
def saluta():
    print("Ciao")

saluta
```

* **Cosa ci si aspetta:**
  Che venga stampato `"Ciao"`.

* **Cosa succede davvero:**
  Non succede nulla.

* **Perché succede:**
  Senza parentesi la funzione non viene chiamata.

> **Errore comune**  
> Confondere il nome di una funzione con la sua chiamata.  
> Scrivere `saluta` non esegue la funzione, scrivere `saluta()` sì.


## ✅ Check rapido (autoverifica)

1. Prevedi l’output:

```python
print(stampa_titolo("X"))
```

Spiega perché viene visualizzato quel valore.

2. Prevedi l’output:

```python
print(somma(2, 7))
```

Spiega perché la funzione restituisce proprio quel risultato.


## 🧩 Esercizi (autonomia)

### Base

* Scrivi una funzione `quadrato(n)` che restituisce il quadrato di un numero.

### Intermedio

* Scrivi una procedura `stampa_linea(n)` che stampi una linea di `n` asterischi.

### Sfida

* Scrivi una funzione `area_rettangolo(base, altezza)` che restituisca l’area.
* Scrivi una procedura che stampi un messaggio con il risultato ottenuto.

**Suggerimenti:**

* Se la funzione restituisce un valore, usa `return`.
* Se devi solo mostrare qualcosa all’utente, puoi usare `print`.


## ✅ Checklist finale

* So definire una funzione con `def`.
* So chiamare una funzione usando le parentesi.
* So descrivere il flusso di esecuzione di una funzione.
* So distinguere tra `return` esplicito e implicito.


## 🧠 Trappola comune

Credere che `print` e `return` siano equivalenti.  
`print` mostra un valore all’utente, ma `return` restituisce un valore al programma.

> **Idea chiave**  
> Usa `print` per comunicare con l’utente e `return` per comunicare con il codice.
