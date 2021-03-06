---
layout: post
title:  "Project Treble Slot Değiştirme"
date:   2019-09-08 15:21:03 +0300
categories: project_treble

---
## Project Treble Slot Değiştirme ve Avantajı


Android 8.0 ile birlikte desteğini kazanan project treble ile ilgili konular epeyce varken bu durumla ilgili kullanıcıların veya testerlerin bilmediği slot olayına değineceğim.

Slot değiştirme durumunda veri kaybı yaşanır ve OEM - BootLoader kilidi aktiflik durumu değişmez.

Project Treble'in iki çeşidi vardır. Bunlar sadece A Partition ve AB Partition olmak üzere iki kısımdır. Slot değiştirme avantajı sadece AB Partition kullanıcılarında işe yaramaktadır.

Cihazınızda varsayılan olarak A slot kullanıyorsanız ve birtakım custom rom vs değişiklikler yapıp orijinal roma geri dönmek istiyorsanız işinize yarayacaktır.


> Bunun için Treble destekli TWRP Recovery'inizi açın.

>Reboot - Yeniden Başlat Butonuna basın.

>Dikkat Veri Kaybı Olacaktır

>En altta varsayılan slot yazacaktır. Diğerini seçin.

>Ardından ana menüye gelip Wipe - Temizle sekmesine girip factory reset atın.
Diğer slota geçiş yapmış oldunuz.

O slotta oynama yapmadıysanız veya varsayılan slotu değiştirmediğiniz takdirde stock rom a geri döneceksiniz.

Slot değiştirme durumunda IMEI - Seri numaralarınız değişmez. Değişecekleri cihazınızın partitionlarına baktığınızda _a _b ile biten dosyalardan olduğunu bilin.
