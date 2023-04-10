# Tarayıcının Üst Düzey Yapısı 

Tarayıcıların çalışma prensiplerini anlamak için, tarayıcının ana bileşenlerini anlamak önemlidir. Bu bileşenler aşağıdaki gibidir:

- **The user interface:** Tarayıcının ana bileşenlerinden biri olan kullanıcı arayüzü, adres çubuğu, geri/ileri düğmesi, yer imi menüsü gibi öğeleri içerir. Kullanıcı arayüzü, kullanıcının istenen sayfayı görüntülemesi için tasarlanmıştır ve tarayıcının diğer bölümlerinden farklı bir şekilde görüntülenir.

- **The browser engine:** Tarayıcının arayüzünü ve içeriğini oluşturan motor, arayüz ve oluşturma motoru arasındaki eylemleri sıralar. Tarayıcı motoru, HTML, CSS ve JavaScript gibi kodları ayrıştırmak, yorumlamak ve görüntülemek için kullanılır.

- **The rendering engine:** Tarayıcının, kullanıcının istediği içeriği işlemek ve görüntülemek için kullandığı bileşendir. İstenen içerik HTML ise, işleme motoru HTML ve CSS'yi ayrıştırır ve ayrıştırılan içeriği ekranda görüntüler.

- **Networking:** Tarayıcının, HTTP istekleri gibi ağ çağrıları için, farklı platformlar için farklı uygulamalar kullanarak platformdan bağımsız bir arabirim sağlayan bileşenidir.

- **UI backend:** Tarayıcının, açılan kutular ve pencereler gibi temel widget'ları çizmek için kullanılan arka uç bileşenidir. Bu bileşen, platforma özgü olmayan bir genel arabirim sağlar ve altında işletim sistemi kullanıcı arayüzü yöntemlerini kullanır.

- **JavaScript interpreter:** JavaScript kodunu ayrıştırmak ve yürütmek için kullanılan bileşendir. JavaScript, web sayfalarında sıklıkla kullanılan bir kodlama dilidir.

- **Data storage:** Tarayıcının, kullanıcı verilerini (örneğin çerezler) yerel olarak kaydetmesi gerektiği durumlarda kullanılan bileşendir. Tarayıcılar, localStorage, IndexedDB, WebSQL ve FileSystem gibi depolama mekanizmalarını desteklerler.

Bu bileşenler, bir tarayıcının çalışma prensiplerinin anlaşılması için önemlidir ve birçok tarayıcı bu bileşenleri farklı şekillerde kullanarak özelleştirebilir.

![Tarayıcılar nasıl çalışır](https://github.com/burak-yldrm/learning-backend/blob/main/doc/Taray%C4%B1c%C4%B1lar%20nas%C4%B1l%20%C3%A7al%C4%B1%C5%9F%C4%B1r.png)