# Ciclo di vita

## Analisi requisiti

- Lo scopo è produrre un documento che specifica i requisiti.
    utente finale e progettista si accordano sulle specifiche finali del sw e necessita:
  - chiarezza
  - non ambiguità
  - consistenza

### Come modellare?

In modo incrementale, non ambiguo esauriente coerente per rappresentare gli aspetti:

- Statici → Stati
- Dinamici  → Oggetti
- Funzionali  → Funzioni

#### Analisi Oggetti (Informazioni complesse, funzioni relativamente semplici)

**`identificazione`** oggetti e **`interazione`** tra essi

Le proprietà degli oggetti rimangono abbastanza stabili varia notevolmente l’uso che se ne fa.

#### Analisi Funzioni (complessità nelle trasformazioni input-output)

Sistema rappresentato come una **`rete di processi`** che trasforma **`flussi informativi`,**  tramite una progressiva costruzione di una gerarchia funzionale.

#### Analisi Stati (Modellare la sincronizzazione tra diverse attività cooperanti nel sistema)

Sistema pensato come un **`insieme di stati operativi`** e studio delle eventuali transizioni.

### Come costruire una base di conoscenza ?

si utilizzano i metodi di astrazione:

- **Classificazione**→ raggruppa in classi degli oggetti in base alle loro proprietà
- **Generalizzazione** → **is-a** astrae caratteristiche comuni in quelle di superclassi
- **Aggregazione** → **part-of** aggregazione tra oggetti, funzioni e stati
- **Associazioni**→ Associazioni tra varie classi

### Linguaggi per specificare requisiti

- **INFORMALI** (naturale) → lunghi e ambigui
- **SEMI-FORMALI** (grafici, ER) → più utilizzati, ma con semantica leggermente sfumata
- **FORMALI**(predicati, algebrici, concettuale per DB) → più complessi e non usati

### Uso di notazioni

notazioni diverse vengono usate per rappresentare informazioni diverse

Formalismi operazionali → Definiscono il problema in base al comportamento

Formalismi dichiarativi → Definiscono sistema in base alle proprietà

## Progettazione

Ponte tra la fase di specifica alla fase di codifica, si passa da “che cosa” a “come”.

Il sistema generale viene diviso in sottoparti.

Due esigenze:

- Sufficientemente astratto per confrontarlo con specifiche
- Sufficientemente dettagliato per permettere l’implementazione

La progettazione è un’attività altamente creativa,  e ci sono vari obbiettivi che devono essere rispettati:

## Paradigma a Oggetti

### Oggetti

Elementi di base del paradigma, possiedono:

- Identità (OID, object identifier)
- Stato: insieme di valori assunti in un determinato istante
- Comportamento: definito da un insieme di operazioni

### Interfaccia

Signature → operazione svolta dall’oggetto con parametri in input e output

Interfaccia → insieme signature

### Dati astratti

rappresentazione di un’insieme di oggetti “simili”

### Classi

Realizzazione di un tipo astratto, fornendo i metodi a esso associati.

### Incapsulamento

Protezione di attributi dell’oggetto, e possibilità di modificarli solo attraverso i metodi che l’interfaccia mette a disposizione.

Vantaggi:

- per usare una classe basta conoscere interfaccia
- Modificando la classe non si modifica l’applicazione
- meno errori e debugging più facile

### Operazioni e metodi

Il metodo implementa un’operazione:

Vari tipi:

- Costruttori → costruiscono ogg con parametri
- Distruttori → distruggono ogg e altri ogg collegati
- Accessori → informazioni su proprietà
- Trasformatori → modificano stato

Pubblici, protetti, privati

### Ereditarietà

Basare la definizione di una classe e implementazione su quella di altre classi.

Generalizzazione → super-classe

Classe specializzante → sotto-classe

Vengono ereditati metodi e attributi, con possibilità di aggiungerne altri o modificare quelli vecchi.

#### Ereditarietà multipla

quando una sotto-classe eredita da più super-classi, formando gerarchie di classi (ad albero o DAG).

### Polimorfismo

Possibilità di creare metodi con stesso nome ma implementazioni differenti.

Stesso nome, ma *signature *****diversa.

![Screenshot 2024-09-24 at 16.22.34.png](Paradigma%20a%20Oggetti%20d2278a1a0b19469782cd214c7c847211/Screenshot_2024-09-24_at_16.22.34.png)

Per permettere il polimorfismo è necessario l’istanziamento dinamico (a run-time).

### Oggetto complesso

Quando un determinato oggetto contiene il riferimento ad un altro oggetto, e delega operazioni a quest’ ultimo.

Permette di implementare associazione tra classi.

### Obbiettivo OOP

migliorare produttività e garantire estendibilità e riusabilità.

### Approccio funzionale

Il sitema ha una unica funzionalità, e a basso livello ci sono vari compiti (task), ma ci sono vari problemi:

- mancanza di iterazione

## UML

Fornisce costrutti per le fasi di sviluppo SW:

- analisi requisiti tramite use cases
- analisi e progettazione a OOP
- modellazione componenti
- modellazione struttura e configurazione

→ Ogni entità può apparire più volte per garantire una visione sotto i punto di vista statico dinamico e funzionale.

→ Un diagramma rappresenta uno stesso modello ma da un punto di vista diverso.

**MODELLO** → rappresentazione dominio applicativo

**DIAGRAMMA** → una particolare vista del dominio

**ELEMENTO** → in più diagrammi ma in un solo modello, sempre con stessa nomenclatura.

![Screenshot 2024-09-25 at 15.44.43.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-09-25_at_15.44.43.png)

### Struttura

### Costituenti fondamentali - ENTITà

![Screenshot 2024-09-25 at 15.47.07.png](UML%2010c3dd22936380e18da4ee2177f47a6c/485efe63-b2b4-493d-83a5-ca9263c3dec1.png)

#### STRUTTURE

- **INTERFACCIA** → comportamento di una classe
- **COLLABORAZIONE** → per ottenere un certo comportamento, alcune classi dentro l’ovale collaborano tra di loro, ma **non lo useremo**
- **CASO D’USO** → i metodi devono essere basati su casi d’uso, è una funzionalità del sistema. (es: iscriviti ad appello)
- **COMPONENTE** → parte di SW, composizione SW
- **NODO** → parte di HW (stampante, pc), composizione HW

#### COMPORTAMENTI

- **STATI** → insieme dei valori di attributi di un oggetto in un determinato istante, non interessano tutti i valori di un oggetto, ma le astrazioni di uno stato
- **INTERAZIONE** → un oggetto manda un messaggio ad un altro oggetto, ovvero **invocare un’operazione su un altro oggetto**

#### RAGGRUPPAMENTI

- **PACKAGE** → una cartella dentro cui possiamo mettere elementi del modello che sono semanticamente correlati

#### INFORMAZIONI

- **ANNOTAZIONE** → informazioni aggiuntive

### Costituenti fondamentali - RELAZIONI

![Screenshot 2024-09-25 at 15.47.25.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-09-25_at_15.47.25.png)

- **ASSOCIAZIONE** → astrazione per associazione, relationship delle ER, lega non solo le classi ma anche tipi diversi
- **PART-OF (aggregazione, composizione)** → rombo dove sta il tutto, il composto e non il componente. La differenza sta nella forza del part of. Aggregazione debole, il tutto non possiede le parti, le parti esistono senza il tutto se distruggo team corse non muoiono gli studenti. Composizione forte, il tutto possiede le parti, se distruggo aula le pareti non esistono.
- **IS-E (generalizzazione)** → UML supporta ereditarietà multipla (DAG directed a-ciclic graph)
- **DIPENDENZA** → entità A dipende da entità B quando una modifica in B può implicare modifica in A in questo caso la freccia va verso B. Per capire quali sono le entità impattate quando viene fatta una modifica.
- **CONTENIMENTO** → package sta dentro un altro
- **REALIZZAZIONE** → Realizzazione di una interfaccia da parte di una classe.

    Es: interfaccia stack con push pop ecc.. che può essere implementata in vari modi, per esempio con classe che contiene un array. Classe StackArray realizza interfaccia Stack, sulla punta si ha l’interfaccia.

  - **RAFFINAMENTO →** Collegare due entità a diversi livelli progettuali.

      Es: Collegare classi di analisi con classi di progetto. (collegato con la stessa freccia di realizzazione).

![Screenshot 2024-09-25 at 16.21.36.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-09-25_at_16.21.36.png)

### Costituenti fondamentali - DIAGRAMMI

#### STATICI

- **Diagramma classi →** diagramma fondamentale, modella la struttura delle classi da cui si può generare il codice.
- **Diagramma Oggetti →** istanza del diagramma delle classi, mostro il comportamento di alcuni oggetti specifici. Utile in alcune situazioni in cui il programmatore può non capire come concatenare
- **Diagramma dei package →** Collega vari package con relazioni di: dipendenza, contenimento, specializzazione.
- **Diagramma dei componenti →**  Architettura sistema, i moduli
- **Diagramma di deployment →** struttura del HW e allocazione SW

#### DINAMICI

- **DIAGRAMMA DEGLI STATI** → completamente dinamico, notazione di Harel. Notazione degli automi a stati finiti.  NEGLI ESERCIZI
- **DIAGRAMMA ATTIVITà** → molto espressivo, coniuga aspetti funzionali e dinamici. Quando devo fare un’azione, mostra la **sequenza delle cose da fare**. Nativamente **dinamico** ma viene associata una parte **funzionale**. Workflow aziendale.
- **DIAGRAMMI DI INTERAZIONE** → messaggi tra i vari oggetti all’interno di una interazione di un sistema.
- **DIAGRAMMA DI SEQUENZA** → porta in primo piano l’ordine delle informazioni

#### FUNZIONALI

- **CASI D’USO** → elenco casi uso del sistema, il primo che si disegna, il più semplice. Specificazione dei requisiti con il cliente. Un caso d’uso è una funzionalità, perchè i casi d’uso sono dei processi. NEGLI ESERCIZI

verde esercizi, giallo anche teoria

## Specifiche

Sono la descrizione testuale della semantica di un elemento

### Ornamenti

Rendono visibili gli aspetti particolari della specifica dell’elemento, non sono indispensabili. Negli esercizi non ci saranno mai ornamenti completi.

![Screenshot 2024-09-25 at 16.22.46.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-09-25_at_16.22.46.png)

### Distinzioni Comuni

**Classificatore** → Classe

**Istanza** → Stessa cosa di classificatore ma sottolineata

![Screenshot 2024-09-25 at 16.25.02.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-09-25_at_16.25.02.png)

**Interfaccia** → Separa signatura da implementazione di un oggetto  

**Implementazione** → Implementa i metodi di una interfaccia specifica  

![Screenshot 2024-09-25 at 16.24.56.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-09-25_at_16.24.56.png)

## Estendibilità e personalizzazione

### Stereotipo

Uno **stereotipo** → variazione di un elemento di modellazione esistente, *stessa forma ma diverso scopo*.  

Permette quindi di **introdurre nuovi elementi** di modellazione a partire da quelli esistenti. Dico di più rispetto al linguaggio UML.

![Classe utente stereotipata attore](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-09-25_at_16.26.50.png)

Classe utente stereotipata attore

### Proprietà

Valore associato a un elemento del modello. Espresso associato a una stringa dell’elemento.
`{ author = “Joe Smith”, status = analysis }` → proprietà

`{ disjoint , complete}`  → vincolo, una regola di un elemento del dominio che deve sempre risultare vera

`{ subset }` → vincolo

### Profilo

Insieme di stereotipi, proprietà e vincoli, usato per personalizzare UML.

## Architettura - Viste del software

### Vista dei casi d’uso

Descrive le **funzionalità del sistema** come vengono percepite dagli utenti, dagli analisti e dagli esecutori del testing. Non specifica l’organizzazione del software ma è la **base per le altre viste**.

### Vista Logica

Stabilisce la **terminologia del dominio del problema sotto forma di classi e oggetti**, illustrando come essi implementano il comportamento richiesto

### Vista dei processi

È una variante **orientata ai processi della vista logica**; modella i thread e i processi sotto forma di classi attive

### Vista di implementazione

Descrive i **moduli implementativi e le loro dipendenze**, illustrandone la configurazione così da definire il concetto di versione del sistema

### Vista di deployment

Mostra la distribuzione fisica del sistema software sull’architettura hardware

## DIAGRAMMA - casi d’uso

Ruoli di utilizzo del sistema da parte dei vari attori (utilizzatori).

- Non rappresenta la logica ma le interazioni tra il sistema e gli attori.
- Comprensibile anche per non programmatori, devono descrivere i casi d’uso dal punto di vista del cliente.

### Attore

Attore → entità esterna al sistema ma che interagisce con esso

- Lancia i casi d’uso
- Stereotipo di classe

Caso d’uso → Funzionalità come percepita da un attore, e deve fare qualcosa di visibile e utile, e deve essere completo.

L’unico modo per collegare un attore e un caso d’uso è tramite l’associazione di comunicazione

![Screenshot 2024-10-01 at 09.30.33.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-01_at_09.30.33.png)

![Screenshot 2024-10-01 at 09.36.08.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-01_at_09.36.08.png)

**TIPI DI RELAZIONI IN CASI D’USO:**

- **Relazioni tra attori** → esclusivamente generalizzazioni, quindi specializzazioni
- **Attori e casi d’uso** → associazione unidirezionale, e la freccia è aperta.
- **Relazioni tra casi d’uso** → Dipendenza e generalizzazione

Controllo impronta → IS-E e non è un PART-OF

Dipendenza, A→B se una modifica fatta in B comporta una modifica su A

- **Include** → va dal principale al secondario
- **Extend** → va dal secondario al principale  (la liberatoria per libri rari è un’estensione particolare di una richiesta di prestito)

Include deve essere vista come una chiamata a funzione, ogni volta che faccio prelievo bancomat, deve essere fatta una “chiamata a funzione” di verifica identità.

![Screenshot 2024-10-01 at 09.50.48.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-01_at_09.50.48.png)

Errore perché Login è una precondizione ma non viene fatto ogni volta che viene fatta una iscrizione.

![Screenshot 2024-10-01 at 09.53.18.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-01_at_09.53.18.png)

Versione corretta con precondizione di Login

### Ruolo casi d’uso

- Ruolo contrattuale per fare capire la specificazione dei requisiti del cliente e chiarire cosa deve essere sviluppato.
- Sono il punto di partenza per il testing
- Rappresentano le unità di rilascio, per seguire un approccio incrementale.

### Come disegnare casi d’uso

- Confini sistema
- Elenco attori
- Pero ogni attore pensare ai casi d’uso che utilizza
- Relazioni tra attori e casi d’uso

### Scenario

Una specifica esecuzione(istanza) di un caso d’uso.

Successo → termina con esito positivo

Insuccesso → termina con esito negativo

![Screenshot 2024-10-01 at 10.06.58.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-01_at_10.06.58.png)

![Screenshot 2024-10-01 at 11.33.20.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-01_at_11.33.20.png)

![Screenshot 2024-10-01 at 11.33.37.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-01_at_11.33.37.png)

## DIAGRAMMA - classi

Generalmente alcuni attori rientrano nel diagramma delle classi, i tipici attori esterni che il sistema deve memorizzare.

**Classe** → astrazione per classificazione di oggetti simili

**Attributi** → proprietà che tutti gli oggetti hanno

**Comportamento** → elenco delle operazioni

![Screenshot 2024-10-01 at 11.37.15.png](UML%2010c3dd22936380e18da4ee2177f47a6c/3a51c5dd-1fec-4df7-ac83-7d61c496df1c.png)

### Attributi

- **Visibilità**  : pubblica +, privata - , protected # (visibile da gerarchia), package ~
- **Molteplicità**: String [5], Real [2..*], Boolean [0..1]
- **Tipo**:  Integer, UnlimitedNatural, Real, Boolean, String
- **Ambito**: istanza o classe, ambito di classe, quindi attributi statici che sono sempre uguali per ogni classe

### Operazioni

direzione nomeParametro: tipoParametro=valoreDefault

![Screenshot 2024-10-09 at 14.36.56.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-09_at_14.36.56.png)

- **Direzione:**
  - in
  - out
  - inout
  - return(si usa quando l’operazione restituisce più valori)
- **Ambito:**
    istanza o classe

### Associazione

Connessione tra classi, tipicamente bidirezionale.

Le cardinalià vengono lette sulla classe di arrivo.

![Persona possiede una o più case](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_15.21.36.png)

Persona possiede una o più case

**ASSOCIAZIONI UNIDIREZIONALI →** il flusso dati avviene principalmente o esclusivamente in una direzione, ma è molto raro.

Indicare il verso di lettura si può fare ma non è obbligatorio. Si possono anche specificare i ruoli della classe all’interno della associazione

![L’opzionalità in dirigente è obbligatoria perché altrimenti si creerebbe una gerarchia infinita.](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_15.33.38.png)

L’opzionalità in dirigente è obbligatoria perché altrimenti si creerebbe una gerarchia infinita.

VINCOLI E CLASSI ASSOCIATIVE

![Una persona può essere a capo del comitato se ne fa parte, e un comitato ha un solo capo. {Subset} è una property](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_15.38.40.png)

Una persona può essere a capo del comitato se ne fa parte, e un comitato ha un solo capo. {Subset} è una property

![Proprietà per rappresentare un vincolo, {proprietà} e vincolo or già integrato nella sintassi](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_15.35.32.png)

Proprietà per rappresentare un vincolo, {proprietà} e vincolo or già integrato nella sintassi

![Possibilità di inserire una annotazione. Dot notation, data una  persona, percorro l’associazione e trovo il suo capo. Tra graffe quindi è un vincolo. Si possono scrivere in linguaggio naturale. [Va letta al contrario → il datore della persona = persona.datore e il datore del capo della persona = persona.capo.datore]](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_15.41.29.png)

Possibilità di inserire una annotazione. Dot notation, data una  persona, percorro l’associazione e trovo il suo capo. Tra graffe quindi è un vincolo. Si possono scrivere in linguaggio naturale. [Va letta al contrario → il datore della persona = persona.datore e il datore del capo della persona = persona.capo.datore]

Classe associativa, per rappresentare attributi di associazione

![Il vincolo della classe associativa rapporto uno uno tra istanze della classe associativa e istanze della associazione, quindi per ogni istanza di persona e azienda si ha una istanza di Posizione. In presenza di classi associative tutte le classi appartenenti all’istanza possono entrare una volta sola, come negli E/R.](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_15.46.02.png)

Il vincolo della classe associativa rapporto uno uno tra istanze della classe associativa e istanze della associazione, quindi per ogni istanza di persona e azienda si ha una istanza di Posizione. In presenza di classi associative tutte le classi appartenenti all’istanza possono entrare una volta sola, come negli E/R.

![Screenshot 2024-10-02 at 16.19.52.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_16.19.52.png)

ASSOCIAZIONI QUALIFICATE

!!!

ASSOCIAZIONI N-ARIE

definite tra n classi

![Screenshot 2024-10-02 at 16.13.05.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-02_at_16.13.05.png)

Tutte le n-arie devono essere vere n-arie e non false, quindi non devono essere scindibili.

Le molteplicità di un ruolo rappresenta il numero di istanze quando sono fissati n-1 og. Questa ternaria ha 2 dipendenze funzionali, perchè ha due cardinalità a 1.

**Come valutare le cardinalità :**

Aula 2.12, ingegneria Sw → n slot, quindi *

mercoledì 14, ingegneria Sw → 1 aula

Aula 2.12, mercoledì 14→  1 corso

### Elementi derivati

Rappresentare il fatto che un attributo o una associazione sono derivabili da un’altra.

![/attribute → significa che è derivabile da altri. {} tra graffe vincoli.](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_09.23.28.png)

/attribute → significa che è derivabile da altri. {} tra graffe vincoli.

**Associazioni derivate →** Molto spesso determinate relazioni (quando sono cicliche) possono essere considerate derivabili, per lasciare il vincolo che si vuole esprimere si possono inserire delle relazioni ridondanti.

### Aggregazione

Sia il tutto e le parti esistono indipendentemente

![Screenshot 2024-10-08 at 09.45.31.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_09.45.31.png)

Nell’aggregazione il legame è debole, il composto non contiene le parti e le parti esistono indipendentemente dal tutto.

Se io sciolgo una squadra i giocatori esistono ancora indipendentemente dalla squadra.

### Composizione

Sempre un part-of. Ogni parte appartiene esattamente al tutto.

![Screenshot 2024-10-08 at 09.51.32.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_09.51.32.png)

Sul rombo nero va sempre cardinalità 1.

![Screenshot 2024-10-08 at 09.52.57.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_09.52.57.png)

Non mi interessa mai sapere a che poligono appartiene un punto, viene utilizzata anche una freccia monodirezionale.

![Screenshot 2024-10-08 at 09.55.26.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_09.55.26.png)

#### Gerarchia part of

Una finestra è costituita da…

#### Differenze tra le due

La squadra conterrà riferimento agli oggetti  →**aggr**

La stanza viene istanziata dentro l’ggetto edificio → **comp**

### Generalizzazione

Tutti attributi e operazioni della superclasse venfonon ereditati dalle sotto-classi

![Screenshot 2024-10-08 at 10.01.51.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_10.01.51.png)

Possibile usare notazione a tridente

#### Supportata ereditarietà multipla

Anche se c’è la possibilità di conflitti tra operazioni.

![Screenshot 2024-10-08 at 10.02.41.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_10.02.41.png)

Overlapping → sovrapposto

Se c’è assenza di vincolo sono overlapping e incomplete.

### Classi astratte

Sono implementabili ma non istanziabili.

### Powertype

Tipizzazione potente, le istanze di tipoArticolo sono le classi che specializzano articolo e quindi possono essere solo quelle disponibili.

![Screenshot 2024-10-08 at 10.28.06.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_10.28.06.png)

### Dipendenza

*A dipende da B quando una variazione in B può
comportare una variazione in A*

![Screenshot 2024-10-08 at 10.50.58.png](UML%2010c3dd22936380e18da4ee2177f47a6c/e79c266f-3568-459b-acf8-fccb36136b8f.png)

### Template

descrive una classe in cui uno o più parametri formali non sono istanziati, parametri formali T,k.

Bound element → una classe che istanzia i parametri di un template.

![Screenshot 2024-10-08 at 10.55.56.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_10.55.56.png)

### Raffinamento

Raffinamento tra un tipo astratto e una classe che lo realizza. Tra classe di analisi e una di progetto

![Screenshot 2024-10-08 at 10.58.04.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_10.58.04.png)

### Interfacce

Stereotipo definito e particolare rappresentazione grafica. Meccanismo di astrazione potente, è una classe senta struttura, dotata solo di operazioni. Non tutte le classi astratte sono interfaccie ma una interfaccia è una classe astratta.

![Screenshot 2024-10-08 at 10.59.34.png](UML%2010c3dd22936380e18da4ee2177f47a6c/Screenshot_2024-10-08_at_10.59.34.png)

la rappresentazione lollipop è migliore perchè è più sintetica delle altre.

## Classi di progettazione

Si specifica come le classi devono essere implementate.

requisiti di ogni classe :

completa

sufficiente

essenziale

massimamente coesa

minimamente interdipendente

Alcuni costrutti come le associazioni o classi associative non sono implementabili direttamente, ma devono essere trasformate in base al carico di lavoro.

## Associazione molti-a-uno molti-molti

![Screenshot 2024-10-15 at 09.58.15.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-15_at_09.58.15.png)

Dipendenza trace. Posso sapere l’azienda di una persona, ma se voglio sapere tutti i dipendenti di una azienda devo guardare tutte le persone. quella sopra è una soluzione completa, efficiente per determinate query. Devo poter accedere a tutti gli oggetti che ho creato (contenitore).

![Screenshot 2024-10-15 at 09.58.22.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-15_at_09.58.22.png)

Se il carico di lavoro è bilanciato, meglio usare questa soluzione. Può creare ridondanza che è risolta con l’incapsulamento.

### Associazioni uno-uno

![Screenshot 2024-10-15 at 10.06.23.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-15_at_10.06.23.png)

rombo bianco → collegamento riferimento

rombo nero → collegamento per valore

### Associazioni ternarie

![Screenshot 2024-10-15 at 10.08.11.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-15_at_10.08.11.png)

reificare la relazione con una classe. No legami diretti tra corso e aula o corso e orario. Reificare sempre n-aria

sempre progettare da una classe verso classe reificata e poi verso le altre classi.

le cardinalità da esterne e reificata sono quelle di andata della ternaria.

le dipendenze funzionali che c’erano nei diagrammi di analisi, non ci sono nei diagrammi di progettazione

soluzione 1 ottima se so corso e voglio ottenere orario e aula, mentra la seconda soluzione è ridondande parzialmente, per capire quante lezioni ci sono in una determianta aula, ma senza sapere il corso

### Classe associativa

Rimane così anche nel diagramma di progettazione.

![Screenshot 2024-10-15 at 10.19.31.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-15_at_10.19.31.png)

### Diagrammi degli oggetti

![Screenshot 2024-10-15 at 11.25.16.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-15_at_11.25.16.png)

Al centro un oggetto anonimo, a destra una composizione, dove c’è una gerarchia di composizione si possono comunque inserire le istanze.

Serve per mostrare esempi delle strutture dati.

![Screenshot 2024-10-15 at 11.34.14.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-15_at_11.34.14.png)

Da diagramma degli oggetti a diagramma delle classi

### Diagramma package

i package annidati vedono lo spazio die nomi dei package che li contengono, il contrario non è vero.

4 tipi di dipendenza tra package:

- $<<use>>$ quando un elemento del package cliente usa un elemento del opackag efornitore
- $<<trace>>$ evoluzione di un elemento (dipendenza)
- $<<import>>$ quando gli elementi pubblici dello spazio dei nomi del package fornitore
vengono aggiunti come elementi pubblici allo spazio dei nomi del package cliente

GENERALIZZAZIONE

quando un package specifico si deve conformare all’interfaccia del package generale.

![Screenshot 2024-10-16 at 15.54.53.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-16_at_15.54.53.png)

Non ci sono indicazioni precise su come identificare package. Seguendo gerarchie del diagramma delle classi (gerarchie part-of e gerarchie is-e suddivise). Oppure secondo i casi d’uso. Tra 4 e 10 classi in un package, no dipendenze circolari.

### Diagrammi di sequenza

4 tipi di interazione, cose simili ma enfasi diversa:

- sequenza → enfasi tempo
- comunicazione → enfasi  chi parla con chi(oggetto parla con chi)
- sintesi interazione → spezzare l’interazione in più parti
- temporizzazione → aspetti real time

TERMINOLOGIA:

- Interazione → serie messaggi tra oggetti per ottenere obbiettivo
- contesto → ambito dell’interazione, generalmente una parte specifica del caso d’uso, molto spesso un caso d’uso.
- linea di vita→ è un oggetto, istanza di classificatore. Rappresenta come un oggetto partecipa nell’interazione.

![Screenshot 2024-10-16 at 16.05.57.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-16_at_16.05.57.png)

L’istanza che partecipa come linea di vita a quella interazione. linea tratteggiata = vita del sistema

Messaggio → chiamata, creazione e distruzione

chiamata, operazione su un altro oggetto

creazione, invocano il construttore, entrano in una linea di vita

distrizione, cancellano oggetto.

![Screenshot 2024-10-16 at 16.07.52.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-16_at_16.07.52.png)

#### 17,20-21,46

attivazione → intervallo in cui linea di vita è attiva

### Frammenti combinati

![Screenshot 2024-10-16 at 16.29.17.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-16_at_16.29.17.png)

iterazione con loop →

ripeto l’operazione

per ogni elemenot dell’ordine, se elevato → riguardo altrimenti distibutore qualsiasi,

uscito dal loop → se bisogno conferma la mando altrimenti niente

![Screenshot 2024-10-16 at 16.29.42.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-16_at_16.29.42.png)

## Diagramma degli stati

Grammatica → insieme di regole con le quali si definisce un linguaggio, usando notazione apposita (BNF, backus-naur form).

Automa a stati finiti → serve per fare un parsing di un linguaggio.

**I diagrammi di stato** descrivono in modo esaustivo l’evoluzione temporale delle istanze di un classificatore (classe, caso d’uso, sottosistema) in risposta alle interazioni con altri oggetti.

**stato** → **astrazione** degli attributi in un determinato istante
**evento** *→* provoca la transizione tra uno stato e l’altro

**azioni *→*** sono operazioni **istantanee**, atomiche e non interrompibili; sono associate a transizioni attivate da eventi

**attività** → fatte durante uno stato, potenzialmente continue, ma possono anche finire. Entrambe richiedono uno stato, fino a che sei in quello stato fai quella cosa

![Screenshot 2024-10-22 at 10.05.22.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-22_at_10.05.22.png)

Transizioni→ passaggio da uno stato a un altro, associata a uno o più eventi.

Evento → in un preciso istante e con durata

Una *condizione* è un’espressione booleana che deve risultare vera affinché
la transizione possa avvenire

*azione* è un’operazione istantanea, atomica e non interrompibile che viene eseguita all’atto della transizione.

Event condition action (**eca** rule), abbinate alle transizioni, quaddo si verifica questo evento se condizione vera fai l’azione

Transizione con nome implicito → Stato in cui esco è abbinato a una attività che termina

Se ogni volta che entro nello stato faccio la stessa azione, l’azione la scrivo dentro allo stato con :

- (entry/ azione)

stessa cosa per l’uscita:

- (exit/ azione)

![Screenshot 2024-10-22 at 10.05.31.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-22_at_10.05.31.png)

![Screenshot 2024-10-22 at 10.23.59.png](Classi%20di%20progettazione%201203dd229363808b9973db8def6fa5e7/Screenshot_2024-10-22_at_10.23.59.png)

### Tipi di eventi

- Evento di variazione: quando una condizione diventa vera, denotato da espressione booleana
- Evento di segnale: nel momento in cui un oggetto riceve un oggetto segnale da un altro oggetto.
- Evento di chiamata: invocazione di una operazione
- Evento temporale: scadere di un periodo di tempo:
  - when(data = 01/01/2008)
  - after (10 seconds)

### Stati compositi

## Ingegneria SW

### Produzione

la sequenza di operazioni che viene
seguita per costruire, consegnare e modificare un prodotto.

### Modelli prescrittivi

Insieme di attività azioni e compiti che sono necessari per ingengerizzare un sw di qualità

Producono programmi documenti e dati, e tutti i modelli comprendono le stesse attività:

- comunizazione
- pianificazione
- modellazione
- costruzione
- deployment

### Modello a cascata

Approccio sistematico e sequenziale lineare

![Screenshot 2024-11-12 at 09.20.34.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.20.34.png)

Output 1 = input 2, questo modello è obsoleto, versione funzionale solo alla fine del progetto, e non sono permesse modifiche alle fasi precedenti.

### Modello incrementale

Modello iterativo che consiste nell’applicare più sequenze lineari che produce uno stadio operativo del SW

![Screenshot 2024-11-12 at 09.22.57.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.22.57.png)

### RAD

Rapid application developement. Adattamento del modello a cascata, ogni funzionalità che parallelizzo deve essere sviluppabile in meno di 3 mesi perchè deve essere rapid.

NON si usa quando:

- gli utenti non seguono
- il sistema è modularizzabile
- sono richieste alte prestazioni di ottimizzazione

![Screenshot 2024-11-12 at 09.25.42.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.25.42.png)

### Incrementale vs iterativo

Similarità:

- Entrambi più versioni successive del sistema.
- Ad ogni istante dopo il primo rilascio esiste una versione in esercizio e una versione in sviluppo

Differenze:

- *incrementale*: ogni versione aggiunge nuove funzionalità o sottosistemi
- *iterativo*: da subito sono presenti le funzionalità/sottosistemi di base che vengono successivamente raffinate e migliorate. I requisiti possono cambiare

## Modelli evolutivi

Sono iterativi, caratterizzati per consentire sviluppo di versioni sempre più complete del SW

si basano sulla prototipazione:

Obbiettivi:

- animare e dimostrare i requisiti
- addestramento dell’utente prima del pordotto finale

Benefici:

- Equivoci e funzionalità mancanti possono emergere
- Un sistema funzionante è subito disponibile e si possono derivare specifiche aggiuntive

![Screenshot 2024-11-12 at 09.33.24.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.33.24.png)

### Prototipazione evolutiva

ma i cambiamenti continui corrompono il sistema e il mantenimento è costoso, sono richieste grandi capacità e il tempo di vita è corto.

Sistemi in cui le specifiche non possono essere sviluppate in anticipo,

![Screenshot 2024-11-12 at 09.35.51.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.35.51.png)

### Prototipazione usa e getta

Non deve essere considerato un sistema finale perchè è creato per sperimentazione poi eliminato, e non è strutturato per essere mantenuto a lungo termine.

![Screenshot 2024-11-12 at 09.38.14.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.38.14.png)

### Modello a spirale

![Screenshot 2024-11-12 at 09.40.40.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.40.40.png)

Crescita incrementale del grado di definizione e implementazione del sistema.

### Model driven development

I modelli diventano la guida del processo di sviluppo, si creano modelli formali del sw che vengono fatti evolvere mentre il sw viene progettato e implementato.

![Screenshot 2024-11-12 at 09.45.08.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_09.45.08.png)

### Modelli agili

insieme di linee guida che trascurano la fragilità delle persone che realizzano il software. Cicli di operazioni incrementali consegnate velocemente al cliente. Ricerca della velocità, sconsigliato UML, semplicità di sviluppo. Comunicazione continua tra user e developer.

### Extreme programming

**Pianificazione**: definizione di User story, funzionalità del sistema. L’utente attribuisce priorità e il developer costo. Se user story impiega più di 3 settimane deve essere frammentata.

**Design:** massima semplicità, no funzionalità aggiuntive e uso di *schede CRC*. Se c’è un problema viene ideato uno spike, incoraggiando il refactoring. L’architettura viene rimessa in discussione ogni iterazione.

**Programmazione:** basata sul pair programming, due persone sulla stessa workstation.

**Testing:** test di regressione a ogni modifica del SW. testare tutto il SW ogni iterazione, perchè c’è la possibilità che le nuove funzionalità intacchino quelle testate in precedenza.

---

Dopo il primo rilascio il team calcola la velocità del progetto. Determinare se le user story sono state sottovalutate e modificano il contenuto e le date di consegna.

## Unified Process

CHI: una risorsa o un ruolo definisce il comportamento e le responsabilità di un gruppo

COSA: il comportamento è espresso intermini di attività e manufatti

QUANDO: Si modellano i flussi di lavoro, ossia le sequenze di attività.

### Manufatti

- Set di gestione
- Set dei requisiti (documenti visione)
- Set progettazione
- Set implementazione
- Set rilascio utenti (script installazione)

### Flussi di lavoro

![Screenshot 2024-11-12 at 10.11.55.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_10.11.55.png)

### Fasi

Le fasi sono sequenziali, e corrispondono a milestone significativi
per committenti, utenti, management

- Inception (avvio): definisce gli obiettivi del progetto, ne investiga la
fattibilità, ne stima i costi, il potenziale di mercato e i rischi, analizza i
prodotti concorrenti
- Elaboration: pianifica il progetto e ne definisce le caratteristiche
funzionali, strutturali e architetturali
- Construction: sviluppa il prodotto attraverso una serie di iterazioni,
effettua il testing, prepara la documentazione
- Transition: consegna il sistema agli utenti finali (include marketing,
installazione, configurazione, formazione, supporto, mantenimento)

## Verifica del software

Serve per controllare se il sistema corrisponde alle specifiche del progetto. La verifica segue passo passo il progetto.

- **Dinamiche o di testing**, verifica lanciando il sw
- **Statiche o di analisi,** analizzando la struttura e i moduli.

### Testing in the **Small**

parto dalle operazioni più critiche

![Screenshot 2024-11-12 at 10.41.52.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-12_at_10.41.52.png)

- Criterio di copertura dei programmi (statement test) garantire che un’operazione viene eseguita almeno una volta.
- Criterio di copertura delle decisioni (branch test), controllare che almeno ogni nodo del grafo di controllo deve essere toccato almeno una volta.
- Criterio di copertura delle decisioni e delle condizioni, per ogni predicato composto devo valutare almeno una volta un sottopredicato true e una volta false.

### **Testing in the Large**

Tecnica black-box, analizzando le corrispondenze input-output.

- test di modulo → correttezza modulo in base a comportamento esterno
- test d’integrazione → comportamento di sottoparti. Utile per scoprire eventuali bug durante lo sviluppo.
- test di sistema → verifica il comportamento intero

### Code inspection/ Code walk-through

eseguita da un team di persone che dopo aver selezionato opportune porzioni del codice e opportuni valori di input ne simulano su carta il comportamento.

### Analisi flusso dati

Tipo particolare di code inspection, Analisi dell’evoluzione del valore associato alle variabili durante l’esecuzione di un programma. Ad ogni comando è possibile associare staticamente il tipo di operazioni eseguite sulle variabili:

definizioni d, usi u, annullamenti a.

## Certificazione

Significa che un ente riconosciuto dichiara che un prodotto è conforme a una specifica o norma, attraverso l’accreditamento mediante prove in laboratorio.

Attraverso normativa ISO 9000 che ha due obbiettivi principali:

- Gestione per la qualità → guida per aziende che progettano un sistema di qualità, per migliorare le attività e i processi.
- Assicurazione della qualità → requisiti generali a fronte dei quali il cliente valuta l’adeguatezza di un sistema

![Screenshot 2024-11-13 at 15.46.19.png](Ingegneria%20SW%2013c3dd22936380debac1d4bb83423063/Screenshot_2024-11-13_at_15.46.19.png)

## Manutenzione

- Correttiva → correzzione errori
- Adattiva → quando mutano le condizioni di utilizzo del sw, es nuova normativa.
- Perfettiva → migliora qualitativamente le caratteristiche funzionali o tecniche del sistema, es algoritmo più efficiente.
- Evolutiva → miglioramento quantitativo delle caratteristiche
