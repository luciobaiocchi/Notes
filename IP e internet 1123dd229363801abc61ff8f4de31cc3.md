# Appunti reti

## IP e internet

### Composizione Indirizzo IP

IP→ Progettato per funzionare a commutazione di pacchetto in modalità connectionless.

identifica Host e router tramite indirizzi di lunghezza fissa, raggruppandoli in reti IP.
****

![Screenshot 2024-10-01 at 16.49.03.png](/img/Screenshot_2024-10-01_at_16.49.03.png)

**Version**→ indica il formato dell’intestazione, attualmetne 4

**IHL** **→** ip header length, lunghezzza dell’intestazione. 

**Type of service →**  tipo di servizio richiesto, usato anche come sorta di priorità

**Total length →** lunghezza totale del datagramma 

**Identification →** valore intero che identifica univocamente il datagramma (pacchetto).

**Flag →** 
### Funzioni

| Funzione            | Descrizione                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `Version`           | Indica il formato dell’intestazione, attualmente 4                           |
| `IHL`               | IP header length, lunghezza dell’intestazione                                |
| `Type of service`   | Tipo di servizio richiesto, usato anche come sorta di priorità               |
| `Total length`      | Lunghezza totale del datagramma                                             |
| `Identification`    | Valore intero che identifica univocamente il datagramma (pacchetto)          |
| `Flag`              | Vari flag utilizzati per il controllo della frammentazione dei pacchetti     |

---

![Se non posso frammentare il pacchetto lo distruggo. ](/img/Screenshot_2024-10-02_at_13.39.55.png)

Se non posso frammentare il pacchetto lo distruggo. 

**Fragment offset→** indica quale è la posizione di questo frammento (della dimensione di 8 byte , 64 bit)nel datagramma, come distanza dall’inizio. Il numero logico del primo blocco viene scritto nel Fragment Offset del datagramma 

**Implementazione frammentazione:** 

- Effettuata da qualsiasi apparato di rete dotato di protocollo.
- I nodi intermedi non riassemblano, solo il terminale ricevente
- Sono possibili frammentazioni multiple

Grazie alla numerazione tramite offset permette di rinumerare facilmente i segmenti.

> La segmentazione è fondamentale perché non sempre la dimensione del pacchetto è corretta per essere elaborata dai macchinari disponibili sulla rete
> 

**Riassemblamento** 

![Screenshot 2024-10-02 at 13.55.55.png](/img/Screenshot_2024-10-02_at_13.55.55.png)

**Time to travel (TTL)→** max numero nodi attraversabili

**Protocol→** quale protocollo di livello superiore appartengono i dati del datagramma

**Header checksum→** controllo di errore di intestazione. Ricalcolato da ogni nodo attraversato dal datagramma

**Source and Destination→** indirizzi sorgente e destinazione

**Options→** lunghezza variabile perché contiene opzioni relative al trasferimento 

**Padding→** bit inutili per fare tornare intestazione multiplo di 32 bit

## Instradamento IP

Internet → rete a commutazione di pacchetto, con più percorsi disponibili

Come funziona internet → Rete di reti.

### Network IP → componente elementare

Una sorta di isola che contiene calcolatori che fanno da **Host** 

**Gateway o Router** → componenti che fanno da ponte.

Ogni Network IP viene implementata con una tecnologia specifica, per esempio : 

- Wi-Fi
- Ethernet, cavo breve distanza locale
- ADSL e xDSL, cavo a media distanza
- **GPRS/EDGE/LTE,** radio media distanza

I calcolatori di una network IP devono potersi scambiare pacchetti in modo diretto tra di loro. 

![Screenshot 2024-10-04 at 11.35.42.png](/img/Screenshot_2024-10-04_at_11.35.42.png)

> **La tecnologia IP è agnostica rispetto alla tecnologia
con cui sono realizzate le network**
> 

Quindi non dipende dalla tipologia di tecnologia utilizzata 

Quando un terminale invia un pacchetto ha due alternative:

- Dentro la network **→** **Direct delivery**
- Fuori network, usando gateway **→** **Indirect delivery**

La scelta è binaria, ma deve essere fatta in poco tempo. 

Ogni nodo ha una base di dati che contiene la lista degli ip che può raggiungere

I collegamenti fra router vengono visti come network 

![Screenshot 2024-10-04 at 11.45.55.png](/img/Screenshot_2024-10-04_at_11.45.55.png)

### Invio pacchetto

1. Il **calcolatore** **instrada** il pacchetto verso il router
2. il **router** decide che direzione seguire e **instrada nuovamente** il pacchetto 
- Un salto viene detto **hop**

### Semantica indirizzo IP

Due parti : 

- Network ID → identifica network di appartenenza
- Host ID → identifica l’host vero e proprio (interfaccia) contenuto nella network

Per entrambi vengono usati bit contigui.

![Screenshot 2024-10-04 at 11.59.51.png](/img/Screenshot_2024-10-04_at_11.59.51.png)

000000 e 111111 sono due numeri speciali e non possono essere usati come Host id

Per ogni elemento hardware che si connette a una rete è necessario avere un IP

IP è un indirizzo locator, che indica la posizione.

**Net Mask** → deve essere configurata localmente. Calcolatori della stessa network devono avere la stessa Net Mask

## Instradamento

### Diretto

Una consegna **diretta** avviene quando l'IP sorgente e destinatario sono nella stessa rete. In questo caso, il pacchetto viene inviato utilizzando il MAC del destinatario, che viene trovato tramite il protocollo ARP se non già noto. ARP effettua una richiesta broadcast per associare l'IP al MAC corretto.

### Indiretto

Nella consegna **indiretta**, quando l'IP destinatario è su un'altra rete, il pacchetto viene prima inviato al router della rete sorgente. A livello di collegamento dati, il MAC sarà quello del router, che instraderà il pacchetto verso il prossimo router fino a raggiungere la rete di destinazione. Il TTL limita il numero massimo di salti. Anche nei passaggi indiretti, ARP viene utilizzato per ottenere il MAC del gateway successivo.

### Tabella di instradamento

Ogni nodo, che sia un host o un router, possiede una tabella di instradamento che descrive come gestire i pacchetti in rete. Questa tabella contiene diverse informazioni essenziali, organizzate in cinque colonne principali:

1. **Destination**: Indica gli IP o i gruppi di IP raggiungibili. in forma di singoli o insiemi
2. **Netmask**: Specifica la netmask per interpretare correttamente l'IP e identificare la rete.
3. **Gateway**: Mostra l'IP del gateway successivo (o se è l'host finale, può indicare il proprio IP o "self").
4. **Interface**: Definisce l'interfaccia di rete attraverso cui inviare il pacchetto e da cui eseguire richieste ARP, se necessario.
5. **Metric**: Rappresenta il costo del percorso, aiutando a scegliere il percorso migliore quando esistono più opzioni di instradamento.

![Screenshot 2024-10-23 at 13.43.14.png](/img/Screenshot_2024-10-23_at_13.43.14.png)

### Table look-up

Per selezionare la riga corretta vengono fatti 2 passaggi:

- Selezione ip destinazione da **datagramma**
- AND bit a bit con il relativo ip attraverso la **netmask** di ogni riga e viene selezionato il primo corretto.

la riga numero 1 è quella di default, perchè AND è sempre 0.0.0.0

![Screenshot 2024-10-23 at 14.00.17.png](/img/Screenshot_2024-10-23_at_14.00.17.png)

![Screenshot 2024-10-23 at 14.35.26.png](/img/Screenshot_2024-10-23_at_14.35.26.png)

il router ha lo stesso net-id mio e come ultimo numero ha 254, ma più generalmente il numero massimo di host-id. 

Qual’è la configurazione minima dell’interfaccia IP?

numero ip e netmask

![Screenshot 2024-10-24 at 10.33.53.png](/img/Screenshot_2024-10-24_at_10.33.53.png)

settando delle netmask apposite posso creare una aggregazione di righe (aggregazione di rotte). nel caso di r2 è comodo perchè ho solo due instradazioni possibili e posso ottimizzare gli AND da fare. Si può fare solo se sono righe contigue.

![Screenshot 2024-10-24 at 10.36.31.png](/img/Screenshot_2024-10-24_at_10.36.31.png)

Le righe delle tabelle di route vanno ordinate, per dare precedenza alle route più specifiche.

### Intervalli di indirizzi

Inizialmente, gli indirizzi IP erano suddivisi in classi (A, B, C, D, E) con netmask implicite e fisse che limitavano la flessibilità nella gestione degli indirizzi. Questo sistema rigido causava inefficienze e sprechi di indirizzi. Per risolvere questi problemi, è stato introdotto il Classless Inter-Domain Routing (CIDR), che utilizza netmask variabili, espresse in notazione slash (ad esempio, /24). CIDR consente una suddivisione più efficiente e flessibile degli indirizzi IP, supportando anche il supernetting per ridurre la complessità delle tabelle di routing e migliorare l’efficienza e la scalabilità della rete.

### Supernetting

la soluzione è stata quella di utilizzare reti più piccole con indirizzi consecutivi, per ottimizzare l’utilizzo degli indirizzi.  Lo stesso indirizzo può essere interpretato diversamente in base a dove si trova nella rete, quindi le tabelle di instradamento devono



## Metodologie di filtraggio dei datagrammi
### Packet filter
I nodi di rete eseguono delle operazioni di tipo attivo sui dati, generalmente per scopi di filtraggio. Quindi in nodi assumono un ruolo attivo nell'instradamento.


##### Come si fa?
l'instradamento selettivo viene fatto attraverso un packet filter, che instrada solo alcuni pacchetti che rispettano le caratteristiche indicate. I filtri operano a livello IP, quindi il filtro si basa al massimo sull'header IP, es: pacchetti con questo TTl passano e altri no.
Viene fatto attraverso tabelle affiancate a tabelle di indirizzamento.

##### Che vantaggio ha ?
dal punto di vista architetturale è in linea ai soliti protocolli (OSI).

### Statefull packet inspection

<img src="./img/049_statefull_packet_inspection.png" alt="Diagramma di rete" width="500"/>

Utilizzano informazioni prese dagli header di livello superiore (es : numero di porta utilizzata ecc...) 
Questa operazione "viola" l'idea del protocollo iso-osi.

### Application layer gateway (proxy)

<img src="./img/050_application_layer_gateway.png" alt="Diagramma di rete" width="500"/>

Da più funzionalità possibili ma è anche il più dispendioso di tutti perchè controlla tutto il pacchetto (livello 3 e 4).
Posso anche decidere di fare passare solo determinati protocolli 
(FTP HTTP)

#### Firewall

Protegge interno da esterno ed esterno da interno. Solitamente è una combinazione di packet filter, statefull packet inspection, e ALG.


#### Nat

Gateway che filtra pacchetti, statefull packet inspection tra due network, e modifica i pacchetti modificando gli indirizzi.
È un concetto, ma ci sono molte implementazioni diverse. 

<img src="./img/Screenshot 2024-10-30 at 17.29.58_nat.png" alt="Diagramma di rete" width="500"/>

Il nat permette anche di modificare il verso dei pacchetti, permettendo a quelli che sono dentro di parlare all'esterno, mentre quelli all'esterno possono parlare solo se hanno ricevuto una richiesta.
Oggi è concepito come uno strumento di protezione, ma inizialmente è nato perchè stavano finendo i numeri IP. Infatti tutti quelli che stanno alla sinistra del NAT possono essere visti come lo stesso numero IP.
NAPT -> traduce anche i nueri di porta.
Esistono degli **indirizzi privati**, che vengono utilizzati storicamente solo per essere attribuiti all'interno dei NAT.

| Tipo di Indirizzo | Descrizione |
|-------------------|-------------|
| Pubblico          | Utilizzato per comunicare su Internet |
| Privato           | Utilizzato all'interno di una rete locale |



## Instradamento nelle reti a pacchetto e in Internet

Scelta del percorso = scegliere il nodo successivo sapendo che esiste una connessione 
Tutte le metodologie di instradamento si devono adattare a modifiche della rete in due modi:

- dinamici -> percosi aggionrati periodicamente per sopportare anche cambiamenti repentini
- statico -> i percorsi vengono aggiornati e nel breve periodo non cambiano

### Algoritmi di instradamento 
I nodi di commutazione per applicare l’algoritmo possono utilizzare informazioni predisposte localente tipicamente sotto forma di tabelle


#### Senza tabella:

##### Flooding (broadcast)
Pro:

- ogni nodo ritrasmette tutte le porte in uscita ogni pacchetto ricevuto
- Praticamente non c'è elaborazione
- il primo che arriva -> strada più breve

Contro:
I pacchetti proliferano in maniera esponenziale.
Soluzioni :

- fare si che i pacchetti non ritornano da dove sono venuti
- aggiungere TTl

##### Random 
Poco usato perchè poco efficiente.

##### Deflection Routing (hot potato)
Il pacchetto viene inviato all aporta con meno pacchetti in fila da inviare. 
Per reti con spazio e risorse limitate.
Problemi: possibili pacchetti che girano all'infinito e potrebbero non arrivare in ordine 


#### Con tabella 
instradamento principalmente statico  
Linee di ingresso -> funzione di instradamento -> linee di uscita 

Il pacchetto viene prima memorizzato interamente nel nodo e quindi ritrasmesso nella direzione opportuna
In generale dovrebbe esistere una base dati per il confronto che è la tabella di instradamento

##### Shortest path routing
Ogni nodo ha una lunghezza, difficoltà per attraversare due punti.
Per implementare il routing shortest path verso una qualunque destinazione devono utilizzare:

- Uno o più **protocolli** di routing per scambiarsi informazioni ed apprendere la topologia della rete
- Uno o più **algoritmi** per il calcolo degli SP sulla base delle informazioni ottenute

<img src="./img/tabella_routing_esempio_1.png" alt="Diagramma di rete" width="500"/>


<br>

---

<br>








### Broadcast livello 2
In informatica, un broadcast di livello 2 si riferisce a una trasmissione dati all'interno del livello Data Link (Livello 2) del modello OSI, che coinvolge tutti i dispositivi collegati nella stessa rete locale (LAN).

In pratica, il broadcast di livello 2 invia un messaggio a tutti i dispositivi connessi a un segmento di rete, senza una destinazione specifica. Il messaggio viene inviato all'indirizzo MAC di broadcast (FF:FF:FF:FF:FF:FF), che tutti i dispositivi all'interno della rete ascoltano e ricevono. Un esempio comune è l'uso del broadcast per la risoluzione dell'indirizzo IP tramite ARP (Address Resolution Protocol), in cui un dispositivo chiede a tutti i dispositivi della rete se possiedono un determinato indirizzo IP.

I broadcast di livello 2 sono limitati alla rete locale e non vengono inoltrati dai router a meno che non siano configurati in modo specifico per farlo, mantenendo il traffico di broadcast contenuto all'interno di una singola LAN.

### 1. DHCP (Dynamic Host Configuration Protocol)

- **Funzione**: Il DHCP si occupa di assegnare automaticamente gli indirizzi IP ai dispositivi connessi a una rete.
- **Come funziona**: Quando un dispositivo si collega a una rete, invia una richiesta di DHCP. Il server DHCP risponde con un indirizzo IP disponibile, una subnet mask, un gateway, e altre configurazioni di rete (come i DNS).
Livello del modello OSI: Lavora a livello Applicazione (Livello 7).
- **Obiettivo**: Assicurare che ogni dispositivo connesso alla rete ottenga un indirizzo IP unico e una configurazione di rete corretta senza la necessità di configurazioni manuali.

### 2. ARP (Address Resolution Protocol)

- **Funzione**: ARP è utilizzato per tradurre un indirizzo IP in un indirizzo MAC (fisico) in una LAN.
- **Come funziona**: Quando un dispositivo conosce l’indirizzo IP di un altro dispositivo nella rete locale ma non il suo indirizzo MAC, invia una richiesta ARP in broadcast. Il dispositivo destinatario risponde con il proprio indirizzo MAC, permettendo così la comunicazione a livello di collegamento dati.
Livello del modello OSI: Lavora a livello Collegamento Dati (Livello 2) ma può anche interagire con il Livello di Rete (Livello 3).
- **Obiettivo**: Consentire la comunicazione tra dispositivi in una rete locale traducendo indirizzi IP in indirizzi MAC, necessari per l’instradamento dei pacchetti a livello di collegamento dati.

#### Differenze Chiave

- **Funzione**: DHCP assegna indirizzi IP e configurazioni di rete, mentre ARP traduce indirizzi IP in indirizzi MAC.
- **Livello OSI**: DHCP opera a livello Applicazione, mentre ARP opera a livello Collegamento Dati.
- **Ambito di utilizzo**: DHCP è usato per l'assegnazione iniziale della configurazione di rete; ARP è usato per risolvere indirizzi IP in MAC all'interno della stessa rete locale.
In sintesi, DHCP fornisce gli indirizzi IP, mentre ARP permette di individuare l'indirizzo MAC associato a un IP specifico per comunicare nella LAN.

### Livelli iso-osi
Il modello **ISO/OSI** è uno standard di riferimento per la comunicazione di rete che organizza le funzioni di rete in 7 livelli distinti, ognuno dei quali ha un ruolo specifico nel processo di trasmissione e ricezione dei dati. Ecco una panoramica dei livelli:

1. **Livello Fisico**: Definisce le caratteristiche fisiche della trasmissione (cavi, frequenze, segnali elettrici) e il modo in cui i dati sono trasmessi fisicamente tra dispositivi.

2. **Livello Collegamento Dati**: Gestisce la comunicazione tra due dispositivi collegati direttamente, organizzando i dati in frame e garantendo che non ci siano errori di trasmissione tra i nodi.

3. **Livello Rete**: Gestisce l'instradamento dei pacchetti di dati attraverso la rete, trovando il percorso migliore tra mittente e destinatario. Utilizza indirizzi IP.

4. **Livello Trasporto**: Fornisce la consegna affidabile dei dati, segmentandoli e garantendo il loro corretto ordine di arrivo. Include protocolli come TCP e UDP.

5. **Livello Sessione**: Gestisce l’inizio, la gestione e la terminazione delle sessioni di comunicazione tra applicazioni, mantenendo aperta una connessione per lo scambio continuo di dati.

6. **Livello Presentazione**: Si occupa della formattazione e della traduzione dei dati per renderli comprensibili all'applicazione, ad esempio, codificando e decodificando i dati (come la crittografia).

7. **Livello Applicazione**: È il livello più alto e interagisce direttamente con il software applicativo. Include protocolli come HTTP, FTP e SMTP, che permettono all’utente di accedere ai servizi di rete.

In sintesi, ogni livello del modello OSI è responsabile di una parte specifica della comunicazione, e tutti insieme permettono la trasmissione ordinata e affidabile dei dati tra dispositivi diversi.
