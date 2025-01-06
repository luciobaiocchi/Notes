# secondo anno

- [secondo anno](#secondo-anno)
  - [Broadcast livello 2](#broadcast-livello-2)
  - [1. DHCP (Dynamic Host Configuration Protocol)](#1-dhcp-dynamic-host-configuration-protocol)
  - [2. ARP (Address Resolution Protocol)](#2-arp-address-resolution-protocol)
    - [Differenze Chiave](#differenze-chiave)
    - [Livelli iso-osi](#livelli-iso-osi)

## Broadcast livello 2

In informatica, un broadcast di livello 2 si riferisce a una trasmissione dati all'interno del livello Data Link (Livello 2) del modello OSI, che coinvolge tutti i dispositivi collegati nella stessa rete locale (LAN).

In pratica, il broadcast di livello 2 invia un messaggio a tutti i dispositivi connessi a un segmento di rete, senza una destinazione specifica. Il messaggio viene inviato all'indirizzo MAC di broadcast (FF:FF:FF:FF:FF:FF), che tutti i dispositivi all'interno della rete ascoltano e ricevono. Un esempio comune è l'uso del broadcast per la risoluzione dell'indirizzo IP tramite ARP (Address Resolution Protocol), in cui un dispositivo chiede a tutti i dispositivi della rete se possiedono un determinato indirizzo IP.

I broadcast di livello 2 sono limitati alla rete locale e non vengono inoltrati dai router a meno che non siano configurati in modo specifico per farlo, mantenendo il traffico di broadcast contenuto all'interno di una singola LAN.

## 1. DHCP (Dynamic Host Configuration Protocol)

- **Funzione**: Il DHCP si occupa di assegnare automaticamente gli indirizzi IP ai dispositivi connessi a una rete.
- **Come funziona**: Quando un dispositivo si collega a una rete, invia una richiesta di DHCP. Il server DHCP risponde con un indirizzo IP disponibile, una subnet mask, un gateway, e altre configurazioni di rete (come i DNS).
Livello del modello OSI: Lavora a livello Applicazione (Livello 7).
- **Obiettivo**: Assicurare che ogni dispositivo connesso alla rete ottenga un indirizzo IP unico e una configurazione di rete corretta senza la necessità di configurazioni manuali.

## 2. ARP (Address Resolution Protocol)

- **Funzione**: ARP è utilizzato per tradurre un indirizzo IP in un indirizzo MAC (fisico) in una LAN.
- **Come funziona**: Quando un dispositivo conosce l’indirizzo IP di un altro dispositivo nella rete locale ma non il suo indirizzo MAC, invia una richiesta ARP in broadcast. Il dispositivo destinatario risponde con il proprio indirizzo MAC, permettendo così la comunicazione a livello di collegamento dati.
Livello del modello OSI: Lavora a livello Collegamento Dati (Livello 2) ma può anche interagire con il Livello di Rete (Livello 3).
- **Obiettivo**: Consentire la comunicazione tra dispositivi in una rete locale traducendo indirizzi IP in indirizzi MAC, necessari per l’instradamento dei pacchetti a livello di collegamento dati.

### Differenze Chiave

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
