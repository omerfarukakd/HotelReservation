# Otel Rezervasyon Sistemi (Python + GUI)

Bu proje; **AVL**, **A\***, **mergesort + heapsort + binary search**, **stack/queue**, **JSON/CSV IO** gibi dersin zorunlu DS/Algoritmalarını **tek bir senaryoda** toplar.

## Kurulum / Çalıştırma
Python 3.10+ önerilir.

```bash
python hotel_reservation_app.py
```

Klasör yapısı:
- `hotel_reservation_app.py` (GUI + çekirdek)
- `data/rooms.json`
- `data/services.json`
- `data/reservations.json`
- `data/maintenance.json`
- `data/celeb_codes.json`

## Demo Bilgileri
- Ünlü katı için demo kod: **STAR2026**
- Rezervasyon ufku: **bugünden itibaren 180 gün**

## Fiyat Kuralları
- 0–10 gün: +%50
- 10–30 gün: +%25
- 1–4 ay: normal
- 4–6 ay: -%25
- Talep çarpanı: boş oda oranına göre artar
- Kişi sayısı: 3. kişi +%20, 4. kişi +%15 (kapasite dahilinde)
- Çocuk indirimi: çocuk payına göre ~%20 indirim
- Ek hizmetler: `services.json`

## DS/Algo Checklist
- [x] AVL Tree (dengeli arama ağacı)
- [x] A* (alternatif rezervasyon önerisi)
- [x] mergesort + heapsort
- [x] binary search (lower_bound)
- [x] stack (undo/redo), queue (waitlist)
- [x] JSON persistence + CSV export

## Raporlar
GUI içinden:
- `occupancy_daily.csv`
- `revenue_monthly.csv`

## Not
Bu bir “ders projesi” şablonu. Sunum için:
- DS/Algo’ları GUI üstünden kısa demo yapmak çok kolay:
  - Ünlü kodu dene
  - Kat tadilatı ekle
  - Çakışan rezervasyon iste → A* alternatif öner
  - İptal et → waitlist kuyruğu doluysa otomatik yerleşsin
  - Undo/Redo göster
