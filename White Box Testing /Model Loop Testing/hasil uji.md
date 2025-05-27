| No | Deskripsi Skenario                                | books                                               | bookId yang dicari | Output Diharapkan |
|----|---------------------------------------------------|-----------------------------------------------------|--------------------|-------------------|
| 1  | Loop tidak dieksekusi (array kosong)              | `[]`                                                | `'a1'`             | -1                |
| 2  | Loop berjalan 1x, ID cocok                        | `[{ id: 'a1' }]`                                    | `'a1'`             | 0                 |
| 3  | Loop berjalan 1x, ID tidak cocok                  | `[{ id: 'a1' }]`                                    | `'b1'`             | -1                |
| 4  | Loop berjalan 3x, ID cocok di posisi tengah       | `[{ id: 'x' }, { id: 'b1' }, { id: 'z' }]`          | `'b1'`             | 1                 |
| 5  | Loop berjalan 3x, ID cocok di akhir               | `[{ id: 'x' }, { id: 'y' }, { id: 'b1' }]`          | `'b1'`             | 2                 |
| 6  | Loop berjalan 3x, ID tidak ditemukan sama sekali  | `[{ id: 'x' }, { id: 'y' }, { id: 'z' }]`           | `'b1'`             | -1                |
