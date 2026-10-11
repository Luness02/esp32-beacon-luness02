# ESP32 Beacon Spam

## Değişiklikler

Bu kodu 25.09.2018 tarihinde uyarladım:
- ESP32 altyapısına aktarıldı.

Bile bile bir `.bin` dosyası yayınlamadım. Bu projeyi Arduino ile hazırlamak çok kolay ve herkes çalışır hale getirebilmeli!  
Buradaki amaç, insanları hekleme (hacking), elektronik ve Arduino dünyasına adım atmaya teşvik etmektir; bu yüzden üşenmeyin ve kendi projelerinizi yapmaya başlayın! :D

## Hakkında

![network scanner](https://raw.githubusercontent.com/Luness02/esp32-beacon-luness02/refs/heads/main/img/networkscanner.png)

Bu Arduino projesi (sketch) varsayılan olarak 50 farklı SSID (ağ adı) ile gelir, ancak kaynak kod içinden bu listeyi kolayca düzenleyebilirsiniz :).  
Cihaz, "Beacon Frame" (işaretçi çerçevesi) olarak adlandırılan paketleri sürekli olarak yayınlayarak standart Wi-Fi tarayıcılarının yakında aktif ağlar olduğunu düşünmesini ve bunları listeye eklemesini sağlar.  
Ancak gerçekte, sadece bu ağ isimlerinin reklamını yapar; aslında gerçek bir ağ oluşturmaz. Bu yüzden "oluşturulan" bu ağlardan hiçbirine bağlanmak mümkün değildir.  

Sistem, ESP32 Arduino Core SDK içerisinde yer alan `esp_wifi_80211_tx` fonksiyonunu kullanır. Bu fonksiyon, belirli Wi-Fi çerçeveleri için paket enjeksiyonu (packet injection) yapılmasına olanak tanır.

## Sorumluluk Reddi (Disclaimer)

Gerçek bir zarara yol açabilecek bir şeyden ziyade eğlenceli bir şaka projesi olsa da, **lütfen bunu sorumluluk bilinciyle kullanın!**  
Bazı insanlar bunu bir "Sinyal Kesici (Jammer)" olarak yorumlayabilir ve jammer cihazları yasa dışıdır. Fakat bu proje yalnızca havaya bir dizi Wi-Fi paketi gönderir ve 802.11 Wi-Fi standartları dahilinde çalışır.

## Kurulum

- İlk olarak bir ESP32 geliştirme kartı edinin! 
- [Arduino IDE](https://www.arduino.cc/en/Main/software) yazılımını kurun.
- [ESP32 Arduino Core](https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/boards_manager.md) paketini yükleyin.
- Bu projeyi klonlayın (veya indirin).
- İsterseniz kod içindeki SSID (ağ) isimlerini düzenleyin.
- Araçlar > Kart menüsünden doğru kartı ve cihazınızın bağlı olduğu seri (COM) portu seçip yükle (upload) butonuna basın!

## Lisans

Bu proje MIT Lisansı altında lisanslanmıştır - detaylar için [lisans dosyasına](LICENSE) göz atabilirsiniz.

## Kaynaklar

Varsayılan 50 SSID buradaki listeden alınmıştır: http://www.makeuseof.com/tag/50-funny-wi-fi-names-network-ssid/  
Beacon çerçeveleri hakkında daha fazla bilgi için: https://mrncciew.com/2014/10/08/802-11-mgmt-beacon-frame/
