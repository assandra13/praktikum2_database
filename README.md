# Praktikum 2 Database

**Nama    : Assandra Julyant Firdausy**
**NIM     : 312210384**
**Kelas   : TI.22.A.4**

# DDL (Data Definition Language) & DML (Data Manipulation Language)
![img](gambar/27.png)


- Data Model Mapping
    - Mahasiswa (nim, nama, jenis_kelamin, tgl_lahir, jalan, kota, kodepos, no_hp, kd_ds)
    - Dosen (kd_ds, nama)
    - Matakuliah (kd_mk, nama, sks)
    - JadwalMengajar (kd_ds, kd_mk, hari, jam, ruang)
    - KRSMahasiswa (nim, kd_mk, kd_ds, semester, nilai)

# A.Script DDL & DML
  1. DDL Script
     Data definition Language (DDL) adalah bahasa pemrogaraman yang digunakan untuk mengola objek database, seperti tabel, indeks, dan constraint. DDL digunakan untuk membuat, mengubah dan menghapus struktur database, termasuk tabel, kolom, kunci utama, indeks dan tampilan.
Berikut adalah perintah-perintah DDL yang digunakan untuk membuat sebuah DBMS berdasarkan skema diatas.

- Membuat sebuah database:
```sql
CREATE DATABASE nama_database;
```

- Menggunakan sebuah database:
```sql
USE nama_database;
```

- Membuat sebuah tabel:
```sql
CREATE TABLE nama_tabel (field1,...,fieldn) VALUE
(value1 tipe_data(ukuran),...,
(valuen tipe_data(ukuran))
);
```sql

- Menambah Primary KEY:
```sql
ALTER TABLE nama_tabel ADD PRIMARY KEY (nama_field)
```

- Menambah CONSTRAINT FOREIGN KEY:
```sql
ALTER TABLE nama_tabel ADD CONSTRAINT nama_constraint
FOREIGN KEY (nama_field) REFERENCES nama_tabel_referensi(nama_field_referensi)
```

- Menambah AUTO INCREMENT:
```sql
ALTER TABLE nama_tabel MODIFY nama_field tipe_data(ukuran) AUTO_INCREMENT;
```

  2. DML Script 
  Data Manipulation Language (DML) adalah bahasa yang digunakan untuk mengakses, memanipulasi, dan mengubah data dalam database. Berikut adalah perintah-perintah DML yang digunakan untuk membuat sebuah DMS berdasarkan skema diatas.

- Menambah data:
```sql
INSERT INTO <table_name> (filed1,...,fieldn) VALUE (val1,...,valn);
```

- Mengubah data:
```sql
UPDATE <table_name> SET [field1=val1,..,fieldn=valn] WHERE <kondisi>
```

- Menghapus data:
```sql
DELETE FROM <table_name> WHERE <kondisi>
```

- Menampilkan data:
```sql
SELECT * FROM <table_name>
```

- Menampilkan data sesuai kondisi:
```sql
SELECT * FROM <table_name> WHERE <kondisi>
```

 Selisih tahun
 ```sql
 SELECT * FROM <table_name> WHERE TIMESTAMPDIFF (YEAR, tgl_lahir, CURDATE()) < usia
 ```

 Sesuai urutan
 ```sql
 SELECT * FROM <table_name>  WHERE ORDER BY <acuan>
 ```

 Sesuai field/kolom yang di inginkan
 ```sql
 SELECT <field1,...,fieldn> FROM <nama_tabel>;
 ```

# B. Evaluasi dan Pertanyaan

• Tulis semua perintah-perintah SQL percobaan di atas beserta outputnya!
[Script_DDL_DML](#a-script-ddl--dml)   

• Apa bedanya penggunaan BETWEEN dan penggunaan operator >=
dan <= ?
• (misal: tgl_lahir BETWEEN '1990-10-10' AND '1992-10-11')
• (misal: tgl_lahir >= '1990-10-10' AND tgl_lahir <= '1992-10-11')

Kedua pernyataan SQL di atas menghasilkan hasil yang sama, yaitu mencari data yang memiliki tanggal lahir antara 10 Oktober 1990 dan 11 Oktober 1992. Namun, terdapat perbedaan antara penggunaan operator BETWEEN dan operator >= dan <= secara terpisah, yaitu:

Operator BETWEEN memudahkan penggunaan rentang nilai, sehingga kita hanya perlu menuliskan nilai awal dan akhir, sementara operator >= dan <= harus ditulis secara terpisah.

Ketika kita menggunakan operator BETWEEN, nilai awal dan akhir yang diberikan juga diikutsertakan dalam pencarian data. Sebaliknya, ketika kita menggunakan operator >= dan <=, kita perlu menambahkan pernyataan = di akhir pernyataan. Sebagai contoh, jika kita ingin mencari data yang memiliki tanggal lahir antara 10 Oktober 1990 dan 11 Oktober 1992, maka kita perlu menambahkan pernyataan tgl_lahir = '1990-10-10' OR tgl_lahir = '1992-10-11' ketika menggunakan operator >= dan <=.

Oleh karena itu, ketika kita ingin mencari data yang berada dalam rentang nilai tertentu, operator BETWEEN akan lebih mudah digunakan dan menghindari kesalahan penulisan pernyataan SQL. Namun, ketika kita ingin mencari data yang lebih kompleks, misalnya mencari data yang memiliki tanggal lahir sebelum 10 Oktober 1990 atau setelah 11 Oktober 1992, maka operator >= dan <= akan lebih fleksibel.

• Berikan kesimpulan anda!

Kesimpulannya, operator BETWEEN dan operator >= dan <= secara terpisah dapat digunakan untuk mencari data dalam rentang nilai tertentu, tetapi memiliki perbedaan dalam penulisan dan hasil yang dihasilkan. Operator BETWEEN memudahkan penggunaan rentang nilai, sementara operator >= dan <= memerlukan pernyataan tambahan jika ingin memasukkan nilai awal dan akhir dalam pencarian data. Pilihan antara kedua operator tersebut tergantung pada kebutuhan dan kompleksitas dari pencarian data yang ingin dilakukan.

• Buat laporan praktikum yang berisi, langkah-langkah praktikum
beserta screenshot yang sudah dilakukan dalam bentuk dokumen.
[Laporan_Praktikum2](laporan praktikum 2 basis data.pdf)


