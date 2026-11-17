# EduShield Exam Browser (Android APK)

Aplikasi Android Kiosk / Exam Browser khusus untuk membungkus sistem ujian online **EduShield CBT**.

## Fitur Keamanan Bawaan
1. **Screen Pinning / Lock Task Mode**: Mengunci aplikasi di layar depan sehingga panel notifikasi atas tidak bisa ditarik turun, tombol Home & Recent Apps mati, serta mencegah siswa membalas chat dari notifikasi.
2. **Anti-Screenshot & Screen Recording (`FLAG_SECURE`)**: Layar tidak dapat direkam maupun di-screenshot.
3. **Blokir Situs Eksternal & Copy-Paste**: Siswa hanya bisa mengakses domain ujian sekolah dan database Supabase.
4. **Keluar Wajib PIN Pengawas**: Tombol kembali dimatikan; untuk keluar aplikasi wajib memasukkan PIN Pengawas (default: `202699`).

---

## Cara Mengubah Link Ujian & PIN Pengawas
Buka file `app/src/main/java/id/sch/edushield/exambrowser/MainActivity.kt`, lalu ubah dua baris berikut:
```kotlin
private const val DEFAULT_EXAM_URL = "https://link-netlify-sekolahmu.netlify.app"
private const val PROCTOR_EXIT_PIN = "202699"
```

---

## Cara Mengubah Kode Ini Menjadi File `.apk`

### Opsi A: Tanpa Install Android Studio (Otomatis via GitHub Cloud - Gratis)
1. Buat akun gratis di [github.com](https://github.com) lalu buat Repository baru (misalnya `cbt-exambrowser`).
2. Unggah seluruh isi folder proyek ini ke repository tersebut.
3. Buka tab **Actions** di GitHub -> klik workflow **Build EduShield Exam Browser APK** -> klik **Run workflow**.
4. Tunggu ~2–3 menit hingga muncul centang hijau, lalu unduh file **`EduShield-ExamBrowser-APK`** di bagian **Artifacts** paling bawah halaman.

### Opsi B: Menggunakan Android Studio di Laptop
1. Buka folder `EduShield-ExamBrowser` menggunakan **Android Studio**.
2. Tunggu proses *Gradle Sync* selesai.
3. Klik menu **Build -> Build Bundle(s) / APK(s) -> Build APK(s)**.
4. File `.apk` siap dibagikan ke HP seluruh siswa.
