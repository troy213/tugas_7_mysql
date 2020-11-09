# Tugas 7 MySQL
![Tugas 7](https://github.com/troy213/tugas_7_mysql/blob/main/pasted%20image%200.png)

#### 1. Buatlah struktur tabel yang akan menampung data-data diatas (CREATE TABLE). Kali ini saya tidak akan membatasi nama tabel, nama kolom maupun tipe datanya. Silahkan teman-teman berkreasi sendiri.
```
CREATE TABLE kota (kota VARCHAR(30), kecamatan INT, kelurahan INT, luas FLOAT, penduduk INT);
```

#### 2. Input 8 kota pertama menggunakan query INSERT ... VALUES, bisa menginputnya satu per satu (satu query INSERT untuk setiap baris), atau sekaligus dalam satu query INSERT.
```
INSERT INTO kota VALUES 
("Jakarta", 44, 267, 664.01, 9988495), 
("Surabaya", 31, 154, 350.54, 2805906), 
("Medan", 21, 151, 265, 2465469), 
("Bekasi", 12, 56, 206.61, 2381053), 
("Bandung", 30, 151, 167.67, 2339463), 
("Makassar", 14, 143, 199.26, 1651146), 
("Depok", 11, 63, 200.29, 1631951), 
("Semarang", 16, 177, 373.78, 1621384);
```

#### 3. Input 2 kota terakhir menggunakan query INSERT ... SET.
```
INSERT INTO kota SET kota = "Tangerang", kecamatan = 13, kelurahan = 104, luas = 153.93, penduduk = 1566190;
INSERT INTO kota SET kota = "Palembang", kecamatan = 14, kelurahan = 107, luas = 369.22, penduduk = 1548064;
```

#### 4. Buat tabel kedua dengan menggunakan struktur yang sama dengan tabel pertama. Artinya, akan ada 2 tabel: Tabel pertama yang sudah berisi data (yang kita buat berdasarkan soal 1 - 3), dan tabel kedua yang belum berisi data. Struktur tabel pertama dan kedua ini sama persis, dimana sama-sama terdiri dari 5 kolom.
```
CREATE TABLE kota_2 LIKE kota;
```

#### 5. Ubah tabel kedua, hapus kolom Kecamatan, Kelurahan dan Luas Wilayah. Sehingga tabel kedua hanya berisi 2 kolom saja: Nama Kota dan Jumlah Penduduk.
```
ALTER TABLE kota_2 DROP COLUMN kecamatan, DROP COLUMN kelurahan, DROP COLUMN luas;
```

#### 6. Input tabel kedua dengan data yang diambil dari tabel pertama. Disini gunakan query INSERT ... SELECT. Perhatikan bahwa jumlah kolom di tabel kedua hanya tinggal 2 buah: Nama Kota dan Jumlah Penduduk. Struktur kolom ini sudah tidak sama dengan jumlah kolom dari tabel pertama. Hasil akhirnya dari query INSERT ... SELECT, tabel kedua akan berisi 10 nama kota beserta jumlah penduduk, seperti tampilan berikut:
```
INSERT INTO kota_2 SELECT kota, penduduk FROM kota;
```

![Tugas 7 2](https://github.com/troy213/tugas_7_mysql/blob/main/Tugas%207%20MySQL.jpg)

**Note:** Kerjakan latihan diatas secara berurutan. Tidak ada aturan harus menggunakan tipe data apa atau memberi nama kolom apa. Selama data bisa diinput semua, hal tersebut tidak menjadi masalah.
