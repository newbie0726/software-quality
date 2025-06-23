# Matrix Testing – Booking Form

## 1. Faktor dan Level

| Faktor          | Level 1          | Level 2       | Level 3       |
|-----------------|------------------|---------------|---------------|
| Kelas Kamar     | Suite            | Deluxe        | Deluxe RO     |
| Fasilitas       | Mewah            | Menengah      | Standar       |
| Harga           | Mahal (> Rp1M)   | Sedang (500K–1M) | Murah (< 500K) |
| Durasi Menginap | Sebentar (1 hari)| Sedang (2–3 hari)| Lama (> 3 hari)|

## 2. Contoh Matrix Kombinasi (Orthogonal Subset)

| No. | Kelas Kamar | Fasilitas | Harga     | Durasi  |
|-----|-------------|-----------|-----------|---------|
| M1  | Suite       | Mewah     | Mahal     | Sebentar|
| M2  | Suite       | Menengah  | Sedang    | Lama    |
| M3  | Deluxe      | Standar   | Murah     | Sedang  |
| M4  | Deluxe RO   | Standar   | Murah     | Lama    |
| M5  | Deluxe      | Mewah     | Mahal     | Sedang  |

*(Anda bisa tambahkan atau turunkan kombinasi lain sesuai cakupan fitur.)*

## 3. Test Case Turunan

| TC   | Kelas Kamar | Fasilitas  | Harga     | Durasi   | Input Contoh                                               | Expected                                                                 |
|------|-------------|------------|-----------|----------|------------------------------------------------------------|--------------------------------------------------------------------------|
| TC01 | Suite       | Mewah      | Mahal     | Sebentar | Pilih “Suite”, fasilitas lengkap, harga ≥ 1.000.000, durasi 1 hari | Masuk ke halaman konfirmasi, data muncul: nomor kamar aktif, total sesuai |
| TC02 | Suite       | Menengah   | Sedang    | Lama     | Pilih “Suite”, fasilitas menengah, harga 600K, durasi 4 hari   | Masuk konfirmasi; cek total = 600K × 4; detail fasilitas menengah         |
| TC03 | Deluxe      | Standar    | Murah     | Sedang   | Pilih “Deluxe”, fasilitas standar, harga 450K, durasi 2 hari   | Konfirmasi total = 450K × 2; pastikan tombol booking aktif               |
| TC04 | Deluxe RO   | Standar    | Murah     | Lama     | Pilih “Deluxe Room Only”, harga 300K, durasi 5 hari            | Tombol aktif; data terkirim; tidak ada fasilitas tambahan di ringkasan   |
| TC05 | Deluxe      | Mewah      | Mahal     | Sedang   | Pilih “Deluxe”, fasilitas lengkap, harga 1.2M, durasi 3 hari   | Konfirmasi total = 1.2M × 3; cek fasilitas lengkap tampil              |



Hasil Uji berdasarkan fitur data pesanan yang di akses melalui login admin  

Dokumentasi Data Pesanan :
![Dokumentasi Hasil Uji](matrixtesting(2).jpg)
