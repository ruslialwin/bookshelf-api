# 📚 Bookshelf API
Bookshelf API adalah project akhir dari kelas *Belajar Back-End Pemula dengan JavaScript* di Dicoding. Aplikasi ini merupakan implementasi RESTful API yang memungkinkan pengguna untuk mengelola data buku secara digital.

## 🚀 Fitur Utama
✅ Menambahkan buku baru  
✅ Melihat daftar buku (dengan filter berdasarkan status selesai)  
✅ Melihat detail buku berdasarkan ID  
✅ Mengubah data buku  
✅ Menghapus buku dari daftar
✅ Query parameters pada endpoint `GET /books`:
- `?name` — Menampilkan buku yang mengandung kata tertentu (non-case sensitive)  
- `?reading` — Filter buku berdasarkan status sedang dibaca (`0` atau `1`)  
- `?finished` — Filter buku berdasarkan status selesai dibaca (`0` atau `1`)  
✅ Konsistensi gaya penulisan kode menggunakan ESLint dan style guide

## 🧪 Pengujian
Semua endpoint diuji menggunakan Postman untuk memastikan:
- Format respons JSON sesuai standar
- Validasi input berjalan dengan baik
- Penanganan error yang konsisten
- Fungsionalitas CRUD berjalan lancar

## 🛠️ Dibuat Dengan
- Node.js (Native & Hapi Framework)  
- JavaScript  
- Postman (untuk pengujian API)  

## 📦 Cara Menjalankan Secara Lokal
1. Clone repository ini  
   ```bash
   git clone https://github.com/ruslialwin/bookshelf-api.git
   ```
2. Masuk ke folder project
  ```bash
  cd bookshelf-api
  ```
3. Inisialisasi project Node.js
  ```bash
  npm init -y
  ```
4. Install dependencies
  ```bash
  npm install
  ```
5. Jalankan server
  ```bash
  npm run start
  ```
6. Gunakan Postman untuk mengakses endpoint sesuai dokumentasi

## 📘 API Endpoint Documentation
### 🔹 GET /books
**Deskripsi**: Mengambil daftar seluruh buku. 
**Query Parameters (Opsional)**:
- name → Filter buku berdasarkan nama (non-case sensitive)
- reading → 0 untuk buku yang tidak sedang dibaca, 1 untuk yang sedang dibaca
- finished → 0 untuk buku yang belum selesai dibaca, 1 untuk yang sudah selesai
**Respons**:
```bash
json
{
  "status": "success",
  "data": {
    "books": [
      {
        "id": "book-id",
        "name": "Book Title",
        "publisher": "Publisher Name"
      }
    ]
  }
}
```
### 🔹 GET /books/{id}
**Deskripsi**: Mengambil detail buku berdasarkan ID. 
**Respons**:
```bash
json
{
  "status": "success",
  "data": {
    "book": {
      "id": "book-id",
      "name": "Book Title",
      "year": 2021,
      "author": "Author Name",
      "summary": "Short summary",
      "publisher": "Publisher Name",
      "pageCount": 100,
      "readPage": 50,
      "reading": true,
      "finished": false
    }
  }
}
```
### 🔹 POST /books
**Deskripsi**: Menambahkan buku baru. 
**Body**:
```bash
json
{
  "name": "Book Title",
  "year": 2021,
  "author": "Author Name",
  "summary": "Short summary",
  "publisher": "Publisher Name",
  "pageCount": 100,
  "readPage": 50,
  "reading": true
}
```
**Respons (Berhasil)**:
```bash
json
{
  "status": "success",
  "message": "Buku berhasil ditambahkan",
  "data": {
    "bookId": "generated-id"
  }
}
```
### 🔹 PUT /books/{id}
**Deskripsi**: Mengubah data buku berdasarkan ID. 
**Body**: Sama seperti POST /books 
**Respons**:
```bash
json
{
  "status": "success",
  "message": "Buku berhasil diperbarui"
}
```
### 🔹 DELETE /books/{id}
**Deskripsi**: Menghapus buku berdasarkan ID. 
**Respons**:
```bash
json
{
  "status": "success",
  "message": "Buku berhasil dihapus"
```
