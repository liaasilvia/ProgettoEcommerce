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

Quest'anno abbiamo creato un **sito multi pagina per un e-commerce**. Io ho optato per la realizzazione di un negozio virtuale specializzato in abbigliamento di lusso, sfruttando le mie competenze pregresse in **HTML, CSS e Javascript**.

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
Marp conosciuto anche come _Markdown Presentation Ecosystem_ offre un approccio rapido e intuitivo per la creazione di slide basilari. Quello che noi dobbiamo fare è semplicemente scrivere un documento in **markdown**.



---
# Visual Studio Code: Programmazione
![bg right:33% width:300px](vs.png)
Ho usato il _code editor_ **Visual Studio Code**, clonando il mio repository di GitHub localmente, potendo **programmare** tranquillamente **offline** per poi sincronizzare le modifiche con il mio repository GitHub.

---
![bg right:33% width:300px](Bootstrap.png)
# Bootstrap
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
- **Home**
- **Brand**
- **Clothing**
- **Cart**
- **Contact**

Ogni pagina presenta degli elementi di base come la **navbar** e il **footer**

---
# Navbar
![width:5000px](navbar.png)
In alto abbiamo la **navbar** importante per la navigazione all'interno del nostro e-commerce.
Composta da vari elementi che permettono di avere un collegamento con le altre pagine del sito.


---
# Footer
![width:5000px](footer.png)
In basso abbiamo il **footer** un elemento importante perchè vi sono le informazioni principali dell'azienda, come indirizzo email, numero di telefono.
Nel footer della Home e dei contacts è presente anche la posizione sulla mappa di Google Maps.


---
# Homepage
![bg right:50% width:500px](home.png)
In alto abbiamo la **navbar** aseguire vi è lo **slider**, che scorre 3 fotografie diverse, successivamente vi sono altre informazioni e foto, infine vi è il **footer**. Una caratteristica importante è la presenza della finestra dei cookie.

---
# Slider
![bg right:50% width:500px](slider.png)
Nella home è presente questo slider, realizzato usando delle demo di [Swiper](https://swiperjs.com/demos) Il carosello iniziale prevede un **autoplay** genrato grazie a javascript, con un intervallo di tempo specifico e la possibilità di fare swipe e vedere le altre diapositive, tre in totale.

---
# Codice js dello slider
```js
var swiper = new Swiper(".mySwiper", {autoplay: {
  
  delay: 2500,
  disableOnInteraction: false,
}});  
]
```

---
# Cookie
![bg right:50% width:500px](cookie.png)
I cookie sono piccoli file di testo memorizzati sul tuo dispositivo quando visiti un sito web. Essi svolgono diverse funzioni, tra cui il **tracciamento** delle tue attività, il **miglioramento** dell'esperienza utente, e la **memorizzazione** delle tue preferenze durante la navigazione su Internet.


---
# Codice js dei cookie
```js
//cookie
function hideCookie() {
  let cookie = document.querySelector("#innercookie");
  cookie.style = "display:none;";
}
function showCookie() {
  let cookie = document.querySelector("#innercookie");
  cookie.style = "display:block;";
}

```

---
![bg right:50% height:400px](brand.png)
# Brand
In questa pagina vi è una breve **descrizione** del brand, dei suoi valori e delle caratteristiche principali e nella parte inferiore sono presenti tre immagini.

---
![bg right:45% width:600px](filtromockup.png)
# Clothing
La pagina dei prodotti come nella home è resa **dinamica attraverso un array di prodotti** che permette di **generare codice HTML per ogni prodotto**, inserito all'interno di un elemento specifico (determinato da un ID) nel documento HTML.
Inoltre è presente un **filtro dei prodotti** in base alla categoria (Dress, Top, Buttom)

---
# Filtro prodotti
```js
function filterProducts() {
  // Seleziona tutti gli elementi della griglia di prodotti
  var products = document.querySelectorAll('.product');

  // Ottieni la categoria selezionata
  var selectedCategory = document.querySelector('#inputCategory').value;

  // Mostra solo i prodotti della categoria selezionata
  for (var i = 0; i < products.length; i++) {
      if (products[i].dataset.category === selectedCategory || selectedCategory==='tutte') {
          products[i].style.display = 'block';
      } else {
          products[i].style.display = 'none';
      }
// Mostra tutti i prodotti all'avvio della pagina
filterProducts();
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