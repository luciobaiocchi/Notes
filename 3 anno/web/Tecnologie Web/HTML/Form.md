# Form

Meccanismo input output. 

## Form <form>

Contiene controlli di input, bottoni campi testo ecc..

Può avere anche campi per l’output, e può essere **processato** sia lato server che client

### Attributi

- Action → specifica l’URL dell’applicazione server-side
che riceverà i dati.
- **Method →** specifica il metodo HTTP che deve essere
    
    usato per i dati, può essere:
    
    - **GET**: richiede dati da processare
        - Invia dati testuali, aggiungendo una query string alla URL richiesta.
        - Non va bene per dati troppo voluminosi
    - **POST**: invia dati da processare
        - Non ha restrizioni su dimensione e tipo di dato
        - I dati sono nel body del messaggio e sono non visibili
        - Con http no sicuro
        - più scomodo di get perché non rimane in cache

### Attributi non comuni

- Name → Specifica il nome del controllo
- Required → booleano che indica inserimento obbligatorio
- Autofocus → focus su questo controllo
- Autocomplete → se attivato autocompletamento

### Label

label che descrve il controllo all’utente, per motivi di accessibilità del sito, sia annidandola nel controllo sia con id 

```html
<form>
<p><label>Customer name:
<input....../></label></p>
</form>

<p><label for="CN">Customer name: </label>
<input .... id="CN" /></p>
</form>
```

### FieldSet

raggruppa più controlli che hanno semantica comune 

### Input

inserire input specificandolo con attributo type, che assume valori :

hidden, text, search, tel, url, email, password, date, time, number, range, color, checkbox, radio, file, submit, image, reset, button.

- Reset → ripristina i valori del form
- Submit → genera un bottone per sottomettere il form
- Button → azione con onclick Javascript
- Value → modifica il testo del bottone

### Image

Il tipo **image**ha la stessa funzione di un bottone

### Hidden

Viene usato per inserire valori nascosti che vengono visualizzati poi 

### Password