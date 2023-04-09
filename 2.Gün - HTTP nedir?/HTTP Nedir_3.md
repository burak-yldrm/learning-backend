# HTTP/1.1 - 1997

HTTP/1.0'dan sadece 3 yıl sonra, 1999'da bir sonraki sürüm olan HTTP/1.1 yayınlandı ve öncüsüne göre birçok önemli iyileştirme yapıldı. Bu iyileştirmeler şunları içerir:

Yeni HTTP yöntemleri eklendi: PUT, PATCH, OPTIONS, DELETE gibi.
HTTP/1.0'da Host başlığı gerekli değildi, ancak HTTP/1.1 zorunlu hale getirdi.
Kalıcı Bağlantılar: HTTP/1.0'da bağlantı başına sadece bir istek vardı ve istek karşılandıktan sonra bağlantı kapatılıyordu, bu da keskin bir performans darbesi ve gecikme sorunlarına neden oluyordu. HTTP/1.1, kalıcı bağlantıları tanıttı; yani varsayılan olarak bağlantılar kapatılmaz ve ardışık birden fazla isteğe izin verir. Bağlantıları kapatmak için istekte Connection: close başlığının kullanılması gerekiyor. İstemciler genellikle bağlantıyı güvenli bir şekilde kapatmak için bu başlığı son istekte gönderirler.
Pipelining: HTTP/1.1, pipelining desteğini de tanıttı. Burada istemci aynı bağlantı üzerinden sunucuya yanıtı beklemeden birden çok istek gönderebilir ve sunucu yanıtı aldığı sırayla yanıtı göndermek zorundadır. Ancak, istemci ilk yanıtın indirilmesinin tamamlandığı ve bir sonraki yanıtın içeriğinin başladığı noktayı nasıl bilebilir? Bu sorunu çözmek için, yanıtın nerede bittiğini belirlemek için İçerik Uzunluğu başlığı bulunmalıdır ve istemciler bu başlığı kullanarak yanıtın nerede bittiğini ve bir sonraki yanıtı beklemeye başlayabileceğini belirleyebilirler.

```
Kalıcı bağlantılardan veya pipelining'den faydalanmak için, yanıtta Content-Length başlığının mevcut olması gerektiğini belirtmek gerekir. Çünkü bu, istemcinin aktarımın ne zaman tamamlandığını ve bir sonraki isteği gönderebileceğini (normal sıralı istek gönderme şeklinde) veya bir sonraki yanıtın beklemeye başlayabileceğini (pipelining etkinleştirildiğinde) bilmesini sağlar.

Ancak bu yaklaşımda hala bir sorun vardı. Veriler dinamik ise ve sunucu önceden içerik uzunluğunu belirleyemiyorsa, kalıcı bağlantılardan faydalanmak mümkün olamaz. İşte bu durumu çözmek için HTTP/1.1, chunked encoding'i tanıttı. Bu durumlarda sunucu, content-Length yerine chunked encoding yöntemini kullanarak yanıtı gönderebilir. Ancak, hiçbiri mevcut değilse, bağlantı isteğin sonunda kapatılmalıdır.
```

- **Chunked Transfer:** Dinamik içerik durumunda, sunucu aktarım başladığında Content-Length'i gerçekten bulamazsa, içeriği parça parça (chunk by chunk) göndermeye başlayabilir ve her parça gönderildiğinde ilgili parça için Content-Length ekleyebilir. Tüm parçalar gönderildiğinde, yani tüm iletişim tamamlandığında, sunucu, iletişimin tamamlandığını belirtmek için sıfır olarak ayarlanmış Content-Length'e sahip boş bir parça gönderir. Sunucu, chunked transfer hakkında istemciyi bilgilendirmek için Transfer-Encoding: chunked başlığını içerir.

- **Kimlik doğrulama:** HTTP/1.0'da sadece Temel kimlik doğrulama kullanılırken, HTTP/1.1, Özet doğrulama ve Proxy kimlik doğrulamasını da içerir.

- Caching

- Byte Ranges

- Character sets

- Language negotiation

- Client cookies

- Enhanced compression support

- New status codes

- ..and more (Elimden geldiğince Türkçe yazmaya çalışıyorum fakat bazı kelime ve cümleleri çevirmemek en doğrusu bence (:) )

Bu yazıda, HTTP/1.1'in tüm özellikleri hakkında detaylı bir açıklama yapmak yerine, konunun kapsamlı olduğunu ve zaten birçok kaynakta ele alındığını belirtmek istiyorum. Ancak okumanızı önerdiğim kaynaklardan biri, [HTTP/1.0 ve HTTP/1.1 arasındaki temel farklar](https://www.ra.ethz.ch/cdstore/www8/data/2136/pdf/pd1.pdf)ı anlatan bir belgedir ve ilgilenenler için orijinal [RFC](https://www.rfc-editor.org/rfc/rfc2616) bağlantısı da burada verilmiştir. Böylece konu hakkında daha fazla bilgi edinebilirsiniz.

HTTP/1.1, 1999 yılında tanıtıldı ve uzun yıllar boyunca bir standart olarak kaldı. Ancak internetin her gün değişmesiyle birlikte, HTTP/1.1'in yaşlanmaya başladığı görülmeye başlandı. Günümüzde bir web sayfası yüklemek, eskisinden çok daha fazla kaynak tüketiyor. Basit bir web sayfası bile artık 30'dan fazla bağlantı açmak zorunda kalıyor. Peki HTTP/1.1 kalıcı bağlantılara sahipken neden bu kadar çok bağlantı gerekli dersiniz? Sebebi şu ki, HTTP/1.1'de herhangi bir anda sadece bir bağlantı açılabilir. HTTP/1.1, bunu çözmek için boru hattı kullanımını tanıttı ancak yavaş veya ağır bir istek, arkasındaki istekleri engelleyerek sorunu tamamen çözemeyebilir. Bir istek boru hattına takıldığında, diğer isteklerin gerçekleştirilmesini beklemesi gerekebilir. Bu sorunları çözmek için, geliştiriciler workarounds (çalışma yöntemleri) geliştirdi. Örneğin, sprite sayfaları, kodlanmış CSS görüntüleri, tek devasa CSS/Javascript dosyaları, alan paylaşımı vb. kullanılmaya başlandı.

