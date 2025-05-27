



Komponen                             | Definisi                                               | Penggunaan                             | Deskripsi                                                                |
| ------------------------------------ | ------------------------------------------------------ | -------------------------------------- | ------------------------------------------------------------------------ |
| Buka Halaman Info Kamar              | Menampilkan informasi dan form pemesanan kamar         | Langkah awal sebelum memesan kamar     | Pengguna membuka halaman info kamar untuk melihat detail dan memesan.    |
| Cek Status Kamar Tersedia            | Mengecek apakah kamar tersedia                         | Validasi awal ketersediaan kamar       | Sistem mengecek status kamar apakah masih bisa dipesan.                  |
| Tampilkan Alert Kamar Tidak Tersedia | Pesan peringatan jika kamar tidak tersedia             | Ditampilkan jika status\_kamar != 0    | Sistem menampilkan alert jika kamar tidak tersedia.                      |
| Isi Form Pemesanan                   | Input data dari user (check-in, check-out, nama, dll.) | Input wajib dari pengguna              | Pengguna mengisi semua kolom form pemesanan.                             |
| Validasi Form Terisi                 | Mengecek apakah semua field terisi                     | Validasi input                         | Sistem tidak melanjutkan jika ada field kosong.                          |
| Alert Check In Success               | Memberikan konfirmasi jika data berhasil disimpan      | Ditampilkan setelah pemesanan berhasil | Jika validasi berhasil, sistem menampilkan alert bahwa pemesanan sukses. |
| Data Dikirim ke Admin                | Proses penyimpanan ke database untuk konfirmasi admin  | Setelah alert sukses                   | Data dikirim ke admin untuk dikonfirmasi di backend.                     |

| Potongan Kode                                                                                                         | Penjelasan                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| <?php $this->load->view("tamu/head.php") ?> <br> <?php $this->load->view("tamu/navbar.php") ?>                        | Memuat bagian head dan navbar dari template utama. Ini menandai awal halaman info kamar.                             |
| <?php if(validation_errors()) { ?> ... <?php echo validation_errors(); ?> <?php } ?>                                  | Menampilkan pesan error validasi jika ada field yang tidak sesuai atau kosong saat submit form.                      |
| <?php if($this->session->flashdata('berhasil')){ echo "<div class='alert alert-success'>Check In SUCCESS</div>"; } ?> | Menampilkan notifikasi flashdata jika proses booking kamar berhasil dilakukan dan dikirim ke admin.                  |
| foreach (\$kamar->result\_array() as \$value) { <br> \$status\_kamar = \$value\['status\_kamar']; <br> ... }          | Melakukan iterasi terhadap data kamar dari database dan mengambil status apakah kamar tersedia.                      |
| if (\$status\_kamar == 0) { ?> <br> <?php echo form_open('welcome/reservasi/'); ?>                                    | Jika kamar tersedia (status 0), maka tampilkan form pemesanan. Form ini akan dikirim ke method welcome/reservasi.    |
| <input type="text" name="tgl_reservasi_masuk" placeholder="Tanggal Check In">                                         | Field input untuk tanggal check-in. Harus diisi agar form bisa dikirim.                                              |
| <input type="text" name="tgl_reservasi_keluar" placeholder="Tanggal Check Out">                                       | Field input untuk tanggal check-out. Jika lebih awal dari check-in, tidak akan diproses di backend.                  |
| <input type="text" name="nama_reservasi" placeholder="Nama">                                                          | Field input untuk nama pemesan. Harus diisi.                                                                         |
| <input type="number" name="tlp_reservasi" placeholder="Tlp">                                                          | Field input untuk nomor telepon. Hanya menerima angka (jika huruf diketik, tidak muncul).                            |
| <textarea name="alamat_reservasi" placeholder="Alamat"></textarea>                                                    | Field input untuk alamat lengkap pemesan. Harus diisi agar form dapat dikirim.                                       |
| <button type="submit" class="btn btn-primary">Booking Kamar</button>                                                  | Tombol submit form. Akan aktif hanya jika semua input sudah diisi.                                                   |
| <?php } else { ?> <br> <div class='alert alert-danger'>Kamar Not Available</div> <?php } ?>                           | Jika kamar tidak tersedia (status\_kamar ≠ 0), maka tampilkan peringatan “Kamar Not Available” dan sembunyikan form. |
| <?php echo form_close(); ?>                                                                                           | Menutup form pemesanan.                                                                                              |
| <?php $this->load->view("tamu/footer.php") ?> <br> <?php $this->load->view("tamu/js.php") ?>                          | Memuat bagian footer dan skrip JavaScript untuk interaksi form dan tampilan.                                         |
