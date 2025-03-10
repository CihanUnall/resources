# SPA-DOM - Giriş ve Selektörler

## Selektörler

Bir selektör yardımıyla HTML öğelerini seçebiliriz, tıpkı CSS'te olduğu gibi. Bu, HTML öğelerini seçmek için sınıf (class), id, etiket adı ya da atribut (örneğin: `input[type="text"]`) gibi özelliklere dayalı olarak yapılabilir.

> Aşağıda en yaygın kullanılan selektörlerden bazılarını bulabilirsiniz:

###### Örnek:

```js
// ID'ye göre öğe seçme
document.getElementById("myID");

// class'a göre öğe seçme
document.getElementsByClassName("myClass");
document.getElementsByClassName("myClass:last-child");

// Etiket adına göre öğe seçme
document.getElementsByTagName("div");
```

###### Örnek:

           <div>
             <p class="myClass">Bu bir p-tag ve sınıfı var!</p>
             <p id="myID">Bu bir p-tag ve ID'si var!</p>
           </div>

> querySelector kullanırken, CSS'teki gibi sınıf ya da ID seçicileri (yani . ya da #) kullanmamız gerekir.

###### Örnek:

            document.querySelector(".myClass");
            document.querySelector("#myID");
            document.querySelector("ul");
            document.querySelector("ul li");
            document.querySelector(".myClass a");
            document.querySelector('input[type="text"]');

> Önemli Not: querySelector sadece ilk eşleşen öğeyi döner. Eğer birden fazla öğe seçmek istiyorsanız, querySelectorAll kullanmalısınız.

###### Örnek:

            document.querySelectorAll("li");
            document.querySelectorAll("ul li");
            document.querySelectorAll(".myClass");
            document.querySelectorAll('input[type="text"]');
            document.querySelectorAll("h1, h2");

JavaScript ve HTML Bağlantısı, DOM

Şimdi, bazı temel kavramları daha netleştirelim:

    JavaScript, bir öğenin sınıfı olup olmadığını nasıl bilir?
    DOM nedir?
    document nesnesi nereden gelir?

HTML'ye benzer şekilde, JavaScript de HTML belgesine içeriye veya dışarıya eklenebilir. Bu, `<script>` etiketiyle yapılır.

Sayfa yüklendiğinde önce HTML, sonra CSS, ve son olarak JavaScript yüklenir. Bu nedenle, JavaScript dosyaları genellikle HTML'nin alt kısmına yerleştirilir.

                  <body>
                    <!-- HTML içeriği -->

                    <!-- En son JavaScript dosyası yüklenir -->
                    <script src="index.js"></script>
                  </body>

Bir alternatif ise, defer özniteliğini kullanarak JavaScript dosyasını `<head>` kısmına yerleştirmektir.

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

#### DOM - Document Object Model

> DOM (Belge Nesne Modeli), HTML belgesinin yapısal bir temsilidir. JavaScript'te neredeyse her şey bir nesnedir, bu yüzden HTML elemanları da birer nesne olarak DOM ağacında yer alır. HTML belgesinin yapısal bir temsilini oluşturmak için DOM kullanılır.

> DOM ağacı, HTML belgesinin yapısının kaydını tutar ve bu yapı Node (düğüm) adı verilen birimleri içerir. Bir Node, bir `ElementNode` veya bir `TextNode` olabilir. `ElementNode`, bir HTML öğesinin (örneğin, `<div>, <p>`) tüm bilgilerini içerir. `TextNode`, HTML öğesinin içerdiği metni ve bu metnin hangi öğeye ait olduğunu tutar.

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

#### Özet (Önemli Noktalar)

> --DOM (Belge Nesne Modeli) bir HTML belgesinin yapısını temsil eder.
> --DOM, Node adı verilen öğelerden oluşur ve bu öğeler array-benzeri bir yapı olan NodeList içinde yer alır.
> --ElementNode ve TextNode türleri, HTML elemanları ve metin içeriklerini temsil eder.
> --DOM ağacı, HTML, CSS ve JavaScript'in birlikte çalışmasını sağlar.
> --JavaScript, bu ağacın üzerinden HTML öğelerini manipüle edebilir.

#### JavaScript ile Stil Verme

Her ne kadar genellikle stil verme işlemleri CSS ile yapılırsa da, bazı durumlarda JavaScript ile stil verme gerekebilir. Örneğin, kullanıcı tıklamaları veya diğer olaylara tepki olarak stil değişiklikleri yapabiliriz.

            const myDiv = document.getElementById("myDiv");
                  myDiv.style.color = "red";
                  myDiv.style.backgroundColor = "lightgray";
                  myDiv.style.fontSize = "20px";

Bir öğenin sınıf listesini değiştirme (ekleme, çıkarma veya toggle işlemi) de bazen gereklidir. Örneğin, bir Dark/Light Mode işlemi için:

            const myDiv = document.getElementById("myDiv");
                  myDiv.classList.add("highlight");  // Sınıf ekleme
                  myDiv.classList.remove("hidden");  // Sınıf çıkarma
                  myDiv.classList.toggle("active");  // Sınıf ekleme veya çıkarma

#### İçerik Ekleme

Metin eklemek için `innerText` veya `innerHTML` kullanabilirsiniz:

            const myDiv = document.getElementById("myDiv");
                  myDiv.innerText = "Merhaba Dünya!";

#### innerHTML

✅ İçeriği tamamen değiştirir ve HTML etiketleri kabul eder.
❌ Önceki içerikler silinir!
❌ Güvenlik riski oluşturabilir (XSS saldırıları).

            const myDiv = document.getElementById("myDiv");
                  myDiv.innerHTML = "<strong>Kalın Metin</strong>";

#### appendChild

✅ Sadece öğe (Node) ekler.
✅ Mevcut içeriği korur.
❌ Birden fazla öğe veya metin ekleyemez.

            const newParagraph = document.createElement("p");
                  newParagraph.innerText = "Yeni bir paragraf";

            // appendChild yalnızca tek bir öğe ekler
            document.body.appendChild(newParagraph);

#### append

✅ Hem öğe hem de metin ekler.
✅ Birden fazla öğe veya metin ekleyebilir.
✅ Mevcut içeriği korur.
❌ Eski tarayıcılarda desteklenmez (ES6 sonrası).

            const myDiv = document.getElementById("myDiv");

            // append, hem metin hem de öğe ekler
            myDiv.append("Metin ekle", document.createElement("span"));
