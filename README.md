# Tutorial GO

| Nama            | NRP       | Kelas      |
|-----------------|-----------|------------|
| Samuel Berkat Hulu | 5025201055 | PBKK-D |

## Daftar tutorial:
1. Writing Web Applications
   - ![image](https://github.com/user-attachments/assets/8d115212-a248-46d4-a19a-b887b36c011d)

2. Accessing a relational database
   - ![Screenshot 2024-12-15 095341](https://github.com/user-attachments/assets/490e4147-fa2c-47d8-86a1-5d7038743fb1)

   - ![image](https://github.com/user-attachments/assets/5b2eb50f-bb9a-4bc8-b628-e688bfd12c93)

5. Developing a RESTful API with Go and Gin
   - 


## Tutorial: Menulis Aplikasi Web Go-Wiki (Writing Web Applications)
### Perkenalan 
Yang dibahas dalam tutorial ini:

- Membuat struktur data dengan metode muat dan simpan
- Menggunakan net/httppaket untuk membangun aplikasi web
- Menggunakan html/templatepaket untuk memproses template HTML
- Menggunakan regexppaket untuk memvalidasi masukan pengguna
- Menggunakan penutupan

### Tugas

Here are some simple tasks you might want to tackle on your own:

- Store templates in tmpl/ and page data in data/.
- Add a handler to make the web root redirect to /view/FrontPage.
- Spruce up the page templates by making them valid HTML and adding some CSS rules.
- Implement inter-page linking by converting instances of [PageName] to <a href="/view/PageName">PageName</a>. (hint: you could use regexp.ReplaceAllFunc to do this)

## Menjalakan Program

Anda dapat mengkompilasi dan menjalankan program seperti ini:

```R
$ go build wiki.go
$ ./wiki
```
`go build wiki.go` digunakan untuk mengompilasi file program dan dependensinya. Perintah ini akan menghasilkan file executable atau binary pada folder yang sedang aktif `wiki.exe`.



akses dengan :
```R
http://127.0.0.1:8080/view/FrontPage
http://127.0.0.1:8080/view/Example
```



## Tutorial: Accessing a relational database (Mengakses Database Relasional)

### Tutorial yang di Pelari
- Buat folder untuk kode Anda.
- Siapkan basis data.
- Impor driver basis data.
- Dapatkan pegangan basis data dan hubungkan.
- Kueri untuk beberapa baris.
- Kueri untuk satu baris.
- Tambahkan data.

### Persayaratan
- Instalasi sistem manajemen basis data relasional (DBMS) MySQL .
- Instalasi Go. Untuk petunjuk instalasi, lihat Menginstal Go .
- Alat untuk mengedit kode Anda. Editor teks apa pun yang Anda miliki akan berfungsi dengan baik.
- Terminal perintah. Go berfungsi dengan baik menggunakan terminal apa pun di Linux dan Mac, serta di PowerShell atau cmd di Windows.


Hubungkan Mysql dengan file  `create-tables.sql ` pada promt Mysql Command Line Client. dengan table yang berisikan 5 bari dan 4 kolom seperti konfigurasi awal pada  `create-tables.sql`
gunakan perintah 
```R
select * from album
```
untuk untuk menampilkan bentuk tabel.

![Screenshot 2024-11-21 193857](https://github.com/user-attachments/assets/e40c9120-5d95-4569-94fd-d26deb779a0a)


Pada main.go di directori data-access run code tersebut dengan 
```R
go run .
```

`go run .` untuk mejalankan code program pada main.go, programnya akan menambahkan data baru pada  tabel album 
berikut hasilnya run nya.
```R
PS C:\Users\Emperor Tampan\data-access> $ go run .
Connected!
Albums found: [{1 Blue Train John Coltrane 56.99} {2 Giant Steps John Coltrane 63.99}]
Album found: {2 Giant Steps John Coltrane 63.99}
ID of added album: 5
New album added: {5 Samuel Berkat Hulu Samuel 99.99}
```
program diatas telah berhasil jalan, dan berhasil menambahkan data baru pada tabel album yang yang terdapat pada database recordings.
berikut hasilnya.

![Screenshot 2024-11-21 195123](https://github.com/user-attachments/assets/649a4204-5969-43cd-b899-278ff32d7997)

Run programnya main.go jika ingin menambahkan data baru. 

### Referensi Writing Web Applications
```
https://go.dev/doc/articles/wiki/
```

### Referensi Accessing a relational database
```R
https://go.dev/doc/tutorial/database-access
```

### Referensi Developing a RESTful API with Go and Gin
```R
https://go.dev/doc/tutorial/web-service-gin#all_items
```


