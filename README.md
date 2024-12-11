# lab-8

## BIODATA 
## Nama    : Lola Seftyliani
## Kelas   : TI.24.A.4
## NIM     : 312410339
## Matkul  : Bahasa Pemograman

# TUGAS PRAKTIKUM
# OOP-PYTHON

# Deskripsi

Program ini merupakan program manajemen data mahasiswa yang dibangun menggunakan Python. Program ini memungkinkan pengguna untuk menambah, mengubah, menghapus, dan mencari data mahasiswa. Data mahasiswa disimpan dalam format JSON, sehingga mudah untuk dibaca dan dikelola.

# Fitur
Tambah data mahasiswa
Ubah data mahasiswa
Hapus data mahasiswa
Cari data mahasiswa berdasarkan NIM
Tampilkan semua data mahasiswa

# Deskripsi Kode
# 1. data/mahasiswa.py
File ini berisi definisi kelas Mahasiswa yang memiliki atribut nama, nim, dan nilai. Selain itu, terdapat beberapa fungsi untuk mengelola data mahasiswa:

tambah_mahasiswa(data_mahasiswa, mahasiswa): Menambahkan objek mahasiswa ke dalam daftar.
ubah_mahasiswa(data_mahasiswa, nim, nilai_baru): Mengubah nilai mahasiswa berdasarkan NIM.
hapus_mahasiswa(data_mahasiswa, nim): Menghapus mahasiswa dari daftar berdasarkan NIM.
cari_mahasiswa(data_mahasiswa, nim): Mencari mahasiswa berdasarkan NIM.
tampilkan_semua_mahasiswa(data_mahasiswa): Menampilkan semua data mahasiswa.

# 2. view/input_form.py
File ini berisi fungsi input_data_mahasiswa() yang digunakan untuk mengambil input dari pengguna untuk menambah data mahasiswa.
```pythin
class InputForm:
    @staticmethod
    def input_mahasiswa():
        print("\n=== Form Input Mahasiswa ===")
        nim = input("Masukkan NIM: ")
        nama = input("Masukkan Nama: ")
        jurusan = input("Masukkan Jurusan: ")
        return nim, nama, jurusan
````
# 3. view/mahasiswa.py
File ini berisi fungsi tampilkan_data_mahasiswa(mahasiswa) yang digunakan untuk menampilkan informasi mahasiswa.
```python
class ViewMahasiswa:
    @staticmethod
    def tampilkan_list(data_mahasiswa):
        if not data_mahasiswa:
            print("Tidak ada data mahasiswa.")
        else:
            print("\n=== Daftar Mahasiswa ===")
            for mahasiswa in data_mahasiswa:
                print(mahasiswa)

    @staticmethod
    def tampilkan_detail(mahasiswa):
        if mahasiswa:
            print("\n=== Detail Mahasiswa ===")
            print(mahasiswa)
        else:
            print("\nMahasiswa tidak ditemukan.")
```
# 4. main.py
File ini adalah file utama yang menjalankan aplikasi. Di dalamnya terdapat fungsi load_data() untuk memuat data dari file JSON dan save_data(data) untuk menyimpan data ke file JSON. Fungsi main() mengatur menu interaksi dengan pengguna.
```python
from data.mahasiswa import Mahasiswa, DataMahasiswa
from view.input_from import InputForm
from view.mahasiswa import ViewMahasiswa

def main():
    data_mahasiswa = DataMahasiswa()

    while True:
        print("\nMenu:")
        print("1. Tambah Data Mahasiswa")
        print("2. Hapus Data Mahasiswa")
        print("3. Ubah Data Mahasiswa")
        print("4. Cari Data Mahasiswa")
        print("5. Tampilkan Semua Data")
        print("6. Keluar")

        pilihan = input("Pilih menu: ")

        if pilihan == "1":
            nim, nama, jurusan = InputForm.input_mahasiswa()
            mahasiswa = Mahasiswa(nim, nama, jurusan)
            data_mahasiswa.tambah_data(mahasiswa)
            print("Data berhasil ditambahkan.")
        elif pilihan == "2":
            nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
            data_mahasiswa.hapus_data(nim)
            print("Data berhasil dihapus.")
        elif pilihan == "3":
            nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
            nama_baru = input("Masukkan Nama baru: ")
            jurusan_baru = input("Masukkan Jurusan baru: ")
            data_mahasiswa.ubah_data(nim, nama_baru, jurusan_baru)
            print("Data berhasil diubah.")
        elif pilihan == "4":
            nim = input("Masukkan NIM mahasiswa yang akan dicari: ")
            mahasiswa = data_mahasiswa.cari_data(nim)
            ViewMahasiswa.tampilkan_detail(mahasiswa)
        elif pilihan == "5":
            semua_data = data_mahasiswa.tampilkan_semua_data()
            ViewMahasiswa.tampilkan_list(semua_data)
        elif pilihan == "6":
            print("Keluar dari program.")
            break
        else:
            print("Pilihan tidak valid.")

if __name__ == "__main__":
    main()
```

# Penggunaan
Instalasi: Pastikan Anda memiliki Python terinstal di sistem Anda. Anda dapat mengunduhnya dari python.org.

Clone Repository: Clone repositori ini ke mesin lokal Anda menggunakan perintah berikut:

## ss an
![Screenshot 2024-12-11 065540](https://github.com/user-attachments/assets/8df78e88-23b0-4b4a-8aa5-20887a4bbea4)

