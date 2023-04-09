# HTTP/2 - 2015

HTTP/2, HTTP protokolünün ikinci ana sürümüdür ve HTTP/1.1'in yerini almıştır. HTTP/2, daha hızlı, daha güvenli ve daha verimli bir web deneyimi sunmak için tasarlanmıştır.

HTTP/2'nin bazı farkları şunlardır:

İletişimde Multiplexing: HTTP/1.1'de, web tarayıcıları tek bir sunucuya aynı anda sadece bir istek gönderebilirlerdi. Ancak, HTTP/2'de, tek bir TCP bağlantısı üzerinden birden fazla istek gönderilebilir ve sunucu da birden fazla yanıt gönderebilir. Bu, web sayfalarının daha hızlı yüklenmesine ve daha iyi performans sağlanmasına yardımcı olur.

Binary İletişim: HTTP/1.1, metin tabanlı bir protokoldür ve okunması kolaydır. Ancak, bu aynı zamanda veri yükünü de artırır. HTTP/2, ikili protokolü kullanır, yani bilgileri daha verimli bir şekilde kodlar. Bu, veri yükünü azaltır ve iletişim sürecini daha hızlı hale getirir.

Header Sıkıştırması: HTTP/1.1'de, her istek ve yanıt için gereksiz tekrarlanan bilgiler gönderilir. HTTP/2, istek ve yanıtlardaki tekrarlanan bilgileri sıkıştırmak için özel bir algoritma kullanır. Bu, veri yükünü azaltır ve iletişim sürecini daha hızlı hale getirir.

Server Push: HTTP/2'de sunucu, web sayfasının yüklenmesi için istenecek olan kaynakları istek edilmeden önce gönderebilir. Bu, web sayfalarının daha hızlı yüklenmesine yardımcı olur.

Güvenliği İyileştirilmiş: HTTP/2, Transport Layer Security (TLS) üzerinde çalışır ve bu da iletişimi daha güvenli hale getirir.

HTTP/1.1'e Göre Daha Verimli: Tüm bu özellikler bir araya geldiğinde, HTTP/2, HTTP/1.1'e göre daha verimli bir protokoldür ve daha iyi performans sunar.

![HTTP 2](https://github.com/burak-yldrm/learning-backend/blob/main/doc/HTTP2.png)