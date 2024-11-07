# Menulis Aplikasi Web Go-Wiki

| Nama            | NRP       | Kelas      |
|-----------------|-----------|------------|
| Samuel Berkat Hulu | 5025201055 | PBKK-D |

## Perkenalan 
Yang dibahas dalam tutorial ini:

- Membuat struktur data dengan metode muat dan simpan
- Menggunakan net/httppaket untuk membangun aplikasi web
- Menggunakan html/templatepaket untuk memproses template HTML
- Menggunakan regexppaket untuk memvalidasi masukan pengguna
- Menggunakan penutupan

## Tugas

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
## Referensi
```
https://go.dev/doc/articles/wiki/
```

