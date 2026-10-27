
# VineCast TV

**Modern IPTV ve VOD Web Oynatıcı | Android TV · LG webOS · FlutterFlow WebView**

VineCast TV; M3U/M3U8 oynatma listelerini kullanmak ve internet üzerinden erişilebilen canlı yayınları veya isteğe bağlı video içeriklerini oynatmak üzere tasarlanan, televizyon kullanımına odaklı bir web uygulamasıdır.

Arayüz; uzaktan kumandayla gezinme, geniş ekran kullanımı ve farklı WebView ortamlarına uyum hedefleri doğrultusunda geliştirilir.

## İçindekiler

- [Özellikler](#özellikler)
- [Teknoloji Yığını](#teknoloji-yığını)
- [Gereksinimler](#gereksinimler)
- [Yerel Kurulum](#yerel-kurulum)
- [Üretim Derlemesi](#üretim-derlemesi)
- [FlutterFlow WebView Entegrasyonu](#flutterflow-webview-entegrasyonu)
- [Güvenlik ve Gizlilik](#güvenlik-ve-gizlilik)
- [Lisans](#lisans)

## Özellikler

### IPTV ve VOD

- **M3U/M3U8 oynatma listeleri:** Desteklenen oynatma listelerinin ayrıştırılması ve kanal bilgilerinin işlenmesi.
- **HLS oynatma:** Uyumlu HLS akışlarının HLS.js üzerinden oynatılması; tarayıcının yerel HLS desteği de dikkate alınır.
- **Canlı yayın ve VOD:** Uygun kaynaklar için canlı yayın ve isteğe bağlı video oynatma deneyimi.
- **Hata yönetimi:** Erişilemeyen veya desteklenmeyen akışlar için kullanıcıya anlaşılır geri bildirim sağlanması.

### Televizyon arayüzü

- **D-pad navigasyonu:** Yön tuşları ve onay düğmesiyle menüler, kanal listeleri ve oynatıcı kontrolleri arasında gezinmeye uygun tasarım.
- **Uzaktan kumanda odak yönetimi:** Odak göstergelerinin görünür tutulması ve klavye tabanlı gezinmenin desteklenmesi.
- **Geniş ekran tasarımı:** Televizyon ekranlarında okunabilir metinler ve kolay erişilebilir kontroller.

### QR ve bağlantı paylaşımı

- **QR kod üretimi:** Desteklenen bağlantı veya aktarım bilgilerinin QR koduyla gösterilmesi.
- **Derin bağlantı (deep link):** Uygulama tarafından tanımlanan bağlantı biçimi üzerinden uygun içeriğin açılmasına yönelik altyapı.
- **Güvenli aktarım:** QR koduna veya bağlantıya hassas erişim bilgileri eklenirken dikkatli olunması.

> Not: Bu özelliklerin çalışması, ilgili bileşenlerin ve olay işleyicilerinin uygulama kaynak kodunda gerçekten bulunmasına bağlıdır. README tek başına işlev eklemez.

## Teknoloji Yığını

| Teknoloji | Kullanım amacı |
|---|---|
| React 19 | Kullanıcı arayüzü ve bileşenler |
| TypeScript | Tür güvenliği ve kod bakımı |
| Vite | Geliştirme sunucusu ve üretim derlemesi |
| Tailwind CSS v4 | Yardımcı sınıflarla arayüz stilleri |
| HLS.js | Uyumlu tarayıcılarda HLS akışı oynatma |
| qrcode | QR kodu oluşturma |
| Framer Motion | Arayüz animasyonları |
| lucide-react | Simge bileşenleri |
| Bun | Paket yönetimi ve komut çalıştırma |

## Gereksinimler

- Güncel bir Bun sürümü
- Git
- Desteklenen bir web tarayıcısı
- Oynatma testi için erişilebilir bir M3U/M3U8 kaynağı

## Yerel Kurulum

### 1. Depoyu indirin

```bash
git clone https://github.com/isgcep-ux/VineCast-Tv.git
cd VineCast-Tv
```

### 2. Bağımlılıkları yükleyin

Depoda `bun.lock` bulunuyorsa:

```bash
bun install
```

### 3. Geliştirme sunucusunu başlatın

```bash
bun run dev
```

Terminalde gösterilen yerel adresi tarayıcıda açın. Vite projelerinde adres genellikle `http://localhost:5173` olur; terminalde gösterilen adresi esas alın.

## Üretim Derlemesi

Uygulamayı üretim için derleyin:

```bash
bun run build
```

Derleme çıktısı, standart Vite yapılandırmasında `dist/` dizinine yazılır.

Derlenmiş sürümü yerel olarak önizlemek için:

```bash
bun run preview
```

Bu komutların çalışması için `package.json` dosyasında sırasıyla `dev`, `build` ve `preview` betiklerinin tanımlanmış olması gerekir.

## FlutterFlow WebView Entegrasyonu

VineCast TV, FlutterFlow içinde bir WebView üzerinden açılacak şekilde barındırılabilir. WebView entegrasyonu, web uygulamasının FlutterFlow projesine kendiliğinden yerel bir Flutter bileşeni olarak dönüştürüldüğü anlamına gelmez.

### 1. Web uygulamasını yayınlayın

Önce uygulamayı bir web barındırma hizmetinde yayınlayın. HTTPS kullanan, erişilebilir bir yayın adresi elde edin.

Örnek adres biçimi:

```text
https://your-domain.example
```

Bu adres örnektir; kendi yayın adresinizle değiştirin.

### 2. FlutterFlow'a WebView ekleyin

1. FlutterFlow projenizi açın.
2. WebView bileşenini destekleyen bir sayfaya ekleyin.
3. WebView URL alanına yayınladığınız VineCast TV adresini girin.
4. Bileşeni sayfaya ve ekran boyutuna uygun şekilde düzenleyin.
5. Hedef cihazda ağ erişimini, ekran yönünü, tam ekran davranışını ve odak yönetimini test edin.

FlutterFlow sürümünüze göre WebView bileşeninin özellikleri ve kullanılabilir eylemler değişebilir.

### 3. D-pad ve uzaktan kumanda

Android TV veya TV kutusunda aşağıdaki kontrolleri gerçek cihazda test edin:

- Yukarı/aşağı/sol/sağ yön tuşları
- OK/Enter
- Geri tuşu
- Kanal listesi ve oynatıcı kontrolleri arasında odak geçişi

Web sayfasındaki klavye olaylarının WebView tarafından doğru iletildiğini doğrulayın. Gerekirse FlutterFlow tarafında özel eylem veya yerel kod gerekebilir.

### 4. JavaScript ve uygulama iletişimi

Web uygulamasıyla FlutterFlow arasındaki iletişim, kullanılan WebView bileşeninin desteklediği JavaScript köprüsüne bağlıdır. `window.postMessage` tek başına her FlutterFlow WebView kurulumunda yerel uygulamayla çift yönlü iletişim garantisi vermez.

Bir köprü kurmadan önce mesaj biçimini belirleyin. Örneğin:

```json
{
  "type": "OPEN_CHANNEL",
  "payload": {
    "channelId": "example-channel"
  }
}
```

Bu yalnızca örnek mesaj biçimidir. `example-channel` gerçek bir kanal değildir. Mesajı gönderen ve alan tarafların aynı sözleşmeyi uygulaması gerekir.

### 5. QR kod ve derin bağlantı

QR kodu, uygulamanın desteklediği bir web adresini veya tanımlanmış bir derin bağlantıyı içerebilir. Kullanılacak bağlantı biçimi uygulamada açıkça tanımlanmalı ve hedef cihazda test edilmelidir.

- Gerçek yayın adresini kullanın.
- Desteklenmeyen özel URL şemaları varsaymayın.
- Hassas oynatma listesi URL'lerini veya kimlik bilgilerini QR koduyla paylaşmayın.
- Android, LG webOS ve FlutterFlow ortamlarında bağlantı açılışını ayrı ayrı test edin.

### 6. Yayın öncesi kontrol listesi

- [ ] HTTPS üzerinden erişim çalışıyor.
- [ ] WebView sayfası doğru açılıyor.
- [ ] Uzaktan kumanda ile gezinme test edildi.
- [ ] HLS akışları hedef cihazda test edildi.
- [ ] QR kod ve derin bağlantı akışı doğrulandı.
- [ ] Geri tuşu ve tam ekran davranışı kontrol edildi.
- [ ] Hatalı veya erişilemeyen kaynaklar için kullanıcı geri bildirimi var.

## Güvenlik ve Gizlilik

- Yalnızca erişim izniniz olan yayınları ve medya kaynaklarını kullanın.
- Parolaları, API anahtarlarını ve özel oynatma listesi bağlantılarını Git deposuna eklemeyin.
- Gizli yapılandırmaları `.env` gibi yerel dosyalarda tutun; gerçek gizli değerleri istemci tarafında yayınlamayın.
- Kaynağı bilinmeyen M3U bağlantılarını açarken dikkatli olun.
- Kullanıcıların eklediği URL'leri doğrulayın ve uygulama içinde güvenli hata yönetimi uygulayın.

## Lisans

Lisans bilgisi için depodaki `LICENSE` dosyasını kontrol edin. Lisans dosyası yoksa dağıtımdan önce projeye uygun bir lisans ekleyin.
p