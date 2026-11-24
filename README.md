# Marine Diesel Lab

Türkçe arayüzlü, bağımsız HTML/SVG/JavaScript eğitim uygulaması. `index.html` dosyasını tarayıcıda açmak yeterlidir. Ağ isteği, harici paket veya veri toplama yoktur.

## Başlatma ve paylaşma

Depoyu **Code → Download ZIP** ile indirin, ZIP dosyasını çıkarın ve `index.html` dosyasını güncel bir tarayıcıda açın. Kurulum veya derleme gerekmez.

GitHub Pages yayını için depo ayarlarında **Settings → Pages → Deploy from a branch → main → / (root)** seçin. Yayın adresi: [Marine Diesel Lab](https://mberkantastan.github.io/Marine-Diesel-Lab/).

Bu depodaki `index.html`, [Sites üzerindeki mevcut uygulamanın](https://marine-diesel-lab-mbt.mberkantastan.chatgpt.site/) kaynak dosyasıyla aynıdır. Sites bağlantısının erişimi kendi yayın ayarlarına bağlıdır; indirilen uygulama bağımsız çalışır.

## Dosyalar

- `index.html`: arayüz, SVG çizimleri, stiller ve animasyon/model kodunun tamamı.
- `.nojekyll`: GitHub Pages üzerinde doğrudan statik yayın.
- `README.md`: kullanım, model açıklamaları ve teknik kaynaklar.

Uygulamayı değiştirmek için `index.html` dosyasını düzenleyin. Dış bağımlılık veya sunucu yapılandırması bulunmaz.

## İçerik

- İki zamanlı, uzun stroklu, kroshedli ve uniflow süpürmeli gemi ana makinesi.
- Dört zamanlı, orta hızlı trunk piston ana makinesi; iki krank turunda bir iş çevrimi.
- Krank–biyel geometrisiyle senkron piston, piston rod, kroshed, biyel, krank ve valf hareketleri.
- Piston konumundan hesaplanan iki zamanlı skavenç port açıklığı.
- Hız kontrolü, duraklatma, 1° adım, açı sürgüsü ve sayısal açı seçimi.
- Tıklanabilir olay açıları, açıklık eğrileri, parça açıklamaları ve görünüm katmanları.
- Model bilgisi panelinden tek dosyalı çevrimdışı HTML indirme.

## Eğitim profilleri

0° yanma ÜÖN'sidir. Dört zamanlı modelde 360° gaz değişimi ÜÖN'sidir.

| Model | Egzoz açılma/kapanma | Hava açılma/kapanma | Yakıt başlangıç/bitiş |
| --- | --- | --- | --- |
| 2 zamanlı, 360° çevrim | 110° / 250° | Port: 140° / 220° | 350° / 15° |
| 4 zamanlı, 720° çevrim | 130° / 400° | Emme: 320° / 570° | 708° / 18° |

Tutuşma, püskürtme başlangıcından temsili 6° sonra başlar. Açılar üreticiden bağımsız örnek eğitim değerleridir. Teknik ayar talimatı değildir. Valf liftleri sinüs kare eğrileriyle temsil edilir; yakıt ON/OFF'tur. Port açıklığı geometriktir. Görsel devir 1× için 12 d/dk'dır; referans makine devrinden ayrıdır. Kesit boyutları şematiktir; basınç, sıcaklık veya akışkanlar dinamiği çözümü yoktur.

Hareket: `s = r(1-cos(theta)) + L - sqrt(L*L-r*r*sin(theta)^2)`.

## Kontroller

Boşluk oynat/durdur, sol/sağ yön tuşları 1°, Shift ile 10°, R sıfırla. Metin alanları ve erişilebilir düğmeler odaktayken kendi tuş davranışlarını korur. Azaltılmış hareket tercihi etkinse animasyon duraklatılmış başlar.

## Teknik kaynaklar

- [WinGD X82DF Operation Manual, §3.1.1 diesel mode](https://wingd.com/media/yemj1tfo/om_wingd-x82df-1-0.pdf)
- [Wärtsilä: Scavenging methods](https://www.wartsila.com/encyclopedia/term/scavenging-methods)
- [Wärtsilä: Trunk piston engine](https://www.wartsila.com/encyclopedia/term/trunk-piston-engine)
- [Wärtsilä: Crosshead](https://www.wartsila.com/encyclopedia/term/crosshead)

Kaynaklar mimariyi ve çevrim sırasını destekler; uygulamadaki örnek sayısal profil bunlara ait özgül makine ayarı olarak sunulmaz.
