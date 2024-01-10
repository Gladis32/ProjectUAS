# Project UAS
>Project UAS Bahasa Pemrograman | Universitas Pelita Bangsa

| Variable | Isi |
| -------- | --- |
| **Nama** | Gladis Toti Anggraini |
| **NIM** | 312310566 |
| **Kelas** | TI.23.A.5 |
| **Mata Kuliah** | Bahasa Pemrograman |

## Program Kasir Sebuah Kantin 
### Link Youtube

| Link Youtube| Isi |
| --------    | --- |

### Input Program
``````
pembeli = input("Masukkan Nama Pembeli: ")
NomorMeja = input("Masukkan Nomor Meja: ")

print("\nSelamat Datang Di Kantin")

menu = {
    1: {"nama": "Nasi Goreng", "harga": 10000,},
    2: {"nama": "Mie Kwetiaw", "harga": 10000,},
    3: {"nama": "Batagor", "harga": 10000,},
    4: {"nama": "Seblak", "harga": 13000,},
    5: {"nama": "Gorengan", "harga": 1000,},
}

keranjang = {}
totalmakan = 0

while True:
    print("\nDaftar Menu:")
    for i in menu:
        print(f"{i}. {menu[i]['nama']} - Harga: {menu[i]['harga']}")

    pil = int(input("\nMasukkan pilihan (1: ubah nama, 2: beli, 3: keluar, 4: struk): "))

    if pil == 1:
        for j in menu:
            print(j, menu[j]["nama"])
        pilihan = int(input("Masukkan nomor item yang ingin dirubah nama: "))
        new_name = input("Masukkan nama baru: ")
        menu[pilihan]["nama"] = new_name
        print("Nama item berhasil diubah.")

    elif pil == 2:
        while True:
            for k in menu:
                print(f"{k}. {menu[k]['nama']} - Harga: {menu[k]['harga']}")
            beli_pilihan = int(input("Masukkan nomor item yang ingin dibeli (0: selesai beli): "))
            
            if beli_pilihan == 0:
                break
                
            if beli_pilihan in menu:
                jumlah = int(input("Masukkan jumlah yang ingin dibeli: "))
                if menu[beli_pilihan]["nama"] in keranjang:
                    keranjang[menu[beli_pilihan]["nama"]] += jumlah
                else:
                    keranjang[menu[beli_pilihan]["nama"]] = jumlah
                print(f"{jumlah} {menu[beli_pilihan]['nama']} telah ditambahkan ke keranjang.")
                totalmakan += menu[beli_pilihan]['harga'] * jumlah
            else:
                print("Nomor item tidak valid.")

    elif pil == 3:
        print("Program dihentikan.")
        break

    elif pil == 4:
        print("\n=============================")
        print("====== S T R U K   B E L I ======")
        print("\n=============================")
        for item, jumlah in keranjang.items():
            print(f"{item}\t\t: {jumlah} porsi (Rp {menu[next((k for k, v in menu.items() if v['nama'] == item), None)]['harga'] * jumlah})")
        print("\nTotal Harus Dibayar: Rp", totalmakan)
        uang = int(input("Uang Tunai Pembeli: Rp"))
        kembalian = uang - totalmakan
        print("Kembalian\t: Rp", kembalian)
        print("====== SELAMAR MENIKMATI ========")
        print("======   TERIMA KASIH    ========")

    else:
        print("Pilihan tidak ada dalam menu. Silahkan masukkan ulang.")
``````
Penjelasan:
1. Input Pembeli dan Nomor Meja:
</br>pembeli = input("Masukkan Nama Pembeli: "): Mengambil input nama pembeli.
</br>NomorMeja = input("Masukkan Nomor Meja: "): Mengambil input nomor meja.

2. Daftar Menu:
</br>Membuat dictionary menu yang berisi daftar makanan beserta harga.
</br>keranjang digunakan untuk menyimpan pilihan makanan dan jumlahnya.
</br>totalmakan digunakan untuk menghitung total harga pesanan.
Menu Utama:

3. Sebuah loop tak terbatas (while True) digunakan untuk </br>memungkinkan pengguna melakukan beberapa tindakan.
</br>Menampilkan daftar menu setiap kali iterasi.
</br>Pengguna diminta untuk memilih tindakan:
</br>Pilihan 1 (pil == 1): Mengubah nama item menu tertentu.
</br>Pilihan 2 (pil == 2): Menambahkan item ke keranjang belanja.
</br>Pilihan 3 (pil == 3): Menghentikan program.
</br>Pilihan 4 (pil == 4): Menampilkan struk belanja.

4. Ubah Nama Item:
</br>Pengguna dapat memilih untuk mengubah nama item menu tertentu.
Beli Item:
</br>Pengguna dapat memilih item yang ingin dibeli dari daftar menu.
</br>Jumlah item dan harganya ditambahkan ke keranjang.
Keluar dari Program:
</br>ilihan 3 (pil == 3) menghentikan program.
5. Struk Belanja:
</br>Pilihan 4 (pil == 4) menampilkan struk belanja.
</br>Menampilkan item, jumlah, dan total harga.
</br>Meminta input uang tunai dari pembeli.
</br>Menghitung dan menampilkan kembalian.
</br>Memberikan ucapan selamat menikmati dan terima kasih.
6. Rumus untuk menghitung total harga menu 
</br>Rumus ini menggunakan operator perkalian untuk mengalikan </br>harga menu dengan jumlah menu yang dibeli 
</br>Misalnya, jika menu yang dipilih adalah nasi goreng dengan </br>harga 10.000 dan jumlah yang dibeli adalah 2 makan total </br>harganya ada a
``````
Menu[beli_pilihan]['harga']*jumlah=10.000*2=20.000
``````
7. Sedangkan rumus untuk menghitung kembalian 
</br>Menggunakann operator pengurangN untuk mengurangin uang </br>tunai yang dibayarkan dengan total harga yang harus dibayarkan 
</br>Misalnya, jika uang tunai yang dibayarkan adalah 50.000 dan total harga yang harus dibayarkan 30.000 kakan kembaliannya adalah 
Uang-totalmakan = 50.000-30.000=20.000

### Output Program
![ss output beli](https://github.com/Gladis32/ProjectUAS/assets/148181064/30a4cb29-fb69-4b88-98b6-12910958c984)
![ss output struk](https://github.com/Gladis32/ProjectUAS/assets/148181064/2fc0e262-f68f-4dc0-85d5-d5dc7ddc0083)
![output ubah item](https://github.com/Gladis32/ProjectUAS/assets/148181064/7293229c-729c-4642-9a26-2c2cbc2bd440)






