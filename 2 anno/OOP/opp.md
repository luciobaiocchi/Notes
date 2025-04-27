# opp

[laboratorio ](laboratorio.md)

SHELL 

usato per testin in riga, le variabili sono temporanee

kiss →   keep it simple 

dry  →   don’t repeat yourself 

## PROGETTAZIONE

- Interfacce: riportano le funzionalit`a definitorie del concetto
- Classi astratte: fattorizzano codice comune alle varie implementazioni
    
    Realizzano “scheletri” di classi per collezioni, corrispondenti alle relative interfacce, Facilitano lo sviluppo di nuove classi aderenti alle interfacce
    
- Classi concrete: realizzano le varie implementazioni

NEL CODICE CLIENTE 

- In variabili, argomenti, tipi di ritorno, si usano le interfacce
- Le classi concrete solo nella new, a parte casi molto particolari
- Le classi astratte non si menzionano praticamente mai, solo eventualmente per chi volesse costruire una nuova implementazione

## TIPI DI DATO

- classificare valori
- nome, set di valori, operazioni e meccanismi per manipolazione, relative a ogni tipo di dato

IN JAVA 

- PRIMITIVI
    - [boolean](opp.md), byte, short, int, long, float, double, char
- ARRAY
    
    boolean[], byte[], String[], String[][]
    
- CLASSICI
    
    Object, String, ArrayList, JFrame
    

Ha typing statico, ogni espressione ha tipo noto al compilatore, e non si accettano espressioni con tipo diverso da quello atteso 

## Booleani

esempio : boolean b = 10 > 20 ⇒ false 

Valori: true, false
Operatori unari: ! (not)

& = and logico 

&& = and condizionale 

- Operatori binari: & (and), | (or), ˆ (xor), && (and-c), || (or-c)
    - && e || valutano il secondo argomento solo se necessario
    - false && X d`a comunque false
    - true || X d`a comunque true
    

Operatori di confronto numerici: >, <, >=, <=

- Operatori di uguaglianza (su tutti i tipi): ==, !=
    - 10 == 20 (false)
    - new Object() == new Object() (false, confronta i riferimenti)
- Operatore ternario (booleano,tipo,tipo): ?:
    
    b?v1:v2 restituisce v1 se b è vero, v2 altrimenti
    
    (v1 e v2 devono avere stesso tipo)
    
- non si sa quanto spazio occupa in memoria, perchè non è un problema rilevante

## TIPI NUMERICI

![Screenshot 2023-09-27 alle 09.48.47.png](Screenshot_2023-09-27_alle_09.48.47.png)

### INTERI

![Screenshot 2023-09-27 alle 09.49.32.png](Screenshot_2023-09-27_alle_09.49.32.png)

![Screenshot 2023-09-27 alle 09.49.50.png](Screenshot_2023-09-27_alle_09.49.50.png)

![Screenshot 2023-09-27 alle 09.49.59.png](Screenshot_2023-09-27_alle_09.49.59.png)

### FLOAT

![Screenshot 2023-09-27 alle 09.50.31.png](Screenshot_2023-09-27_alle_09.50.31.png)

![Screenshot 2023-09-27 alle 10.10.40.png](Screenshot_2023-09-27_alle_10.10.40.png)

- operazioni bit a bit:
    
    servono per fare operazioni di insiemistica in modo conciso, anche se in java si usano gli oggetti che rappresentano degli insiemi. Con bit a bit sono limitato ad un numero massimo di 32 elementi, dato dal numero di bit, inoltre renderebbe il codice molto meno comprensibile.
    

per controllare i bit è meglio utilizzare la codifica esadecimale, i numeri con 0 davanti vengono considerati come codifica ottale 

oltre il range degli int bisogna mettere l finale per considerare long: numero l 

## CONVERSIONI

cast che possono causare perdita di informazioni 

⇒ (tipo) valore

es : (int)3.33, ((double)10)/3, (short)100

- conversioni automatiche, dette coercizioni
    
    ![Untitled](Untitled.png)
    

### CARATTERI

![Screenshot 2023-09-27 alle 10.41.32.png](Screenshot_2023-09-27_alle_10.41.32.png)

## ARRAY

- lunghezza accessibile
    
    [https://www.notion.so](https://www.notion.so)
    
- sono oggetti
- impossibile violare limiti di un array
- accesso leggermente più lento rispetto a C

**SINTASSI**

- int[] ar1 = new int[]{10,20,30,40,50,7,8,9};
- int[] ar2 = new int[200]; // new int[]{0,0,...,0}
- (variante con var:
    
    var ar3 = new int[]{10,20,30})
    
- (variante senza new: int[] ar4 = {10,20,30})
- Array di Array:
    - int[][] m=new int[][]{new int[]{..},..};
    - int[][] m2=new int[200][200];

## CODICE STATICO

campi e metodi di una classe possono essere dichiarati static

posso chiamare un metodo su una classe solo se è dichiarato statico 

non statico, chiama metodi su oggetti

![Screenshot 2023-11-03 alle 16.06.51.png](Screenshot_2023-11-03_alle_16.06.51.png)

se XYZ `e una classe usata per generare oggetti, la classe XYZs conterrà` solo proprietà statiche relative, es: Object/Objects

- inizializzazione con this
    
    ![Screenshot 2023-11-03 alle 16.21.51.png](Screenshot_2023-11-03_alle_16.21.51.png)
    

## Package

Un framework mainstream come quello di Java può disporre di decine di migliaia di classi di libreria e di applicazione, Per poter meglio gestirli in memoria secondaria, e per meglio accedervi.

**dichiarazione package** 

Ogni unità di compilazione (file .java) deve specificare il suo package
Lo fa all’inizio del sorgente con la direttiva package pname;

**importazione classi da altri package**

Per evitare tale specifica, si inserisce una direttiva di importazione
    import java.util.*; importa tutte le classi di java.util 

    import java.util.Date; importa la sola java.util.Date

**unità di compilazione** 

E` un file .java compilabile atomicamente da javac contenente varie classi, indicate una dopo l’altra

**Livello d’accesso PACKAGE** 

Le classi in una unità di compilazione, i loro metodi, campi, e costruttori hanno di default il livello d’accesso package
⇒ sono visibili e richiamabili solo dentro al package stesso 

⇒ sono invisibili da fuori 

**Livelli di accesso PUBLIC PRIVATE** 

public → La corrispondente classe/metodo/campo/costruttore sarà `visibile ed utilizzabile da qualunque classe`, senza limitazioni

private → Il corrispondente metodo/campo/costruttore sarà `visibile ed utilizzabili solo dentro alla classe in cui` e definito

**final** 

final = non modificabile

## Incapsulamento

- principio di decomposizione
    
    La soluzione di un problema complesso avviene dividendolo in
    problemi più semplici, tra loro indipendenti
    
    Per suddividere efficacemente, isolare i sottoproblemi semplici e minimizzare le dipendenze tra loro. Questo promuove l'autonomia decisionale, riduce l'interazione e le influenze negative se ci sono modifiche. Specificamente:
    
    1. Minimizzare le dipendenze
    2. Favorire le dipendenze intra-componenti rispetto alle inter-componenti
    3. Favorire le dipendenze nei componenti più annidati
    
    in OO package→classi→metodi
    
    durante la suddivisione è fondamentale minimizzare le dipendenze 
    
    dipendenza = A è dipendente da B se dentro il codice di A viene menzionato B → genera codice “rigido” 
    

## Composizione, INTERFACCE

![Screenshot 2023-11-06 alle 09.08.49.png](Screenshot_2023-11-06_alle_09.08.49.png)

**Composizione =** has-a a si compone di oggetti b1, b2,…, bn (oggetti e non primitivi)

**Aggregazione =** composizione in cui b1,b2,…, bn hanno anche vita propria 

### **diagrammi UML**

![Screenshot 2023-11-06 alle 09.22.57.png](Screenshot_2023-11-06_alle_09.22.57.png)

![Screenshot 2023-11-06 alle 09.28.45.png](Screenshot_2023-11-06_alle_09.28.45.png)

![Screenshot 2023-11-06 alle 09.30.21.png](Screenshot_2023-11-06_alle_09.30.21.png)

### **Polimorfismo** = molte forme (molti tipi)

inclusivo→ subtyping 

parametrico→ genericità 

## 07-Inheritance

### composizione

![Screenshot 2023-11-14 alle 11.01.11.png](Screenshot_2023-11-14_alle_11.01.11.png)

ottengo composizione tramite “delegazione”

```java
/* Si noti la clausola extends, per estendere una classe */
public class MultiCounter extends Counter {
	/*
	* I costruttori vanno ridefiniti. Devono tuttavia richiamare
	* con super(...) quelli ereditati dalla sopraclasse */
	public MultiCounter(int initialValue) { 
		super(initialValue);
	}
	// increment e getValue automaticamente ereditati
	// si aggiunge multiIncrement
	public void multiIncrement(final int n) {
	 for (int i = 0; i < n; i++) {
		this.increment(); 
		}
	} 
}
```

### Protected

E` un livello intermedio fra public e private
Indica che la proprietà (campo, metodo, costruttore) è accessibile dalla
classe corrente, da una sottoclasse, e dalle sottoclassi delle sottoclassi
(ricorsivamente)
Cavillo: protected in Java consente accesso anche da tutto il package,
ovvero è “meno stringente” rispetto al livello di default package protected

Consente alle sottoclassi di accedere ad informazioni della sopraclasse che
non si vogliono far vedere agli utilizzatori

### Overriding

riscrivere nella sottoclasse uno (o più) dei metodi della superclasse.

Se necessario, il metodo riscritto può invocare la versione del padre usando il receiver speciale super

## 10 - Collections

![Screenshot 2023-12-05 alle 16.35.51.png](Screenshot_2023-12-05_alle_16.35.51.png)

COLLECTION (interface) → contenitore di elementi (insieme) (Collections = class)

MAP (interface) → contenitore coppie chiavi valore 

FOR EACH → implementato per ogni classe di Collections, se voglio creare una classe iterabile deve implementare Iterable (interface) che ha solo un metodo iterator → next()   boolean hasNext()

![Screenshot 2023-12-05 alle 16.50.09.png](Screenshot_2023-12-05_alle_16.50.09.png)

- ESEMPIO
    
    ![Screenshot 2023-12-05 alle 16.41.01.png](Screenshot_2023-12-05_alle_16.41.01.png)
    
    ![Screenshot 2023-12-05 alle 16.41.12.png](Screenshot_2023-12-05_alle_16.41.12.png)
    
    ![Screenshot 2023-12-04 alle 16.37.53.png](Screenshot_2023-12-04_alle_16.37.53.png)
    
    come funziona un iterator
    
- SET
    - no duplicati
    - non aggiunge metodi rispetto Collection
    - metodi di modifica rispettano la non duplicazione
    
    IMPLEMENTAZIONI
    
    - HashSet
        
        Si usa il metodo Object.hashCode() come funzione di hash, usata per
        posizionare gli elementi in uno store di elevate dimensioni
        
        - IMPORTANTE: per ogni classe contenuta dentro un HashSet devo implementare metodi equals e hascode, per far si che possano essere confrontate in modo ragionevole
    - TreeSet (meno usati)
        
        Specializzazione di SortedSet e di NavigableSet. Gli elementi sono ordinati, e quindi organizzabili in un albero (red-black tree) per avere accesso in tempo logaritmico.
        
        - IMPORTANTE: per garantire l’ordinamento devo specificare come ordinare ogni classe da me implementata contenuta in un TreeSet.
        
        DUE MODI:
        
        - interno: utilizzo elementi che implementano Comparable
            
            che ha il metodo compareTo() che definisce il ritorno della comparazione di due elementi 
            
        - esterno: comparator fornito nella new TreeSet()
- LIST
    - sequenze di elementi
    - posso accedere ad una determinata posizione
    - 

## 11- Generics and Collections

## 12 - Errors

TIPOLOGIE:

- a tempo di compilazione (errori di sintassi )
- a tempo di esecuzione, sono condizioni anomale ma si possono intercettare e gestire

![Screenshot 2023-11-24 alle 17.37.52.png](Screenshot_2023-11-24_alle_17.37.52.png)

ERRORS → tirate dall’interprete e sono precostituiti (basso livello) e non risolvibili

UNCHECKED EXCEPTIONS →  programmatiche, se estendono da RuntimeException, bug di programmazione, errore del programmatore. 

```java
if (pos < 0 || pos >= array.length){
	final String msg = "Accesso fuori dai limiti, in posizione "+pos;
	throw new java.lang.IllegalArgumentException(msg); 
}
return array[pos];
```

TRY-CATCH

```java
try { <body-maybe-throwing-an-exception>}
   catch (<throwable-class> <var>) { <handler-body>}
//esegue il catch esclusivamente se cattura l'eccezione 
//posso mettere direttamente Exception e, per catturare qualsiasi eccezzione 

//soluzione migliore :
try { <body-maybe-throwing-an-exception>
	}catch (<throwable-class> <var>) { 
	<handler-body>
	}catch (<throwable-class> <var>) { 
	<handler-body>
	}
	...
	catch (<throwable-class> <var>) { 
	<handler-body>
	}finally { <completion-body>} 
}  // clausola finale opzionale

System.err.println("errore");  //per stampare sotto formato di errore  
```

![Screenshot 2023-11-25 alle 12.45.17.png](Screenshot_2023-11-25_alle_12.45.17.png)

![Screenshot 2023-12-11 alle 18.01.58.png](Screenshot_2023-12-11_alle_18.01.58.png)

CHECKED→ Obbligo a far si che si debbano gestire le eccezioni, utilizzo throw nel metodo getIntFromKbd per delegare l’handle dell’errore al chiamante della funzione stessa.

## 13 - Advanced mechanism

![Screenshot 2023-11-26 alle 17.22.48.png](Screenshot_2023-11-26_alle_17.22.48.png)

```java
class Outer { ...
	static class A { .. static class C{..} ..} 
	static class B {..}
	interface I {..} // static `e implicito
}.  //esempio di classi innestate 
```

MOTIVI PER USARE NESTING:

- Evitare il proliferare di classi in un package
- Migliorare l’incapsulamento, con un meccanismo per consentire un accesso locale anche a membri private
- Migliorare la leggibilità (classi piccole)

```java
public class UseOuter {
	
	public static void main(String[] args) { 
		Outer o = new Outer(5);
		Outer.Inner in = o.new Inner(); //caso di classe inn. non statica
		System.out.println(in.getValue()); // 0 
		in.update();
		in.update(); 
		System.out.println(in.getValue()); // 5
		
		Outer.Inner in2 = new Outer(10).createInner(); 
		in2.update();
		in2.update(); 
		System.out.println(in2.getValue()); // 20
	} 
}
```