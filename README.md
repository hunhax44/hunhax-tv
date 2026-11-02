# 🇹🇷 HunHax TV — CloudStream Repository

HunHax TV, CloudStream için Türkçe açıklamalara sahip, Android telefon ve Android TV odaklı bir eklenti deposu projesidir.

## Kategoriler için yol haritası

- Film
- Dizi
- Anime
- Belgesel
- Çizgi film
- Herkese açık canlı yayınlar

> Bu depo başlangıç iskeletidir. Henüz yayımlanmış/kurulabilir bir içerik eklentisi içermez.
> `plugins.json`, ilk eklenti derlenene kadar boş bir listedir. Yalnızca yayınlama ve dağıtma
> hakkımız olan kaynaklar kullanılmalıdır; telif korumalı içeriklerin izinsiz kopyalarına
> veya erişim kısıtlarını aşan kaynaklara yönelik eklentiler eklenmemelidir.

## CloudStream'e ekleme

Derleme başarılı olduktan sonra CloudStream → Ayarlar → Eklentiler → Depo ekle bölümüne şu adresi gir:

```text
https://raw.githubusercontent.com/hunhax44/hunhax-tv/builds/repo.json
```

## Geliştirme

Bu depo, CloudStream'in resmi eklenti Gradle altyapısı ile kullanılmalıdır.
Henüz eklenti modülü ve Gradle Wrapper (`gradlew`) eklenmediği için GitHub Actions
iş akışı şu anda gerçek bir eklenti derleyemez. Önce resmi eklenti şablonunu depoya
dahil et ve `ExampleProvider` gibi örnek modülü koru veya kendi modülünü ekle.

Yerel derleme komutu:

```bash
./gradlew make makePluginsJson
```

Windows:

```powershell
.\gradlew.bat make makePluginsJson
```

## Otomatik yayınlama

`.github/workflows/build.yml`:
- `main` dalına push yapıldığında veya Actions ekranından elle çalıştırıldığında tetiklenir.
- JDK 17 ve Android SDK kurar.
- CloudStream eklentilerini derler ve `plugins.json` üretir.
- `.cs3` paketlerini, `plugins.json` ve `repo.json` dosyalarını `builds` dalına yayınlar.

`builds` dalı otomatik üretilir; elle düzenleme.

## Kaynaklar

- [CloudStream geliştirici belgeleri](https://recloudstream.github.io/csdocs/devs/gettingstarted/)
- [Kendi JSON deponu oluşturma](https://recloudstream.github.io/csdocs/devs/create-your-own-json-repository/)
- [Resmî eklenti şablonu](https://github.com/recloudstream/TestPlugins)

## Lisans

Bu başlangıç dosyaları MIT lisansı altında sunulur. Eklentilere ve üçüncü taraf kaynaklara ait lisanslar ayrıca geçerlidir.
