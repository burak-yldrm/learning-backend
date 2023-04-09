# HTTP/0.9 - Tek Satırlık (1991)

HTTP'nin belgelenmiş ilk sürümü HTTP/0.9, 1991'de ortaya atıldı. **Bu, şimdiye kadar var olan en basit protokoldü ve sadece GET adlı bir yönteme sahipti.** Bir istemci, sunucuda bir web sayfasına erişmek istediğinde, aşağıdaki gibi basit bir istekte bulunurdu.

```
GET /index.html
```

Ve sunucudan gelen yanıt aşağıdaki gibi görünürdü

```
(response body)
(connection closed)
```

- Header yoktu, 
- yalnızca GET metodu kullanılabiliyordu ve 
- yanıtın HTML olması gerekiyordu. 

Yani, sunucu talebi aldıktan sonra yanıt olarak HTML içeriğini gönderir ve içerik aktarıldıktan hemen sonra bağlantı kapatılırdı. **Protokolde header yoktu, sadece GET metodu kullanılabilirdi ve yanıtın HTML olması gerekiyordu.** Gördüğünüz gibi, bu protokol, gelecekte nelerin olacağına dair bir basamak taşından başka bir şey değildi. Ancak, web gelişimi için büyük bir adım olmuştu.