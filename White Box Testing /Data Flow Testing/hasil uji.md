Flowchart :  
![Dokumentasi Hasil Uji](flowchart.png)  




Komponen                             | Definisi                                               | Penggunaan                             | Deskripsi                                                                |
| ------------------------------------ | ------------------------------------------------------ | -------------------------------------- | ------------------------------------------------------------------------ |
| Buka Halaman Info Kamar              | Menampilkan informasi dan form pemesanan kamar         | Langkah awal sebelum memesan kamar     | Pengguna membuka halaman info kamar untuk melihat detail dan memesan.    |
| Cek Status Kamar Tersedia            | Mengecek apakah kamar tersedia                         | Validasi awal ketersediaan kamar       | Sistem mengecek status kamar apakah masih bisa dipesan.                  |
| Tampilkan Alert Kamar Tidak Tersedia | Pesan peringatan jika kamar tidak tersedia             | Ditampilkan jika status\_kamar != 0    | Sistem menampilkan alert jika kamar tidak tersedia.                      |
| Isi Form Pemesanan                   | Input data dari user (check-in, check-out, nama, dll.) | Input wajib dari pengguna              | Pengguna mengisi semua kolom form pemesanan.                             |
| Validasi Form Terisi                 | Mengecek apakah semua field terisi                     | Validasi input                         | Sistem tidak melanjutkan jika ada field kosong.                          |
| Alert Check In Success               | Memberikan konfirmasi jika data berhasil disimpan      | Ditampilkan setelah pemesanan berhasil | Jika validasi berhasil, sistem menampilkan alert bahwa pemesanan sukses. |
| Data Dikirim ke Admin                | Proses penyimpanan ke database untuk konfirmasi admin  | Setelah alert sukses                   | Data dikirim ke admin untuk dikonfirmasi di backend.                     |




| Kode                                                                                                          | Penjelasan                                                                            |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `php<br><?php $this->load->view("tamu/head.php") ?><br><?php $this->load->view("tamu/navbar.php") ?>`         | Memuat bagian head dan navbar. Digunakan saat halaman info kamar dibuka pertama kali. |
| `php<br><?php if(validation_errors()) { ?><br>...<br><?php echo validation_errors(); ?><br><?php } ?>`        | Menampilkan pesan error jika ada input form yang kosong atau tidak sesuai.            |
| `php<br><?php if($this->session->flashdata('berhasil')) { ?><br>echo "Check In SUCCESS";<br><?php } ?>`       | Flashdata untuk menampilkan pesan sukses setelah form berhasil dikirim.               |
| `php<br>foreach ($kamar->result_array() as $value) {<br> $status_kamar = $value['status_kamar'];<br>...<br>}` | Mengambil data kamar dari database dan mengecek status apakah tersedia atau tidak.    |
| `php<br>if ($status_kamar == 0) {<br>echo form_open('welcome/reservasi/');<br>`                               | Menampilkan form pemesanan jika status kamar = 0 (tersedia).                          |
| `html<br><input type="text" name="tgl_reservasi_masuk" placeholder="Tanggal Check In">`                       | Input tanggal check-in. Harus diisi agar form bisa dikirim.                           |
| `html<br><input type="text" name="tgl_reservasi_keluar" placeholder="Tanggal Check Out">`                     | Input tanggal check-out. Harus lebih dari atau sama dengan check-in.                  |
| `html<br><input type="text" name="nama_reservasi" placeholder="Nama">`                                        | Input nama pemesan. Wajib diisi.                                                      |
| `html<br><input type="number" name="tlp_reservasi" placeholder="Tlp">`                                        | Input nomor telepon. Hanya menerima angka.                                            |
| `html<br><textarea name="alamat_reservasi" placeholder="Alamat"></textarea>`                                  | Input alamat lengkap pemesan.                                                         |
| `html<br><button type="submit">Booking Kamar</button>`                                                        | Tombol untuk submit form. Hanya aktif jika seluruh field terisi.                      |
| `php<br>} else { ?><br><div class="alert alert-danger">Kamar Not Available</div><br><?php } ?>`               | Jika kamar tidak tersedia, tampilkan alert peringatan.                                |
| `php<br><?php echo form_close(); ?>`                                                                          | Menutup tag form setelah seluruh field input.                                         |
| `php<br><?php $this->load->view("tamu/footer.php") ?><br><?php $this->load->view("tamu/js.php") ?>`           | Menampilkan bagian footer dan file JavaScript penutup halaman.                        |
