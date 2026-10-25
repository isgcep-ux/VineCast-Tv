# VineCast-Tv
X96Q App
# 📺 VineCast TV

**X96Q Android TV, Smart TV ve FlutterFlow WebView Launcher** için özel olarak geliştirilmiş, yüksek performanslı ve modern IPTV & VOD web oynatıcısı.

![VineCast TV Banner](https://img.shields.io/badge/VineCast-TV-orange?style=for-the-badge&logo=react&logoColor=white)
![Version](https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)

## ✨ Özellikler

-  **M3U/M3U8 Playlist Desteği:** Harici IPTV listelerini (URL veya Ham Metin) anında ayrıştırır, kategorilere ayırır ve aranabilir liste sunar.
- 📱 **QR Kod ile Yayın Aktarma:** İzlenen yayını QR kod ile telefonunuza veya başka bir cihaza anında aktarın (Deep-Link desteği).
- 🎮 **TV Kumandası (DPad) Optimizasyonu:** X96Q, LG Magic Remote ve standart TV kumandalarının yön/OK tuşlarıyla kusursuz navigasyon.
- 🚀 **FlutterFlow Launcher Uyumluluğu:** WebView içinde tam ekran, zoom'suz ve postMessage API'si ile haberleşebilen yapı.
-  **Modern Arayüz:** Tailwind CSS v4 ve Framer Motion ile akıcı, koyu tema (Dark Mode) odaklı premium tasarım.
- 📶 **Çoklu Kalite (HLS):** HLS.js entegrasyonu ile düşük ve yüksek bant genişliğine göre otomatik/manüel kalite geçişi.

## ️ Teknoloji Yığını

- **Framework:** React 19 + TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS v4
- **Video Engine:** HLS.js
- **State & UI:** Framer Motion, Lucide React
- **Package Manager:** Bun

## 📦 Kurulum ve Çalıştırma

Projeyi lokalde çalıştırmak için bilgisayarınızda [Bun](https://bun.sh/) kurulu olmalıdır.

1. Depoyu klonlayın:
```bash
   git clone https://github.com/KULLANICI_ADINIZ/vinecast-tv.git
   cd vinecast-tv
```

2. Bağımlılıkları yükleyin:
```bash
   bun install
```

3. Geliştirme sunucusunu başlatın:
```bash
   bun run dev
```
   *Uygulama varsayılan olarak `http://localhost:3000` adresinde çalışacaktır.*

4. Production derlemesi alın:
```bash
   bun run build
   bun run preview
```

## 📱 FlutterFlow WebView Entegrasyonu

VineCast TV, FlutterFlow projelerinde "Launcher" veya "IPTV Sayfası" olarak kullanılmak üzere optimize edilmiştir.

1. FlutterFlow'da bir **WebView** widget'ı ekleyin.
2. **URL** kısmına VineCast TV'nin host edildiği adresi yazın.
3. WebView Ayarları:
   - `JavaScript`: **Enabled**
   - `LocalStorage`: **Enabled**
   - `ZoomEnabled`: **Disabled**
4. **Deep-Link / Mesajlaşma:** FlutterFlow'dan TV'ye komut göndermek için WebView içinde `window.postMessage` kullanabilir, URL parametresi (`?url=...`) ile doğrudan yayın başlatabilirsiniz.

## 🎮 TV Kumanda Kısayolları

| Tuş | İşlev |
| :--- | :--- |
| **Yukarı / Aşağı** | Kanallar listesinde gezinme |
| **Sağ / Sol** | Yan menüyü açma/kapama (Tam ekran modu) |
| **OK / Enter** | Kanal seçme / Listeyi gösterme |
| **Geri / Escape** | Menüyü kapatma / Geri dönme |
| **Kırmızı (LG)** | QR Kod menüsünü açma/kapama |

## 🤝 Katkıda Bulunma

Katkılarınız, sorun bildirimleriniz ve özellik önerileriniz her zaman açıktır! Lütfen katkıda bulunmadan önce bir "Issue" açarak tartışalım.

## 📄 Lisans

Bu proje [MIT Lisansı](LICENSE) altında lisanslanmıştır.

---
*Made with ❤️ for Smart TV & IPTV Enthusiasts.*