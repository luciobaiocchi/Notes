# Link, tabelle e liste

gli elementi di gestione di liste e tabelle sono detti FLOW

### Ancore

```html
<a> <! --permette di inserire un'ancora nella pagina
ovvero il punto di partenza di un link-->

<nav>
<ul>
<li> <a href="/">Home</a> </li>
<li> <a href="/news">News</a> </li>
<li> <a href="http://www.google.it">Google</a> </li>
<li> <a href="#articolo">Articolo</a> </li>
</ul>
</nav>

<! --collegamento all'interno della pagina-->

<article id="articolo">
<p> testo dell'articolo .... </p>
</article>

```

### Risorse

Una struttura qualsiasi scambiata nel web, il concetto di **struttura** non dipende dal meccanismo di memorizzazione.

Una risorsa non è necessariamente un file, ma può essere anche un DB, una risorsa non elettronica o altro. 

## URI → (uniform resource identifier)

Sintassi usata per definire nomi e indirizzi di risorse su internet, pregi:

- meccanismo unificato
- accessibili da protocolli esistenti
- tutte le istruzioni d’accesso sono codificate in una stringa di indirizzo

### URL → (uniform resource locator)

informazioni utilizzabili per localizzare(indirizzo di rete).

### URN →(uniform resource names)

permetta una etichettatura permanente e non ripudiabile
della risorsa

![Screenshot 2024-09-27 at 10.27.59.png](Link,%20tabelle%20e%20liste%2010e3dd229363802daf24dd4eb4f3c729/Screenshot_2024-09-27_at_10.27.59.png)

## Tabelle

Composizione delle tabelle grazie a **<table>** e sono organizzate per righe:

**<tr>  →** (table row)

**<td> →** table data, celle normali

**<th> →** table header, intestazione

![Screenshot 2024-09-27 at 11.24.11.png](Link,%20tabelle%20e%20liste%2010e3dd229363802daf24dd4eb4f3c729/Screenshot_2024-09-27_at_11.24.11.png)

![Screenshot 2024-09-27 at 11.50.43.png](Link,%20tabelle%20e%20liste%2010e3dd229363802daf24dd4eb4f3c729/Screenshot_2024-09-27_at_11.50.43.png)

righe senza ripetizioni

mailto → serve per aprire direttamente la posta 

## Liste

Tre tipologie: 

- non ordinate → **<ul></ul>**
- ordinate → **<ol></ol>**
- di definizioni → **<dl></dl>**

Nelle liste ordinate e non ordinate ogni item è definito da **<li></li>**

![Screenshot 2024-09-27 at 11.10.03.png](Link,%20tabelle%20e%20liste%2010e3dd229363802daf24dd4eb4f3c729/Screenshot_2024-09-27_at_11.10.03.png)

Per le liste di definizioni si usano due elementi che specificano termine e definizione **<dt>** e **<dd>**.

dt → termine

dd → descrizione che possono essere multiple per un termine.

![Screenshot 2024-09-27 at 11.09.55.png](Link,%20tabelle%20e%20liste%2010e3dd229363802daf24dd4eb4f3c729/Screenshot_2024-09-27_at_11.09.55.png)

### Liste annidate

![Screenshot 2024-09-27 at 11.13.44.png](Link,%20tabelle%20e%20liste%2010e3dd229363802daf24dd4eb4f3c729/Screenshot_2024-09-27_at_11.13.44.png)