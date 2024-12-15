# Tutorial GO

| Nama            | NRP       | Kelas      |
|-----------------|-----------|------------|
| Samuel Berkat Hulu | 5025201055 | PBKK-D |

maaf sebelumnya setalah `push origin main` pada(web-service-gin) saya menimpah semua file yang sudah ada sebelumnya di repository github ini. sehingga semua directory dan filenya ikut terperbaharui, saya juga mencoba untuk mengatur ulang mencoba mereset kembali dengan perintah `git reflog` kemudian `git reset --hard HEAD@{1}` dan `git push origin main --force` hasilnya semua kommmit tereset ulang dari awal dan tidak dapat dipulihkan. 

## Daftar tutorial:
1. Writing Web Applications
   - ![image](https://github.com/user-attachments/assets/8d115212-a248-46d4-a19a-b887b36c011d)

2. Accessing a relational database
   - ![Screenshot 2024-12-15 095341](https://github.com/user-attachments/assets/490e4147-fa2c-47d8-86a1-5d7038743fb1)

   - ![image](https://github.com/user-attachments/assets/5b2eb50f-bb9a-4bc8-b628-e688bfd12c93)

5. Developing a RESTful API with Go and Gin
   - ![image](https://github.com/user-attachments/assets/1dd874bd-a9b1-4927-9bd0-3cd90a6fd803)


## Tutorial: Menulis Aplikasi Web Go-Wiki (Writing Web Applications)
###Perkenalan 
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

### Menjalakan Program

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

### Prasyarat
- Instalasi sistem manajemen basis data relasional (DBMS) MySQL .
- Instalasi Go. Untuk petunjuk instalasi, lihat Menginstal Go .
- Alat untuk mengedit kode Anda. Editor teks apa pun yang Anda miliki akan berfungsi dengan baik.
- Terminal perintah. Go berfungsi dengan baik menggunakan terminal apa pun di Linux dan Mac, serta di PowerShell atau cmd di Windows.


### Menjalakan Program

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



## Tutorial: Accessing a relational database (Mengakses Database Relasional)

### Tutorial yang di pelajari
- Desain titik akhir API.
- Buat folder untuk kode Anda.
- Buat datanya.
- Tulis sebuah pengendali untuk mengembalikan semua item.
- Tulis pengendali untuk menambahkan item baru.
- Tulis sebuah pengendali untuk mengembalikan item tertentu.

### Prasyarat
- Instalasi Go 1.16 atau yang lebih baru. Untuk petunjuk instalasi, lihat [Menginstal Go .](https://go.dev/doc/install)
- Alat untuk mengedit kode Anda. Editor teks apa pun yang Anda miliki akan berfungsi dengan baik.
Terminal perintah. Go berfungsi dengan baik menggunakan terminal apa pun di Linux dan Mac, serta di PowerShell atau cmd di Windows.
- Alat curl. Di Linux dan Mac, alat ini seharusnya sudah terpasang. Di Windows, alat ini disertakan pada Windows 10 Insider versi 17063 dan yang lebih baru. Untuk versi Windows yang lebih lama, Anda mungkin perlu memasangnya. Untuk informasi selengkapnya, lihat [Tar dan Curl Hadir di Windows .](https://learn.microsoft.com/en-us/virtualization/community/team-blog/2017/20171219-tar-and-curl-come-to-windows)


### Menjalakan Program

Mulai dengan membuat folder nya
```R
$ mkdir web-service-gin
$ cd web-service-gin
```

Buat modul tempat Anda dapat mengelola dependensi.

```R
$ go mod init example/web-service-gin
```
buat file baru dan berinam `main.go` dengan ekstensi `.go`, untuk menmulikan code peintah [berikut kodenya](https://github.com/SamuelBerkatHulu/writingwebapplications-_-go-wiki/blob/main/web-service-gin/main.go) atau dapat mengaksenya langsung pada directory web-service-gin/main.go

kemudian install go-ginnya dengan perintah
```R
go get -u github.com/gin-gonic/gin
```
tunggu hingga unduhan go-gin selesai. Jika sudah selesai jalankan kode `main.go`
```R
go run main.go
```
jika sudah berhasil anda dapat mengakses pada `localhost:8080/albums` ini akan menmpikan keseluruhan data albums 
![Screenshot 2024-12-15 105459](https://github.com/user-attachments/assets/8e25f0ee-c5c3-4235-a5eb-5d38ed34b24a)

kita juga bisa mengakses hanya pada data albmums tertentu dengan mengarahkan URL ke `localhost:8080/albums/1` angka `1` pada URL ini merujuk pada data albums dengan ID `1`, jadi hasil yang di tampilkan nantinya hanya data album yang ber `ID:1`, dan sama halnya juga jika ingin mengakses data albums dengan `ID` lain![Screenshot 2024-12-15 105524](https://github.com/user-attachments/assets/c3a3ef1f-808b-46b7-af0a-fa58594c243d)






berikut hasil dari run main.go yang dijalankan akan muncul langsung pada terminal vscodenya `GET` artinya menampikan data
![Screenshot 2024-12-15 105637](https://github.com/user-attachments/assets/cefe0d34-8d17-4694-aade-fd142ccfdfb8)




kemudian untuk menambah data ke data albums dengan perintah
jika menggunakan terminal linux
```R
curl http://localhost:8080/albums \
    --include \
    --header "Content-Type: application/json" \
    --request "POST" \
    --data '{"id": "4","title": "The Modern Sound of Betty Carter","artist": "Betty Carter","price": 49.99}'
```
Jika menggunakan CMD
```R
curl -X POST http://localhost:8080/albums -H "Content-Type: application/json" -d "{\"id\": \"4\", \"title\": \"Mimpi\", \"artist\": \"Anggun\", \"price\": 49.99}"
```
untuk menambahkan file PORT data albums saya menggunakan CMD dan haslinya
![Screenshot 2024-12-15 105721](https://github.com/user-attachments/assets/b6621ec9-b0b3-427c-80fd-4dd45ccd3d6f)




karena data sudah berhasil ditambahakn maka untuk memastika cek lagi di `localhost:8080/albums` dan `localhost:8080/albums/4` jika data sudah berhasil ter `POST`. `POST` merujuk pada menambahkan data.


pengecekan dengan URL `localhost:8080/albums`
![Screenshot 2024-12-15 105919](https://github.com/user-attachments/assets/5fe3fe2d-393c-43e9-92c5-d82363ce00cf)




pengecekan dengan URL `localhost:8080/albums/4`
![Screenshot 2024-12-15 105734](https://github.com/user-attachments/assets/41efeca0-ee8a-4a14-bb9e-9fff5a31b985)




berikut hasil dari run main.go yang dijalankan akan muncul langsung pada terminal vscodenya
![Screenshot 2024-12-15 105833](https://github.com/user-attachments/assets/bd266214-27de-4222-a9f3-a1727d4b31f0)




Referensi Writing Web Applications
```
https://go.dev/doc/articles/wiki/
```

Referensi Accessing a relational database
```R
https://go.dev/doc/tutorial/database-access
```

Referensi Developing a RESTful API with Go and Gin
```R
https://go.dev/doc/tutorial/web-service-gin#all_items
```


