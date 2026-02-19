import database as db
import data

def pinjam_buku():
    data.lihat_buku()

    i = int(input("Pilih buku: ")) - 1

    if 0 <= i < len(db.buku_db):
        buku = db.buku_db[i]

        if buku["stok"] > 0:
            nama = input("Nama peminjam: ")

            buku["stok"] -= 1

            db.peminjaman_db.append({
                "nama": nama,
                "judul": buku["judul"]
            })

            print("✅ Buku dipinjam")
        else:
            print("❌ Stok habis")

def kembalikan_buku():
    nama = input("Nama peminjam: ")

    for pinjam in db.peminjaman_db:
        if pinjam["nama"] == nama:

            for buku in db.buku_db:
                if buku["judul"] == pinjam["judul"]:
                    buku["stok"] += 1

            db.peminjaman_db.remove(pinjam)
            print("✅ Buku dikembalikan")
            return

    print("❌ Data tidak ditemukan")
