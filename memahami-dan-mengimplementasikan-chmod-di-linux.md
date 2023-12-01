# Memahami dan Mengimplementasikan CHMOD (Permission) di Linux

File permission memiliki peran besar pada aspek keamanan di sebuah sistem Linux. Pada file-file yang dianggap krusial dan penting, penyesuaian permission ini perlu dilakukan agar nantinya file tidak dapat diakses oleh pihak-pihak yang tidak diinginkan. Salah satu perintah yang dapat digunakan untuk pengelolaan permission ini adalah `chmod`. 

## Struktur Command CHMOD

Pada command `chmod` memmiliki tiga bagian permission yang dapat di-set, yaitu `user`, `group`, dan `other`. `User` merupakan pemilik dari sebuah file/direktori. Nantinya, pemilik tersebut dapat melakukan aktivitas pada sebuah file sesuai dengan permission yang diberikan.

`Group` merupakan kumpulan user. Serta, `other` adalah pihak selain `user` dan `group`.

Dalam penggunaan command-nya, setiap level permission dinyatakan secara simbolik ataupun numerik. Berikut ini detailnya.

| Pemilik file |    4    |    2    |    1    |
| ------------ | ------- | ------- | ------- |    
| User         |    R    |    W    |    X    |
| Group        |    R    |    W    |    X    |
| Other        |    R    |    W    |    X    |

- **READ (R)**  : Permission untuk dapat membaca suatu file atau direktori.
- **WRITE (W)** : Permission untuk dapat menulis atau mengedit suatu file atau direktori.
- **Execute (X)** : Permission untuk dapat menjalankan atau mengeksekusi suatu file.

## Penggunaan Command CHMOD

Perintah `chmod` ini berfungsi untuk melakukan pengubahan pada permission satu atau lebih file yang diinginkan. 

Berikut ini contoh sintaks dari penggunaan `chmod`.
```
chmod [mode] [file]
```
- `mode`: Permission yang ingin diberikan, dapat berupa simbolik ataupun numerik
- `file`: File yang ingin diberikan permission 

### Penggunaan Simbolik pada Command CHMOD
Berikut ini contoh penerapan `chmod` dengan menggunakan simbolik.
```
chmod u=rwx,g=rx,o=r [nama file]
```
Pada command diatas, pemilik file dinyatakan dengan huruf `u`, `g`, dan `o`. `u` untuk user, `g` untuk group, dan `o` untuk other. Setelah pemilik file dinyatakan, tambahkan lambang `=` lalu diikuti dengan permission apa saja yang akan diberikan.
 - Lambang `=` : menyatakan permission yang akan diberikan
 - Lambang `+` : menambahkan permission baru 
 - Lambang `-` : menghapus permission yang telah ditambahkan sebelumnya

### Penggunaan Numerik pada Command CHMOD
Berikut ini contoh penerapan `chmod` dengan menggunakan numerik.
```
chmod 754 [nama file]
```
Pada command diatas, digit pertama menyatakan level permission untuk user, digit kedua untuk group, dan digit ketiga untuk other. 

Angka `7` pada digit pertama merupakan kombinasi dari permission `4+2+1 (r,w,x)`. Angka `5` pada digit kedua merupakan kombinasi dari permission `4+0+1 (r,x)`, dan Angka `4` pada digit ketiga merupakan kombinasi dari permission `4+0+0 (r)`.

## CHMOD untuk mengamankan File serta Direktori

Pemberian permission pada file serta direktori ini perlu diperhatikan dengan seksama. Berikan permission sebagaimana yang diperlukan pada setiap user ataupun group yang tersedia. Kurangilah permission yang dianggap tidak perlu. Terutama pada file-file penting pada sistem.

Dalam penerapannya, permission file serta direktori di sistem linux bisa diberikan sebagai berikut:
- File (`user`: rw, `group`: r, `other`: r )
```
chmod 644 test.txt
```
- Direktori (`user`: rwx, `group`: rx, `other`: rx )
```
chmod 755 direktoritest
```
Untuk lebih amannya, Anda juga dapat mengurangin permission `other` menjadi `0`.
- File (`user`: rw, `group`: r, `other`: - )
```
chmod 640 test.txt
```
- Direktori (`user`: rwx, `group`: rx, `other`: - )
```
chmod 750 direktoritest
```
