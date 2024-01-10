# Project UAS
>Project UAS Bahasa Pemrograman | Universitas Pelita Bangsa

| Variable | Isi |
| -------- | --- |
| **Nama** | Gladis Toti Anggraini |
| **NIM** | 312310566 |
| **Kelas** | TI.23.A.5 |
| **Mata Kuliah** | Bahasa Pemrograman |

## Input

iput untuk memasukkan nama pembeli dan nomor meja pembeli
``````
pembeli = input("Masukkan Nama Pembeli: ")
NomorMeja = input("Masukkan Nomor Meja: ")
``````


``````
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



