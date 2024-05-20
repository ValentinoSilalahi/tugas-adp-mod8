def tb(jdb, nps, npt, tht):
    with open("tino.txt", "a") as file:
        file.write(f"{jdb}, {nps}, {npt}, {tht}\n")
        print("Data telah ditambahkan cuy")
        print()

def hps(jdb):
    with open("tino.txt", "r") as file:
        baris = file.readlines()
    with open("tino.txt", "w") as file:
        for i in baris:
            if i.strip().split(",")[0] != jdb:
                file.write(i)
        print("Data telah dihapus cuy")
        print()

def tmpl():
    with open("tino.txt", "r") as file:
        baris = file.readlines()
        print("Data-data buku anda selama ini : ")
        print("==============================================================================")
        print(f"|| {'Judul Buku':<15} || {'Penulis':<15} || {'Penerbit':<15} || {'Tahun Terbit':<15} ||")
        print("==============================================================================")
        for i in baris:
            jdb, nps, npt, tht = i.strip().split(",")
            print(f"|| {jdb:<15} || {nps:<15} || {npt:<15} || {tht:<15} ||")
            print("------------------------------------------------------------------------------")
        print()

while True:
    print("Menu :")
    print("1. Tambah")
    print("2. Hapus")
    print("3. Tampilkan")
    print("4. Keluar")

    ph = int(input("Pilih menu cuy (1/2/3/4) : "))
    if ph == 1:
        print("Anda masuk kedalam menu penambahan data buku")
        jdb = input("Masukkan judul buku : ")
        nps = input("Masukkan nama penulis buku : ")
        npt = input("Masukkan nama penerbit buku : ")
        tht = input("Masukkan tahun terbit buku : ") 
        tb(jdb, nps, npt, tht)
    elif ph == 2:
        print("Anda masuk kedalam menu penghapusan data menurut judul")
        jdb = input("Masukkan judul buku : ")
        hps(jdb)
    elif ph == 3:
        tmpl()
    elif ph == 4:
        print("Keluar cuy")
        print()
        break
    else:
        print("Menu tidak valid cuy. Ulang lagi")
        print()
