---
layout: post
title:  "A-AB Treble Zip Dönüştürme"
date:   2019-09-08 21:40:03 +0300
categories: Project Treble
---
### Çıkartılabilir ZIP Kurulum Mantığı

Bu dosyaların içinde META-INF klasörü bulunur ki içinde updater-script dosyası vardır.
Bu script dosyası içerisinde /system klasörüne çıkartma yapabilen kodlar barındırabilir.
Amacından bir kısım şöyledir , zipin içindeki dosyasını /system klasörüne çıkartır ve gerekli izinleri verir.

###  Farklılık

Buradaki farklılık treble cihazların TWRP Recovery üzerinde bölümlenmesinin /system yerine /system/system olmasıdır.

Dizin değişikliği sebebi ile script dosyası /system e çıkartma yaparken sizin bölümlemeniz /system/system olduğundan istediğiniz verime ulaşamayabilirsiniz.

# A ‘dan AB’ye Convert
**![](https://lh6.googleusercontent.com/XbMPcKHThPciTw6B3yjELZKHDhOZtSCwGrJe35Tv13wRtSrG3JkBmsHh8iSXHqKmGTUWGbc7PeXizVjdymy2d1gwzD5Aiw8pFhMu22kVoWPYkifnfXagTbCjErK8DVa8836X1Y3G)**
> Zip dosyasını bir klasöre çıkartın aşağıdaki yolu takip edin.

>META-INF\com\google\android

>Buradaki updater-script dosyasını bir metin editörü ile açın tavsiyem 

>NotePad++ dır.

>CTRL + H tuşuna basın. Üst satıra /system alt satıra da /system/system 

>yazın ve tüm açık belgelerde değiştir butonuna basın

>Ardından CTRL + S yaparak kaydedin.

>Projeyi tekrar zip haline getirin.

Aşağıdaki tabloda yer aldığı gibi AB'den A'ya dönüştürme işlemlerini yapabilirsiniz.

|       Partition         |A Only                           |AB                         |
|------------------|------------------------------- |---------------------------------|
|system            |`/system`					  | `/system/system`

