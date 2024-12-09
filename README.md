# lab-8

## BIODATA 
## Nama    : Lola Seftyliani
## Kelas   : TI.24.A.4
## NIM     : 312410339
## Matkul  : Bahasa Pemograman

# TUGAS PRAKTIKUM
![Screenshot 2024-12-09 142848](https://github.com/user-attachments/assets/12c29799-f9ba-42ff-8618-4cf78791dc97)

# Lab8.py
```python
class Mahasiswa:
    def __init__(self, nama, nilai):
        self.nama = nama
        self.nilai = nilai

class DaftarNilaiMahasiswa:
    def __init__(self):
        self.daftar_nilai = {}

    def tambah(self, nama, nilai):
        """Menambahkan data mahasiswa"""
        self.daftar_nilai[nama] = Mahasiswa(nama, nilai)
        print(f"Data {nama} berhasil ditambahkan.")

    def tampilkan(self):
        """Menampilkan data mahasiswa"""
        print("Daftar Nilai Mahasiswa:")
        for mahasiswa in self.daftar_nilai.values():
            print(f"Nama: {mahasiswa.nama}, Nilai: {mahasiswa.nilai}")

    def hapus(self, nama):
        """Menghapus data mahasiswa berdasarkan nama"""
        if nama in self.daftar_nilai:
            del self.daftar_nilai[nama]
            print(f"Data {nama} berhasil dihapus.")
        else:
            print(f"Data {nama} tidak ditemukan.")

    def ubah(self, nama, nilai_baru):
        """Mengubah data mahasiswa berdasarkan nama"""
        if nama in self.daftar_nilai:
            self.daftar_nilai[nama].nilai = nilai_baru
            print(f"Data {nama} berhasil diubah.")
        else:
            print(f"Data {nama} tidak ditemukan.")
            
daftar_nilai = DaftarNilaiMahasiswa()

while True:
    print("\nMenu:")
    print("1. Tambah Data")
    print("2. Tampilkan Data")
    print("3. Hapus Data")
    print("4. Ubah Data")
    print("5. Keluar")

    pilihan = input("Pilih menu: ")

    if pilihan == "1":
        nama = input("Masukkan nama: ")
        nilai = input("Masukkan nilai: ")
        daftar_nilai.tambah(nama, nilai)
    elif pilihan == "2":
        daftar_nilai.tampilkan()
    elif pilihan == "3":
        nama = input("Masukkan nama: ")
        daftar_nilai.hapus(nama)
    elif pilihan == "4":
        nama = input("Masukkan nama: ")
        nilai_baru = input("Masukkan nilai baru: ")
        daftar_nilai.ubah(nama, nilai_baru)
    elif pilihan == "5":
        break
    else:
        print("Pilihan tidak valid.")
```
## code penjelasan
1. `DaftarNilaiMahasiswa` adalah kelas yang mengelola daftar mahasiswa. Kelas ini memiliki metode untuk menambah, mengubah, menghapus, dan menampilkan daftar nilai mahasiswa.
2. Method `tambah(self, nama, nilai)` Menambahkan data mahasiswa baru ke dalam daftar.
3. Method `tampilkan(self)` Menampilkan semua data mahasiswa yang tersimpan dalam daftar.
4. Method `hapus(self, nama)` Menghapus data mahasiswa berdasarkan nama.
5. Method `ubah(self, nama, nilai_baru)` Mengubah nilai mahasiswa yang sudah ada berdasarkan nama.
6. Metode `daftar_nilai` menampilkan daftar nilai semua mahasiswa

Mencetak menu dengan lima opsi yang dapat dipilih pengguna tersebut:

1. Tambah data: untuk menambahkan data mahasiswa baru
2. Tampilkan data: untuk menampilkan semua data mahasiswa yang telah dimasukkan
3. Hapus data: Menghapus data mahasiswa berdasarkan nama
4. Ubah data: Mengubah nilai mahasiswa berdasarkan nama
5. Keluar: Keluar dari program

# diagram class
![393718692-72efa054-e9e1-493f-8b30-10eb8cecb51c](https://github.com/user-attachments/assets/4080253e-cc25-4516-87c3-5597c65c110b)

# flowchart nya
![flowchart_mahasiswa](https://github.com/user-attachments/assets/6c2a516b-d226-4579-850a-1088c707e588)


