# Logika-Informatika
# Tugas 1

|                |                    |
| -------------- | ------------------ |
|      Nama    | Vivit Nurul Hidayah |
|      NIM     |      312410110     |
|     Kelas    |      TI.24.A1      |
|  Mata Kuliah | Logika Informatika |

# Soal

Sebuah jasa pengiriman memiliki aturan biaya yang bergantung pada beberapa faktor. Biaya dasar pengiriman ditetapkan sebesar Rp 10.000.
Jika berat paket melebihi 5 kg, maka akan dikenakan tambahan biaya sebesar Rp 5.000. Selain itu, jika jarak pengiriman lebih dari 10 km, maka ada tambahan biaya sebesar Rp 8.000.
Jika pelanggan memilih layanan pengiriman express, maka akan dikenakan tambahan biaya sebesar Rp 20.000. Namun, jika pelanggan merupakan member, mereka akan mendapatkan diskon 10% dari total biaya pengiriman yang dihitung sebelum diskon.

Buatlah sebuah fungsi dalam Python yang dapat menghitung total biaya pengiriman berdasarkan aturan tersebut, dengan parameter berat paket, jarak pengiriman, jenis pengiriman (biasa atau express), serta status keanggotaan pelanggan (member atau non-member).

# Input Program 
```python
def hitung_biaya_pengiriman(berat, jarak, jenis_pengiriman, status_member):
    # Biaya dasar
    biaya_total = 10000
    
    # Detail perhitungan
    perhitungan = []
    
    # Menambahkan biaya dasar
    perhitungan.append(["Biaya Dasar", 10000])

    # Menambahkan biaya jika berat paket melebihi 5 kg
    if berat > 5:
        biaya_total += 5000
        perhitungan.append(["Biaya Berat > 5 kg", 5000])
    
    # Menambahkan biaya jika jarak pengiriman lebih dari 10 km
    if jarak > 10:
        biaya_total += 8000
        perhitungan.append(["Biaya Jarak > 10 km", 8000])
    
    # Menambahkan biaya jika memilih pengiriman express
    if jenis_pengiriman.lower() == "express":
        biaya_total += 20000
        perhitungan.append(["Biaya Pengiriman Express", 20000])
    
    # Memberikan diskon 10% jika pelanggan adalah member
    diskon = 0
    if status_member.lower() == "member":
        diskon = biaya_total * 0.1
        biaya_total -= diskon
        perhitungan.append(["Diskon Member (10%)", -diskon])
    
    # Menampilkan tabel perhitungan secara manual
    print(f"{'Keterangan':<25} {'Biaya (Rp)'}")
    print("="*40)
    for item in perhitungan:
        print(f"{item[0]:<25} {item[1]:>10}")
    
    print("="*40)
    print(f"{'Total Biaya Pengiriman':<25} {biaya_total:>10.2f}")
    
    return biaya_total

# Mengambil input dari pengguna
try:
    berat_paket = float(input("Masukkan berat paket (kg): "))
    jarak_pengiriman = float(input("Masukkan jarak pengiriman (km): "))
    jenis_pengiriman = input("Masukkan jenis pengiriman (biasa/express): ").lower()
    status_member = input("Apakah Anda member? (member/non-member): ").lower()

    # Menghitung dan menampilkan biaya pengiriman
    total_biaya = hitung_biaya_pengiriman(berat_paket, jarak_pengiriman, jenis_pengiriman, status_member)

except ValueError:
    print("Input yang Anda masukkan tidak valid. Pastikan menggunakan angka untuk berat dan jarak.")
```

# Output Program 
```
Masukkan berat paket (kg): 10
Masukkan jarak pengiriman (km): 100
Masukkan jenis pengiriman (biasa/express): express
Apakah Anda member? (member/non-member): member
Keterangan                Biaya (Rp)
========================================
Biaya Dasar                    10000
Biaya Berat > 5 kg              5000
Biaya Jarak > 10 km             8000
Biaya Pengiriman Express       20000
Diskon Member (10%)          -4300.0
========================================
Total Biaya Pengiriman      38700.00
PS C:\Users\hp\Documents\KULIAH SEMESTER 2\Logika Informatika coding\tugas pertm 1>

Masukkan berat paket (kg): 5 
Masukkan jarak pengiriman (km): 10
Masukkan jenis pengiriman (biasa/express): biasa
Apakah Anda member? (member/non-member): non-member
Keterangan                Biaya (Rp)
========================================
Biaya Dasar                    10000
========================================
Total Biaya Pengiriman      10000.00
PS C:\Users\hp\Documents\KULIAH SEMESTER 2\Logika Informatika coding\tugas pertm 1>
```


