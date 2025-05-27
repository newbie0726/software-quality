| Bagian | Path                         | Code (Logika Controller)                                                                                             | Jalur Eksekusi                                                                   |
| ------ | ---------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| A      | Sudah Login (Session aktif)  | if (\$this->session->userdata('role'))<br>→ if role = 'Admin', redirect ke admin<br>→ else redirect ke user          | 1. Cek session login<br>2. Cek role<br>3. Redirect sesuai role                   |
| B1     | Login Berhasil sebagai User  | if (\$username\_user && \$password\_user cocok di DB)<br>→ set session & role = User<br>→ redirect ke halaman user   | 1. Ambil POST<br>2. Validasi DB<br>3. Set session<br>4. Redirect ke user         |
| B2     | Login Berhasil sebagai Admin | if (\$username\_user && \$password\_user cocok di DB)<br>→ set session & role = Admin<br>→ redirect ke halaman admin | 1. Ambil POST<br>2. Validasi DB<br>3. Set session<br>4. Redirect ke admin        |
| B3     | Login Gagal (Data Salah)     | if query user gagal match<br>→ tampilkan pesan error<br>→ redirect back to login                                     | 1. Ambil POST<br>2. Query tidak cocok<br>3. Tampilkan error<br>4. Tetap di login |
| B4     | Field Kosong (input invalid) | if (\$this->input->post() kosong / form validation gagal)<br>→ tidak diproses, tetap di halaman login                | 1. Validasi gagal<br>2. Tidak query<br>3. Kembali ke form login                  |

Cyclomatic Complexity  

Node: 7 (start, form check, validasi, login success user, login success admin, login gagal, session redirect)  

Edge: 9  

Komponen Terhubung: 1  

Rumus: V(G) = E - N + 2P = 9 - 7 + 2(1) = 4  

Hasil:  
Ada 4 jalur independen yang bisa diuji:  

A (Session redirect)  

B1 (Login success user)  

B2 (Login success admin)  

B3 dan B4 digabung sebagai skenario gagal (invalid credentials & field kosong)  

| Jalur | Kondisi                  | Hasil Diharapkan                                   |
| ----- | ------------------------ | -------------------------------------------------- |
| A1    | Session = Admin          | Redirect ke dashboard admin (mis. admin/dashboard) |
| A2    | Session = User           | Redirect ke halaman user (mis. user/beranda)       |
| B1    | Login valid admin        | Redirect ke dashboard admin (mis. admin/dashboard) |
| B2    | Login valid user         | Redirect ke halaman user (mis. user/beranda)       |
| B3    | Login gagal / data salah | Tampilkan pesan error dan tetap di halaman login   |

Penjelasan Jalur:  

Jalur A1 & A2: Untuk pengguna yang sudah login dan memiliki session, sistem langsung mengarahkan ke dashboard masing-masing sesuai peran (admin/user).  

Jalur B1 & B2: Pengguna baru login, dan kredensial cocok → diarahkan ke dashboard sesuai peran.  

Jalur B3: Username/password tidak cocok → sistem menolak login dan tetap di form.  

Catatan tambahan:  

Sistem Anda saat ini tampaknya tidak menampilkan notifikasi visual (alert) saat login gagal—ini bisa ditambahkan untuk meningkatkan UX.  

Tidak ada CAPTCHA → potensi brute-force attack bisa menjadi perhatian.  
