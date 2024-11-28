#Tugas praktikum 06

Buat program sederhana dengan mengaplikasikan penggunaan fungsi
yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan:
1. Fungsi tambah() untuk menambah data
2. Fungsi tapilkan() untuk menampilkan data
3. Fungsi hapus(nama) untuk menghapus data berdasarkan nama
4. Fungsi ubah(nama) untuk mengubah data berdasarkan nama

kode python

    # Daftar untuk menyimpan data mahasiswa
     data_mahasiswa = []

    # Fungsi untuk menambah data mahasiswa
     def tambah():
     nama = input("Masukkan nama mahasiswa: ")
     nim = input("Masukkan NIM: ")
     nilai = float(input("Masukkan nilai: "))
     data_mahasiswa.append({"nama": nama, "nim": nim, "nilai": nilai})
     print("Data berhasil ditambahkan.")

     # Fungsi untuk menampilkan data mahasiswa
     def tampilkan():
     if not data_mahasiswa:
     print("Tidak ada data mahasiswa.")
     else:
     print("Daftar Data Mahasiswa:")
     for i, mahasiswa in enumerate(data_mahasiswa, start=1):
     print(f"{i}. Nama: {mahasiswa['nama']}, NIM: {mahasiswa['nim']}, Nilai: {mahasiswa['nilai']}")

     # Fungsi untuk menghapus data mahasiswa berdasarkan nama
     def hapus(nama):
     for mahasiswa in data_mahasiswa:
     if mahasiswa['nama'].lower() == nama.lower():
     data_mahasiswa.remove(mahasiswa)
     print(f"Data mahasiswa dengan nama {nama} berhasil dihapus.")
     return
     print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")

     # Fungsi untuk mengubah data mahasiswa berdasarkan nama
     def ubah(nama):
     for mahasiswa in data_mahasiswa:
     if mahasiswa['nama'].lower() == nama.lower():
     print(f"Data lama: Nama: {mahasiswa['nama']}, NIM: {mahasiswa['nim']}, Nilai: {mahasiswa['nilai']}")
     mahasiswa['nama'] = input("Masukkan nama baru: ")
     mahasiswa['nim'] = input("Masukkan NIM baru: ")
     mahasiswa['nilai'] = float(input("Masukkan nilai baru: "))
     print("Data berhasil diubah.")
     return
     print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")

     # Menu utama
     def menu():
     while True:
           print("\nMenu:")
           print("1. Tambah Data")
           print("2. Tampilkan Data")
           print("3. Hapus Data")
           print("4. Ubah Data")
           print("5. Keluar")
           pilihan = input("Pilih menu (1-5): ")
           if pilihan == "1":
               tambah()
           elif pilihan == "2":
               tampilkan()
           elif pilihan == "3":
               nama = input("Masukkan nama mahasiswa yang akan dihapus: ")
               hapus(nama)
           elif pilihan == "4":
               nama = input("Masukkan nama mahasiswa yang akan diubah: ")
               ubah(nama)
           elif pilihan == "5":
               print("Keluar dari program.")
               break
           else:
               print("Pilihan tidak valid. Silakan coba lagi.")

               # Menjalankan menu utama
               menu()
               

Penjelasan:

1.Memasukkan data inputan seperti : nama, nim, dan nilai mahasiswa

2.Menggunakan try dan except untuk memastikan bahwa nilai yang
dimasukkan adalah angka. jika tidak, pengguna akan disuruh mengulangnya lagi

3.Fungsi berguna untuk memeriksa apakah mahasiswa dengan nama yang ada dalam daftar. jika tidak ada, program tidak akan menambahkan data tersebut

4.Jika semua validasi diatas sudah benar, data berhasil ditambahkan
kedalam list

5.Memeriksa apakah daftar mahasiswa kosong atau tidak. Jika kosong, menampilkan tidak ada data

6.Jika ada data, fungsi inni mencetak daftar mahasiswa dengan format yang terstruktur

7.Menghapus data berfungsi untuk menghapus data mahasiswa dari daftar dan memberi tau pengguna bahwa data berhasil ke hapus

8.Mengubah data berfungsi untuk mengubah data mahasiswa yang lama dengan yang baru dengan memasukkan nama, nim dan nilai

Latihan 1
#Ubahlah kode dibawah ini menjadi fungsi menggunakan lambda

kode python

    import math

    # Menggunakan lambda untuk mendefinisikan fungsi
      a = lambda x: x**2
      b = lambda x, y: math.sqrt(x*2 + y*2)
      c = lambda *args: sum(args) / len(args)
      d = lambda s: "".join(set(s))

    if _name_ == "_main_":
    print("a(5):", a(5))
    print("b(3, 4):", b(3, 4))
    print("c(1, 2, 3, 4, 5):", c(1, 2, 3, 4, 5))
    print("d('hello world'):", d('hello world'))
