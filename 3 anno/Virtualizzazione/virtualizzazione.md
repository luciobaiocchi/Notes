# VIrtualizzazione 

## Scenari di integrazione

### Intro

#### Figura del system integrator

Il termine più corretto per individuare l'attività del sistemista moderno è "Systems Integration and Testing". Mentre si delinea anche la figura di Systems Integration Architect si occupa della progettazione delle infrastrutture software per gestire, a livelli architetturali diversi, una molteplicità di entità differenziate che interagiscono continuamente.

#### Ambito corso

Il filo conduttore del corso è la progettazione, il dispiegamento e la manutenzione di sistemi software tipicamente multi-utente, distribuiti e virtualizzati.

### Integrazione col mondo dell'automazione 

All'interno di grandi aziende è sempre più importante interagire con dati forniti dai macchinari (progrrammati con PLC) per integrare real-time analisys, e vi è quindi la necessità di conoscere i protocolli specifici di comunicazione.

### Sistemi a micro servizi

Diversamente da quanto abbiamo sempre visto gli applicativi sono generalmente conmposti da molti componenti diversi, su stessa rete o anche collocati in zone diverse che interagiscono tra loro scamnìbiando messaggi tramite interfacce standard. Questo approccio permette il riuso del software.

![](microservizi_vs_monolitico.png)

**Vantaggi dei miscroservizi:**

- Riusabilità: da diversi applicativi
- Scalabilità: replicati e bilanciati i microservizi
- Deployment: realizzato su una macchina o su diverse, con possibilità di riconfigurazione molto semplice
- Cloud: perfettamente in linea con cloud computing, dato che i provider cloud offrono quasi esclusivamente microservizi.

**Svantaggi dei miscroservizi:**

- progettare le applicazioni stesse affinché utilizzino solo interfacce software e protocolli di comunicazione diffusi e condivisi (standard de facto).
- assicurarsi che la rete permetta il passaggio di messaggi all'interno, e se non possibile configurare il NAT.
- è fondamentale quindi e parte integrante del processo di creazione del sistema **progettare opportunamente le comunicazioni**

### Sicurezza nei sistemi informatici

I requisiti di sicurezza vanno pensati al momento in cui si concepisce il sistema e non dopo averlo creato.

Molto spesso un requisito è centralizzare il servizio di autenticazione, per limitare i punti di attacco e favorire il controllo. Gli scenari in cui è necearia la centralizzazione si estendono non solo agli utenti, ma anche all'autorizzazione all'accesso delle risorse delle entità o nei mezzi trasmissivi. Un esempio è l'autenticazione degli access point wifi di ateneo, l'access point chiede autorizzazione a server Radius.

### Directory Service

Sistema centralizzato che deve gestire utenti macchine ecc. 
![](directory_service.png)


Le macchine possono essere riconosciute anche al boot, e cambiando la configurazione in un server cambiano le informazioni automaticamente in tutte le macchine. Nella fase iniziale di installazione, ad ogni macchina viene dato un certificato digitale che serve per rendere sicure le comunicazioni tra macchina e server. Questo processo si chaima Join con dominio.

![](log_centralizzato.png)