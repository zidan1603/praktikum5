# praktikum5

## Program
dibawah ini adalah program sederhana untuk membuat daftar nilai mahasiswa dengan mnggunakan Kamus , dan menampilkan pilihan Menu Tambah, Ubah, Hapus, Cari, dan Lihat.

![ss23](https://user-images.githubusercontent.com/115911489/204246407-b5046dd2-aa52-42d7-bc33-be60517e462d.JPG)


![ss24](https://user-images.githubusercontent.com/115911489/204246482-e9dd1ed1-6068-4480-802e-fae9b697f670.JPG)


![ss25](https://user-images.githubusercontent.com/115911489/204246524-c819e9df-e1b1-4945-9678-194f91633be7.JPG)


## Flowchart
Berikut adalah tampilan dari flowchartnya:

<img width="217" alt="ss31" src="https://user-images.githubusercontent.com/115911489/204246871-db4cc05d-059b-45ea-a98f-60140f2af16d.png">

Penjelasan

Mendeklarasikan Dictonary kosong dengan synatax data = {}

Lalu buat perulangan sambil dan untuk menginisialisasikan penambahan menu pilihan Tambah, Ubah, Hapus, Cari, Lihat, dan Keluar :

while True:
 
 x = input("(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")

Menambahkan Data

Berikut adalah Syntax untuk menambahkan data dengan ketentuan jika kita mengetikkan T pada keyboard, maka akan melakukan penambahan data dan ditampung ke dalam 

Dictonary data yang telah kita buat, dengan nama sebagai keys dan yang lainnya sebagai nilai.

if x.lower() == 't':

    print("Tambah Data")

    nama = input("Nama           : ")

    nim = int(input("NIM            : "))
    
    uts = int(input("Nilai UTS      : "))
    
    uas = int(input("Nilai UAS      : "))
    
    tugas = int(input("Nilai Tugas    : "))
    
    n_akhir = tugas * 0.30 + uts * 0.35 + uas * 0.35
    
    data[nama] = nim, uts, uas, tugas, n_akhir

Mengubah Data

Jika input yang dimasukkan adalah U, di dalam kondisi ini terdapat input dan kondisi, dimana jika input nama ada didalam variabel data maka akan muncul beberapa 

pilihan untuk mengubah semua data atau data tertentu saja.

elif x.lower() == 'u':
   
   print("Ubah Data")
    
    nama = input("Masukkan Nama   : ")
    
    if nama in data.keys():
        
        nim = int(input("NIM            : "))
        
        uts = int(input("Nilai UTS      : "))
        
        uas = int(input("Nilai UAS      : "))
        
        tugas = int(input("Nilai Tugas    : "))
        
        n_akhir = tugas*0.30 + uts*0.35 + uas*0.35
        
        data[nama] = nim, uts, uas, tugas, n_akhir
   
   else:
        
        print("Nama{0} Tidak Ditemukan".format(nama))

Menghapus Data

Sama seperti mengubah data yang dipilih.

Data yang dihapus adalah data yang di input dalam variabel nama dimana berisi (string) yang mewakili NIM, Nilai Tugas, UTS, UAS.
    
    elif x.lower() == 'h':
       
       print("Hapus Data")
       
       nama = input("Masukkan Nama  : ")
      
      if nama in data.keys():
           
           del data[nama]
        
      else:
          print("Nama {0} Tidak Ditemukan".format(nama))

Mencari Data

Perbandingan untuk mencari data yang akan diubah sama seperti cara mengubah data, hanya saja perintah ini digunakan untuk menampilkan data yang di input berdasarkan 

nama. Berikut kode yang digunakan.

elif x.lower() == 'c':
   
   print("Cari Data")
   
   nama = input("Masukkan Nama : ")
   
   if nama in data.keys():
       
       print("=" * 73)
       
       print(
       
             "|                             Daftar Mahasiswa                          |")
        
        print("=" * 73)
       
       print(
            
            "| Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
        
        print("=" * 73)
        
        print("| {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
              
              .format(nama, nim, uts, uas, tugas, n_akhir))
        
        print("=" * 73)
    
    else:
        
        print("Nama {0} Tidak Ditemukan".format(nama))

Melihat Data

Selanjutnya adalah kode yang digunakan untuk melihat input yang sudah dimasukkan.

Data dalam perulangan for diambil dari variabel Dictionary datapada bagian value yang berbntuk list. variabel i = 0 digunakan untuk membuat nomer. Data yang akan 

diambil adalah Nama, NIM, Nilai Tugas, UTS, UAS dan Nilai Akhir

elif x.lower() == 'l':
    
    if data.items():
        
        print("=" * 78)
        
        print(
            
            "|                               Daftar Mahasiswa                             |")
        
        print("=" * 78)
        
        print(
            
            "|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
        
        print("=" * 78)
        
        i = 0
        
        for y in data.items():
            
            i += 1
            
            print("| {no:2d} | {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                  
                  .format(y[0][:13], y[1][0], y[1][1], y[1][2], y[1][3], y[1][4], no=i))
            
            print("=" * 78)
    
    else:
        
        print("=" * 78)
        
        print(
            
            "|                               Daftar Mahasiswa                             |")
        
        print("=" * 78)
        
        print(
            
            "|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
        
        print("=" * 78)
        
        print(
            
            "|                                TIDAK ADA DATA                              |")
        
        print("=" * 78)

Keluar

Perulangan diatas adalah perulangan yang akan berjalan terus menerus dan akan berhenti jika kode berikut di eksekusi 

elif x.lower() == 'k':

Jika k di input dan lower()digunakan untuk mengkonversi input yang dimasukkan ke bentuk lower case dan input k digunakan berdasarkan perintah yang sudah dimasukan 

dalam keterangan pada fungsi input dibawah ini:
    
    elif x.lower() == 'k':
        
        break

    else:
        
        print("Pilih Menu Yang Tersedia
        
##Keluaran Hasil

Apabila program dijalankan maka akan menghasilkan output sebagai berikut :

Menambahkan Data dengan input T dan melihat data dengan input L

![ss26](https://user-images.githubusercontent.com/115911489/204249537-f0edd358-c341-4558-b379-39a1920e898b.JPG)

Mengubah Data dengan input U dan melihat data dengan input L

![ss27](https://user-images.githubusercontent.com/115911489/204249960-4ee5a59e-7cdc-4697-bea9-04cc8668f838.JPG)

Menghapus Data dengan input H dan melihat dan melihat data dengan input L

![ss28](https://user-images.githubusercontent.com/115911489/204250216-a05a5f41-1e71-4983-b5ed-f7129a1c2702.JPG)

Mencari Data dengan input C

![ss29](https://user-images.githubusercontent.com/115911489/204250353-69e1f730-6860-4757-8652-ed2366635912.JPG)


Keluar dari program dengan input K

![ss30](https://user-images.githubusercontent.com/115911489/204250504-5e32e23d-c7fd-4824-a8ba-d8b976bdb804.JPG)

## Terima Kasih

