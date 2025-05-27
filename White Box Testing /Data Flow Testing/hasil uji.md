



Komponen                             | Definisi                                               | Penggunaan                             | Deskripsi                                                                |
| ------------------------------------ | ------------------------------------------------------ | -------------------------------------- | ------------------------------------------------------------------------ |
| Buka Halaman Info Kamar              | Menampilkan informasi dan form pemesanan kamar         | Langkah awal sebelum memesan kamar     | Pengguna membuka halaman info kamar untuk melihat detail dan memesan.    |
| Cek Status Kamar Tersedia            | Mengecek apakah kamar tersedia                         | Validasi awal ketersediaan kamar       | Sistem mengecek status kamar apakah masih bisa dipesan.                  |
| Tampilkan Alert Kamar Tidak Tersedia | Pesan peringatan jika kamar tidak tersedia             | Ditampilkan jika status\_kamar != 0    | Sistem menampilkan alert jika kamar tidak tersedia.                      |
| Isi Form Pemesanan                   | Input data dari user (check-in, check-out, nama, dll.) | Input wajib dari pengguna              | Pengguna mengisi semua kolom form pemesanan.                             |
| Validasi Form Terisi                 | Mengecek apakah semua field terisi                     | Validasi input                         | Sistem tidak melanjutkan jika ada field kosong.                          |
| Alert Check In Success               | Memberikan konfirmasi jika data berhasil disimpan      | Ditampilkan setelah pemesanan berhasil | Jika validasi berhasil, sistem menampilkan alert bahwa pemesanan sukses. |
| Data Dikirim ke Admin                | Proses penyimpanan ke database untuk konfirmasi admin  | Setelah alert sukses                   | Data dikirim ke admin untuk dikonfirmasi di backend.                     |

