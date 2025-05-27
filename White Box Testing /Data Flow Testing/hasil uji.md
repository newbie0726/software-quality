| No | Komponen Flowchart                    | Deskripsi                                                                | Kode Pemanggil (PHP/CI3)                                          |
| -- | ------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------- |
| 1  | Mulai                                 | Proses dimulai ketika user membuka halaman kamar                         | Route: /welcome/kamardetail/{id}                                  |
| 2  | Cek status kamar tersedia             | Mengecek status dari variabel \$status\_kamar                            | if (\$status\_kamar == 0) {...} else {...}                        |
| 3  | Tampilkan alert “Kamar Not Available” | Menampilkan alert jika kamar tidak tersedia                              | echo "<div class='alert alert-danger'>Kamar Not Available</div>"; |
| 4  | User mengisi form pemesanan           | Form input data reservasi kamar (check in, check out, nama, tlp, alamat) | form\_open('welcome/reservasi', 'role="form"')                    |
| 5  | Cek apakah form terisi                | Validasi input apakah semua field terisi                                 | required="required" pada semua input form                         |
| 6  | Tampilkan alert “Check In Success”    | Alert jika data berhasil terkirim                                        | if(\$this->session->flashdata('berhasil')) echo alert             |
| 7  | Data terkirim ke admin                | Data masuk ke database untuk dikonfirmasi admin                          | Controller: Welcome/reservasi() → Model insert\_reservasi()       |
| 8  | Selesai                               | Proses pemesanan selesai                                                 | Redirect halaman atau reload ke halaman info kamar                |
