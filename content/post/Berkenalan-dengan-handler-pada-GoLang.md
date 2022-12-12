---
title: "Berkenalan Dengan Handler Pada GoLang"
date: 2022-12-12T14:50:50+07:00
images: [bingpic.jpg]
categories: ["golang",]
tags: ["golang"]
authors: ["Eko Salvinus"]
---

Untuk meng-otentikasi client atau consumer, salah satu cara yang dapat dilakukan adalah dengan menggunakan handler. 
<!--more-->
Handler merupakan sebuah komponen yang bertugas untuk melakukan verifikasi terhadap client atau consumer yang ingin mengakses suatu sistem atau layanan. Biasanya, handler akan meminta client atau consumer untuk menyediakan informasi tertentu seperti username dan password sebelum diizinkan untuk mengakses sistem atau layanan tersebut.

Dengan menggunakan handler, sistem atau layanan dapat menjadi lebih aman karena hanya client atau consumer yang terotentikasi saja yang dapat mengaksesnya. Selain itu, handler juga dapat digunakan untuk mengelola hak akses client atau consumer terhadap sistem atau layanan, sehingga memungkinkan untuk memberikan akses yang lebih terbatas kepada client atau consumer yang tidak memiliki otoritas yang cukup.


Pada bahasa pemrograman Golang, handler adalah sebuah fungsi yang digunakan untuk menangani permintaan HTTP. Fungsi ini biasanya didefinisikan dengan menggunakan tipe http.HandlerFunc. Sebagai contoh, berikut adalah implementasi dari sebuah handler yang dapat menangani permintaan GET pada path "/hello":

```go
package main

import (
    "fmt"
    "net/http"
)

func hello(w http.ResponseWriter, r *http.Request) {
    if r.Method == "GET" {
        fmt.Printf("Hello, world!")
    }
}

func main() {
    http.HandleFunc("/hello", hello)
    http.ListenAndServe(":8080", nil)
}
```
<!--more-->

Pada contoh di atas, fungsi hello akan dipanggil setiap kali ada permintaan HTTP GET pada path "/hello". Fungsi ini akan menuliskan pesan "Hello, world!" pada response yang akan dikirim kepada client. Selain itu, fungsi hello juga dapat memproses request dan mengambil informasi dari request tersebut sebelum menuliskan pesan pada response.