
# Katkıda Bulunma Rehberi

VineCast TV projesine katkıda bulunmak istediğiniz için teşekkürler. Daha güvenilir ve sürdürülebilir bir uygulama geliştirmek için aşağıdaki adımları izleyin.

## Başlamadan Önce

1. Depoyu kendi GitHub hesabınıza fork edin veya çalışma izniniz varsa doğrudan depoyu kullanın.
2. Git ve Bun kurulumunuzun hazır olduğundan emin olun.
3. Projeyi yerel ortamınıza alın:

   ```bash
   git clone https://github.com/isgcep-ux/VineCast-Tv.git
   cd VineCast-Tv
   bun install
   ```

## Geliştirme

Geliştirme sunucusunu başlatın:

```bash
bun run dev
```

Değişiklik yaparken mevcut proje yapısını ve kullanılan teknolojileri koruyun. Yeni bir bağımlılık eklemeden önce gerçekten gerekli olup olmadığını değerlendirin.

## Kod Standartları

- TypeScript türlerini mümkün olduğunca açık tanımlayın.
- Bileşenleri okunabilir ve yeniden kullanılabilir tutun.
- Televizyon arayüzünde görünür odak durumlarını ve D-pad navigasyonunu koruyun.
- Hatalı veya erişilemeyen medya kaynaklarını kontrollü biçimde ele alın.
- API anahtarlarını, parolaları veya özel oynatma listesi bağlantılarını depoya eklemeyin.
- Kullanıcı arayüzündeki metinlerde Türkçe dil tutarlılığına dikkat edin.

## Değişiklikleri Test Etme

Göndermeden önce mevcut komutların çalıştığını kontrol edin:

```bash
bun run build
bun run preview
```

Ayrıca mümkünse aşağıdaki senaryoları test edin:

- M3U/M3U8 oynatma listesi yükleme ve ayrıştırma
- HLS oynatma ve hata durumları
- Klavye ve TV uzaktan kumandası navigasyonu
- QR kod ve derin bağlantı akışı
- WebView içinde açılma ve geri tuşu davranışı

Bir komut proje yapılandırmasında tanımlı değilse önce `package.json` dosyasını kontrol edin.

## Pull Request Gönderme

1. Değişikliklerinizi ayrı bir dalda yapın.
2. Anlamlı ve kısa commit mesajları kullanın.
3. Değişikliğin amacını, etkisini ve yaptığınız testleri açıklayın.
4. Varsa ekran görüntüsü, hata çıktısı veya yeniden üretme adımlarını ekleyin.
5. Pull request açmadan önce değişikliklerin kapsamını gözden geçirin.

## Hata Bildirimi ve Öneriler

Bir hata bildirirken cihazı, tarayıcıyı veya WebView ortamını, sorunu yeniden üretme adımlarını ve beklenen davranışı belirtin. Hassas URL'leri ve kişisel bilgileri herkese açık raporlara eklemeyin.

Katkılarınız için teşekkür ederiz!
