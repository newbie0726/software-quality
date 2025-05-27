| Test Case | Deskripsi                                                   | Hasil Diharapkan                                       |
| --------- | ----------------------------------------------------------- | ------------------------------------------------------ |
| TC1       | Semua field diisi dengan valid (nama, tanggal, tip, alamat) | Pesanan langsung dikirim ke admin tanpa notifikasi     |
| TC2       | Salah satu field kosong (misal: alamat tidak diisi)         | Tombol Booking tidak bisa diklik, tidak ada notifikasi |
| TC3       | Isi Tip dengan huruf                                        | Tidak tampil (input otomatis difilter) – hanya angka   |
| TC4       | Tanggal Check-out < Check-in                                | Tidak bisa klik tombol booking, data tidak dikirim     |
| TC5       | Isi semua data dengan benar lalu tekan Booking              | Data masuk ke admin                                    |

•	Karena sistem tidak menampilkan error, maka validasi dideteksi melalui perilaku tombol Booking yang tidak aktif.  
•	Tidak ada pesan gagal / sukses — hanya perilaku sistem dan flow data ke admin.
