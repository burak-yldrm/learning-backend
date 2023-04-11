# Bir Web Sayfasının Yüklenmesiyle İlgili 4 DNS Sunucusu Vardır

Bir web sayfasının yüklenmesi sırasında, genellikle dört DNS sunucusu ile etkileşim kurulur:

- **Local DNS Sunucusu:** Kullanıcının bilgisayarında veya ağında bir DNS sunucusu varsa, kullanıcının tarayıcısı ilk olarak bu sunucuya istek gönderir. Local DNS sunucusu, istenilen web sitesinin IP adresini daha önce cache'lemişse ve hala geçerliyse, bu adresi tarayıcıya hemen gönderir. Aksi takdirde, tarayıcı daha sonra bir sonraki DNS sunucusuna sorgu gönderir.

- **Root DNS Sunucusu:** Kullanıcının yerel DNS sunucusu istenen web sitesinin IP adresini bilmiyorsa, root DNS sunucusu ile iletişim kurar. Root DNS sunucusu, .com, .org, .edu gibi üst düzey alan adlarının (top-level domains) yönetimini sağlar ve istekli alan adının uzantısı (örneğin .com) tarafından yönetilen yetkili DNS sunucularının IP adreslerini döndürür.

- **Yetkili DNS Sunucusu:** Root DNS sunucusu, alan adının uzantısının yetkili DNS sunucusunun IP adresini döndürür. Bu sunucu, istenilen alan adının IP adresini döndürebilecek kayıtları içerir ve cevabı yerel DNS sunucusuna gönderir.

- **Recursive DNS Sunucusu:** Yerel DNS sunucusu, cevabı almak için istekli DNS sunucusuna istek gönderir. Ancak istekli sunucu sadece tek bir IP adresi döndürür. Bu durumda, yerel DNS sunucusu genellikle bir "recursive" sorgu yapar ve yetkili DNS sunucusu ile etkileşime girerek tüm IP adreslerini elde eder. Bu IP adresleri daha sonra yerel DNS sunucusuna ve nihayetinde tarayıcıya gönderilir. Tarayıcı, IP adresini kullanarak istenen web sitesine bağlanır ve içeriği alır