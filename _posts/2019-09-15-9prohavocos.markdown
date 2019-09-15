---
layout: post
title:  "General Mobile GM9PRO HavocOS (GSI)"
date:   2019-09-15 13:10:03 +0300
categories: CustomRom
---

# General Mobile GM9PRO HavocOS (GSI)

*Uyarı*: *Bu rom **Generic System Image (GSI)** 'dır.*

**Kullanımda sorumluluk kullanıcıya aittir.**

*Tarafımca cihaza özgü özelleştirmeler ve hata düzeltmeleri yapılmıştır.*

## Çalışan Özellikler
- Wi-Fi - Hotspot
- Bluetooth
-  4G - LTE
-  Always on Display (AOD)
- Ses
-  Arama Servisleri
-  MTP - PTP - Tethering
-  Parmak İzi
-  Çift Dokunuşla Açma - Kapatma
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
- `./install_linux.sh` çalıştırın ve kurulumun bitmesini bekleyin.
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
## Ekran Alıntıları
 ![](https://lh3.googleusercontent.com/HargkuNmlTMPPQe_YurDu0IMHI0CYmRoRFDArcDDT0q87F6B59Zc6iHuegT5ty3mlBz_iQMiJj3pvk-S2V_UAzOVD-VGs2CQ3p8zxi6oBaQduHGKZh-u10J4tmishHM7udbGNmUhetZWHvksCrNxbHROGiAtxI2yKHvL3CgTCKcCJB5YFCgNI7RhpDAt4ytkCII_IZKIpQ4ws2zLpY484HOiW5v7hEeR6I29bYfP9Ou0Q5VhiJ3MnWnQVoi5VdyU8fPGf6NwCH-MPEO4c8m8nOBLA-1KJGwR4iTZZK60Ss_VZIq0zExm4emx4-fkIcceObFMEodZE66GKS2IrlGmNfxubOub-cuS7HHaH5iAUP0nfG8lUG7Bcco0TJwE8d8Iy4PrUTRq7xGGGyTiktDLrEy4SW-EBakySiFOP1wCNlNLoJoOPr4w8ZxV_6qup22LOxqQxlnXNMr_viHlC-LamRz5q1u9aKJDcbakekg-3PSF0WxmUfR73uiYrX0r5px3gTDya3Yom3YH4SPl6HXo188ORIj9JXypSAzpBB7OZ3rJWfmV0T57e5toDh6Ems8c_qkFXiOg7YL6NcA9kdXDu4Ii2VY6dNVq5BoQtnP6FEDjNyZfEfCdFEmNcRhUx1hEO3pDSvJhmMZUiH21xl6RwX2blr0eCJh4vgKBsEXlajt82CP1tONTvv4=w329-h657-no)![](https://lh3.googleusercontent.com/5mlGPOHHcJqhE9NUy0u06BtOByk0FYEw7xArKmrZOkeogPMCIdDK5Y-1-KM6QVNNBxOT_7ucAvwH2VLaTYCzVshwbe_wzBe-GMcOJNQqvfNN7zFDCu7jThmDf7AHAaCX7EYxQ_miOB80B5CdTX9hROGqx9lvHNw-HAfgx24d5-07RDW47r7scbuGAZsS-33h__BKSLQklCds8MjVp8vYqJrgkw6VRCkmBwwaS81mPFGANfkB8hVQawR7nN4X1t82Wk0XDX2pQChj8MCz2NjAC26Qw0425dBQIOB3vJnVeIE0eLWShYvpt9w5BozealvQDrIdHT5mQkj5mEil4rBgL4pHP6tq5XJB_IYRc6NzktI9CKRiZaq6QlCae2xF_44vBCGokVMHQ7vzCm7kuMSxMZB6vIhkWLwQZFHZvea5y4xgWdRqP9B3qgY9txRYEbPxF83iJV19StxrowB5WTe7O7Km5Gz0VA1FdcCHeDKQ7ZLMlXaGBExNUsMDvWjwVwGib4XIPf5pDG0a2aiGByyyF6e41eC6TThH9KPXnmIrL1czJwcyL1iMnQFthhiwbHHyPhXqPx0_FwkjsR1bLbF6xxCDVzrk4LQ2ygDyYamvqLQV0Hhf46qs_xmGLfrXEDnva5xQMIf5p5qL5kYsl8XkDazwxXbEV-6LEiG_IF_qtbc2vUSHnh6JkCE=w329-h657-no)![](https://lh3.googleusercontent.com/rNC27RuEG0xlPJJHLOuVWipbZMH09mIOakuxaIaj_MfWMFmiYuqGVlWfA6w_5ju4ZWMucRLzE8PB-lv9ZpHXT8YVPbDIqGQ1QiWM3GbGiyGPkIrZLgwQ4TQjt6CdqihBo4AC94j4dBMnhXBMWg0nFUgHtnGACaL69BZz23kek5gbVAUUcU7FRhRW-v9rvRcW8X91zOjgM3idfM9EXI4ecWhXgkuakyz37ZS4YZZNGm2G4kCw-qHv7qZNfnXL5MADn9ccoJAKjc5Z3hvpCQ5UW1iLJhLFVgYAjnoBXhszTKrhzXxkm7DtxZo4L_q36JBZn0JDQd7w_lt1j-q_EEt7iFRuOpbffdGmVLWMQpIjdJq-9Emldfcliss2gY6lD_osRGqFVfo9F_qaxz4GBtvUsyknl5qnPHJHpDifVPcx8hFMjcwWZ2cSbLGrk-nE--VCm3RM8QlRU6rWyUhaCI-EFqf_RCymW571T_mWTIuKbMQCPaHIYOHOkQsrxUtprUcHJ60Q78p1ikGyGztAbBT34SP090rsVM5iuUPaPX4sKuPu5a51fqg2deIErIm6JNUe3-XFngN3yyGUwU204pRQ4-9zvichr7k8Pshmb2cNDz72AsH1ceq5sdeju0wzZNTqNufy5WaM17vhBr6Sen-KOwv23vkH7SJW4Kn0-x2atA8TJTTeU86Q_mg=w329-h657-no)![](https://lh3.googleusercontent.com/Bbp8pzmA6j45KvKwMiG-fafEKcvD1l9hhuYe0ZjLkl2N1YU1WKyKj5ffxbUGcAnNSAV0eDv0_5GD84A_WcBvRLRC0rSK9hkhPdeOb_RJQ2wl_std9zF6MFEoa_Wy8Wz1surA4uhAeR7HLXy9foYpxfNXtTAqvTDXGxUDp_SgmBVDbCfUy3bzEC4kpXPWYzMFmm4Qna01ZNDGnCXzJANzKfZMj-MJe3i0eIIlb3ctMyozBHjUYvIiyc2-vSGjpVlDxpc1RV4N8KtVW4YFeCv3feMFZjNBAdVmbmJyvtyWfs9CcJxjPrMKDPv_l4Qa2v7YkhayM-SFNyv2kqXuk3jHTtgc3m7ZdC7I6t2c7GYkm-LBtmRBpjz_J4CeIBE-z0kPymvkcX1S-HyHL3DrHzsYugkoFdgi71sXtNUfNrFVCjljPfU5hyBsx8s10awK0D_95qLtRDRR-PtFCmPLtQm_1GOaTU4Qoa6w2uya-WLTw7aYiNCg1H9s3ajKrwGCtGrz86Ql9Rn7aW7s5K0pMjKcSvlT8w812U7BruuzQORg4DSAk9vcTA-7iliaULuVdGWpYq_x-Iezx5Y6-YktLR8JWcsRD262KyLls0AswxF5KBcHqql4MMtAH3aeWIJ0dLhj-5Jd_Xl4sxGriSIYC9f9eBiebmJI21Og_JyYrOpDXFYf25JcKvPEvGA=w329-h657-no)
 
## Link
 [Github Release](https://github.com/zenlty/GM9Pro_Sprout-Custom-Rom/releases/download/2.9/HavocOS_ZENLTY.zip)
