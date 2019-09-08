---
layout: post
title:  "Şifreli Cihazdan Data Yedeği Almak"
date:   2019-09-08 22:12:03 +0300
categories: Solution
---
  ## Bilgilendirme
  
  **Bu konu, kullanıcının veri kaybını önlemesini hedefleyerek paylaşılmıştır.
  Konudaki işlemleri uygulaması ve oluşabilecek her türden hasardan kullanıcı sorumludur.** 

_Aynı zamanda TWRP Recovery'de /data is not mounted hatası alıp verilerini kurmak isteyenler için de bir çözümdür._

### İzlenecek yol
> 1. Cihaza root at.
> 2. Shell ile partitionu manuel bulup dd ile yedek al.

### İlk Adım

>Cihaza bir hafıza kartı takıp içine SuperSU ya da Magisk atınız.  
TWRP'den SdCard'ı seçip cihaza root atınız.  
Kendi root yöntemleriniz varsa onları da yapabilirsiniz.  
Cihaz rootlu ise bu adımı atlayabilirsiniz.

> Root yaptıktan sonra ADB portunu açın. `adb devices` yazarak kontrol edin.
> Cihazı gördükten sonra `adb shell` yazın.
> Adb shell ekranın girdikten sonra 
> $kod_adi tarzında bir ekran ile karşılacaksınız. `su` yazıp root iznini isteyin.
> Cihazda ekranınızda beliren root iznine onay verin.
> `#kod_adi` şekline gelecektir. Eğer # gözükmedi ise root izinlerinizi tekrar kontrol edin.

### Data Partition Bulma
Cihazınızın partitionlarını biliyorsanız bu adımı atlayabilirsiniz.

>Stock Recovery veya Boot Image'i kitchen ile ayıklayın.  
Fstab dosyası içinden partitionları çekin.

Diğer bir yol ise :

`~ ls`  
**komutunu verin.  
Dosya içeriğini alacaksınız.**  
`~ cd /dev/block`  
**_Böyle tek tek klasörler arasında gezip datayı bulursunuz._**

Bir diğer yol ise :

> Twrp recovery'de iken hafıza kartını takıp yükleme kısmından depolama seç butonundan hafıza kartınızı takın.
Ana menüden Gelişmiş bölümüne girip kaydı kopyala diyin.
Ardından hafıza kartı içine recovery.log gelecektir. MTP mevcutsa pcden bağlanıp dosyayı alın. İçerisinde tüm partitionları yazılı olacaktır.
CTRL + F yaparak `/data` aratın ve tam partitionunuzu `/dev/block/mmcblk0pX` şeklinde bulacaksınız. X yerinde sayı olacaktır. Bu partitionunuzu bir yere not edin.
Eğer MTP Bağlanmıyor ise adb ekranına  `adb pull /external_storage/recovery.log` yazın.  Adb'nin kurulu olduğu dizine gelecektir. Eğer ADB portundan da alamadıysanız sd cardı pcye bağlayıp recovery log'a erişin.

Bir diğer yol ise :

Android Sürümü|Dahili Konumu| Fstab Konumu | İşlemci
|--|--|--|--|
|6.0 veya Eski Sürüm|Boot veya Recovery Imajı | /ramdisk/fstab.mt6XXX | MediaTek
|6.0 veya Eski Sürüm|Boot veya Recovery Imajı | /ramdisk/fstab.qcom | Qualcomm
|7.0 - 7.1.2 Arası Sürüm| /vendor  | /vendor/etc/fstab.mt6XXX | MediaTek
|7.0 - 7.1.2 Arası Sürüm| /vendor  | /vendor/etc/fstab.qcom | Qualcomm
|8.0  ve üzeri| /vendor  | /vendor/etc/fstab.mt6XXX | MediaTek
|8.0  ve üzeri| /vendor  | /vendor/etc/fstab.qcom | Qualcomm
| *Generic*| *Recovery Image* | /ramdisk/etc/recovery.fstab | Generic


Burada partitionlara eriştikten sonra */data* veya *userdata/* bölümünü aratın. */dev/block* ile başlayan bölümü / sonuna kadar kopyalayın.

**Partitionumuzu bulduktan sonra bir yere not edelim.  
Ben konuya not ediyorum.**  
`/dev/block/bootdevice/by-name/data`  
**Aşağıya yazdığım formule göre uyuşturmanızı kendiniz yapınız.**  
  

Kod:

```
dd if=/partitionadi of=/sdcard/dosyaninadi.img bs=4096
```

**_Örneğimiz:_**  

Kod:

```
dd if=/dev/block/bootdevice/by-name/data of=/sdcard/datayedek.img bs=4096
```

### Önemli
_**Mümkünse dosya adında boşluk ve türkçe karakterler olmasın.**_
