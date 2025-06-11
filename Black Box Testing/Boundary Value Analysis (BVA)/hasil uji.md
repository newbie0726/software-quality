![bpath](./infokamar.png)


| Test Case | Input                                                                 | Diharapkan                                              | Status            |
|-----------|-----------------------------------------------------------------------|----------------------------------------------------------|-------------------|
| TC1       | Tanggal Check-in: 25 Mei 2025<br>Tanggal Check-out: 25 Mei 2025      | Valid (boleh sama)                                      | ✅                |
| TC2       | Tanggal Check-in: 26 Mei 2025<br>Tanggal Check-out: 25 Mei 2025      | Invalid (Check-in > Check-out) → Tidak bisa booking     | ❌ Perlu Validasi |
| TC3       | Tlp (Nomor Telepon): 15 [digit](#)                                    | Valid                                                    | ✅                |
| TC4       | Tlp: mengetik huruf                                                   | Tidak muncul di field (terfilter otomatis)              | ✅                |

•	Field “Tip” sudah diberi batasan input berupa angka saja (client-side), jadi tidak perlu validasi lagi.  
•	Tanggal boleh sama, logika sudah sesuai sistem Anda.

