# Memahami dan Mengimplementasikan CHMOD (Permission) di Linux

File permission memiliki peran besar pada aspek keamanan di sebuah sistem Linux. Pada file-file yang dianggap krusial dan penting, penyesuaian permission ini perlu dilakukan agar nantinya file tidak dapat diakses oleh pihak-pihak yang tidak diinginkan. Salah satu perintah yang dapat digunakan untuk pengelolaan permission ini adalah `chmod`. Perintah `chmod` ini berfungsi untuk melakukan pengubahan pada permission satu atau lebih file yang diinginkan. 

Berikut ini contoh sintaks dari penggunaan `chmod`.
```
chmod [mode] [file]
```
- `mode`: Permission yang ingin diberikan, dapat berupa simbolik ataupun numerik
- `file`: File yang ingin diberikan permission 

## Penggunaan Command CHMOD
