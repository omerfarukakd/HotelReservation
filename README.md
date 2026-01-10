# Otel Rezervasyon Sistemi (Hotel Reservation System)

Bu proje, kapsamlı Veri Yapıları ve Algoritmalar (Data Structures & Algorithms) uygulamalarını içeren, Grafik Arayüzlü (GUI) bir otel rezervasyon yönetim sistemidir. 6 aylık bir takvim ufku üzerinde çalışır ve rezervasyon, iptal, bekleme listesi, dinamik fiyatlandırma ve bakım yönetimi gibi karmaşık senaryoları simüle eder.

Proje, harici kütüphane gereksinimi olmadan **saf Python** (Tkinter) kullanılarak geliştirilmiştir.

## 🚀 Öne Çıkan Özellikler

### 1. Rezervasyon Yönetimi
*   **Oda Sorgulama:** Tarih aralığı, kişi sayısı ve oda tipine göre uygunluk kontrolü.
*   **Rezervasyon:** Misafir bilgileri ve seçilen hizmetlerle rezervasyon oluşturma.
*   **İptal Politikası:** Giriş tarihine kalan süreye göre dinamik kesinti oranı (%3 veya %10). Son 1 gün kala iptal yasağı.
*   **Görüntüleme:** Aktif ve geçmiş (arşiv) rezervasyonları listeleme, filtreleme.

### 2. Algoritmalar ve Veri Yapıları
Proje, verimlilik ve işlevsellik için aşağıdaki yapıları kullanır:
*   **AVL Ağacı (AVL Tree):** Odaların ID'ye göre indekslenmesi ve hızlı erişimi için dengeli arama ağacı ($O(\log N)$).
*   **MergeSort:** Rezervasyon listelerinin tarihe veya oluşturulma zamanına göre kararlı (stable) sıralanması ($O(N \log N)$).
*   **HeapSort:** Uygun odalar arasında, dinamik fiyatlandırma sonucu en düşük fiyatlı odayı seçmek için kullanılır (#1 en iyi fiyat).
*   **Binary Search (Lower Bound):** Tarih çakışmalarını ve uygunluk aralıklarını hızlıca bulmak için kullanılır.
*   **A\* Algoritması (Pathfinding):** Dolu dönemlerde alternatif tarih veya oda önerileri sunmak için yol bulma mantığı.
*   **Knapsack (DP) - Bütçe Sihirbazı:** Kullanıcının belirlediği bütçeye en uygun "Oda + Hizmet" kombinasyonunu öneren Dinamik Programlama (Dynamic Programming) modülü.
*   **Stack & Queue:** `Undo/Redo` işlemleri için Stack, `Waitlist` (Bekleme Listesi) için Queue (FIFO) yapısı.

### 3. Yönetim ve Diğer Fonksiyonlar
*   **Bakım Modu (Maintenance):** Belirli bir odayı veya tüm katı belirli tarihler arasında bakıma alma (rezervasyona kapatma).
*   **Bekleme Listesi (Waitlist):** Oda bulunamadığında bekleme listesine kayıt. İptal durumunda sıradaki misafirin otomatik yerleştirilmesi.
*   **Dinamik Fiyatlandırma:**
    *   Erken rezervasyon indirimi veya son dakika zammı.
    *   Doluluk oranına göre talep çarpanı.
    *   Kişi sayısına göre ek ücretlendirme.
*   **Çoklu Dil Desteği:** Türkçe (TR) ve İngilizce (EN) dil seçeneği.
*   **Tema Desteği:** Açık (Light) ve Koyu (Dark) mod.
*   **Raporlama:** `CSV` formatında günlük doluluk (`occupancy_daily.csv`) ve aylık gelir (`revenue_monthly.csv`) raporu dışa aktarma.

## 🛠 Kurulum ve Çalıştırma

Proje standart Python 3 kütüphanelerini kullanır. Ekstra kurulum gerektirmez.

**Gereksinimler:**
*   Python 3.10 veya üzeri önerilir.

**Çalıştırma:**
Terminal veya komut satırında proje dizinine giderek:

```bash
python hotel_reservation_app.py
```

## 📂 Dosya Yapısı

*   `hotel_reservation_app.py`: Ana uygulama dosyası (GUI ve tüm mantık).
*   `data/`: Veri klasörü (Uygulama çalıştığında otomatik oluşturulur/güncellenir).
    *   `rooms.json`: Oda tanımları.
    *   `services.json`: Ek hizmetler.
    *   `reservations.json`: Kayıtlı rezervasyonlar.
    *   `maintenance.json`: Bakım kayıtları.
    *   `celeb_codes.json`: Özel indirim kodları.

## 💡 Demo İpuçları
*   **Ünlü Katı Kodu:** `STAR2026` (Celeb Floor için gereklidir).
*   **Undo/Redo:** Yapılan işlemleri (Rezervasyon, İptal vb.) sol menüdeki "Geri Al" butonu ile geri alabilirsiniz.
*   **Bütçe Sihirbazı:** "İşlemler" menüsünden bütçenize uygun tatil paketi önerisi alabilirsiniz.
