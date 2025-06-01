Un **cifrario**, nella crittografia, è un algoritmo utilizzato per eseguire operazioni o una serie di passaggi ben definiti che possono essere eseguiti come una procedura, volte a rendere _oscuro_, ossia semanticamente non leggibile, un testo di un messaggio in chiaro (_plain text_) o, al contrario, al ripristino in chiaro di un messaggio precedentemente cifrato.

### Cifrario one-time pad 
#### Cifrari perfetti
È un cifrario perfetto, che però ha dei difetti che lo rendono praticamente inutilizzabile. Viene studiato perché introduce dei concetti utili. Esistono cifrari in grado di nascondere l’informazione con certezza assoluta ma a un costo così alto da mettere in dubbio la loro esistenza pratica. Il loro impiego, o meglio l’impiego di una buona approssimazione di essi, è limitato a comunicazioni sporadiche in casi di estrema segretezza.

#### Cifrari utilizzati in pratica
Esistono cifrari non inviolabili, ma sufficientemente sicuri ed economici, che vengono utilizzati ogni giorno per comunicazioni di massa.

Esistono cifrari inviolabili? Se si intercetta un messaggio si può decodificare?

Non si può dimostrare che un algoritmo è inviolabile. Si può dimostrare che quel problema è risolvibile in maniera molto difficile.

#### Modello matematico
La comunicazione tra un mittente **Mitt** e un destinatario **Dest** è modellata come un processo stocastico in cui il comportamento del mittente è descritto da una variabile aleatoria M che assume valori nello spazio Msg dei messaggi, e le comunicazioni sul canale sono descritte da una variabile aleatoria C che assume valori nello spazio Critto dei crittogrammi. La distribuzione di probabilità della M dipende dalle caratteristiche della sorgente, cioè dalla propensione di Mitt a spedire diversi messaggi.

m = messaggio e appartiene a M
$C(m) = c$ = crittogramma in transito

$Pr (M = m)$ è la probabilità che Mitt voglia spedire proprio il messaggio m a Dest
$Pr (M = m|C = c)$ come la probabilità a posteriori che il messaggio inviato sia effettivamente m dato che c è il crittogramma in transito.

#### Definizione di cifrario perfetto
Un cifrario è perfetto se per ogni $m \in Msg$ e per ogni $c \in Critto$ vale la relazione  $Pr (M = m|C = c) = Pr (M = m)$, ovvero leggere il crittogramma non mi ha aumentato la probabilità di riconoscere il messaggio. Un cifrario perfetto quindi deve garantire che non venga determinata **nessuna** informazione leggendo c, non solo che il contenuto finale non sia comprensibile.