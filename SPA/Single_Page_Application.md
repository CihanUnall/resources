#### SPA (Single Page Application) Nedir?

Single Page Application (SPA), web uygulamalarının sadece tek bir HTML sayfası üzerinden çalıştığı bir tür web uygulamasıdır. SPA'lar, sayfalar arası geçişleri sağlamak için sayfanın tamamını yeniden yüklemek yerine, yalnızca ihtiyaç duyulan verileri ve içerikleri günceller. Bu, kullanıcı deneyimini daha hızlı ve akıcı hale getirir.

#### SPA'ların temel avantajları:

###### Hızlı kullanıcı deneyimi:

    Sayfa yenilemesi olmadığı için daha hızlıdır.

###### Dinamik içerik yükleme:

    Sayfa yeniden yüklenmeden içerik değişebilir.

###### Asenkron veri güncellemeleri:

    API'ler ile veri çekilebilir ve güncellenebilir, sayfa taze bir şekilde yeniden yüklenmez.

SPA'larda genellikle JavaScript kullanılarak içerikler dinamik bir şekilde yönetilir. Bu yüzden, SPA'larda DOM, JavaScript aracılığıyla manipüle edilir.

#### DOM (Document Object Model) Nedir?

DOM, bir web sayfasının yapısını, içeriğini ve stilini temsil eden bir modeldir. Web sayfası yüklendiğinde, HTML ve CSS dosyaları DOM'a dönüştürülür ve JavaScript bu DOM üzerinde değişiklikler yaparak sayfayı dinamik bir şekilde yönetebilir. Örneğin, sayfadaki bir butona tıklanıldığında DOM aracılığıyla butonun stilini değiştirebilir veya sayfadaki metni güncelleyebilirsiniz.

DOM, web sayfasındaki her öğeyi (etiketler, metinler, görseller, vb.) bir ağaç yapısı şeklinde organize eder ve JavaScript bu ağacın elemanlarına erişip manipüle edebilir.

#### DOM'un yapısal öğeleri:

###### Doküman (Document):

     Sayfanın genel yapısı.

###### Elementler (Elements):

     HTML etiketleri (örneğin <div>, <p>, <h1>).

###### Nodlar (Nodes):

     DOM ağaç yapısındaki her bir eleman bir düğümdür.

###### Attributes (Öznitelikler):

     HTML öğelerinin özellikleri (örneğin, id, class, src gibi).

#### SPA ve DOM Arasındaki İlişki

SPA'da, bir kullanıcı sayfayı gezdiğinde, her sayfa geçişi DOM üzerinde yapılır. Ancak, bir SPA'nın ana özelliği olan sayfa yenilemesiz navigasyon sırasında, JavaScript bu DOM manipülasyonlarını kontrol eder.

###### Örnek:

    React, Vue veya Angular gibi framework'ler, sayfanın sadece gerekli kısımlarını günceller.
    Bu işlem Virtual DOM (Sanal DOM) kullanarak daha hızlı yapılır. Virtual DOM, gerçek DOM üzerinde yapılan işlemlerden önce yapılan sanal bir kopyadır. Bu sayede, gereksiz güncellemelerden kaçınılır.

#### Selektörler (Selectors) Nedir?

Selektörler, DOM içindeki öğeleri (HTML etiketlerini) tanımlamak ve bunlara erişmek için kullanılan yöntemlerdir. JavaScript'te, bir öğe ile etkileşimde bulunmak için önce onu seçmeniz gerekir. Bu işlemde kullanılan selektörler şunlar olabilir:

##### 1. ID Selektörü

> getElementById(): Sayfadaki bir öğeyi, id özelliği ile seçer.

###### Örnek:

> const element = document.getElementById('myElement');

##### 2. Class Selektörü

> getElementsByClassName(): Sayfadaki bir öğeyi, class adı ile seçer.

###### Örnek:

> const elements = document.getElementsByClassName('myClass');

##### 3. Tag Selektörü

> getElementsByTagName(): Sayfadaki tüm öğeleri, etiket adıyla seçer.

###### Örnek:

> const elements = document.getElementsByTagName('div');

##### 4. CSS Selektörleri ile Seçim (querySelector ve querySelectorAll)

> querySelector(): CSS seçicisi kullanarak tek bir öğeyi seçer.

###### Örnek:

     const element = document.querySelector('.myClass');

> querySelectorAll(): CSS seçicisi kullanarak birden fazla öğeyi seçer.

###### Örnek:

> const elements = document.querySelectorAll('.myClass');

#### SPA'da DOM Manipülasyonu

SPA uygulamalarında, DOM manipülasyonu genellikle JavaScript ile yapılır. Örneğin, sayfanın içerikleri dinamik olarak güncellenir veya veri çekme işlemleri yapılır.

    React gibi frameworklerde, DOM manipülasyonu, React'ın sanal DOM (Virtual DOM) kullanarak daha verimli bir şekilde yapılır. React, gerçek DOM ile sanal DOM arasındaki farkları belirler ve sadece gerekli olan öğeleri günceller.
    Vue.js ve Angular gibi diğer modern çerçeveler de benzer şekilde DOM üzerinde verimli değişiklikler yapar.

#### Sonuç

    SPA, kullanıcıya hızlı bir deneyim sunmak için sayfa yenilemeyi ortadan kaldırır ve dinamik içerik güncellemeleri sağlar.
    DOM, sayfanın yapısını temsil eder ve JavaScript ile bu yapıyı değiştirmek mümkündür.
    Selektörler, DOM öğelerini seçmek ve üzerinde işlem yapmak için kullanılır.

    https://education.github.com/pack/redeem/copilot-student About GitHub Copilot
Use GitHub Copilot to get autocomplete-style suggestions from an AI pair programmer as you code.

Offers

