HTTP İsteği Nedir?

Bir HTTP isteği, bir tarayıcıdan veya başka bir istemciden bir sunucuya yapılan veri istekleridir. Bu istekler dört ana bölümden oluşur:

    Yöntem (Method):
        HTTP isteği, bir method (yöntem) kullanır. Bu yöntemler şunlardır: GET, POST, DELETE, PUT, PATCH.
            GET: Veri almak için kullanılır.
            POST: Yeni veri göndermek için kullanılır.
            PUT: Var olan veriyi güncellemek için kullanılır.
            DELETE: Veri silmek için kullanılır.
            PATCH: Verinin bir kısmını güncellemek için kullanılır.

    URL:
        URL, isteğin hedeflediği adresi belirtir. Örneğin, https://myBank.com/deposit, burada sunucunun adresi ve hangi kaynağa istek yapıldığını gösterir.

    Başlık (Headers):
        HTTP başlıkları, istek hakkında meta veri sağlar. Başlıklar, tarayıcı ve sunucu arasında bilgi aktarımı sağlar. Örneğin:
            Content-Type: Gönderilen verinin tipini belirtir (örneğin, JSON verisi gönderiyorsanız application/json).
            Accept: Sunucudan hangi tür verilerin kabul edileceğini belirtir (örneğin, JSON yanıtı almak için Accept: application/json).

    Vücut (Body):
        Veriyi içerir. POST, PUT, PATCH gibi isteklerde, sunucuya gönderilen veriler burada bulunur. Örneğin, bir banka işleminde gönderilen para miktarı gibi.

Örnek bir POST isteği:

fetch("https://myBank.com/deposit", {
method: "POST",
headers: {
"Content-Type": "application/json",
Accept: "application/json",
},
body: JSON.stringify({ euro: 1000 }),
});

URL Yapısı

Bir URL'nin farklı bölümleri vardır:

    Şema (Protokol): https:// gibi, protokolü belirtir.
    Subdomain: www gibi, ana etki alanının alt birimi.
    Alan Adı: maybank.com gibi, web sitesinin ana adresi.
    TLD (Top-Level Domain): .com, .org, .de gibi, alan adı uzantısı.
    Yol (Path): /deposit, /withdraw gibi, web sitesinde belirli bir sayfaya veya API endpoint'ine işaret eder.
    Port: :8080 gibi, sunucunun bağlantı noktasıdır. Çoğu zaman belirtilmez çünkü varsayılan portlar (80 ve 443) zaten kullanılır.

Aynı Köken Politikası (SOP) ve CORS

    SOP (Same-Origin Policy): Bu, tarayıcıların güvenlik için uyguladığı bir politikadır. Yalnızca aynı kaynaktan (protokol, alan adı, port) gelen isteklere izin verir. Örneğin, https://myBank.com adresine gelen bir istek yalnızca o kaynağa ait olmalıdır.

    SOP, kötü niyetli sitelerin bir kullanıcının tarayıcısı üzerinden farklı bir kaynağa istek yaparak saldırmasına (CSRF - Cross-Site Request Forgery) karşı bir güvenlik önlemidir.

    CORS (Cross-Origin Resource Sharing): Farklı kaynaklardan (origin) gelen isteklerin kontrol edilmesini sağlayan bir mekanizmadır. CORS, bir kaynağın başka bir kaynaktan gelen isteklere nasıl yanıt vereceğini belirler.
        Örneğin, myBank.com sunucusu, sadece https://safe-website.com gibi belirli bir kaynağa istek yapmasına izin verebilir. Başka bir kaynaktan gelen istekler CORS tarafından engellenebilir.

CORS, "ön uç" (front-end) ile "arka uç" (back-end) arasında güvenli veri paylaşımını sağlayan bir mekanizmadır.
CORS İstekleri

CORS, genellikle iki aşamalı bir süreçle çalışır:

    Preflight (Uçuş Öncesi) İsteği: Tarayıcı, sunucuya bir istek göndermeden önce, sunucudan izin alır. Yani, tarayıcı, sunucuya "Bu kaynaktan gelen isteklere izin veriyor musunuz?" diye sorar.
    Gerçek İstek: Eğer sunucu "Evet" cevabı verirse, gerçek istek yapılır.

Örnek bir CORS kontrolü:

if (protocol === "https" && origin === "myBank.com") {
// CORS izin verildi
} else {
// CORS engellendi
}

Vekil Sunucular (Proxy Servers)

CORS kısıtlamalarını aşmak için bazen proxy sunucuları kullanılır. Proxy, iki nokta arasında durarak istekleri yönlendiren bir sunucudur. Örneğin, Tor gibi anonimlik sağlayan proxy hizmetleri, CORS kısıtlamalarını aşmanıza yardımcı olabilir.
Özetle:

    SOP: Farklı kaynaklardan gelen istekleri güvenlik amacıyla engeller.
    CORS: Farklı kaynaklardan gelen istekleri kontrol eder ve güvenli bir şekilde yanıt verir.
    Proxy: CORS kısıtlamalarını aşmak için kullanılan bir araçtır.

Bu şekilde HTTP istekleri, CORS ve SOP hakkında temel bir anlayışa sahip olabilirsiniz.
