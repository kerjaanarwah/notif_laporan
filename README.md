# APK Pengingat Laporan (Capacitor)

Aplikasi ini hanyalah "cangkang" Android untuk antarmuka web (www/index.html).
Data & login tetap di Google Apps Script/Sheets Anda. Saat pertama dibuka, isi "URL Web App" (…/exec).
Web App harus di-deploy dengan akses "Anyone" (login ditangani aplikasi sendiri).

## Cara A - tanpa Android Studio (GitHub Actions)
1. Buat repository GitHub baru, unggah seluruh isi folder ini (termasuk folder .github).
2. Buka tab Actions > "Build APK" > Run workflow (otomatis jalan saat push).
3. Setelah hijau, unduh artifact "pengingat-laporan-apk" -> app-debug.apk -> pasang di HP
   (izinkan "pasang dari sumber tidak dikenal").

## Cara B - di komputer sendiri (Node 20, JDK 17, Android SDK)
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk

Ubah tampilan/fitur: edit www/index.html (salinan Index.html), lalu build ulang.
