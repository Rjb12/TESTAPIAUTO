Script di atas adalah contoh penggunaan framework RestAssured untuk mengotomatisasi pengujian API dengan menggunakan TestNG sebagai framework testing.

Pada script tersebut, terdapat tiga metode pengujian yang mencakup berbagai skenario:

testPositiveScenario: Melakukan pengujian pada respons yang benar dengan input yang benar.
testNegativeScenario: Melakukan pengujian pada respons yang salah dengan input yang salah.
testBoundaryScenario: Melakukan pengujian pada edge cases yang berbeda.
Setiap metode pengujian menggunakan RestAssured untuk membuat request API dengan berbagai header yang diperlukan. Kemudian, kode status response diperiksa dan beberapa assertion ditambahkan sesuai kebutuhan.

Untuk menggunakan script tersebut, pastikan telah mengatur dependensi yang diperlukan, seperti RestAssured dan TestNG, dalam proyek. Selanjutnya, jalankan masing-masing metode pengujian sesuai kebutuhan untuk menguji API yang ditentukan.
