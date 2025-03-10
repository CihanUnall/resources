```js
function randomNumber() {
  return Math.floor(Math.random() * 10) + 1;
}
```

```js
function guessingGame() {
  let number = randomNumber();
  let chanse = 3;
  // promt uyarı ekranında veri girmenizi sağlar
  for (let i = 0; i < chanse; i++) {
    let userGuess = prompt(`Guess a number 1-10`);
    if (userGuess === number) {
      alert("Congratulations! You guessed it.");
      return;
    } else if (i < chanse - 1) {
      alert("Wrong guess. Try again.");
    } //alert uyarı olaraj ekrana yazı yazdırırsınız.
    alert("Sorry! You guessed wrong 3 times. The correct number is: " + number);
  }
}
```

```js
// .h1 öğesinin en yakın ebeveyn <header> öğesini seç
const h1 = document.querySelector("h1");
const header = h1.closest("header");
```

```js
//.info içindeki .info-package öğeleri varsa, .package-title öğelerinin önceki kardeş öğelerine sınır ekle
const info = document.querySelector(".info");
const infoPackege = document.querySelector(".info-package");
if (info.contains(infoPackege)) {
  let packageTitles = document.querySelectorAll(".package-title");
  packageTitles.forEach((title) => {
    const previousSibling = title.previousElementSibling;

    previousSibling.style.border = "2px solid  #072F5F";
  });
}
```

```js
//.info içindeki tüm <label> etiketlerini seç
const info2 = document.querySelector(".info");
const labels = info2.querySelectorAll("label");

labels.forEach((label) => {
  if (label.classList.contains("mild")) {
    label.style.border = "2px solid  rgb(255, 255, 0)";
  } else if (label.classList.contains("intense")) {
    label.style.border = "2px solid rgb(255, 165, 0)";
  } else {
    label.style.border = "2px solid rgb(255, 0, 0)";
  }
});
// T
```

```js
//.nav-list öğesinin çocuklarını .site-map öğesine kopyala
const navList = document.querySelector(".nav-list");
const siteMap = document.querySelector(".site-map");

// .nav-list öğesinin çocuklarını al
const navListItems = navList.children;
```

```js
// .nav-list öğesinin çocuklarını al
const navListItems = navList.children;

// .site-map öğesine, .nav-list öğesinin tüm çocuklarını kopyala
for (let i = 0; i < navListItems.length; i++) {
  siteMap.appendChild(navListItems[i].cloneNode(true));
}
```

```js

```

```js

```

```js
document.getElementById("myID");
document.getElementsByClassName("myClass");
document.getElementsByClassName("myClass:last-child");
document.getElementsByTagName("div");
```

```js
<div>
  <p class="myClass">Bu bir p-tag ve sınıfı var!</p>
  <p id="myID">Bu bir p-tag ve ID'si var!</p>
</div>
```

```js
document.querySelector(".myClass");
document.querySelector("#myID");
document.querySelector("ul");
document.querySelector("ul li");
document.querySelector(".myClass a");
document.querySelector('input[type="text"]');
```

```js
document.querySelectorAll("li");
document.querySelectorAll("ul li");
document.querySelectorAll(".myClass");
document.querySelectorAll('input[type="text"]');
document.querySelectorAll("h1, h2");
```

```js
<body>
    <!-- HTML içeriği -->
    <!-- En son JavaScript dosyası yüklenir -->
    <script src="index.js"></script>
</body>
```

```js
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width,    initial-scale=1.0" />

    <!-- CSS -->
     <link rel="stylesheet" href="style.css" />

    <!-- JavaScript dosyası defer ile sonradan yüklenir -->
    <script src="index.js" defer></script>
</head>
<body>
</body>
```

```js
elementNode = {
  elem: "div",
  classList: ["myClass1", "myClass2"],
  id: "",
  parent: "body",
  children: ["p", "p", "h3"],
};

textNode = {
  text: "Merhaba Dünya",
  parent: "div",
};
```

```js
const myDiv = document.getElementById("myDiv");
myDiv.style.color = "red";
myDiv.style.backgroundColor = "lightgray";
myDiv.style.fontSize = "20px";
```

```js
const myDiv = document.getElementById("myDiv");
myDiv.classList.add("highlight");
// Sınıf ekleme
myDiv.classList.remove("hidden");
// Sınıf çıkarma
myDiv.classList.toggle("active");
// Sınıf ekleme veya çıkarma
```

```js
const myDiv = document.getElementById("myDiv");
myDiv.innerText = "Merhaba Dünya!";
```

```js
const myDiv = document.getElementById("myDiv");
myDiv.innerHTML = "<strong>Kalın Metin</strong>";
```

```js
const newParagraph = document.createElement("p");
newParagraph.innerText = "Yeni bir paragraf";

// appendChild yalnızca tek bir öğe ekler
document.body.appendChild(newParagraph);
```

```js
const myDiv = document.getElementById("myDiv");

// append, hem metin hem de öğe ekler
myDiv.append("Metin ekle", document.createElement("span"));
```

```js
//inertext içeriği eğer true olursa değiştiriyor.  INNERTEXT
let isLogedIn = false;
if (isLogedIn) {
  const h1 = document.querySelector("h1");
  h1.innerText = "Hallo Bro!";
  h1.style.color = "red";
}
```

```js
//
const hiddenDiv = document.querySelector(".hiddenDiv");
hiddenDiv.innerHTML = `<p>Merhaba <span>Violet</span> nasılsın?</p>`;

hiddenDiv.classList.add("specialDiv");
```

```js
const hiddenDiv = document.querySelector(".hiddenDiv");
hiddenDiv.innerHTML = `<p>Wusstest du schon, dass <span>Violet</span> recht auffällig ist?</p>`;

hiddenDiv.classList.add("specialDiv");

// Dark/Ligh Mode
// hiddenDiv.classList.toggle()

const showPW = true;
// burada parola kısmının gözükmesi gözükmemesi konusudur. true olursa parola gözükür false olursa gözükmez.
if (showPW) {
  const inputPW = document.querySelector("#pw");

  // ("Key", "Value")
  inputPW.setAttribute("type", "text");
  //Bu satırda, setAttribute() metodu kullanılarak, seçilen inputPW öğesinin type özelliği değiştirilir. Başlangıçta type="password" olabilecek bir şifre giriş alanının türü burada "text" olarak değiştiriliyor. Bu, şifrenin yerine düz metin (gizlenmeden) görünmesini sağlar.
}

// appendChild() VS append() (ES6)

/*
append()
- Aynı anda birden fazla eleman veya dize eklenebilir.
- ES6 (2015) ile yeni kuruldu
- Değer döndürmez (tanımsız)
- appendChild()'dan daha esnek çalışır.

appendChild()
- yalnızca bir öğe oluşturulabilir
- başlangıçtan beri var
- Dizeleri doğrudan ekleyemezsiniz.
*/

const body = document.querySelector("body");

// 4 yeni paragraf oluşturuldu ve metin eklendi
const newParagraph1 = document.createElement("p");
newParagraph1.innerText = "P1: Ich wurde mit append erstellt!";

const newParagraph2 = document.createElement("p");
newParagraph2.innerText = "P2: Ich wurde mit append erstellt!";

const newParagraph3 = document.createElement("p");
newParagraph3.innerText = "P3: Ich wurde mit appandChild erstellt.";

const newParagraph4 = document.createElement("p");
newParagraph4.innerText = "P4: Ich wurde mit appandChild erstellt.";
// P1 ve P2 ekleme ile oluşturulur
body.append(newParagraph1, newParagraph2);
// appendChild P3 ve P4 aynı anda oluşturulamaz
// sadece bir argüman kabul eder!
// body.appendChild(yeniParagraf4, yeniParagraf3)

// Her bir öğenin kendi appendChild'ına ihtiyacı vardır
body.appendChild(newParagraph3);
body.appendChild(newParagraph4);
```

```js
let kategorie = document.querySelectorAll(".category");
kategorie.forEach((category) => {
  category.style.fontStyle = "italic";
  category.style.fontSize = "2rem";
  category.style.borderBottom = "1px solid black";
});
```

<!-- ------------------------------------------------- -->

```js
const bookListElement = document.querySelector(".book-list"); // ul yi seç
```

```js
const liElement = document.createElement("li"); // li elementi oluştur
liElement.classList.add("book");
```

```js
const bookImg = document.createElement("img");
bookImg.classList.add("book-img");
bookImg.src = book.imageUrl;
// bookImg.src
//<img  class="book-img" src="book taki urlye git">
```

```js
const bookTitle = document.createElement("h2");
bookTitle.classList.add("book-title");
bookTitle.textContent = book.title;
```

```js
const bookAuthor = document.createElement("p");
bookAuthor.classList.add("book-author");
bookAuthor.textContent = `By ${book.author}`;
```

```js
liElement.appendChild(bookImg);
liElement.appendChild(bookTitle);
liElement.appendChild(bookAuthor);
bookListElement.appendChild(liElement);
//
```

```js
const liElement = document.createElement("li");
liElement.classList.add("book");
```

```js

```

```js

```

```js

```

```js

```

```js

```
