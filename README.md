# Lab9Web

    project/
    │── index.php
    │
    │── config/
    │ └── database.php
    │
    │── views/
    │ ├── header.php
    │ ├── footer.php
    │ └── dashboard.php
    │
    │── modules/
    │ ├── user/
    │ │ ├── list.php
    │ │ ├── add.php
    │ │ ├── edit.php
    │ │ └── hapus.php
    │ │
    │ └── auth/
    │ ├── login.php
    │ └── logout.php
    │
    │── assets/
    ├── css/
    │ └── style.css
    └── js/

<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/507977a8-84c5-47ec-a696-2a24a1a7ecef" />


---

# ⚙️ Konfigurasi Database  
Menggunakan database dari Praktikum 8:

### **database: latihan1**

    CREATE TABLE data_barang (
    id_barang int(10) auto_increment PRIMARY KEY,
    kategori varchar(30),
    nama varchar(30),
    gambar varchar(100),
    harga_beli decimal(10,0),
    harga_jual decimal(10,0),
    stok int(4)
    );


---

# 📂 Penjelasan Setiap File

## 1. `config/database.php`
File ini digunakan untuk koneksi ke database MySQL.

## 2. `views/header.php` & `views/footer.php`
Berisi template layout HTML yang dipanggil di semua halaman via `require`.

## 3. `index.php`
File utama untuk routing:

    index.php?page=user/list
    index.php?page=user/add
    index.php?page=user/edit&id=1


Routing menentukan file mana di folder `modules/` yang akan dipanggil.

## 4. Folder `modules/user/`
Berisi proses CRUD dari Praktikum 8:
- list.php → Menampilkan data barang  
- add.php → Menambahkan data  
- edit.php → Mengubah data  
- hapus.php → Menghapus data  

## 5. Folder `modules/auth/`
Contoh tambahan login/logout sederhana (opsional).

---

# 🧩 Routing System

Routing diproses melalui:

    ```php
        $page = isset($_GET['page']) ? $_GET['page'] : 'dashboard';
        
        | URL                          | Halaman          |
        | ---------------------------- | ---------------- |
        | `/index.php`                 | Dashboard        |
        | `/index.php?page=user/list`  | List Data Barang |
        | `/index.php?page=user/add`   | Tambah Data      |
        | `/index.php?page=auth/login` | Halaman Login    |


<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/fd291fc2-6409-4b2b-8f94-0cea3c731cc6" />

<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/229b4532-5bed-4d2c-8bc0-eb65a9b840e2" />

<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/91f628d2-9c8b-48e2-b9d1-c3df3a71d8b5" />

<img width="960" height="540" alt="image" src="https://github.com/user-attachments/assets/2881fd64-f086-4268-884d-852e403c01da" />


---

## Cara Menjalankan Project

1. Pindahkan folder project/ ke:
   
       C:\xampp\htdocs\
   
2. Jalankan Apache & MySQL di XAMPP.
3. Akses melalui browser:

        http://localhost/project/

4. Untuk halaman user list:

        http://localhost/project/index.php?page=user/list

