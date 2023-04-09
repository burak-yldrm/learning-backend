# HTTP/1.0 - 1996

1996 yılında, HTTP/1.0 olarak adlandırılan bir sonraki HTTP sürümü, orijinal sürüme göre önemli ölçüde geliştirildi.

Sadece HTML yanıtı için tasarlanan HTTP/0.9'un aksine, HTTP/1.0 diğer yanıt formatlarıyla da başa çıkabiliyordu; yani resimler, video dosyaları, düz metin veya herhangi bir içerik türü ile de ilgilenebiliyordu. Daha fazla metod (örneğin POST ve HEAD) eklendi, istek/yanıt formatları değiştirildi, HTTP başlıkları isteklere ve yanıtlara eklendi, yanıtı tanımlamak için durum kodları eklendi, karakter seti desteği tanıtıldı, çoklu parça türleri, yetkilendirme, önbellekleme, içerik kodlaması ve daha fazlası dahil edildi.

İşte örnek bir HTTP/1.0 isteği:

```
GET / HTTP/1.0
Host: cs.fyi
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
Accept: */*
```

Gördüğünüz gibi, istekle birlikte istemci, kişisel bilgilerini, gereken yanıt türünü vb. de göndermiştir. HTTP/0.9'da istemci böyle bilgileri asla gönderemezdi çünkü header yoktu.

Yukarıdaki isteğe verilebilecek örnek bir yanıt şöyle olabilirdi:

```
HTTP/1.0 200 OK 
Content-Type: text/plain
Content-Length: 137582
Expires: Thu, 05 Dec 1997 16:00:00 GMT
Last-Modified: Wed, 5 August 1996 15:55:28 GMT
Server: Apache 0.84

(response body)
(connection closed)
```

HTTP/1.0'ın yanıtının başında, HTTP'nin sürüm numarası olan HTTP/1.0 yer alır. Sonrasında 200 durum kodu ve açıklaması bulunur.

Bu yeni sürümde, istek ve yanıt başlıkları hala ASCII kodlu olarak tutulmuş olmasına rağmen, yanıt gövdesi artık herhangi bir tür olabilir. Yani, sunucu artık istemciye herhangi bir içerik türü gönderebilir. Ancak, bu nedenle HTTP'deki "Hyper Text" terimi yanıltıcı bir hal almıştır. HMTP veya Hypermedia aktarım protokolü daha mantıklı olabilirdi, ancak isim değişikliği yapılmamıştır.

HTTP/1.0'ın önemli bir dezavantajı, bir bağlantıda birden fazla istek yapılamamasıdır. Yani, bir istemci bir şeyler gerektirdiğinde, her seferinde yeni bir TCP bağlantısı açmak zorunda kalır. Bu da her istek için üçlü el sıkışma işlemi ve yavaş başlangıç gibi performans problemlerine yol açar.

Bu durum özellikle bir web sayfasında birden fazla öğe varsa ciddi bir performans darbesi yaratır. Örneğin, 10 resim, 5 stil sayfası ve 5 JavaScript dosyası içeren bir web sayfası ziyaret edildiğinde, toplamda 20 öğenin istek yapıldığını düşünelim. Sunucu her isteği tek tek karşıladıktan sonra bağlantıyı kapatacağı için, her bir öğe ayrı ayrı bağlantıları üzerinden tek tek sunulacaktır. Bu büyük sayıda bağlantı, performansı önemli ölçüde etkileyen bir durumdur.