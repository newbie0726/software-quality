![bpath](./infokamar1.png)


| Test Case | Semua Field Terisi | Check-in ≤ Check-out | Tip hanya angka | Output (Sistem)             |
| --------- | ------------------ | -------------------- | --------------- | --------------------------- |
| TC1       | Ya                 | Ya                   | Ya              | Data terkirim ke admin      |
| TC2       | Tidak              | Ya                   | Ya              | Tombol Booking tidak aktif  |
| TC3       | Ya                 | Tidak                | Ya              | Tombol Booking tidak aktif  |
| TC4       | Ya                 | Ya                   | Ada huruf       | Huruf otomatis tidak muncul |
| TC5       | Tidak              | Tidak                | Ya              | Tidak bisa klik tombol      |

•	Aplikasi tidak memberikan notifikasi eksplisit, tetapi perilaku sistem (tombol Booking aktif/tidak) menunjukkan validasi berjalan.  
•	Input telepon sudah difilter (client-side only input angka) → dapat diuji dengan BVA dan Equivalence.  
•	Proses hanya mengirim ke admin jika semua input valid → cocok diuji dengan Decision Table dan Equivalence
