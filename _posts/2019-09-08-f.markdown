---
layout: post
title:  "Rawprogram Nedir?"
date:   2019-09-08 15:21:03 +0300
categories: jekyll update
---
# Rawprogram ve Çeşitleri

Qualcomm işlemciye sahip cihazların bazılarında QPST aracı olan QFIL ile fabrika yazılımı (stock rom) yükleniyor. Ancak yükleme esnasında seçtiğimiz XML dosyalarının farkı var. Özellikle bazı cihazlarda bu durum önemlidir ki cihazın Seri numarası, IMEI numarası ve birtakım bilgilerin silinmesi riski var.

Rawprogram tam olarak cihazlarının bölümlerini listeler, QPST aracı olan QFIL in cihaza yüklemesi gereken dosyaların adını ve hex gibi bilgilerini taşır. Bir dosya adı değişikliği yaptığınız zaman rawprogramda da yapılması gerekiyor. QFIL rawprograma bakarak dosyaları tarar ve eksik ya da yanlışlık olduğunda olası veri kayıplarını önlemek adına hata verir.
Rawprogramı değişik isimlerle bulabilirsiniz.

> rawprogram0.xml

> rawprogram0_unsparse.xml

> rawprogram0_upgrade.xml

> rawprogram0_X.xml

> rawprogram0_xml.BAK

rawprogram0_X.xml dosyasını da yazdım ki farklı bir şey görürseniz şaşırmayın. Bu sadece bir rehber.
### Rawprogram0.xml
-   Olur da böyle bir dosyayı görürseniz romunuzun parçalı olmadığını anlamanız gerekir.
-   Romun parçalı olmadığı zamanlarda bu xml kullanılır.

### Rawprogram0_unsparse.xml
-   Romunuz muhtemelen parçalıdır. (system_1.img system_2.img system_X.img ...
-   Romun parçalı olduğu durumlarda bu xml kullanılır.

### Rawprogram0_upgrade.xml

-   Yine romun parçalı olduğu bir durumda kullanılan bir xml dosyasıdır ancak farkları aşağıda incelendi.

### Rawprogram0.xml.BAK

Romunuz parçalıdır içerisinde Unsparse ya da Upgrade vardır ancak ihtiyacınız olabilir diye parcalanmamis halinde bir xml eklenmiştir.

###  UnSparse ile UpGrade farkı 

-   En önemli kısım budur. Unsparse ve upgrade arasındaki farklar çok önemlidir ki IMEI seri numarası gibi önemli bilgileri kayıp edebilirsiniz.
-   Upgrade ile yükleme yaparsanız seri numaranız ve IMEI numaranız gibi bilgiler korunur. Sadece rom yüklenir ve cihazın /data birimi - dahili depolaması temizlenir
-   Unsparse iki duruma ayrılıyor. Bazı cihazlarda seri numarası ve IMEI gibi bilgileri silerken bazi cihazlarda silmez.
-   Bu durum şöyle ayırt edilebilir. Eğer romun içerisinde upgrade varsa Unsparse siliyordur. Lakin Unsparse dışında başka bir xml görmuyorsaniz muhtemelen silinmiyordur

|                |UNSPARSE                           |UPGRADE                         |
|------------------|------------------------------- |---------------------------------|
|IMEI            |`Silinebilir`					  | `Silinmez`
|Seri No           |`Silinebilir`            | `Silinmez`           |
|/data          |`Silinebilir`| `Silinmez`


