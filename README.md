# praktikum-5
## Membuuat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan menggunakan Dictionary

Pada praktikum 5, kita akan membuat program sederhana untuk membuat data mahasiswa menggunakan Dictionary dengan python.
print("Program Input Nilai") print("================")

daftar = {}

while True:

perintah = input("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar: ")
## Masukan huruf T untuk menginput data (Daftar Nilai)
 (T)ambah
    if perintah.lower() == 't':
        nim = input("Masukan NIM: ")
        nama = input("Masukan nama: ")
        n_tugas = int(input("Masukan nilai tugas: "))
        n_UTS = int(input("Masukan nilai UTS: "))
        n_UAS = int(input("Masukan nilai UAS: "))
        a = n_tugas * 30 / 100
        b = n_UTS * 35 / 100
        c = n_UAS * 35 / 100
        n_akhir = a + b + c
        daftar[nama] = [nama, nim, n_tugas, n_UTS, n_UAS, n_akhir]
 ![mencari T](https://user-images.githubusercontent.com/56240221/71557148-bf2a1300-2a74-11ea-8d94-ac4faceedfde.jpg)

## Masukan huruf L untuk melihat Daftar Nilai
(L)ihat
    elif perintah.lower() == 'l':
        print("Daftar Nilai:")
        print("===================================================================")
        print("| No |      Nama      |    NIM    | Tugas |  UTS  |  UAS  | Akhir |")
        print("===================================================================")
        no = 1
        for tabel in daftar.values():
            print("| {0:2} | {1:14} | {2:9} | {3:5} | {4:5} | {5:5} | {6:5} |".format
                  (no, tabel[0],
                   tabel[1], tabel[2],
                   tabel[3], tabel[4], tabel[5]))
            no += 1
 ![mencari L](https://user-images.githubusercontent.com/56240221/71557159-d8cb5a80-2a74-11ea-9f11-7be95300c366.jpg)

## Masukan huruf U untuk mengubah data mahasiswa
(U)bah
    elif perintah.lower() == 'u':
        nama = input("Masukan nama untuk mengubah data: ")
        if nama in daftar.keys():
            print("Masukan data yang ingin di ubah :")
            data = input("(Semua), (Nama), (NIM), "
                         "(Tugas), (UTS), (UAS) : ")
            if data.lower() == "semua":
                print("==========================")
                print("Ubah data {}.".format(nama))
                print("==========================")
                daftar[nama][1] = input("Edit NIM:")
                daftar[nama][2] = int(input("Edit Nilai Tugas: "))
                daftar[nama][3] = int(input("Edit Nilai UTS: "))
                daftar[nama][4] = int(input("Edit Nilai UAS: "))
                # print(daftar)
            elif data.lower() == "nim":
                daftar[nama][1] = input("NIM:")
            elif data.lower() == "tugas":
                daftar[nama][2] = int(input("Nilai Tugas: "))
            elif data.lower() == "uts":
                daftar[nama][3] = int(input("Nilai UTS: "))
            elif data.lower() == "uas":
                daftar[nama][4] = int(input("Nilai UAS: "))
            else:
                print("Perintah tidak ditemukan.")

        else:
            print("'{}' tidak ditemukan.".format(nama))
![mengubah U](https://user-images.githubusercontent.com/56240221/71557168-f1d40b80-2a74-11ea-898f-d1fd4b65d499.jpg)
## Masukan huruf C untuk mencari data nilai mahasiswa
(C)ari
    elif perintah.lower() == 'c':
        print("Mencari daftar nilai: ")
        print("=================================================")
        nama = input("Masukan nama untuk mencari daftar nilai : ")
        if nama in daftar.keys():
            print("Nama {0}, dengan NIM : {1}\n"
                  "Nilai Tugas: {2}, UTS: {3}, dan UAS: {4}\n"
                  "dan nilai akhir {5}".format(nama, daftar[nama][1],
                                               daftar[nama][2], daftar[nama][3],
                                               daftar[nama][4], daftar[nama][5]))
        else:
            print("'{}' tidak ditemukan.".format(nama))
![mengubah C](https://user-images.githubusercontent.com/56240221/71557173-0912f900-2a75-11ea-8cfe-6821a815220d.jpg)

## Masukan huruf H untuk menghapus data nilai mahasiswa
(H)apus
    elif perintah.lower() == 'h':
        nama = input("Masukan nama untuk menghapus data : ")
        if nama in daftar.keys():
            del daftar[nama]
            print("Data '{}' dihapus.".format(nama))
        else:
            print("'{}' tidak ditemukan.".format(nama))
![mengunah H](https://user-images.githubusercontent.com/56240221/71557180-22b44080-2a75-11ea-83d6-3fabd622bcd1.jpg)

## Masukan huruf K untuk keluar/selesai
(K)eluar
    elif perintah.lower() == 'k':
        break

    else:
        print("Silahkan masukan perintah terlebih dahulu.")
        
