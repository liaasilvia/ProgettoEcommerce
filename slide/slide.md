---
backgroundImage: url('sfondo.jpg')
paginate: true
marp: true

---
![bg right:60% height:120px](logoesteso2.png)
# Progetto d'esame
## Lia's House
**Silvia Lia** n° _matricola:847_
Graphic Design
ACME - 3°anno
A.A. 2023-2024
**Materia**:Web Design 2
**Docente**:Matteo Baccan

---
![ width:570px](logoesteso2.png)

Quest'anno abbiamo creato un **sito multi pagina per un e-commerce**. Io ho scelto di progettare un e-commerce di vestiti eleganti di alta qualità, utilizzando le **competenze** acquisite in precedenza su **HTML, CSS e Javascript**.

Il repository è pubblicato a questo indirizzo: https://liashouse.netlify.app/

---
# Strumenti utilizzati
Per la creazione del sito e delle relative slide ho utilizzato: 
- Marp, Markdown Presentation Ecosystem
- GitHub, Codespace (Visual Studio Code)
- Bootstrap
- Chat GPT
- Netlify

---
# Marp: Creazione Slide
![bg right:44% width:400px](marp.png)
Marp conosciuto anche come _Markdown Presentation Ecosystem_ permette un'esperienza intuitiva e veloce per creare delle semplici slide. Quello che noi dobbiamo fare è semplicemente scrivere un documento in **markdown**.



---
# Visual Studio Code: Programmazione
![bg right:33% width:300px](vs.png)
Ho usato il _code editor_ **Visual Studio Code**, clonando il mio repository di GitHub localmente, potendo **programmare** tranquillamente **offline** e successivamente aggiornare il mio repository di GitHub

---
![bg right:33% width:300px](Bootstrap.png)
# Librerie
## Bootstrap
**Bootstrap** è una libreria di **strumenti liberi per la creazione di siti e applicazioni per il Web**. Essa contiene modelli di progettazione basati su HTML e CSS, sia per la tipografia, che per le varie componenti dell'interfaccia, come moduli, pulsanti e navigazione, così come alcune estensioni opzionali di JavaScript.



---
# Chat GPT
![bg right:44% width:250px](ChatGPT.png)
Ho usato questa IA, _intelligenza artificiale_ per **creare parte dei testi** all'interno del sito.

---
# Netlify: Pubblicazione
![bg right:45% width:400px](Netlify.png)
Per la pubblicazione del sito creato abbiamo utilizzato **Netlify**, società di cloud computing basata su servizi di hosting e back-end serverless per applicazioni Web e siti Web statici.

---
# Creazione del sito
---
# Struttura
Il sito è composto da 5 pagine principali: 
- Home
- Brand
- Clothing
- Cart
- Contact

Ogni pagina presenta degli elementi di base come la **navbar** e il **footer**

---
# Navbar
![bg right:33% width:250px](mockuphome.png)
In alto abbiamo la **navbar** importante per la navigazione all'interno del sito.
Caratteristica rilevante sono gli slider, realizzati usando delle demo di [Swiper](https://swiperjs.com/demos)

---
# Footer
![bg right:33% width:250px](mockuphome.png)
In alto abbiamo la **navbar** importante per la navigazione all'interno del sito.
Caratteristica rilevante sono gli slider, realizzati usando delle demo di [Swiper](https://swiperjs.com/demos)


---
# Homepage
![bg right:33% width:250px](mockuphome.png)
In alto abbiamo la **navbar** importante per la navigazione all'interno del sito.
Caratteristica rilevante sono gli slider, realizzati usando delle demo di [Swiper](https://swiperjs.com/demos)

---
### Home Slider:
![](slider2.jpg)
Il carosello iniziale prevede un **autoplay** con un intervallo di tempo specifico
e la possibilità di fare swipe e vedere le altre diapositive, tre in totale.

---
#### Array:
```js
let products = [
  {
    id: 1,
    nome: "Chainsaw Man 12",
    prezzo: 5.0,
    immagine: "immagini/shounen/cm12.jpg",
    categoria: "shounen",
    descrizione: "...",
  },
  ...
]
```
Per far funzionare il tutto ho dovuto creare questa **variabile contenente i vari prodotti** che poi appaiono nella pagina

---
#### Funzione JS che definisce la struttura HTML:
```js
html = "";
products.forEach((product) => {
    html += `
<div class="swiper-slide img">

...

</div>`;
});
document.getElementById("dinamicihome").innerHTML = html;
```
Secondo il codice JS il codice html verrà generato nell'elemento **"dinamicihome"**, un semplice <div> presente nella pagina index.html

---
### Cookie
Ogni sito al giorno d'oggi ha l’obbligo di informare gli utenti sulla raccolta e l’elaborazione dei dati. Anche se un sito web non trae profitto direttamente o sostanzialmente dall’elaborazione dei dati, se vengono raccolti dati personali utilizzando i cookie, **è necessario in ogni modo una cookie policy**.

![](cookie.png)

---
#### Codice HTML
```html
<div id="cookie-banner" class="cookie-banner">
    <p> ... <a href="cookie.html">Maggiori informazioni</a></p>
    <button id="cookie-accept">Accetta</button>
</div>
```
Per accedere alla cookie policy completa basta cliccare su **Maggiori informazioni** e si verrà portati nella pagina **cookie.html**

---
#### Funzione JS:
```js
    cookieAccept.addEventListener("click", function () {
        cookieBanner.style.display = "none";
        localStorage.setItem("cookieConsent", "true");
    });
```
Si aggiunge un gestore di eventi al clic sull'elemento cookieAccept, così quando l'utente fa clicca, viene eseguita una **funzione di callback**. All'interno di questa funzione, viene **impostato lo stile** dell'elemento cookieBanner su **"none"**, che lo **nasconde**.
Viene poi utilizzato l'oggetto **localStorage** per impostare un valore booleano "true" con la chiave "cookieConsent". Questo indica che l'utente ha accettato i cookie.

---
```js
    if (!localStorage.getItem("cookieConsent")) {
        cookieBanner.style.display = "block";
    }
});
```
Successivamente, si verifica se l'utente ha già accettato i cookie, se nel localStorage è **presente** un **valore associato alla chiave "cookieConsent"**. Se non è presente, viene impostato lo stile dell'elemento cookieBanner su "block", che lo rende visibile.

---
![bg right:45% height:200px](logo2.png)
## Brand
In questa pagina vi è semplicemente una breve descrizione dell'e-commerce e delle figure che compongono il team.

---
![bg right:45% width:600px](filtromockup.png)
## Clothing
La pagina dei prodotti come nella home è resa **dinamica attraverso un array di prodotti** che permette di **generare codice HTML per ogni prodotto**, inserito all'interno di un elemento specifico (determinato da un ID) nel documento HTML.
Inoltre è presente un **filtro dei prodotti** in base alla categoria

---
#### Filtro prodotti
```js
function filterProducts() {
...
// prodotti dinamici
  let html = "";
  products.forEach((product) =>
```
Questa parte contiene la funzione filterProducts, che viene chiamata per filtrare i prodotti in base alla categoria e all'intervallo di prezzo. Viene creato un **ciclo forEach** per iterare attraverso ogni prodotto nell'array products.

---
![bg right:45% width:650px](singolo.png)
## Prodotto Singolo
La **generazione** di questa pagina è resa **dinamica** utilizzando l'array con i prodotti

---
![bg right:30% width:650px](carrellomockup1.png)
## Cart
La pagina del carrello non è completamente funzionante, al momento è possibile aggiungere i prodotti al suo interno, ma non è visibile direttamente nel carrello.

---
### Calcolo importo
La funzione `calculateTotal()` viene utilizzata per calcolare il totale dell'importo in base al prezzo e alla quantità di un prodotto selezionato.
```js
function calculateTotal() {
    var priceElement = document.querySelector(".card-text.price");
    var quantityElement = document.querySelector("form-control.quantity");
    var subtotalElement = document.getElementById("subtotal");
    var shippingCostElement = document.getElementById("shippingCost");
    var totalAmountElement = document.getElementById("totalAmount");
    if (priceElement && quantityElement && subtotalElement && shippingCostElement && totalAmountElement)
    ...
```
Inizialmente controlla se tutti gli elementi necessari sono presenti sulla pagina.

---
![bg right:30% width:650px](carrellomockup2.png)
Se tutti gli elementi sono presenti:
- Ottiene il **prezzo del prodotto** dalla stringa **priceElement** assegnandolo alla variabile **price**
- Ottiene la **quantità** del prodotto dal **campo di input in quantityElement**.
- Calcola il **totale moltiplicando il prezzo per la quantità** e assegna il risultato alla **variabile total**.
```js
 var total = price * quantity;
 ```
---
![bg right:30% width:650px](carrellomockup4.png)
A questo punto:
- Aggiorna il contenuto dei vari elementi HTML con i prezzi finali.
- Si imposta il costo di spedizione
- Calcola l'**importo totale** sommando il **totale del prodotto al costo di spedizione** e assegna il risultato alla **variabile totalAmount**.

---
![bg right:30% width:650px](carrellomockup3.png)
#### Rimozione del prodotto
```js
function removeProduct(event) {
    var card = event.target.closest(".card");
    card.remove();

    var subtotalElement = document.getElementById("subtotal");
    var shippingCostElement = document.getElementById("shippingCost");
    var totalAmountElement = document.getElementById("totalAmount");

    if (subtotalElement && shippingCostElement && totalAmountElement) {
        subtotalElement.innerHTML = "€0,00";
        shippingCostElement.innerHTML = "€0,00";
        totalAmountElement.innerHTML = "€0,00";
    }
}
```
La funzione `removeProduct(event)` viene utilizzata per rimuovere il prodotto dal carrello reimpostando a zero i valori dei vari elementi html.

---
## Responsive mockup
![width:900px](mockup.png)

---
## Analisi [GTmetrix](https://gtmetrix.com/)
![width:750px](gtmetrix1.png)
![height:150px](gtmetrix2.png)

---
## Analisi [SEOptimer](https://www.seoptimer.com/)
![width:950px](seo.png)

---
![bg right:40% width:350px](contatti2.png)
## Contatti
In questa pagina ho inserito gli **estremi di contatto** e ho incluso un **form** per permettere alle persone di **contattarci direttamente dalla pagina**.

---

# Grazie per l'attenzione
Silvia Lia