![bpath](./codinglogin.png)
![bpath](./codinglogin(2).png)


| Kondisi                                                                 | Hasil yang Diharapkan                                         | Hasil Aktual                                              | Status |
|-------------------------------------------------------------------------|----------------------------------------------------------------|------------------------------------------------------------|--------|
| username & password sesuai database                                     | Redirect ke halaman dashboard/admin                           | Redirect ke halaman dashboard/admin                        | Passed |
| username ada tapi password salah                                       | Redirect kembali ke halaman login + error                     | Redirect kembali ke halaman login                         | Passed |
| username tidak ditemukan di database                                   | Redirect kembali ke halaman login + error                     | Redirect kembali ke halaman login                         | Passed |
| field username_user kosong (required HTML)                             | Form tidak dikirim (dicegah oleh browser)                     | Form tidak dikirim                                        | Passed |
| field password_user kosong (required HTML)                             | Form tidak dikirim (dicegah oleh browser)                     | Form tidak dikirim                                        | Passed |
| field kosong tapi required dihapus lewat devtools (bypass browser)     | Backend memvalidasi dan tolak login                           | Redirect kembali ke login + error                         | Passed |
