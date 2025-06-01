# 4 componenti principali
## Activity 
Schermata di un app
per avviare una nuova istanza di un’Activity passando un Intent al metodo startActivity()
## Service 
componente che esegue operazioni in background senza un'interfaccia utente
## Broadcast receivers
consente al sistema di inviare eventi all'app al di fuori di un normale flusso utente

## Content providers e content resolver
**Content providers** (gestisce un set condiviso di dati dell'app che è possibile archiviare – tipo esempio, accedere alle info sui contatti).
**Content resolver** lascia uno strato di astrazione tra il fornitore di contenuti e il componente che richiede informazioni.

## Intent
 Un intent è un oggetto di messaggistica che è possibile utilizzare per richiedere un'azione da un altro component di un app:
 - activity e service, un intent definisce l'azione da eseguire
 - broadcast receivers, l'intent definisce semplicemente l'annuncio da trasmettere
### Explicit intent
specifica quale applicazione soddisferà l'intent, fornendo il nome del pacchetto dell'app di destinazione o il nome completo della classe del componente. USATO PER AVVIARE DENTRO PROPRIA APP. Per esempio per caricare home dopo login.
### Implicit intents 
Non si chiama un Intent specifico, bensì  un'azione generale da eseguire. Per esempio visualizzare su mappa.