---
layout: post
title:  "General Mobile GM9PRO HavocOS (GSI)"
date:   2019-09-15 13:10:03 +0300
categories: CustomRom
---

# General Mobile GM9PRO HavocOS (GSI)

*Uyarı*: *Bu rom **Generic System Image (GSI)** 'dır.*
*Tarafımca cihaza özgü özelleştirmeler ve hata düzeltmeleri yapılmıştır.*

## Çalışan Özellikler
- Wi-Fi | Hotspot
- Bluetooth
-  4G | LTE
-  Always on Display (AOD)
- Ses
-  Arama Servisleri
-  MTP | PTP | Tethering
-  Parmak İzi
-  Çift Dokunuşla Açma | Kapatma
-  HavocOS AOD Özelleştirmeleri
-  Bildirim Işığı (LED)
- Parlaklık Çubuğu
-  Sensörler
- ADB Servisleri
- Video Tuşu Medya Tuşu yapıldı.

## Bilinen Hatalar
- VoLTE - VoWiFi  ( [VoEnabler](https://github.com/edgd1er/voenabler) + [ims.apk](https://github.com/EnesSastim/Downloads/blob/master/ims.apk) ile çalışıyor ) 
-  FM Radio

## Rom Hakkında

- Android Sürümü : **9**
- Havoc Sürümü : **2.9**
- Derleme Numarası : **PQ3B.190801.002**
- C2API : **Açık**
- SELinux Durumu : **Permissive (Serbest)**
- Vendor : **9 + AOD Destekli**
- GApss : **Nano Eklendi**
- Root : **Magisk (APK Gerekebilir)**
- Google Kamera : **Config ile Verimli Çalışıyor**
- Dolby : **Eklenmedi, Viper kullanabilirsiniz**
- PHH App : **Ekli**
- Source :  [Havoc-OS](https://sourceforge.net/projects/havoc-os/files/arm64-ab/Havoc-OS-v2.9-20190914-phhgsi_arm64_ab-Official.img.xz/download)
- Kullanılan Fix Pack : [fixpack_gm9pro_sprout](https://github.com/zenlty/fixpack_gm9pro_sprout)

## Medya Tuşu Hakkında

Keycode cinsinden MEDIA_PLAY_PAUSE olan bu özelliğin işlevi şu şekildedir.

|Tek Basma| Çift Basma  | Basılı Tutma |
|--|--|--|
| Müziği Başlat - Durdur | Müziği Değiştir |Google Asistan


Bir nevi kulaklığın orta tuşunun gördüğü işlevi görür

## Otomatik Kurulum
Fastboot ile kurulum hazırladım.

Bunun için linkten romu indirip arşivi bir klasöre çıkartın. 

Windows kullanıcıları Driver kurulumunu yapmaları gerebilir.

Linux kullanıcılarının Driver kurulumu yapmasına gerek yok.

**Uyarı : Mümkünse USB 2.0 portunu kullanın, USB 2.0 portunuz yoksa USB çoğaltıcılar ile bağlantı kurun.**

**USB çoğaltıcılar genellikle 2.0 kullanırlar.**

- Cihazı kapatıp 5 - 6 saniye bekleyin.
- Ses kısma + Güç tuşuna basılı tutarak fastboot moduna geçin
-  **Dikkat Veri Kaybı olacaktır**
- `fastboot oem unlock-go` komutunu verin ve ardından telefondan ses tuşları ile "yes" seçeneğini güç tuşu ile seçin ardından ses kısma tuşuna basılı tutun
- Windows kullanıyorsanız install-windows.bat aracını çalıştırın ve kurulumun bitmesini bekleyin cihaz açılacaktır.
-  Linux kullanıyorsanız terminal ile bulunduğunuz dizine gelin
- `chmod a+x install_linux.sh`
- `.\install_linux.sh` çalıştırın ve kurulumun bitmesini bekleyin.
- 

## Manuel Kurulum

Windows kullanıcıları Driver kurulumunu yapmaları gerebilir.

Linux kullanıcılarının Driver kurulumu yapmasına gerek yok.

**Uyarı : Mümkünse USB 2.0 portunu kullanın, USB 2.0 portunuz yoksa USB çoğaltıcılar ile bağlantı kurun.**

**USB çoğaltıcılar genellikle 2.0 kullanırlar.**

- Cihazı kapatıp 5 - 6 saniye bekleyin.
- Ses kısma + Güç tuşuna basılı tutarak fastboot moduna geçin
-  **Dikkat Veri Kaybı olacaktır**
- `fastboot oem unlock-go` komutunu verin ve ardından telefondan ses tuşları ile "yes" seçeneğini güç tuşu ile seçin ardından ses kısma tuşuna basılı tutun
-  Windows kullanıyorsanız `start.bat` dosyasını çalıştırın.
- Linux kullanıyorsanız terminal ile bulunduğunuz dizine gelip libs klasörü içine girin.
- `fastboot flash system system.img`
- `fastboot flash vendor vendor.img`
- `fastboot flash boot boot.img`
- `fastboot erase userdata`
- `fastboot reboot`
