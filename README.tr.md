# SahaLens

[English](README.md) | **Türkçe**

**Yerel çalışan futbol video analiz ve taktik toplantı stüdyosu.**

SahaLens, amatör ve yarı profesyonel takımların maç görüntülerinden olay önerileri, klipler ve anlaşılır raporlar üretmesini amaçlayan bir araştırma projesidir. Ana akış: **video → AI önerileri → inceleme → klipler → takım toplantısı**.

Bu depo ürün tanıtımı içindir. Uygulama kaynak kodu, model dosyaları, maç videoları ve kullanıcı verileri burada yayımlanmaz. Kaynak kod özel bir GitHub deposunda geliştirilir. Bu depo bir kurulum paketi veya açık kaynak yazılım dağıtımı değildir.

## Arayüzden görüntüler

Görüntüler çalışan uygulamadan, kurmaca takımlar içeren yerleşik **örnek maç** kullanılarak alınmıştır. Bir maç videosunun gerçek analiz sonucu değildir; maç yayını veya gerçek oyuncu görüntüsü içermez.

### Maç stüdyosu
![SahaLens maç stüdyosu — örnek veri](assets/studio.png)

### Olay günlüğü
![Zaman damgalı olay günlüğü — örnek veri](assets/events.png)

### AI önerilerinin incelenmesi
![AI önerileri ve inceleme kuyruğu — örnek veri](assets/review.png)

### Rapor ve istatistik
![Maç raporu ve istatistikler — örnek veri](assets/stats.png)

## Neler geliştirildi?

| Alan | Uygulamadaki karşılığı |
| --- | --- |
| Maç çalışma alanı | Maçlar, kadrolar, zaman damgalı olaylar, yerel kayıt ve yedekler |
| Yayın analizi | Zamansal olay modeli, skor ve maç saati OCR, inceleme kuyruğu |
| Görüntü işleme | Oyuncu/top tespiti, takip ve saha kalibrasyonu araştırmaları |
| Taktik inceleme | 2D saha, pas ağı, saha üstü çizimler, duran top planları |
| Raporlama | Şut konumuna dayalı xG, maç hikâyesi, oyuncu ve rakip raporları |
| Toplantı | Olaylardan klip listesi, sunum görünümü, video ve yazdırılabilir rapor çıktıları |
| Kalite | Veri kaynağı açıklamaları, deneysel sonuç işaretleri ve metrik kalite kapıları |

Bu tablo geliştirilmiş modülleri anlatır; her AI çıktısının her yayın türünde doğrulanmış olduğu anlamına gelmez.

## Teknolojiler

| Katman | Teknolojiler ve amaç |
| --- | --- |
| Arayüz | JavaScript, HTML, CSS, Canvas; taktik saha, grafikler ve video çizimleri |
| Yerel sunucu | Node.js HTTP, dosya tabanlı çalışma alanı ve analiz iş kuyruğu |
| AI ve görüntü | Python, PyTorch, Ultralytics YOLO, OpenCV, NumPy, SciPy |
| Yayın olay modeli | ResNet özellikleri, zamansal konvolüsyon/Transformer ve model topluluğu |
| Sesli notlar | faster-whisper ile yerel konuşma çözümleme |
| Kalite güvencesi | ESLint, Node test runner, Python unittest, Playwright, axe-core, GitHub Actions |

## Araştırma durumu

Proje ticari bir ürün veya hatasız otomatik istatistik sağlayıcısı olarak sunulmaz. Yayın olayları, takım ataması ve oyuncu kimliğinin korunması üzerinde araştırma sürmektedir. Koordinat gerektiren istatistikler saha kalibrasyonu ve takip kalitesine bağlıdır.

Önceki deney kayıtlarında SoccerNet testinde yaklaşık **0,498 loose mAP** raporlanmıştır. Bu, yüzde 49,8 genel doğruluk değildir ve yeni yayınlarda aynı başarıyı garanti etmez. Aynı kayıtlardaki gerçek yayın denemeleri, özellikle eşik kalibrasyonu ve takım atamasında önemli eksikler göstermiştir. Bu tanıtım hazırlanırken eğitim veya benchmark yeniden çalıştırılmamıştır.

## Veriler ve mahremiyet

Temel video işleme yereldir. İsteğe bağlı dış servis özelliklerinin veri akışları ayrıca değerlendirilmelidir; tüm uygulama için koşulsuz çevrimdışı çalışma iddiasında bulunmuyoruz. Araştırmada kullanılan SoccerNet, StatsBomb ve diğer üçüncü taraf kaynakları kendi erişim/lisans koşullarına tabidir; verileri veya ağırlıkları bu depoda dağıtılmaz.

## Daha fazla bilgi

- [Mimari ve tasarım](docs/ARCHITECTURE.md)
- [Geliştirme alanları](docs/ROADMAP.md)
- [Görsellerin kaynağı ve kullanım koşulları](NOTICE.md)

Hazırlanma: 1 Kasım 2026. Ekran görüntüleri ve yetenek açıklamaları bu tarihte incelenen kaynak koduna dayanır.
