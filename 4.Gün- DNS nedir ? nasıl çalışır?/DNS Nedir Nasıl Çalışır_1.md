# DNS Nasıl Çalışır?

DNS, bir alan adının IP adresine çözülmesi işlemini gerçekleştiren bir hiyerarşik dağıtık veritabanı sistemidir. İşleyiş aşağıdaki adımları içerir:

- Bir kullanıcı bir tarayıcıda belirli bir alan adını girer.

- Tarayıcı, alan adının IP adresini bulmak için yerel DNS önbelleğindeki kayıtları kontrol eder. Eğer kayıt varsa, doğrudan IP adresini kullanarak web sunucusuna erişir.

- Eğer kayıt yoksa, tarayıcı yerel DNS sunucusuna sorgu gönderir.

- Yerel DNS sunucusu, alan adının IP adresini biliyorsa, doğrudan yanıt verir. Eğer bilmiyorsa, üst DNS sunucusuna yönlendirir.

- Üst DNS sunucusu, sorgunun cevabını bilmiyorsa, alt DNS sunucusuna yönlendirir. Bu işlem tekrar edilerek, sorgu kök DNS sunucusuna kadar devam eder.

- Kök DNS sunucusu, alan adının kaydını tutan otoritatif DNS sunucusunu tarayıcının yerel DNS sunucusuna bildirir.

- Yerel DNS sunucusu, otoritatif DNS sunucusuna sorgu gönderir ve yanıt olarak IP adresini alır.

- Tarayıcı, aldığı IP adresini kullanarak web sunucusuna erişir ve web sitesinin içeriğini görüntüler.

DNS, bu işlemleri çok hızlı bir şekilde gerçekleştirir ve web sitelerine hızlı bir şekilde erişim sağlar. DNS, internetin güvenli ve hızlı çalışmasına önemli bir katkı sağlar.