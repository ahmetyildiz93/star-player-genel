# Uzaktan ayarlar (config/remote.json)

Uygulama her açılışta bu dosyayı okur (`main` dalındaki hâli). Telefondan düzenlemek için:
GitHub'da depoyu aç → `config` → `remote.json` → kalem simgesi → değiştir → **Commit changes**.
Değişiklik birkaç dakika içinde (GitHub önbelleği) tüm kullanıcılara ulaşır.

## Duyuru
```json
"announcement": {
  "title": "Mutlu yıllar!",
  "message": "Star Player ailesine teşekkürler 🎉",
  "active": true
}
```
- Her kullanıcı bir duyuruyu **bir kez** görür. Başlığı ya da metni değiştirip kaydettiğinde duyuru yeni sayılır ve herkese bir kez daha gösterilir; başka bir şey yapmana gerek yok.
- Kapatmak için `"active": false`.

## Güncelleme uyarısı
- `url`: Yeni sürümün indirileceği mağaza sayfası (ör. Uptodown sayfası, `https://` ile başlamalı). Boş bırakılırsa uyarıda "Güncelle" düğmesi çıkmaz.
- `latestVersionCode`: Play Store'daki en yeni sürüm kodu. Kullanıcının sürümü daha eskiyse "Yeni sürüm var" uyarısı çıkar (kapatılabilir, sürüm başına bir kez).
- `minVersionCode`: Bundan eski sürümler **kapatılamayan** bir "Lütfen güncelleyin" uyarısı görür. Yalnız ciddi bir hata varsa kullan.
- Sürüm kodu `pubspec.yaml`'daki `version: 1.0.0+1` satırında `+`'dan sonraki sayıdır.

## Özellikler
- `"lyrics": false` → Şarkı sözleri düğmesi gizlenir (ör. söz sunucusu çalışmıyorsa).

Dosya bozuk (geçersiz JSON) olursa uygulama son çalışan ayarları kullanmaya devam eder; çökmez.
