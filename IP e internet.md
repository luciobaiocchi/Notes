# Appunti reti

- [Appunti reti](#appunti-reti)
  - [IP e internet](#ip-e-internet)
    - [Composizione Indirizzo IP](#composizione-indirizzo-ip)
    - [Funzioni](#funzioni)
  - [Instradamento IP](#instradamento-ip)
    - [Network IP → componente elementare](#network-ip--componente-elementare)
    - [Invio pacchetto](#invio-pacchetto)
    - [Semantica indirizzo IP](#semantica-indirizzo-ip)
  - [Instradamento](#instradamento)
    - [Diretto](#diretto)
    - [Indiretto](#indiretto)
    - [Tabella di instradamento](#tabella-di-instradamento)
    - [Table look-up](#table-look-up)
    - [Intervalli di indirizzi](#intervalli-di-indirizzi)
    - [Supernetting](#supernetting)
  - [Metodologie di filtraggio dei datagrammi](#metodologie-di-filtraggio-dei-datagrammi)
    - [Packet filter](#packet-filter)
        - [Come si fa?](#come-si-fa)
        - [Che vantaggio ha ?](#che-vantaggio-ha-)
    - [Statefull packet inspection](#statefull-packet-inspection)
    - [Application layer gateway (proxy)](#application-layer-gateway-proxy)
      - [Firewall](#firewall)
      - [Nat](#nat)
  - [Instradamento nelle reti a pacchetto e in Internet](#instradamento-nelle-reti-a-pacchetto-e-in-internet)
    - [Algoritmi di instradamento](#algoritmi-di-instradamento)
      - [Senza tabella:](#senza-tabella)
        - [Flooding (broadcast)](#flooding-broadcast)
        - [Random](#random)
        - [Deflection Routing (hot potato)](#deflection-routing-hot-potato)
      - [Con tabella](#con-tabella)
        - [Shortest path routing](#shortest-path-routing)
          - [Cosa succede se la rete si modifica?](#cosa-succede-se-la-rete-si-modifica)
    - [Routing link state](#routing-link-state)
    - [Cosa sono i nodi](#cosa-sono-i-nodi)
      - [Ruolo router](#ruolo-router)
        - [Tabella routing e forwarding](#tabella-routing-e-forwarding)
  - [Internet moderna](#internet-moderna)
    - [ISP internet service provider](#isp-internet-service-provider)
      - [IGP](#igp)
      - [RIP come funziona](#rip-come-funziona)
      - [OSPF (Open Shortest Path First)](#ospf-open-shortest-path-first)
        - [Caratteristiche principali di OSPF:](#caratteristiche-principali-di-ospf)
        - [Componenti chiave:](#componenti-chiave)
        - [Utilizzi principali:](#utilizzi-principali)
        - [Configurazione iniziale](#configurazione-iniziale)
    - [Pacchetti HELLO](#pacchetti-hello)
      - [Campi dei Pacchetti HELLO](#campi-dei-pacchetti-hello)
    - [EXCHANGE protocol](#exchange-protocol)
    - [Flooding Protocol](#flooding-protocol)
      - [Modalità di Flooding](#modalità-di-flooding)
    - [Exterior Gateway Protocols (EGP)](#exterior-gateway-protocols-egp)
    - [Protocolli EGP per Internet](#protocolli-egp-per-internet)
      - [EGP](#egp)
      - [Limiti di EGP](#limiti-di-egp)
    - [BGP: Border Gateway Protocol](#bgp-border-gateway-protocol)
      - [Caratteristiche principali di BGP:](#caratteristiche-principali-di-bgp)
        - [Attributi](#attributi)
  - [Commutazione di etichetta: MPLS](#commutazione-di-etichetta-mpls)
    - [Label Switching](#label-switching)
    - [label stacking](#label-stacking)
    - [label allocation](#label-allocation)
  - [Reti Overlay](#reti-overlay)
    - [Header](#header)
    - [VXLAN](#vxlan)
    - [Reti private](#reti-private)
      - [Roda warrior](#roda-warrior)
      - [VPN rete a rete](#vpn-rete-a-rete)
        - [IPsec](#ipsec)
  - [Strato fisico](#strato-fisico)
    - [Attenuazione](#attenuazione)
    - [Rame](#rame)
      - [Coppie Intrecciate (Twisted Pair)](#coppie-intrecciate-twisted-pair)
        - [Tipologie](#tipologie)
        - [Miglioramenti](#miglioramenti)
        - [Categorie (dalla Cat. 1 alla Cat. 7):](#categorie-dalla-cat-1-alla-cat-7)
      - [Cavo Coassiale](#cavo-coassiale)
        - [Multiplazione a divisione di frequenza (FDM):](#multiplazione-a-divisione-di-frequenza-fdm)
    - [Comunicazioni Radio](#comunicazioni-radio)
    - [Sistemi Satellitari](#sistemi-satellitari)
    - [Sistemi Cellulari](#sistemi-cellulari)
      - [Considerazioni](#considerazioni)
  - [Funzionalità e prestazioni](#funzionalità-e-prestazioni)
    - [Prestazioni](#prestazioni)
      - [Richieste perdute](#richieste-perdute)
      - [Utenti e servizi](#utenti-e-servizi)
        - [PDU (protocoll data unit)](#pdu-protocoll-data-unit)
      - [Frequenza di servizio](#frequenza-di-servizio)
        - [esempio](#esempio)
      - [Traffico](#traffico)
    - [Prestazioni Ideali per un Protocollo Data Link](#prestazioni-ideali-per-un-protocollo-data-link)
    - [Capacità Effettiva $(C\_e)$](#capacità-effettiva-c_e)
    - [Valutazione efficienza](#valutazione-efficienza)
  - [Reti commutate: il sistema a coda con singolo servitore](#reti-commutate-il-sistema-a-coda-con-singolo-servitore)


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

Il problema di questi algormitmi è che il tempo di convergenza è generalmente pari al numero dei nodi della rete e non è particolarmente conveniente.
Se la rete è grande ci vuole troppo tempo, c'è la possibilità che la rete cambi prima del tempo di convergenza. Non si possono mandare sempre messaggi con distance
vector, per una questione di prestazioni e vengono mandati periodicamente.

###### Cosa succede se la rete si modifica?

<img src="./img/Screenshot_2024-11-25_at_21.19.17.png" alt="Bouncing effect" width="500"/>


- **bouncing effect** la convinzione che un certo router per inviare pacchetti a un altro deve mandarli a lui e poi farseli rispedire indietro.
- **convergenza lenta** la possibilità che anche in una rete con 3 nodi ci si mettano anche 20/30 scambi di distance vector
- **count to infinity** nel caso di tre router collegati in fila A--B--C. 

SOLUZIONI  (temporanee): 

- Decidere una distanza massima, che se raggiunta viene considerata infinito
- Triggered update -> un nodo deve inviare immediatamente notifiche ai vicini nel caso di modifiche di rete.
ma considerando il ritardo di propagazione non c'è comunque la certezza che le informazioni arrivino in tempo
- Split horizon ->  nodo A dice a B tutti i nodi che raggiunge senza passare da B

ma queste soluzioni non sono complete, nel caso di reti circolari ci sono comunque ancora errori

### Routing link state
L'idea è che ogni nodo conosca il grafo della rete e calcola le tabelle di routing in modo ottimale.
Sembra più difficile ma si è verificato molto più efficacie. 

1.  HELLO PACKET Il router scopre i vicini 
2.  ECHO PACKET invio per stimare la distanza
3.  in seguito ogni odo costituisce i LINK STATE PACKET, e li invia nella rete, questi pacchetti contengono la lista dei suoi vicini e le lunghezze dei collegamenti da raggiungere

I pacchetti vengono diffusi nella rete attraverso il Flooding. 

### Cosa sono i nodi
 
i nodi di commutazione vengono chiamati router, e si dividono in macro famiglie:

- SOHO (small office and home) 100 mbs, utilizzo casalingo
- Router di accesso, molte porte non velocissime, raccoglie gli abitanti di una certa zona 
- Router di acceso collegati con campus router. Medie dimensioni, non troppe porte ma molta velocità
- backbone router, router con poche porte con velocità ancora più elevata e garanzie di affidabilità

#### Ruolo router
- routing
    -  Scambio informazioni
    - elaborazione locale
    - popolaizone tabelle routing 
- forwarding
    - ip 
    - table lookup 
    - header update
- Switch
    - trasferimento datagramma da input a output
- trasmissione
    - Trasmissione usando il mezzo fisico 

##### Tabella routing e forwarding

La routing table è usata dai router per determinare il percorso ottimale verso una destinazione, memorizzando informazioni come reti, metriche e next-hop per ciascun possibile percorso. È il risultato di algoritmi di routing (es. OSPF, BGP).

La forwarding table (o forwarding information base, FIB) è una versione ottimizzata della routing table, usata direttamente per inoltrare i pacchetti. Contiene solo le informazioni necessarie per decidere il next-hop e agisce più velocemente, spesso mantenuta in hardware.

**RIB** = routing information base, insieme di tutte le informazioni che riguardano il routing e a cui bisogna credere.
Possono essere configurate manaualmente, staticamente o attraverso determinati algoritmi o protocolli. la politica con cui vengon inserite le informazioni nella rib possono essere variabili.

dopo il rib si applica il route selection process, per selezionare le route migliori 

**FIB** in seguito si compila la route forwarding table che contiene le informazioni filtrate e ottimizzate 

## Internet moderna 
Insieme di sottoninsiemi (autonomus sistem), ordinati con un numero identificativo. 
Si assume che valgano solo i nodi che fanno parlare un sottoinsieme con l'esterno, e in questo modo si semplifica il grafo della rete.
Si scompone anche il problema all'interno (intra Domain) dell'autonomus sistem e all'esterno di esso(inter Domain).

**autonomus sistem** insieme di router che utilizzano stesso protocollo di comunicazione. Oggi viene usata una terminologia più precisa:
Oggi un AS è:
- Un insieme di prefissi di rete IP (network IP definite secondo
la logica CIDR)
- Gestito in modo unitario e con una ben definita politica di routing
- Questo significa che chi gestisce l’AS ha definito in modo chiaro al suo interno come raggiungere le network IP

Un AS importa le informazioni di routing da solo determinati AS certificati.
RADb -> database contenente le politiche di routing 

### ISP internet service provider
Una associazione che fornisce servizi di connnettività, web e mail hosting, registrazione e noleggio di indirizzi IP. Può essere a fini di lucro o no e coperativa o no. Tipocamente un ISP è un AS.

**Internet region** una porzione di internet contenuta in una determinata area. 

Tipologie di ISP:
- Tier 1 ISP (più grandi tipo tim, collegato a internet globale)
- Tier 2 ISP (più piccoli che passano per tier 1 per andare a internet globale)
- Tier 3 o local ISP (vengono aiutati da livello 1 o 2 comprando servizi)

**PEERING** collegamento tra ISP, con lo scopo di scambiare servizi
**POP** Nelle reti, un PoP (Point of Presence) è un punto di accesso fisico che consente la connessione a una rete, come un ISP (Internet Service Provider) o una rete aziendale. 
**Internet Exchange Point (IX o IXP)**
- Infrastrutture attraverso le quali gli ISP possono stabilire
relazioni di peering
- L’IXP è costruito per permettere l’interconnessione diretta degli AS senza utilizzare reti di terze parti
- L’IXP fornisce soluzioni di connettività con specifiche garanzie di qualità (disponibilità elevata, sicurezza fisica, banda garantita ecc.)



#### IGP

Un IGP **(Interior Gateway Protocol)** è un protocollo di routing utilizzato per instradare il traffico all’interno di un’unica rete autonoma, chiamata AS (Autonomous System). È progettato per gestire la comunicazione tra router appartenenti alla stessa organizzazione o dominio amministrativo.

Esempi di IGP:
- OSPF (Open Shortest Path First), basato sullo stato dei collegamenti (link-state).
- RIP (Routing Information Protocol), basato sulla distanza (distance-vector).
    Il RIP (Routing Information Protocol) è un protocollo di routing dinamico basato sull’approccio distance-vector, progettato per reti IP di piccole dimensioni. È uno dei protocolli di routing più semplici ed è stato ampiamente utilizzato in passato, anche se oggi è meno comune a causa delle sue limitazioni.
- EIGRP (Enhanced Interior Gateway Routing Protocol), un protocollo ibrido.

L’IGP si differenzia dai EGP (Exterior Gateway Protocols), come BGP, che gestiscono il routing tra AS differenti.


#### RIP come funziona

1.	**Metriche del percorso:**
•	Utilizza il conteggio dei salti (hop count) come metrica per determinare il percorso migliore.
•	Ogni router aggiunge un salto alla distanza e il limite massimo è di 15 salti (il 16° indica che la destinazione è irraggiungibile).
2.	**Scambio di informazioni:**
•	Ogni router invia periodicamente (default: ogni 30 secondi) la propria tabella di routing ai router adiacenti tramite messaggi broadcast o multicast.
•	I router aggiornano le proprie tabelle di routing basandosi sulle informazioni ricevute, selezionando il percorso con il minor numero di salti.
3.	**Aggiornamenti periodici:**
•	RIP invia aggiornamenti anche se non ci sono cambiamenti nella rete, il che può causare overhead.
4.	**Meccanismi di stabilità:**
•	Split horizon: Evita di pubblicizzare un percorso indietro verso il router da cui è stato appreso.
•	Hold-down timer: Impedisce aggiornamenti troppo frequenti per evitare instabilità.
•	Poison reverse: Annuncia che un percorso non è più raggiungibile, impostando la metrica a 16.

**Versioni di RIP:**

•	**RIP v1:** Supporta solo subnet classful (senza subnet mask).
•	**RIP v2:** Aggiunge supporto per reti classless (CIDR), autenticazione e multicast.

**Limiti di RIP:**

•	Scalabilità ridotta (massimo 15 salti).
•	Lento nel convergere rispetto a protocolli più moderni come OSPF o EIGRP.
•	Overhead causato dagli aggiornamenti periodici.

Utilizzo attuale:

RIP è ormai superato da protocolli più efficienti e scalabili, ma viene ancora usato in reti semplici o per scopi didattici.

#### OSPF (Open Shortest Path First) 

È un protocollo di routing dinamico utilizzato nei sistemi autonomi per instradare i pacchetti all’interno di una rete. È uno dei più comuni (tra gli IGP), progettati per operare all’interno di una singola organizzazione o rete.

##### Caratteristiche principali di OSPF:

1. **<details><summary> Protocollo di routing a stato di collegamento (Link-State): </summary>**
    Un protocollo di routing a stato di collegamento crea una mappa completa della rete, condividendo informazioni sui collegamenti tra i router tramite pacchetti LSA. Ogni router calcola il percorso migliore verso ogni destinazione utilizzando un algoritmo come Dijkstra. Questo approccio garantisce una convergenza rapida, aggiornamenti selettivi e maggiore efficienza, rendendolo ideale per reti complesse. Esempi comuni sono OSPF e IS-IS.
    </details> OSPF utilizza un approccio basato su mappature dettagliate della rete. Ogni router crea una rappresentazione della topologia completa e calcola i percorsi migliori utilizzando l’algoritmo di Dijkstra.

2.	**Routing senza classe:**
Supporta subnet di dimensioni variabili grazie all’uso del VLSM (Variable Length Subnet Mask), permettendo un uso efficiente degli indirizzi IP.
3.	**Scalabilità:**
Può gestire reti grandi suddividendole in aree gerarchiche, riducendo il carico di elaborazione e la dimensione delle tabelle di routing.
4.	**Convergenza rapida:**
Rispetto ai protocolli basati su vettore di distanza (come RIP), OSPF converge rapidamente in caso di cambiamenti nella rete.
5.	**Metriche basate sulla larghezza di banda:**
Determina il percorso migliore in base alla capacità di throughput dei collegamenti, non al numero di hop.
6.	**Aggiornamenti efficienti:**
Invia aggiornamenti solo quando ci sono cambiamenti, anziché inviare l’intera tabella di routing periodicamente.


##### Componenti chiave:

- **Router ID:** Identificatore univoco per ogni router nella rete OSPF.
    **Router catalogati come:**
    - **Internal Router:** router interni a ciascuna area
    - **Area Border Router:** router che scambiano informazioni con
    altre aree
    - **Backbone Router:** router che si interfacciano con il backbone
    - **AS Boundary Router:** router che scambiano informazioni con
    altri AS usando un protocollo EGP
- **Designated Router (DR):** Router eletto per centralizzare la distribuzione delle informazioni di stato dei collegamenti.
- **Backup Designated Router (BDR):** Router eletto per assumere il ruolo di DR in caso di fallimento del DR.
- **Area:** Una rete OSPF può essere divisa in aree per migliorare la scalabilità e l’efficienza. Tutte le aree devono essere connesse all’Area 0 (area backbone).
- **Hello Packets:** Pacchetti inviati periodicamente per stabilire e mantenere le adiacenze tra i router.
- **LSA (Link-State Advertisement):** Messaggi che trasportano informazioni sulla topologia della rete.
- **Database LSDB (Link-State Database):** Contiene le informazioni sulla topologia dell’intera rete OSPF.


<div style="text-align: center;">
  <img src="./img/Screenshot_2024-11-28_at_09.49.29.png" alt="Diagramma di rete" width="400"/>
</div>



##### Utilizzi principali:

- Grandi reti aziendali: Dove è richiesta scalabilità e convergenza rapida.
- Provider di servizi Internet: Per gestione reti interne.
- Ambienti misti: Dove si vogliono integrare diverse sottoreti con requisiti complessi.

OSPF è standardizzato dall’IETF (Internet Engineering Task Force) come parte della famiglia di protocolli TCP/IP ed è definito nell’RFC 2328.


##### Configurazione iniziale
ogni router ha un proprio Router-id. Come eleggere un router designato? inizialmente tutti i router si scambiano i propri vicini e vengono scartati quelli che hanno priorità 0. Viene designato tra i restanti quello con il numero più alto e diventa DR, quello subito dopo diventa il backup router BDR. Il DR diventa adiacente a tutti e diventa il punto di riferimento centrale  per la distribuzione delle informazioni di stato dei collegamenti (Link-State Advertisements, LSA) all'interno di una rete broadcast multi-access, come una rete Ethernet.

<div style="text-align: center;">
  <img src="./img/Screenshot_2024-11-28_at_10.11.50.png
" alt="Diagramma di rete" width="400"/>
</div>

### Pacchetti HELLO

I pacchetti HELLO sono inviati sulle interfacce periodicamente secondo quanto specificato dal parametro `HelloInterval`. Questi pacchetti permettono di:

- **Scoprire i propri vicini**: Includono una lista di tutti i vicini (Neighbor) dai quali è stato ricevuto un pacchetto HELLO recente (cioè non più vecchio di `RouterDeadInterval`). Questo permette di conoscere se per ciascun vicino è presente un collegamento bidirezionale e se esso è ancora attivo.

#### Campi dei Pacchetti HELLO

- **Router Priority, Designated Router e Backup Designated Router**: Utilizzati per l’elezione di DR e BDR.
- **Network Mask**: Indica la maschera relativa all’interfaccia del router (l’indirizzo è nell’header IP).
- **Options**: Indica se si supportano funzionalità opzionali.

### EXCHANGE protocol 
Sincronizzazione dei Link State Database

Una volta stabilite le adiacenze, i router adiacenti devono sincronizzare i rispettivi Link State Database (LSDB). La procedura è asimmetrica e prevede i seguenti passaggi:

1. **Stabilire Master e Slave**: Si determina quale router sarà il master e quale sarà lo slave.
2. **Invio dei Database Description (DD) Packets**: 
   - Il master invia pacchetti DD (Type = 2) con l'elenco dei LSA del proprio database (tipo, età, router generatore, numero di sequenza).
3. **Risposta dello Slave**: Lo slave risponde con l'elenco dei LSA del suo database.
4. **Confronto delle Informazioni**: Entrambi i router confrontano le informazioni ottenute con quelle in proprio possesso.
5. **Richiesta di LSA Meno Recenti**: Se un router ha LSA meno recenti, richiede i LSA aggiornati con un pacchetto Link State Request (Type = 3).

Questa procedura garantisce che entrambi i router abbiano una visione coerente della topologia della rete.

### Flooding Protocol

La diffusione dei LSA (Link-State Advertisements) a tutti i router della rete avviene tramite l'invio di pacchetti Link State Update (Type = 4) nei seguenti casi:

- Cambiamento nello stato di un collegamento
- Ricezione di una Link State Request
- Periodicamente (ogni 30 minuti)

#### Modalità di Flooding

- **Flooding Efficiente**: Utilizza i numeri di sequenza dei LSA per garantire che tutti i router vedano gli aggiornamenti.
- **Affidabilità**: Gli aggiornamenti vengono inviati ripetutamente finché non viene confermata la loro ricezione dai nodi adiacenti tramite il pacchetto Link State Acknowledgment (Type = 5).

Questa procedura assicura che tutti i router abbiano una visione aggiornata e coerente della topologia della rete.


### Exterior Gateway Protocols (EGP)

I protocolli di tipo EGP sono diversi da quelli di tipo IGP. Le principali differenze e caratteristiche includono:

- **Ottimizzazione dei Percorsi**: All'interno di un AS (Autonomous System) si persegue l'ottimizzazione dei percorsi.
- **Politiche di Instradamento**: Nel routing tra diversi AS, si deve tener conto delle politiche di instradamento:
  - Ogni AS vuole mantenere autonomia e indipendenza dagli altri.
  - Alcuni AS non permettono ad altri AS di instradare il traffico attraverso le loro reti.
  - In alcuni casi, bisogna operare secondo accordi internazionali.

### Protocolli EGP per Internet

Due protocolli EGP per Internet:

- **Exterior Gateway Protocol (EGP)**
- **Border Gateway Protocol (BGP)**

#### EGP

- **Primo protocollo di routing tra AS** (anni '80, RFC 827).
- **Funzionalità principali**:
  1. **Neighbor Acquisition**: Verifica accordi per diventare vicini.
  2. **Neighbor Reachability**: Monitora connessioni con i vicini.
  3. **Network Reachability**: Scambia informazioni sulle reti raggiungibili.


EGP è simile a un protocollo di tipo distance vector, con le seguenti caratteristiche:

- Le informazioni inviate ai vicini sono sostanzialmente informazioni di raggiungibilità.
- Non sono specificate le regole per definire le distanze.
- La distanza minima può non essere il criterio migliore da seguire.

Queste caratteristiche rendono EGP un protocollo semplice ma limitato rispetto ai protocolli più moderni come BGP.

#### Limiti di EGP

- Progettato per topologie specifiche (es. ARPAnet).
- Funziona bene per topologie ad albero, non per reti a maglia complessa.
- Convergenza lenta e instabilità.
- Adattamento lento alle modifiche della topologia.
- Nessun meccanismo di sicurezza: vulnerabile a annunci falsi e guasti dei router.

### BGP: Border Gateway Protocol

BGP è stato concepito come sostituto di EGP e oggi è in uso la versione 4 (RFC 1771). I router BGP si scambiano informazioni attraverso connessioni TCP (porta 179) chiamate sessioni BGP.

#### Caratteristiche principali di BGP:

- **Connessioni Affidabili**: Le comunicazioni sono affidabili grazie all'uso di TCP, con funzionalità di controllo degli errori demandate allo strato di trasporto.
  
- **Tipi di Sessioni BGP**:
  - **eBGP (External BGP)**: Sessioni instaurate tra router BGP appartenenti ad AS diversi.
  - **iBGP (Internal BGP)**: Sessioni instaurate tra router BGP appartenenti allo stesso AS.
- **Informazioni Scambiate**: Le informazioni riguardano la raggiungibilità di reti IP secondo lo schema classless (CIDR).

Queste caratteristiche rendono BGP un protocollo robusto e scalabile per il routing tra diversi AS. Utilizza un path vector, un'evoluzione del distance vector, nel vettore dei percorsi si elencano tutti gli AS da attraversare per raggiungere una destinazione per evitare percorsi ciclici. Quando un router riceve un path e c'è già lui dentro lo scarta, evitando di creare cicli.

##### Attributi
A ciascun path vector vengono associati degli attributi
Gli attributi BGP possono essere classificati in diverse categorie:

- **Well-known**: Riconoscibili da tutte le implementazioni BGP e devono essere inoltrati assieme al path vector (dopo un eventuale aggiornamento).
  - **Mandatory**: Devono essere presenti nel path vector.
  - **Discretionary**: Possono anche non essere indicati.
- **Optional**: Possono non essere riconosciuti da alcuni router.
  - **Transitive**: Devono essere inoltrati anche se non riconosciuti.
  - **Non-transitive**: Devono essere ignorati se non riconosciuti.
- **Partial**: Attributi optional-transitive che sono stati ritrasmessi senza modifiche da un router perché non riconosciuti. Indicano se un determinato path vector è stato riconosciuto o meno da tutti i router attraversati.

Queste categorie aiutano a gestire come gli attributi vengono trattati e propagati attraverso la rete BGP.

<div style="text-align: center;"><img src="./img/Screenshot_2024-11-28_at_14.31.58.png" alt="Diagramma di rete" width="400"></div>

## Commutazione di etichetta: MPLS

**Router**

- Instrada i datagrammi IP
  - Longest prefix match
  - Shortest path routing
- Spesso implementa funzioni addizionali
  - packet filtering, QoS etc.
- Supporta interfacce (piano dati) e protocolli (piano di controllo) di tipo diverso

**Switch**

- Instradamento semplice in funzione di indirizzi statici
- Funzionalità limitate all’instradamento delle trame
- Supporto per un numero limitato di interfacce e di protocolli
- Considerando il traffico smaltito il rapporto costo/prestazioni in uno switch è migliore che in un router

**LER label edge router**

- router normale che però può attaccare una label

### Label Switching

Il label switching è una tecnica usata nelle reti (come in MPLS, Multi-Protocol Label Switching) per instradare i dati in modo più veloce rispetto ai metodi tradizionali basati sugli indirizzi IP.

Ecco come funziona in modo semplice:

1. Etichetta (Label):

   - Quando un pacchetto entra nella rete, gli viene assegnata una “etichetta” (un numero breve) che identifica il percorso che deve seguire.

2. Switching basato sull’etichetta:

   - Ogni router (o switch) della rete non guarda l’indirizzo IP del pacchetto, ma legge solo l’etichetta.
   - In base all’etichetta, il router sa subito dove inoltrare il pacchetto, senza dover fare calcoli complicati.

3. Riassegnazione dell’etichetta:

   - Durante il percorso, ogni router può sostituire l’etichetta del pacchetto con una nuova, per aggiornare le istruzioni sul percorso successivo.

4. Rimozione dell’etichetta:

   - Alla fine del percorso, l’ultima etichetta viene rimossa e il pacchetto continua verso la sua destinazione usando il metodo tradizionale (indirizzo IP).

Vantaggi:

- Velocità: Gli switch lavorano più velocemente perché analizzano solo etichette, non indirizzi complessi.
- Efficienza: Si possono creare percorsi ottimizzati per migliorare le prestazioni della rete.
- Flessibilità: Funziona con molti protocolli (non solo IP).

In pratica, il label switching semplifica e velocizza il trasferimento dei dati nella rete!

### label stacking

innestare domini MPLS, simile al concetto di routing gerarchico

- push label, quando si entra nel dominio si aggiunge etichetta
- pull label, si toglie etichetta quando esce dal dominio

### label allocation
chi decide le label? decide sempre il router a valle (il primo router)


## Reti Overlay

Obiettivo della virtualizzazione

- Realizzare topologie o funzionalità sull’infrastruttura esistente
diverse da quelle native
- In generale si parla di reti “overlay”

**Un tunnel GRE** (Generic Routing Encapsulation) è un protocollo di tunneling usato per incapsulare una varietà di protocolli di rete all’interno di una connessione IP.

- Sovrapposte logicamente all’infrastruttura fisica per realizzare funzionalità diverse da quelle normalmente fornite dalla stessa
Un tunnel GRE (Generic Routing Encapsulation) è un protocollo di tunneling usato per incapsulare una varietà di protocolli di rete all’interno di una connessione IP.

Come funziona:

1. Encapsulaamento: I dati originali (pacchetti) vengono racchiusi in un nuovo header GRE.
2. Trasporto: Il pacchetto incapsulato viene inviato attraverso una rete IP.
3. Decapsulamento: Il router di destinazione rimuove l’header GRE e consegna il pacchetto originale.

Caratteristiche principali:

- Flessibilità: Supporta diversi protocolli (IPv4, IPv6, MPLS).
- Indipendenza: Funziona sopra un’infrastruttura IP senza modifiche.
- Overhead: Aggiunge un piccolo sovraccarico ai pacchetti per includere l’header GRE.

Utilizzi comuni:

- Creazione di VPN semplici (ma senza crittografia).
- Collegamento di reti separate (ad esempio, reti aziendali remote).
- Trasporto di protocolli che non possono essere instradati direttamente su IP.

Se viene modificata la rete fisica non c'è modifica nella rete logica. 

### Header 
**L’header GRE** è una struttura di dati utilizzata per incapsulare pacchetti all’interno di un tunnel GRE. Serve a fornire le informazioni necessarie per gestire il pacchetto incapsulato durante il suo transito attraverso la rete.

Struttura dell’header GRE (base)

L’header base di GRE è lungo 4 byte (32 bit) e contiene i seguenti campi principali:
1. Flags e Version (16 bit):
   - C (Checksum Present): Indica se un checksum è incluso (1 = presente).
   - K (Key Present): Indica se un campo di chiave è presente per identificare il tunnel.
   - S (Sequence Number Present): Indica se un numero di sequenza è incluso.
   - Version: Solitamente impostato a 0 per GRE standard.
2. Protocol Type (16 bit):
   - Specifica il tipo di protocollo incapsulato (es. 0x0800 per IPv4, 0x86DD per IPv6).

Header GRE opzionale

A seconda delle impostazioni, possono essere aggiunti altri campi:
- Checksum (32 bit): Per verificare l’integrità del pacchetto.
- Key (32 bit): Per identificare il tunnel o la sessione.
- Sequence Number (32 bit): Per garantire l’ordine dei pacchetti.

Funzionamento

1. Il router sorgente aggiunge un header GRE al pacchetto originale.
2. Il pacchetto incapsulato viene inviato attraverso il tunnel GRE.
3. Il router di destinazione legge l’header GRE, estrae il pacchetto originale e lo consegna alla rete di destinazione.

GRE è semplice e flessibile, ma non offre crittografia o meccanismi di sicurezza avanzati. Per proteggere i dati, può essere combinato con protocolli come IPsec.

### VXLAN
La VXLAN (Virtual Extensible LAN) è una tecnologia di rete che estende reti Layer 2 (L2) su infrastrutture Layer 3 (L3) usando tunneling. Incapsula i frame Ethernet L2 in pacchetti UDP L3, permettendo di creare fino a 16 milioni di reti virtuali grazie al VNI (identificatore a 24 bit), superando il limite di 4096 VLAN.

La VXLAN utilizza dispositivi VTEP per incapsulare i frame Ethernet Layer 2 in pacchetti UDP Layer 3. Ogni VTEP collega una rete virtuale (L2) alla rete fisica (L3). I pacchetti incapsulati viaggiano attraverso la rete Layer 3 e vengono de-incapsulati dal VTEP di destinazione per consegnarli alla rete virtuale corretta, identificata dal VNI.

### Reti private 
Aziende e/o enti di dimensioni medio/grandi in genere hanno necessità di interconnettere in maniera **sicura** sedi sparse sul territorio e distanti tra loro

Soluzione tradizionale: utilizzo di linee dedicate da affittare direttamente presso gli operatori (reti private)

- Implica costi di acquisto e di gestione dedicati
- Le normative non lo permettono
  
Alternativa: utilizzo di una rete in “overlay” attraverso
reti pubbliche (reti private virtuali - VPN)
- flusso punto-punto di pacchetti autenticati (con contenuto
informativo criptato) incapsulati in pacchetti tradizionali - diverse tecnologie disponibili
- Diversi protocolli di tunnelling
  - livello 2: PPTP, L2TP ・livello 3: IPsec
  
#### Roda warrior

Una VPN Roadwarrior è una configurazione VPN per utenti che si connettono da luoghi remoti e variabili, come lavoratori in viaggio o in smart working. Offre una connessione sicura attraverso protocolli di tunneling e crittografia, permettendo l’accesso remoto a risorse aziendali o personali tramite dispositivi come laptop, smartphone o tablet.

Funzionamento:
L’utente utilizza un client VPN per connettersi al server VPN, autenticandosi con credenziali o 2FA. Il server crea un tunnel sicuro per instradare il traffico verso le risorse della rete privata.

Vantaggi:
- Flessibilità: Accesso da qualsiasi luogo con Internet.
- Sicurezza: Protezione dei dati sensibili.
- Accesso centralizzato: Risorse aziendali disponibili in modo sicuro.

TOPOLOGIA : a stella

#### VPN rete a rete

Se ho molti host co-localizzati il rodawarrior è inefficiente

- N host richiedono N tunnel

Si crea un tunnel cifrato su rete pubblica fra due LAN o fra due network IP

- Su rete pubblica i pacchetti vengono cifrati
- Su rete pubblica l’indirizzamento reale può essere
mascherato

Viene utilizzato

##### IPsec

IPsec (Internet Protocol Security) è un insieme di protocolli utilizzati per garantire la sicurezza delle comunicazioni su reti IP. Fornisce cifratura, autenticazione e integrità dei dati, rendendolo ideale per proteggere le connessioni VPN.

Utilizzo nelle VPN Site-to-Site (Net-to-Net):

In una VPN Site-to-Site, IPsec viene utilizzato per creare un tunnel sicuro tra due reti geograficamente separate. Questo consente ai dispositivi di entrambe le reti di comunicare come se fossero nella stessa rete locale.

1. Fasi principali:

    - Autenticazione dei peer: Le reti si autenticano tramite certificati digitali o chiavi pre-condivise (Pre-Shared Keys - PSK).
    - Creazione del tunnel: IPsec stabilisce un tunnel cifrato tra i gateway delle reti.
    - Scambio dei dati: I pacchetti vengono cifrati e autenticati durante il transito per proteggerli.

2. Protocolli utilizzati:

   - IKE(Internet Key Exchange): autentica interlocutore negoziazione algoritmi e chiavi crittografiche
   - AH (Authentication Header): Garantisce integrità e autenticità dei pacchetti.
   - ESP (Encapsulating Security Payload): Cifra i dati per garantirne la riservatezza.

Vantaggi:

- Sicurezza robusta per le comunicazioni aziendali.
- Trasparenza per gli utenti, che non devono configurare nulla sui dispositivi finali.

È una soluzione comune per collegare filiali o data center tramite una rete pubblica come Internet.

## Strato fisico

La capacità dei collegament raddoppia ogni circa 18 mesi

### Attenuazione

Misura del degrado del segnale attraverso il mezzo trasmissivo, si misura in dB/km.
Se l'attenuazione è bassa posso creare collegamenti più lunghi, altrimenti no.

### Rame

$$A_{dB} = 10 \cdot \log_{10} \left( \frac{P_T}{P_R} \right) = \alpha \sqrt{f_{MHz}} L$$

- L'attenuazione cresce esponenzialmente con la lunghezzadel collegamento
- Esponenzialmente con la radfice della frequenza del segnale

#### Coppie Intrecciate (Twisted Pair)

##### Tipologie

1. **Shielded Twisted Pair (STP)**:

- Ogni coppia è avvolta in uno schermo conduttore.
- Costo maggiore e necessità di mettere lo schermo a massa.

1. **Unshielded Twisted Pair (UTP)**:

- Più economici e facili da installare.

##### Miglioramenti

- Aumento del diametro dei conduttori e miglioramento della qualità del dielettrico.
- Miglioramento della regolarità e infittimento del passo di avvolgimento.

##### Categorie (dalla Cat. 1 alla Cat. 7):

- **Cat. 1**: Rete telefonica e ISDN.
- **Cat. 3**: Rete fino a 16 MHz, Ethernet a 10 Mbit/s.
- **Cat. 5**: Frequenze fino a 100 MHz, Ethernet a 100 Mbit/s.
- **Cat. 5e**: Fino a 200 MHz, Fast e Gigabit Ethernet.
- **Cat. 6**: Frequenze fino a 250 MHz.
- **Cat. 6a**: Fino a 500 MHz.
- **Cat. 7**: Fino a 600 MHz, 4 STP in un cavo.
- **Cat. 7a**: Fino a 1 GHz.

#### Cavo Coassiale

- **D**: Diametro cavità conduttore esterno.
- **d**: Diametro conduttore interno.
- La qualità del cavo migliora con l’aumento di D (costo e prestazioni).
- **Cavo coassiale normalizzato**:
  - Diametro interno: 2.6 mm, esterno: 9.5 mm.
  - Attenuazione a 1 MHz = 2.35 dB/km.

##### Multiplazione a divisione di frequenza (FDM):

- Tecnica per inviare più segnali tramite lo stesso canale.

### Comunicazioni Radio

- **Vantaggi**:
  - Adatto per la mobilità.
  - Facilita i servizi di diffusione (broadcasting).

- **Problemi**:
  - Lo spettro radio è limitato.
  - Attenuazione delle onde elettromagnetiche: cresce con la distanza e la frequenza.
  - Propagazione: dipende dalla frequenza (onda di terra, ionosferica o diretta).

### Sistemi Satellitari

- **1960-1970**: Intelsat, satelliti in orbita geostazionaria (GEO).
- **Anni '90**: Satelliti sofisticati, con stazioni a terra economiche.
- **Oggi**: Costellazioni di satelliti in orbita bassa (LEO) e media (MEO).

### Sistemi Cellulari

- **Funzionalità**:
  - Servizi telefonici mobili.
  - Potenza di trasmissione bassa, ma alta efficienza nel riutilizzo delle frequenze (celle non adiacenti).
  
- **Tecnologie**:
  - **ETACS** (900 MHz, analogico).
  - **GSM** (digitale, copertura mondiale).
  - **Generazioni successive** (multimediali, roaming, hand-over).

#### Considerazioni

- **Reti radio**: Economiche per territori vasti e poco popolati.
- **Problemi**:
  - Banda limitata.
  - Vulnerabilità ai disturbi atmosferici e attacchi.
  
## Funzionalità e prestazioni

I protocolli devono garantire :

- funzionalità
- prestazioni
  
### Prestazioni

Un sistema deve smaltire il lavoro offerto dall'esterno.

$$richieste\ in\ arrivo \rightarrow k(t) = numero\ di\ richieste\ da\ elaborare\rightarrow richieste\ soddisfatte$$

<div style="text-align: center;"><img src="./img/Screenshot_2024-12-06_at_09.16.13.png
" alt="Diagramma di rete" width="400"></div>

- Frequenza media richieste offerte

$$\lambda = \lim_{t \to \infty} \frac{a(t)}{t}$$

- Frequenza media richieste smaltite

$$\lambda_s = \lim_{t \to \infty} \frac{p(t)}{t}$$

- Se il sistema in oggetto non produce lavoro ma lo
riceve solamente dall’esterno

$$\lambda_s \le \lambda$$

#### Richieste perdute

$$se\ \lambda_s = \lambda\  \rightarrow\  s(t) = a(t)$$

- tutte richieste accettate prima o poi soddisfatte

$$se\ \lambda_s < \lambda\  \rightarrow\  r(t) = a(t) - s(t)$$

- r(t) rappresenta le richieste non accettate e perdute dal sistema.
quindi :

$$(frequenza\ rifiutate\ o\ perdute)\ \lambda_p = \lim_{t \to \infty} \frac{r(t)}{t}$$
$$\lambda = \lambda_s + \lambda_p$$

#### Utenti e servizi

In una rete non ha senso considerare unicamente il bit rate del canale, perchè l'unità di servizio è il pacchetto e non il bit, perciò si considera come **risultato utile** il tempo per completare la consegna di un intero pacchetto.

$$\theta \rightarrow PDU=tempo\ richiesto\ da\ un\ generico\ cliente$$

$$\bar\theta = \frac{L}{C}$$

- L = lunghezza pacchetto in bit
- C = capacità canale in bit per sec

##### PDU (protocoll data unit)

- Servizio **aleatorio**
  - Si fa riferimento in prima battuta al tempo medio
- Servizio **deterministico**
  - Tempo di servizio costante ed uguale al suo valore medio

#### Frequenza di servizio

$$\mu = \frac{1}{\bar \theta}$$

La frequenza media di servizio è ovviamente legata
alla presenza di utenti del sistema

- Se non vi sono richieste di servizio $\rightarrow$ frequenza di servizio è nulla

- Se vi sono richieste di servizio il parametro da
indicazione di quanto velocemente esse vengono
soddisfatte

##### esempio

se $\bar\theta =0.5s$ allora il servitore può smatltire al massimo $\mu = 2\ pacchetti/s$
$$\lambda^{max}_s = \mu$$

Un utente spende mediamente in coda il tempo del servizio + il tempo di attesa

$$\bar\delta = \bar \theta + \bar T_A$$

#### Traffico

Le prestazioni del sistema che fornisce il servizio
dipendono:

- Dalla numerosità degli arrivi, (utenti per secondo)
- Dalla durata del servizio (utenti al secondo) o il tempo medio di servizio(secondi)

**Traffico** = numero medio di utenti presenti nel sistema

$$A =\lambda \bar\delta$$
$A_0 =\lambda \bar\delta \rightarrow$ Traffico offerto
$A_s =\lambda_s \bar\delta \rightarrow$ Traffico smaltito
$A_p  =\lambda_p \bar\delta\rightarrow$ Traffico perduto

<div style="text-align: center;"><img src="./img/Screenshot_2024-12-09_at_11.26.20.png" alt="Diagramma di rete" width="400">
</div>

<div style="text-align: center;"><img src="./img/Screenshot_2024-12-09_at_11.28.58.png
" alt="Diagramma di rete" width="400"></div>

### Prestazioni Ideali per un Protocollo Data Link

Le prestazioni ideali per un protocollo data link sono determinate dalla capacità massima teorica del canale. Poiché il protocollo invia i bit dello strato 3 sul canale, la sua capacità massima teorica è la velocità del canale \( C \).

- **Capacità Massima Teorica**: La velocità del canale \( C \).

Questa capacità rappresenta il limite superiore delle prestazioni che il protocollo può raggiungere in condizioni ideali.

Tempo medio di servizio $\rightarrow \bar\theta =\frac{L}{C} = \frac{1}{\mu}$

Se richiede maggiore tempo allora $\rightarrow \bar\theta_e =\frac{L}{C_e} = \frac{1}{\mu}$

### Capacità Effettiva $(C_e)$

La capacità effettiva di un protocollo data link dipende dal protocollo stesso e dalle condizioni operative. Se le funzionalità richieste o una situazione non ideale richiedono più tempo per ogni PDU (Protocol Data Unit), parte della capacità risulta inutilizzabile per i dati degli utenti. I fattori che possono ridurre la capacità effettiva includono:

- **PCI Necessarie per la Segnalazione**: Overhead dovuto alle informazioni di controllo.
- **Errori di Trasmissione**: Necessità di correggere errori.
- **Ritrasmissioni**: Pacchetti persi o danneggiati che devono essere ritrasmessi.
- **Tempi Morti Legati alle Dinamiche del Protocollo**: Attese dovute al funzionamento del protocollo.
- **Tempi Morti in Attesa di Accedere al Canale**: Attese per ottenere l'accesso al canale di comunicazione.

Questi fattori riducono la capacità effettiva rispetto alla capacità massima teorica del canale.
Il traffico si misura con una unità di misura fittizia detta E (*Erlang*).

### Valutazione efficienza

Per valutare l'efficienza di un protocollo data link, si fa riferimento alla PDU (Protocol Data Unit). Si confrontano:

- Tempo per inviare i soli dati d'utente **SDU**
- Tempo totale per inviare la **PDU**

L'efficienza è data dal rapporto tra queste due quantità $\eta = \frac{T_u}{T_0} = \frac{\bar\theta}{\bar\theta_e}$.

## Reti commutate: il sistema a coda con singolo servitore
<div style="text-align: center;"><img src="./img/Screenshot_2024-12-09_at_11.59.08.png
" alt="Diagramma di rete" width="400"></div>

****
