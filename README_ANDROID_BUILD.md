# Panduan Kompilasi & Build APK - Live Video Studio (Kotlin + Jetpack Compose)

Proyek ini adalah aplikasi Android native yang siap dikompilasi menggunakan **Android Studio** dan **Gradle**.

---

## 🛠️ Persyaratan Sistem
1. **Android Studio**: Android Studio Hedgehog (2023.1.1) atau versi lebih baru (Iguana, Jellyfish, Koala, Ladybug).
2. **JDK**: Java Development Kit 17 atau yang terbundel di Android Studio.
3. **Android SDK**: Compile SDK 35, Min SDK 24 (Android 7.0 ke atas, kompatibel dengan 99% HP Android saat ini).

---

## 🚀 Langkah-langkah Kompilasi & Menghasilkan APK

### 1. Buka Proyek di Android Studio
1. Ekstrak file zip hasil download dari tombol **Download Proyek Android (ZIP)**.
2. Buka **Android Studio**, pilih **File** > **Open...** lalu pilih folder root hasil ekstrak (`LiveVideoStudio`).
3. Tunggu proses **Gradle Sync** selesai mengunduh library (Media3 ExoPlayer, Jetpack Compose, DataStore).

### 2. Jalankan di HP Fisik atau Emulator
1. Sambungkan HP Android Anda via kabel USB dan aktifkan **USB Debugging** di *Developer Options*.
2. Tekan tombol hijau **Run 'app'** (`Shift + F10`) di toolbar Android Studio.
3. Aplikasi akan langsung terinstal di HP Anda dengan nama **Live Video Studio**.

### 3. Menghasilkan File APK Debug (Tanpa Keystore)
Jalankan perintah ini di Terminal Android Studio:
```bash
./gradlew assembleDebug
```
Lokasi file APK yang dihasilkan:
`app/build/outputs/apk/debug/app-debug.apk`
File ini bisa langsung Anda bagikan dan instal di HP Android manapun!

### 4. Menghasilkan File APK Release (Siap Rilis)
1. Di menu Android Studio, klik **Build** > **Generate Signed Bundle / APK...**
2. Pilih **APK** lalu klik **Next**.
3. Pilih atau buat Keystore baru (`.jks`), masukkan password.
4. Pilih build variant **release**, centang **V1 (Jar Signature)** dan **V2 (Full APK Signature)**.
5. Klik **Finish**. File APK Release akan dibuat di:
`app/release/app-release.apk`

---

## 📺 Integrasi Siaran TikTok LIVE
Karena TikTok tidak menyediakan REST API publik bebas untuk siaran pihak ketiga tanpa izin khusus, terdapat 2 metode resmi yang didukung:

### Metode A: Siaran Menggunakan RTMP Server URL & Stream Key
1. Masuk ke TikTok Creator Portal / TikTok LIVE Center.
2. Dapatkan **Server URL** (`rtmps://live-push.tiktok.com/...`) dan **Stream Key**.
3. Di HP Android, Anda dapat menggunakan modul RTMP Streamer terintegrasi atau aplikasi pembantu seperti Larix Broadcaster / Prism Live Studio dengan mengarahkan video feed dari Live Video Studio.

### Metode B: Screen Broadcast / Bagikan Layar TikTok
1. Buka aplikasi **Live Video Studio**, putar playlist video dan aktifkan jam transparan.
2. Buka aplikasi **TikTok** di HP Anda, tekan tombol **+ (Tambah)** > geser ke **LIVE**.
3. Pilih opsi **Mobile Gaming / Bagikan Layar (Screen Share)**.
4. TikTok akan menyiarkan tampilan layar HP Anda yang menampilkan Live Video Studio secara langsung ke penonton TikTok!
