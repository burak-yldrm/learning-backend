# Üç Yönlü El Sıkışma

Üçlü el sıkışma, TCP bağlantılarının tümünün, uygulama verileri paylaşılmadan önce istemci ve sunucu arasında bir dizi paketin paylaşıldığı bir üç adımlı el sıkışmasıyla başladığını ifade eder.

İlk olarak istemci, rasgele bir sayı (örneğin x) seçer ve bunu sunucuya gönderir (SYN paketi). Sunucu, isteği kabul eder ve bir ACK paketi gönderir. ACK paketi, sunucu tarafından belirlenen rasgele bir sayı (örneğin y) ve istemci tarafından gönderilen sayıya (+1 eklenmiş olarak) eklenen sayı (y+1) içerir (SYN ACK paketi).

Daha sonra istemci, sunucudan aldığı sayıyı (y) artırır ve y+1 sayısı ile bir ACK paketi gönderir (ACK paketi). Üçlü el sıkışması tamamlandıktan sonra, istemci ve sunucu arasında veri paylaşımı başlayabilir.

Ancak, istemci son ACK paketini gönderdikten hemen sonra uygulama verilerini göndermeye başlayabilirken, sunucu isteği yerine getirmek için ACK paketinin alınmasını beklemek zorundadır.


![Üç Yönlü El Sıkışma](https://github.com/burak-yldrm/learning-backend/blob/main/doc/Three-way%20Handshake.png)

HTTP/1.0'ın bazı uygulamaları, bu sorunu aşmak için "Bağlantıyı kapatma, tekrar ihtiyacım olacak" anlamına gelen "Connection: keep-alive" adında yeni bir başlık ekledi. Ancak, bu başlık yaygın olarak desteklenmedi ve sorun devam etti.

HTTP, bağlantısız bir protokol olmasının yanı sıra durumsuzdur. Yani, sunucu istemciyle ilgili bilgiyi saklamaz ve her istek, önceki isteklerle ilişkisiz olarak sunucunun isteği yerine getirebilecek gerekli bilgileri içermelidir. Bu, istemcinin açması gereken büyük sayıda bağlantıya ek olarak, artan bant genişliği kullanımına neden olan gereksiz verilerin kabloya gönderilmesine neden olur.