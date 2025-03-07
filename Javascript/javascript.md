### 1. Değişkenler ve Veri Türleri

var, let, const
Sayılar, metinler (string), diziler (array), nesneler (object)
Tip dönüşümleri

> JavaScript'te veri saklamak için değişkenler kullanılır. Değişkenler farklı veri türlerini tutabilir.

##### let, const, var:

> Değişkenler tanımlamak için kullanılır. `let` ve `const` ES6 ile gelen yeni özelliklerdir.
> `let` değişkenin değerini değiştirmeye izin verirken, `const` sabit bir değeri ifade eder ve değeri değiştirilmesine izin vermez.
> `var` eski bir özelliktir.

##### Veri Türleri: JavaScript'te kullanılan temel veri türleri:

           String (Metin): "Ali"
           Number (Sayı): 10
           Array (Dizi): [1, 2, 3]
           Object (Nesne): { name: "Ali", age: 30 }

##### Örnek:

            let sayi = 10; // Sayı tipi
            const ad = "Ali"; // String tipi
            let dizi = [1, 2, 3]; // Dizi (Array) tipi
            let nesne = { name: "Ahmet", age: 25 }; // Nesne (Object) tipi

### 2. Kontrol Yapıları

Koşullu ifadeler (if, else, switch)
Döngüler (for, while, forEach)
break ve continue komutları

> Kontrol yapıları, belirli koşullara göre kodun farklı bölümlerinin çalışmasını sağlar.

`if `ve` else`: Bir koşula göre seçim yapar.
`switch:` Birden fazla koşulu kontrol etmek için kullanılır.

##### Örnek:

            let x = 5;
            if (x > 10) {
                console.log("X, 10'dan büyük.");
            } else {
                console.log("X, 10'dan küçük veya eşit.");
            }

> Bu kodda, x'in değeri 10'dan büyükse bir mesaj yazdırılır, değilse diğer mesaj yazdırılır.

`switch `ile çoklu koşul kontrolü yapılabilir:

##### Örnek:

             let renk = "kırmızı";
             switch (renk) {
                 case "kırmızı":
                     console.log("Renk kırmızı.");
                     break;
                 case "yeşil":
                     console.log("Renk yeşil.");
                     break;
                 default:
                     console.log("Bilinmeyen renk.");
             }

> Burada, renk değişkenine bağlı olarak farklı mesajlar gösterilir.

### 3. Fonksiyonlar

Fonksiyon tanımlamaları
Parametreler ve geri dönüş değerleri
Anonim fonksiyonlar
Ok fonksiyonları (arrow functions)

> Fonksiyonlar, belirli bir işlemi gerçekleştiren kod bloklarıdır. Kodunuzu daha düzenli hale getirir.

      Fonksiyon Tanımlama: Parametre alabilir ve değer döndürebilir.
      Arrow Fonksiyonları (Ok Fonksiyonları): Daha kısa bir yazım şekli.

##### Örnek:

                 function topla(a, b) {
                 return a + b;
                 }
                 console.log(topla(3, 4)); // 7

> Bu fonksiyon, iki sayıyı toplar ve sonucu döndürür.

`Arrow function`

##### Örnek:

                     const carp = (a, b) => a * b;
                     console.log(carp(3, 4));  // 12

> Bu fonksiyon aynı işlemi daha kısa şekilde yapar.

### 4. DOM Manipülasyonu

DOM ile etkileşim (getElementById, querySelector)
HTML içeriği ve stil değiştirme (innerText, style)
Etkinlikler (events) ve event listener'lar (addEventListener)

> DOM (`Document Object Model`), web sayfasındaki HTML içeriğine JavaScript ile etkileşim sağlamak için kullanılır.

`getElementById` ve `querySelector` gibi metodlarla `HTML` öğelerine ulaşılır.
`innerText` ile metin değiştirilir.
`addEventListener` ile bir öğeye tıklama gibi etkinlikler (`events`) eklenir.

##### Örnek:

                            <button id="changeTextBtn">Metni Değiştir</button>
                            <h1 id="header">Merhaba Dünya!</h1>

                            <script>
                                document.getElementById("changeTextBtn").addEventListener("click", function() {
                                    document.getElementById("header").innerText = "JavaScript ile Metin Değişti!";
                                });
                            </script>

> Burada, butona tıklanınca başlık (h1) içeriği değişir.

### 5. Formlar ve Doğrulama

Form elemanları ile etkileşim (input, select, textarea)
Form doğrulama (required, pattern, validity)
Web sayfalarında form kullanılır. Formun doğru şekilde doldurulup doldurulmadığını kontrol etmek için doğrulama yapılır.

required gibi HTML özellikleriyle alanın boş bırakılmaması sağlanabilir.
JavaScript ile form doğrulama yapılabilir.
Örnekte:

<form id="myForm">
    <label for="username">Kullanıcı Adı:</label>
    <input type="text" id="username" required><br><br>
    <input type="submit" value="Gönder">
</form>

<script>
    document.getElementById("myForm").addEventListener("submit", function(event) {
        const username = document.getElementById("username").value;
        if (username === "") {
            alert("Kullanıcı adı boş olamaz!");
            event.preventDefault();  // Formu göndermeyi engeller
        }
    });
</script>

Bu örnekte, form gönderilmeden önce kullanıcı adı kontrol edilir. Eğer boşsa, uyarı verilir ve form gönderilmez.

### 6. Asenkron Programlama

setTimeout, setInterval
Promise ve async/await
AJAX (Asynchronous JavaScript and XML) ve Fetch API
Asenkron programlama, işlemlerin sırayla değil, paralel veya zamanlayıcılarla yapılmasını sağlar. Bu sayede kullanıcı deneyimi hızlanır.

setTimeout: Belirli bir süre sonra bir işlem yapar.
Promise ve async/await: Asenkron işlemleri daha kolay yönetmeyi sağlar.
Örnekte:
console.log("Başladı");

setTimeout(() => {
console.log("5 saniye sonra!");
}, 5000); // 5 saniye sonra çalışır

console.log("Bitti");
setTimeout 5 saniye sonra mesajı gösterir, ancak console.log("Bitti"); hemen çalışır çünkü JavaScript asenkron olarak işlem yapar.

### 7. Hata Yönetimi (Error Handling)

try, catch, finally
Hata fırlatma (throw)
Özel hata mesajları
Kod yazarken hatalarla karşılaşılabilir. Hata yönetimi, bu hataların doğru şekilde ele alınmasını sağlar.

try-catch: Hata oluştuğunda programın çökmesini engeller.
Örnekte:
try {
let sayi = 10;
if (sayi > 5) throw "Sayı 5'ten büyük!";
console.log("Bu satır çalışmaz.");
} catch (error) {
console.log("Hata: " + error); // Hata mesajı
} finally {
console.log("Bu satır her zaman çalışır.");
}
Bu örnekte, sayi 5'ten büyük olduğu için hata fırlatılır ve catch bloğu çalışır.

### 8. Diziler (Arrays)

Array metodları (push, pop, shift, unshift, map, filter, reduce)
Dizilerde döngü işlemleri (forEach, map, filter)
Diziler, birden fazla veriyi tek bir değişkende saklamak için kullanılır. Dizilerde veriler sıralıdır.

map, forEach, filter, reduce gibi metodlarla diziler üzerinde işlem yapılabilir.
Örnekte:
let dizi = [1, 2, 3, 4, 5];

// Dizinin her elemanını yazdırma
dizi.forEach(num => console.log(num)); // 1, 2, 3, 4, 5

// Dizinin elemanlarını 2 ile çarpma
let yeniDizi = dizi.map(num => num \* 2);
console.log(yeniDizi); // [2, 4, 6, 8, 10]
Burada, forEach ile her bir eleman yazdırılır, map ile her eleman 2 ile çarpılır.

### 9. Nesneler (Objects)

Nesne oluşturma ve kullanma
Nesne metodları
Nesne destrukturizasyonu
Nesneler, anahtar-değer çiftleriyle veri saklar.

Örnekte:
let kisi = {
isim: "Ali",
yas: 30,
selamla: function() {
console.log("Merhaba, benim adım " + this.isim);
}
};

console.log(kisi.isim); // Ali
kisi.selamla(); // Merhaba, benim adım Ali
Bu örnekte, kisi adlı nesne isim ve yas özelliklerine sahip, ayrıca bir selamla fonksiyonu içeriyor.

### 10. JavaScript OOP (Nesne Yönelimli Programlama)

Sınıflar (class ve constructor)
this anahtar kelimesi
Kalıtım (inheritance), polymorphism, encapsulation
Nesne Yönelimli Programlama (OOP), gerçek dünyadaki nesneleri modelleyerek programlamayı sağlar. JavaScript'te sınıflar (classes) ile OOP yapılabilir.

class: Nesne şablonlarını oluşturur.
Örnekte:
class Araba {
constructor(model, renk) {
this.model = model;
this.renk = renk;
}

    tanit() {
        console.log(`Bu bir ${this.model} model, ${this.renk} renk araba.`);
    }

}

let araba1 = new Araba("Toyota", "Kırmızı");
araba1.tanit(); // Bu bir Toyota model, Kırmızı renk araba.
Burada, Araba sınıfı bir araba modelini ve rengini tutar ve tanit fonksiyonu ile arabayı tanıtır.

### 11. Yerel Depolama (LocalStorage & SessionStorage)

Veritabanı olmadan tarayıcıda veri saklama
localStorage ve sessionStorage kullanımı

Yerel depolama, tarayıcıda veri saklamak için kullanılan bir özelliktir. Veriler, tarayıcı kapatılsa bile saklanır.

localStorage: Veriler tarayıcıyı kapatıp açsanız bile saklanır.
sessionStorage: Veriler yalnızca mevcut oturum (yani sayfa kapatılana kadar) için saklanır.
Örnekte:

// LocalStorage'a veri kaydetme
localStorage.setItem("isim", "Ahmet");

// LocalStorage'dan veri okuma
let isim = localStorage.getItem("isim");
console.log(isim); // Ahmet

// SessionStorage'a veri kaydetme
sessionStorage.setItem("gecerliIsim", "Mehmet");

// SessionStorage'dan veri okuma
let gecerliIsim = sessionStorage.getItem("gecerliIsim");
console.log(gecerliIsim); // Mehmet

Açıklama: Bu kodda, localStorage ve sessionStorage kullanılarak veriler kaydedildi ve ardından bu veriler okundu. localStorage verileri tarayıcıyı kapatsanız bile saklar, sessionStorage ise sadece aktif oturum süresince saklar.

### 12. Animasyonlar ve CSS ile Etkileşim

requestAnimationFrame
CSS ile JavaScript animasyonları
Web API'ları (Canvas API, WebGL)
JavaScript ile CSS animasyonları ve hareketler yapılabilir. Bu, görsel öğelerin etkileşimini artırmak için kullanılır.

requestAnimationFrame: Animasyonların performansını optimize etmek için kullanılır.
transition: CSS ile belirli bir süre boyunca animasyon yapılmasını sağlar.
Örnekte:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animasyon</title>
    <style>
        #kutucuk {
            width: 100px;
            height: 100px;
            background-color: blue;
            position: relative;
            transition: all 2s;
        }
    </style>
</head>
<body>

<div id="kutucuk"></div>
<button onclick="moveBox()">Kutuyu Hareket Ettir</button>

<script>
    function moveBox() {
        document.getElementById("kutucuk").style.left = "200px";
    }
</script>

</body>
</html>
Açıklama: Burada, bir butona tıklanınca mavi renkli kutu sağa doğru hareket eder. CSS transition kullanılarak hareketin 2 saniyede yapılması sağlanır.

### 13. Event Handling (Etkinlik Yönetimi)

Etkinlikler (click, mousemove, keydown vs.)
Etkinlik dinleyicileri (addEventListener)
Etkinlik akışı (event propagation)
JavaScript'te etkinlikler (events), kullanıcı etkileşimleri (tıklama, yazma, fare hareketi, vb.) sonucu tetiklenen olaylardır. Bu etkinlikleri kontrol etmek için event listener kullanılır.

Örnekte:
<button id="myButton">Tıkla</button>

<script>
    document.getElementById("myButton").addEventListener("click", function() {
        alert("Butona tıklandı!");
    });
</script>

Açıklama: Bu örnekte, butona tıklanınca bir alert (uyarı) mesajı gösterilir. JavaScript ile bu tür etkinlikleri dinleyip yanıt verebiliriz.

### 14. Web API'ları

Geolocation API (Kullanıcının konum bilgisi)
Fetch API (Veri çekme)
LocalStorage & SessionStorage (Veri depolama)
Web Workers (Arka planda çalışan işler)
JavaScript, tarayıcıda bazı yerleşik API'lere (Application Programming Interface) erişim sağlar. Bu API'ler, çeşitli tarayıcı özelliklerine erişim sağlar. Örneğin:

Geolocation API: Kullanıcının konumunu almayı sağlar.
Fetch API: Sunucudan veri çekmeyi sağlar.
Örnekte (Geolocation API):
if (navigator.geolocation) {
navigator.geolocation.getCurrentPosition(function(position) {
console.log("Enlem: " + position.coords.latitude);
console.log("Boylam: " + position.coords.longitude);
});
} else {
console.log("Geolocation desteklenmiyor.");
}
Açıklama: Bu kod, kullanıcının coğrafi konumunu alır ve enlem/boylam bilgilerini konsola yazdırır.

### 15. Modüller ve Paketler

ES6 Modülleri (import, export)
Paket yöneticileri (npm, yarn)
JavaScript, büyük projelerde modüler bir yapıya sahip olmanızı sağlar. ES6 modülleri sayesinde kodu birden fazla dosyaya bölüp daha düzenli hale getirebilirsiniz. Ayrıca npm veya yarn gibi paket yöneticileri, bağımlılıkları yönetmenizi sağlar.

Örnekte (ES6 Modülleri):

javascript
Kopyala
// math.js
export const topla = (a, b) => a + b;
export const carp = (a, b) => a \* b;

// app.js
import { topla, carp } from './math.js';

console.log(topla(3, 4)); // 7
console.log(carp(3, 4)); // 12
Açıklama: Bu örnekte, math.js dosyasındaki fonksiyonlar export ile dışa aktarılır. Diğer dosyada (örneğin app.js) bu fonksiyonlar import ile alınır ve kullanılabilir.

### 16. Tarayıcı Özellikleri ve Uygulama

Tarayıcı uyumluluğu
Çapraz Tarayıcı Testi (Cross-Browser Testing)
Kullanıcı arayüzü etkileşimi (Alert, Confirm, Prompt)
JavaScript, tarayıcıyla etkileşimi artıran birçok özellik sunar. Bu özellikler, web uygulamanızın kullanıcılara daha etkileşimli ve dinamik bir deneyim sunmasını sağlar.

Örnekte:
if (navigator.geolocation) {
navigator.geolocation.getCurrentPosition(function(position) {
console.log("Konum: " + position.coords.latitude + ", " + position.coords.longitude);
});
} else {
alert("Bu özellik tarayıcıda desteklenmiyor.");
}
Açıklama: Burada, Geolocation API kullanılarak kullanıcının konumu alınır ve bu bilgi konsola yazdırılır. Eğer tarayıcı bu API'yi desteklemiyorsa, bir uyarı mesajı gösterilir.
