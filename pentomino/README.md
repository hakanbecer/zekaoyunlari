# 🧩 PENTOMİNO (AKIL VE ZEKÂ OYUNLARI ATÖLYESİ)

İlkokul ve ortaokul öğrencilerine yönelik, pedagojik, sade ve sindire sindire anlatan 1920x1080 Full HD (30 FPS) bağımsız eğitim videosu ve interaktif HTML5 atölyesi.

---

## 🌟 Proje Özellikleri ve Standart Mimari

1. **Öğrenci Odaklı & Pedagojik Anlatım:**
   - Cümleler kısa, net, duru ve anlaşılır (cümle başına en fazla 8-12 kelime).
   - Tırnak işareti, kesme işareti ve özel semboller içermez (VoxCPM2 ses motoru ile %100 uyumlu).
   - Sayılar ve rakamlar tamamen yazıyla yazılmıştır (on iki, beş, altmış, birinci, ikinci, üçüncü vb.).
   - Harfler ve parçalar uluslararası standart Pentomino adlarıyla anılır: F, I, L, P, N, T, U, V, W, X, Y ve Z parçaları.

2. **Merkezî ve Sade Ekran Mimarisi:**
   - 1920x1080 Full HD @ 30 FPS çözünürlük.
   - Yan bilgi kutuları, madde işaretli kalabalık kartlar kesinlikle bulunmaz.
   - 6x10 Pentomino tahtası ekranın tam merkezine (X: 960, Y: 495) yerleştirilmiştir.
   - **Üst Bilgi Şeridi (Y: 0 - 100):** Sol oyun başlığı rozeti (`🧩 PENTOMİNO DERSİ`), merkez bölüm başlığı, sağ bölüm gösterge rozeti (`BÖLÜM X / 7`).
   - **Alt Altyazı Şeridi (Y: 895 - 1045):** Konuşulan cümlelerle tam senkronize büyük, okunaklı merkezî altyazı.
   - **En Alt İlerleme Çubuğu (Y: 1070 - 1080):** Kesintisiz soldan sağa akan altın renkli ilerleme çubuğu.

3. **%100 Ses-Görsel Senkronizasyonu:**
   - Anlatıcı hangi parçayı söylüyorsa, o parça (I, V, L, P, U, X, Y, F, W, T, N, Z) ekranda süzülerek tam kendi koordinatlarına oturur.
   - Parçaların harf etiketleri, 3D kabartmalı blokları ve canlı renkleri birebir eşleşir.
   - Kurallarda döndürme, çakışma uyarısı ve boşluksuz örtme kuralları görselleştirilmiştir.

4. **7 Bölümlük Pedagojik Ders Akışı:**
   - **Bölüm 1:** Oyun Nedir ve Temel Amaç? (12 parça, 60 birim kare, hedef alanı boşluksuz ve taşmadan doldurma).
   - **Bölüm 2:** Oyun Alanı ve Parçaları Tanıyalım (F, I, L, P, N, T, U, V, W, X, Y ve Z parçaları).
   - **Bölüm 3:** Temel Altın Kurallar (Döndürme & ters çevirme serbestliği, üst üste binmeme, boşluk bırakmama).
   - **Bölüm 4:** Usta Stratejisi (Köşelerden ve kenarlardan başlama, zor parçaları planlama, çıkmaz sokak bırakmama).
   - **Bölüm 5:** Adım Adım Örnek Uygulama: Giriş (İlk 6 parçanın: I, V, L, P, U, X tahtaya yerleştirilmesi).
   - **Bölüm 6:** Adım Adım Örnek Uygulama: Tamamlama (Kalan parçaların: Y, F, W, T, N, Z ile tahtanın bitirilmesi).
   - **Bölüm 7:** Tebrikler ve Şimdi Sıra Sende! (Şampiyonluk kupası, konfeti animasyonu ve oynama çağrısı).

---

## 🎮 İnteraktif Oyun Atölyesi (`index.html`)

Web tarayıcısında çalışan bağımsız atölye sayfası:
- **Çoklu Seviyeler:**
  - 🟢 1. Seviye: 3x5 Mini Tahta (3 Parça)
  - 🔵 2. Seviye: 4x5 Tahta (4 Parça)
  - 🟣 3. Seviye: 5x5 Tahta (5 Parça)
  - 🟠 4. Seviye: 6x5 Tahta (6 Parça)
  - 🏆 5. Seviye: 6x10 Büyük Tahta (Tam 12 Parça)
  - 🎨 6. Seviye: Serbest Mod
- **Dinamik Kontroller & Doğrudan Döndürme:** 
  - Her parça kartı üzerinde doğrudan `↻ Döndür` ve `⇄ Çevir` butonları.
  - Tahta altındaki büyük aktif kontrol çubuğu (`↻ 90° Döndür`, `⇄ Ters Çevir`, `✕ Bırak`).
  - Klavye kısayolları (`R` / `Boşluk` ile döndürme, `F` ile ters çevirme, `Esc` ile iptal) ve fare tekerleğiyle döndürme.
  - Tahtadaki parçaya tıklayarak onu tekrar eline alma ve yönünü değiştirme.
- **Akıllı Araçlar:** 💡 İpucu Al (Hint), 👁️ Çözümü Göster, ⟲ Geri Al (Undo), 🔄 Baştan Başla, 🗑️ Temizle.
- **Ses & Efektler:** Web Audio API ile sıfır harici dosya bağımlılığıyla sentezlenen ses efektleri ve konfeti kutlaması.

---

## 📁 Dosya Yapısı

| Dosya / Klasör | Açıklama |
|---|---|
| `ses_metinleri.txt` | 7 bölümün tırnaksız, rakamsız, pedagojik Türkçe seslendirme metinleri |
| `generate_video_audio.py` | VoxCPM2 Python ortamı ile `cekici_spiker` ve `haber_spikeri` seslerini üreten script |
| `render_video.py` | Pillow + FFmpeg ile 1080p @ 30 FPS video üretim motoru |
| `sesleri_uret.bat` | VoxCPM2 seslerini tek tıkla üreten batch dosyası |
| `videoyu_uret.bat` | Seçenek 1, 2 veya 3 ile videoyu tek tıkla üreten UTF-8 batch dosyası |
| `pentomino_anlatim_cekici_spiker.mp4` | Çekici Spiker sesli Full HD 1080p video |
| `pentomino_anlatim_haber_spikeri.mp4` | Haber Spikeri sesli Full HD 1080p video |
| `index.html` | Bağımsız HTML5 Pentomino oyunu (Giriş ekranı, 6 seviye, Web Audio API ses motoru) |
| `imsmanifest.xml` | SCORM 1.2 standart paket bildirim dosyası |
| `eski_web_surumu/` | Önceki web sürümünün güvenle arşivlendiği klasör |
| `eski_videolar/` | Önceki video sürümlerinin güvenle arşivlendiği klasör |

---

## 🚀 Çalıştırma

1. **İnteraktif Oyun & Video:** `pentomino/index.html` dosyasını tarayıcınızda çift tıklayarak açın.
2. **Video Üretimi:** `videoyu_uret.bat` dosyasına çift tıklayarak 1, 2 veya 3 seçeneğini girin.
3. **Ses Üretimi:** `sesleri_uret.bat` dosyasına çift tıklayın.
