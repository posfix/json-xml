﻿# PosFix servis girdi ve çıktıları

## Servisleri daha iyi anlayabilmek adına bu girdi ve çıktıları inceleyebilirsiniz.

## Kullanım

PosFix servislerini kullanabilmek için [PosFix'e](https://www.posfix.com.tr) üye olmalısınız. Üye olduktan sonra PosFix sizinle private ve public keylerinizi paylaşacaktır. Paylaşılan bu anahtarları kendi projenizde ilgili yerlere yazarak saklamanız ve kullanmanız gerekmektedir.

## Önemli Notlar

Örnek projelerimizi daha iyi anlamak için [PosFix geliştirici merkezini](http://developer.posfix.com.tr) takip etmeniz büyük önem arz etmektedir.

İlgili örnek herhangi bir dilde PosFix servislerine göndereceğiniz verileri görebilmeniz ve anlayabilmeniz için örnekler barındırır. İlgili örneği kendi private key ve public key'inizle birlikte test ederek kullanabilirsiniz. Sonrasında benzer kullanımları kendi projenize referans alarak ilerleyebilirsiniz. Örnek datalardaki değişkenleri kendi projenizdeki gerçek verilerle set etmeyi unutmayınız.

* Servisleri kullanabilmek için PosFix kurum başvuru aşamalarını tamamlamış olmanız gerekmektedir. Başvuru adımlarını tamamladıktan sonra kurum panelinizden alabileceğiniz public ve private key bilgileri ile servisleri kullanabilirsiniz.
* Entegrasyon işlemlerinde encoding “UTF-8” kullanılması gerekmektedir. Özellikle token parametresinden kaynaklı alınan hataların büyük çoğunluğu encoding problemlerinden kaynaklanmaktadır. Ek olarak XML dili için olan özel karakterlerin gönderiminde hata almamak için yine encoding yapılması gerekmektedir.
* Servis isteği yaparaken göndermiş olduğunuz alanların başında ve sonunda oluşabilecek boşluk alanlarını kaldırmanızı ( trim() ) önemle rica ederiz. Çünkü bu alanlar oluşacak hash sonuçlarını etkilemektedir.
* Entegrasyon dahilinde gönderilen input alanlarında, kart numarası alanı dışında kart numarası bilgisi gönderilmesi halinde işlem reddedilecektir.

## Test Kartları

Testleriniz sırasında aşağıdaki kart numaralarını ve diğer bilgileri kullanabilirsiniz.

| Sıra No 	| Kart Numarası    	| SKT   	| CVC 	|
|---------	|------------------	|-------	|-----	|
| 1       	| 4282209004348015 	| 12/26 	| 123 	|
| 2       	| 5571135571135575 	| 12/26 	| 000 	|
| 3       	| 4355084355084358 	| 12/26 	| 000 	|
| 4       	| 4662803300111364 	| 10/25 	| 000 	|
| 5       	| 5166570072166334 	| 10/25 	| 000 	|
| 6       	| 4022774022774026 	| 12/26 	| 000 	|
| 7       	| 5456165456165454 	| 12/26 	| 000 	|
| 8       	| 4531444531442283 	| 12/26 	| 000 	|
| 9       	| 5818775818772285 	| 12/26 	| 000 	|
| 10      	| 4508034508034509 	| 12/26 	| 000 	|
| 11      	| 5406675406675403 	| 12/26 	| 000 	|
| 12      	| 4025903160410013 	| 07/26 	| 123 	|
| 13      	| 5345632006230604 	| 03/26 	| 310 	|
| 14      	| 4282209027132016 	| 05/26 	| 358 	|
| 15      	| 4029400154245816 	| 03/24 	| 373 	|
| 16      	| 4029400184884303 	| 01/26 	| 378 	|

## Hash Hesaplama
PosFix servislerine entegre olurken alınan hataların en sık karşılaşılanı hash değerinin doğru hesaplanmasıdır. Hash değeri her servise göre değişen verilerin yanyana eklenmesi ile oluşan değerin bir dizi işleme tabi tutulması ile oluşur.

Aşağıdaki adreste hash hesaplama ile ilgili detaylar yer almaktadır. Yine burada yer alan interaktif fonksiyon ile hesapladığınız hash fonksiyonlarını test edebilirsiniz.

[PosFix Hash Hesaplama](https://developer.posfix.com.tr/#hashCalculate)

Her örnek projenin Helper sınıfı içinde hash hesaplama ile alakalı bir fonksiyon bulunmaktadır. Entegrasyon sırasıdna bu hazır fonksiyonları da kullanabilirsiniz.

## Canlı Ortama Geçiş

* Test ortamında kullandığınız statik verilerin canlı ortamda gerçek müşteri datasıyla değiştirildiğinden emin olun.
Canlı ortamda yanlış, sabit data gönderilmediğinden emin olun. Gönderdiğiniz işlemlere ait verileri mutlaka size özel panelden görüntüleyin.
* Geliştirmeler tamamlandıktan sonra ödeme adımlarını, PosFix test kartları ile tüm olası durumlar için test edin ve sonuçlarını görüntüleyin.
* PosFix servislerinden dönen ve olabilecek tüm hataları karşılayacak ve müşteriye uygun cevabı gösterecek şekilde kodunuzu düzenleyin ve test edin. PosFix hata kodları kullanıcı dostu mesajlar olup müşterinize gösterebilirsiniz.
* Hassas olmayan verileri ve servis yanıtlarını, hata çözümü ve olası sorunların çözümünde yardımcı olması açısından loglamaya dikkat edin.
* Canlı ortama geçiş sonrası ilk işlemleri kendi kredi kartlarınız ile deneyerek sonuçlarını size özel Kurum ekranlarından görüntüleyin. Sonuçların ve işlemlerin doğru tamamlandığından emin olun.

Sorularınız olması durumunda bize [Destek](http://developer.posfix.com.tr/Home/Support) üzerinden yazabilirsiniz.
