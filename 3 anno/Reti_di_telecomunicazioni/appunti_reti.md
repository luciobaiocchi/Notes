# Appunti reti

## IP e internet

### Composizione Indirizzo IP

IP→ Progettato per funzionare a commutazione di pacchetto in modalità connectionless.

identifica Host e router tramite indirizzi di lunghezza fissa, raggruppandoli in reti IP.

![Screenshot 2024-10-01 at 16.49.03.png](/img/header_ip.png)

### Funzioni

| Funzione            | Descrizione                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `Version`           | Indica il formato dell’intestazione, attualmente 4                           |
| `IHL`               | IP header length, lunghezza dell’intestazione                                |
| `Type of service`   | Tipo di servizio richiesto, usato anche come sorta di priorità               |
| `Total length`      | Lunghezza totale del datagramma                                              |
| `Identification`    | Valore intero che identifica univocamente il datagramma (pacchetto)          |
| `Flag`              | Vari flag utilizzati per il controllo della frammentazione dei pacchetti    - |
| `Fragment offset`   | Indica quale è la posizione di questo frammento nel datagramma, come distanza in unità di 64 bit dall’inizio|

**Flags per la frammentazione**:

- Bit 0: sempre 0
- Bit 1 (DF - Don't Fragment):
  - 0 = si può frammentare
  - 1 = non si può frammentare (nel caso fosse a 1 e fosse necessario frammentarlo lo distruggo)
- Bit 2 (MF - More Fragments):
  - 0 = ultimo frammento (aiuta a riordimare i paccheti in arrivo, è tecnicamente superfluo ma ci risparmia il calcolo di vedere quanto era lungo)
  - 1 = frammento intermedio

![Se non posso frammentare il pacchetto lo distruggo.](/img/flag_ip.png)

<div style="text-align: center;"><img src="./img/Screenshot_2024-12-06_at_09.16.13.png
" alt="Diagramma di rete" width="400"></div>