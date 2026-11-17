# Sulzer 16ZAV40S - Android APK Derleme Rehberi

Bu paket, **Sulzer 16ZAV40S Pmax ve Yanma Teşhis Simülatörü** uygulamasını bilgisayara Android Studio kurmadan doğrudan **Android APK** dosyasına dönüştürmek için hazırlanmıştır.

## Yöntem 1: GitHub Actions ile Bulutta Ücretsiz APK Üretme (Önerilen)

1. [github.com](https://github.com) üzerinde ücretsiz yeni bir depo (repository) oluşturun (ör. `sulzer-16zav40s-apk`).
2. Bu ZIP dosyasını açın ve içindeki **tüm dosya ve klasörleri** (`.github` klasörü dahil!) deponuza yükleyin (**Add file > Upload files**).
   - Dikkat: ZIP'in kendisini değil, içindeki `www`, `.github`, `package.json`, `capacitor.config.json` ve `README.md` öğelerini yükleyin.
3. Depoda üst menüden **Actions** sekmesine tıklayın.
4. `Android APK Olustur` iş akışının çalışmasını bekleyin (yaklaşık 2–3 dakika).
5. İşlem yeşil tik ile tamamlandığında iş akışına tıklayın ve en alttaki **Artifacts** bölümünden **`Sulzer-16ZAV40S-APK`** dosyasını indirin.
6. İnen ZIP içindeki `app-debug.apk` dosyasını Android telefonunuza atıp kurun.

## Yöntem 2: Kendi Bilgisayarınızda APK Üretme

Bilgisayarınızda Node.js ve Android Studio (Android SDK) kuruluysa proje klasöründe sırasıyla şu komutları çalıştırın:

```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

Çıktı APK dosyası `android/app/build/outputs/apk/debug/app-debug.apk` konumunda oluşacaktır.
