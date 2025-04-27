
## identificazione e analisi del problema 

Migliorare l'esperienza del trekking, sotto vari punti di vista:
- Aumentare la sicurezza
- Rendendo l'esperienza più coinvolgente

Come:
Creazione di 3 di dispositivi tascabili che si pongono l'obbiettivo di aiutare gli escursionisti in base al livello di esperienza:
- **Dispositivo madre**, il più grande dei 3, capace di tracciare percorsi con gps, una batteria maggiore, e capace di conoscere la posizione di altri dispositivi figli appartenenti allo stesso gruppo dell'escursione
- **Dispositivo figlio**, simile a livello si struttura rispetto al dispositivo madre, ma pensato per escursionisti meno esperti. Capace di seguire un percorso già tracciato e inviare posizione a dispositivo madre. 
- **Dispositivo per segnalazioni rapide**, il più piccolo tra i tre. Non viene utilizzato se non i caso di grave pericolo, o necessità di soccorso immediato. La sua unica funzionalità è quella di avere un bottone che se premuto invia una richiesta di soccorso a tutti i dispositivi raggiungibili. 

## requisiti funzionali
**Dispositivo madre**:
- Due modalità, che inizialmente verranno utilizzate in maniera esclusiva (se si registra un nuovo tracciato è obbligatorio farlo per la prima volta con un dispositivo madre e non in gruppo):
	- modalità "*recording*" del percorso, utilizzo del modulo GPS per registrare il percorso, (opzionale l'implementazione di altri sensori per migliore telemetria, esempio il barometro per misurare l'altitudine). 
	- modalità "*gruppo*", in questa modalità il dispositivo manda segnali periodici ai componenti del gruppo di escursione per controllare che tutti siano all'interno dei limiti di sicurezza del tracciato. Inoltre è possibile ideare anche una modalità per comunicare messaggi brevi. 
**Dispositivo figlio** :
Esistono due modalità come per il dispositivo madre, ma la differenza principale data nel fatto che in modalità "*singolo*" il dispositivo figlio viene usato solo per seguire un percorso pre-registrato, e nella modalità "*gruppo*" bisogna capire se è utile conoscere la posizione degli altri figli o è solo un inutile dispendio di risorse.

moduli necessari per entrambi i dispositivi: 
- GPS per posizionamento
- LoRa per comunicazione
- Display per visualizzare dati
- Bottoni per interagire. Possibilità di utilizzare un display touch, anche se l'idea iniziale è quella di cercare di utilizzare il dispositivo soltanto con i bottoni per garantire una migliore semplicità e velocità d'uso anche in caso di emergenza.
- Batteria 
- OPZIONALI: microfono e speaker per integrare anche comunicazioni vocali, ed eventualmente un led da usare come torcia

**Dispositivo per segnalazioni rapide**:
Idealmente ha le sembianze di un bottone, ed è ideato per essere appeso ad una stracca dello zaino o anche ad un lembo di un vestito. Come detto in precedenza deve essere in grado di comunicare solo in uscita una richiesta di soccorso ai dispositivi nelle vicinanze. 

Da valutare la possibilità di interagire con il dispositivo figlio della persona che ha mandato la richiesta per inviare anche un messaggio di soccorso non solo tramite connessione lora ma anche al soccorso alpino (magari con connessione satellitare). 




## requisiti non funzionali


## definizione dell’architettura

![[WhatsApp Image 2025-02-22 at 10.12.27.jpeg]]

![[WhatsApp Image 2025-02-22 at 10.12.15.jpeg]]
## Idee per espansioni
- aggiungere sport (per esempio per comunicare tra gruppi di sciatori)
- aggiungere feature per caricare percorsi su un'app e incentivare la condivisione di nuovi tracciati
- segnalazioni in tempo reale di pericolo, date da un sistema esterno(per esempio allerta temporali o valanghe)
- aggiunta di sensori statici lungo il percorso per migliorare l'accuratezza del rilevamento della posizione
