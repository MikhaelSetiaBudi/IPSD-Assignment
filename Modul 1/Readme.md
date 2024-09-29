# <h1 align="center">Laporan Praktikum Modul Dasar-Dasar Python untuk Sains Data</h1>
<p align="center">Mikhael Setia Budi</p>

## Dasar Teori



## Guided 

### 1. [Nama Topik]

```python
print("ini adalah file code guided praktikan")
```
Kode di atas digunakan untuk mencetak teks "ini adalah file code guided praktikan" ke layar menggunakan function print untuk mengeksekusi nya.

## Unguided 

### 1. Memecahkan Masalah Unik dengan Loop dan If-Else
Buatlah program yang dapat menghasilkan pola berbentuk angka seperti di bawah ini, dengan syarat angka yang ditampilkan adalah hasil dari penjumlahan bilangan prima sebelumnya:
```
1
2 3
5 7 11
13 17 19 23
...
```
Jumlah angka pada setiap baris bertambah 1, dan bilangan yang ditampilkan adalah bilangan prima.

#### Jawaban
```
def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True

def generate_primes(n):
    primes = []
    num = 2  
    while len(primes) < n:
        if is_prime(num):
            primes.append(num)
        num += 1
    return primes

def print_prime_pattern(rows):
    total_numbers = (rows * (rows + 1)) // 2  
    primes = generate_primes(total_numbers)

    print(1)  
    index = 0

    for i in range(2, rows + 1):  
        for j in range(i):
            if index < len(primes):
                print(primes[index], end=' ')
                index += 1
        print()  

jumlah_baris = 4  
print_prime_pattern(jumlah_baris)
```

**Code 1**
```
def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True
```
Fungsi is_prime digunakan untuk menentukan apakah sebuah angka (num) adalah bilangan prima.
Sebuah kondisi jika num kurang dari 2 maka akan mengembalikan false. Lalu menggunakan loop untuk memeriksa pembagian dari 2 hinggga akar kuadrat dari num.
Jika tidak ada pembagian yang ditemukan maka akan mengembalikan true.

**Code 2**
```
def generate_primes(n):
    primes = []
    num = 2  
    while len(primes) < n:
        if is_prime(num):
            primes.append(num)
        num += 1
    return primes
```
Fungsi generate_primes(n) digunakan untuk menghasilkan n bilangan prima. 
Membuat list kosong primes untuk menyimpan bilangan prima, dengan memulai num sebagai 2.
Menggunakan loop while untuk mencari bilangan prima sampai jumlah n tercapai.
Lalu memanggil fungsi is_prime(num) untuk memeriksa num apakah bilangan prima, jika benar maka num ditambahkan ke dalam list primes.
Setelah looping selesai maka akan mengembalikan list primes yang berisikan bilangan prima.

**Code 3**
```
def print_prime_pattern(rows):
    total_numbers = (rows * (rows + 1)) // 2  
    primes = generate_primes(total_numbers)

    print(1)  
    index = 0

    for i in range(2, rows + 1):  
        for j in range(i):
            if index < len(primes):
                print(primes[index], end=' ')
                index += 1
        print()
```
Fungsi print_prime_pattern(rows) digunakan untuk mencetak pola bilangan prima dengan bentuk segitiga sesuai dengan jumlah baris.
Menghitung jumlah angka yang dibutuhkan menggunakan rumus segitiga. Menghasilkan bilangan prima sebanyak total_number dengan menggunakan fungsi generate_primes, lalu mencetak angka 1 di awal.
Menggunakan dua loop dimana loop luar mengintegrasi dari 2 hingga rows, dan loop dalam mencetak angka untuk setiap barisnya.
index digunakan untuk melacak posisi dalam list primes dan mencetak bilangan sesuai dengan index.
print() dipanggil untuk pindah ke baris yang baru.

**Code 4**
```
jumlah_baris = 4  
print_prime_pattern(jumlah_baris)
```
Kode diatas digunakan untuk mengeksekusi program. Kode diatas mengatur jumlah_baris ke 4 yang artinya pola yang akan dicetak memiliki 4 baris.
Kode print_prime_pattern(jumlah baris) dipanggil untuk mencetak pola bilangan prima

#### Output
```
1
2 3 
5 7 11 
13 17 19 23 
```
Output membentuk segitiga dengan bilangan prima 2 sampai 23.

#### Screenshot Program:


#### Screenshot Output:
![image](https://github.com/user-attachments/assets/fc05c081-b447-4e91-a2fc-24f481d8a593)


Kode di atas digunakan untuk mencetak teks "ini adalah file code guided praktikan" ke layar menggunakan function print untuk mengeksekusi nya.

### 2. Membuat Fungsi dengan Syarat Spesifik
Buatlah sebuah fungsi yang menerima dua input berupa list angka. Fungsi ini harus mengembalikan sebuah list baru yang berisi elemen dari dua list input yang memiliki indeks ganjil. 
List baru tersebut juga harus diurutkan secara menurun berdasarkan nilai elemen.

#### Jawaban
```
def combine_and_sort_odd_indices(list1, list2):
    odd_indexed_elements = []
    odd_indexed_elements.extend(list1[i] for i in range(1, len(list1), 2))
    odd_indexed_elements.extend(list2[i] for i in range(1, len(list2), 2))
    odd_indexed_elements.sort(reverse=True)
    return odd_indexed_elements

list1 = [10, 20, 30, 40, 50]
list2 = [5, 15, 25, 35, 45]

result = combine_and_sort_odd_indices(list1, list2)
print(result) 
```

**Code 1**
```
def combine_and_sort_odd_indices(list1, list2):
    odd_indexed_elements = []
    odd_indexed_elements.extend(list1[i] for i in range(1, len(list1), 2))
    odd_indexed_elements.extend(list2[i] for i in range(1, len(list2), 2))
    odd_indexed_elements.sort(reverse=True)
    return odd_indexed_elements
```
Fungsi combune_and_sort_odd_indices digunakan untuk menggambungkan elemen-elemen yang terletak pada indeks ganjil dari dua daftar yaitu list1 dan list2, lalu mengurutkan dalam urutan menurun.
Membuat variabel odd_indexed_elements untuk menyimpan elemen yang diambil dari indeks ganjil.
Menggunakan generator expression untuk mengambil elemen dari list1 pada indeks ganjil.
range(1, len(list1), 2) digunakan untuk menghasilkan angka mulai dari 1 hingga panjang list.
Kode diatas juga digunakan unruk mengurutkan elemen odd_indexed_elements dengan urutan menurun, dan mengembalikan list yang telah diisi dengan elemen dari indeks ganjil.

**Code 2**
```
list1 = [10, 20, 30, 40, 50]
list2 = [5, 15, 25, 35, 45]

result = combine_and_sort_odd_indices(list1, list2)
print(result)
```
Kode diatas menginisialisasi list1 dan list2. Lalu memanggil fungsi combine_and_sort_odd_indices(list1, list2) dipanggil dengan list1 dan list2 sebagai argumen, setelah itu hasilnya disimpan di variabel result.
print(result) digunakan untuk mencetak isi dari result.

#### Output
```
[40, 35, 20, 15]
```
Output menampilkan angka dari indeks ganjil.

#### Screenshot Program:


#### Screenshot Output:

### 3. Buat sebuah program untuk mensimulasikan transaksi ATM. Program harus:
1. Meminta pengguna memasukkan PIN (dibatasi 3 kali percobaan).
2. Setelah PIN benar, meminta jumlah penarikan.
3. Jika saldo kurang dari jumlah yang ditarik, munculkan pesan kesalahan.
4. Jika penarikan berhasil, tampilkan saldo akhir.

#### Jawaban
```
def atm_simulation():
    correct_pin = "1234"  
    attempts = 3  
    balance = 100000   
    
    for attempt in range(attempts):
        pin = input("Masukkan PIN Anda: ")
        if pin == correct_pin:
            print("PIN benar!")
            break
        else:
            print("PIN salah. Coba lagi.")
            if attempt == attempts - 1:
                print("Anda telah mencoba terlalu banyak kali. Transaksi dibatalkan.")
                return

    try:
        withdrawal_amount = float(input("Masukkan jumlah penarikan: "))
    
        if withdrawal_amount > balance:
            print("Kesalahan: Saldo tidak cukup untuk penarikan tersebut.")
        else:
            balance -= withdrawal_amount
            print(f"Penarikan berhasil! Saldo akhir Anda: {balance}")
    except ValueError:
        print("Input tidak valid. Harap masukkan jumlah yang benar.")

atm_simulation()
```

**Code 1**
```
def atm_simulation():
```
Kode diatas digunakan untuk mendefinisikan fungsi atm_simulation.

**Code 2**
```
correct_pin = "1234"  
    attempts = 3  
    balance = 100000 
```
Membuat variabel correct_pin digunakan untuk menyimpan PIN yang benar untuk autentikasi, disini diatur dengan PIN "1234". 
Variabel attempts digunakan untuk menentukan jumlah maksimal percobaan untuk memasukkan PIN nya, Percobaan PIN dilakukan sebanyak 3 kali.
Lalu berikutnya membuat variabel balance untuk menyimpan saldo awal pengguna di ATM dimana untuk saldo diatur sebanyak 100000.

**Code 3**
```
for attempt in range(attempts):
        pin = input("Masukkan PIN Anda: ")
        if pin == correct_pin:
            print("PIN benar!")
            break
        else:
            print("PIN salah. Coba lagi.")
            if attempt == attempts - 1:
                print("Anda telah mencoba terlalu banyak kali. Transaksi dibatalkan.")
                return
```
Kode diatas menggunakan loop untuk memeriksa PIN. loop for digunakan untuk memberikan pengguna hingga 3 percobaan dalam memasukkan PIN.
menggunakan input untuk mengambil input PIN yang dimasukkan oleh pengguna. Apabila PIN yang dimasukkan sama dengan correct_pin maka akan mencetak kata "PIN benar!" dan keluar dari loop.
Jika PIN salah maka akan mencetak kata "PIN salah. Coba lagi". Jika percobaan terakhir dalam memasukkan PIN maka mencetak pesan transaksi dibatalkan dan keluar fungsi dengan return.

**Code 4**
```
  try:
        withdrawal_amount = float(input("Masukkan jumlah penarikan: "))
    
        if withdrawal_amount > balance:
            print("Kesalahan: Saldo tidak cukup untuk penarikan tersebut.")
        else:
            balance -= withdrawal_amount
            print(f"Penarikan berhasil! Saldo akhir Anda: {balance}")
    except ValueError:
        print("Input tidak valid. Harap masukkan jumlah yang benar.")
```
Kode diatas digunakan untuk penarikan uang, dengan menggunakan blok try untuk menangani kesalahan saat input. Lalu kode diatas digunakan untuk mengambil input yang ingin ditarik dan mengonversinya menjadi float.
Jika jumlah penarikan lebih besar dari balance maka akan mencetak pesan kesalahan.
Jika valid maka akan mengurangi withdrawal_amount dari balance dan saldo akhir ditampilkan.
Jika input ke float gagal maka akan mencetak pesan bahwa input tidak valid

**Code 5**
```
atm_simulation()
```
Memanggil fungsi atm_simulation() untuk menjalankan simulasi ATM.

#### Output
```
Masukkan PIN Anda:  1234
PIN benar!
Masukkan jumlah penarikan:  50000
Penarikan berhasil! Saldo akhir Anda: 50000.0
```
output yang ditampilkan adalah user memasukkan PIN atm nya jika benar maka user dapat memasukkan nominal yang ingin ditarik, setelah nominal yang ditarik berhasil maka akan menampilkan saldo akhir sete;ah ditarik.

#### Screenshot Program:


#### Screenshot Output:

### 4. Studi Kasus Pengelolaan Data
Anda diberikan file CSV berisi data nilai ujian mahasiswa. Tugas Anda adalah menulis sebuah program yang:
1. Membaca file CSV dan menyimpan datanya ke dalam dictionary.
2. Menghitung rata-rata nilai tiap mahasiswa.
3. Menampilkan mahasiswa dengan nilai tertinggi dan terendah

#### Jawaban
```
import pandas as pd

def baca_data_csv(nama_file):
    return pd.read_csv(nama_file)

def hitung_rata_rata_nilai(data_mahasiswa):
    return data_mahasiswa['Nilai'].mean()

def mahasiswa_terbaik_dan_terburuk(data_mahasiswa):
    mahasiswa_terbaik = data_mahasiswa.loc[data_mahasiswa['Nilai'].idxmax()]
    mahasiswa_terburuk = data_mahasiswa.loc[data_mahasiswa['Nilai'].idxmin()]
    return mahasiswa_terbaik, mahasiswa_terburuk

def main():
    nama_file = 'siswa_nilai.csv'    
    data_mahasiswa = baca_data_csv(nama_file)
    rata_rata = hitung_rata_rata(data_mahasiswa)
    print(f"Rata-rata nilai: {rata_rata:.2f}")
    terbaik, terburuk = mahasiswa_terbaik_dan_terburuk(data_mahasiswa)
    print(f"\nMahasiswa dengan nilai tertinggi: {terbaik['Nama Siswa']} ({terbaik['Nilai']:.2f})")
    print(f"Mahasiswa dengan nilai terendah: {terburuk['Nama Siswa']} ({terburuk['Nilai']:.2f})")

if __name__ == "__main__":
    main()
```

**Code 1**
```
import pandas as pd
```
Kode diatas digunakan untuk mengimport library pandas yang merupakan alat untuk analisis data dan memanipulasi struktur data dalam python.

**Code 2**
```
def baca_data_csv(nama_file):
    return pd.read_csv(nama_file)
```
Mendefinisikan fungsi baca_data_csv untuk mengambil satu argumen yang merupakan nama file CSV yang akan dibaca.
pd.read_csv(nama_file) digunakan untuk membaca file CSV dan mengembalikan sebagai objek DataFrame pandas.

**Code 3**
```
def hitung_rata_rata_nilai(data_mahasiswa):
    return data_mahasiswa['Nilai'].mean()
```
Mendefinisikan Fungsi hitung_rata_rata_nilai untuk mengambil satu argumen yaitu data_mahasiswa yang merupakan DataFrame yang berisikan data mahasiswa. Lalu menghitung rata rata dengan mengakses kolon Nilai dari DataFrame dengan menggunakan metode .mean() untuk menghitung rata-rata nilai mahasiwa.

**Code 4**
```
def mahasiswa_terbaik_dan_terburuk(data_mahasiswa):
    mahasiswa_terbaik = data_mahasiswa.loc[data_mahasiswa['Nilai'].idxmax()]
    mahasiswa_terburuk = data_mahasiswa.loc[data_mahasiswa['Nilai'].idxmin()]
    return mahasiswa_terbaik, mahasiswa_terburuk
```
Mendefinisikan fungsi mahasiswa_terbaik_dan_terburuk yang mengambil satu argumen yaitu data_mahasiswa. Menggunakan metode idxmax() untuk menemukan indeks dari nilai maksimum dalam kolom Nilai. 
data_mahasiswa.loc[] digunakan untuk mengakses baris dari DataFrame untuk mendapatkan informasi lengkap mahasiswa terbaik.
Menggunakan idxmin() untuk menemukan indeks dari nilai minimum di kolom Nilai. Kode diatas mengembalikan dua hasil yaitu mahasiswa terbaik dan terburuk.

**Code 5**
```
def main():
    nama_file = 'siswa_nilai.csv'    
    data_mahasiswa = baca_data_csv(nama_file)
    rata_rata = hitung_rata_rata(data_mahasiswa)
    print(f"Rata-rata nilai: {rata_rata:.2f}")
    terbaik, terburuk = mahasiswa_terbaik_dan_terburuk(data_mahasiswa)
    print(f"\nMahasiswa dengan nilai tertinggi: {terbaik['Nama Siswa']} ({terbaik['Nilai']:.2f})")
    print(f"Mahasiswa dengan nilai terendah: {terburuk['Nama Siswa']} ({terburuk['Nilai']:.2f})")
```
Mendefinisikan fungsi main yang digunakan sebagai titik masuk untuk menjalankan program. Kode diatas digunakan untuk mendefinisikan nama file CSV yang akan dibaca, memanggil fungsi, dan membaca data dari file.
Selain untuk membaca data, kode diatas digunakan untuk menghitung rata-rata dengan memanggil fungsi untuk menghitung rata-rata nilai. 
Print digunakan untuk mencetak hasil rata-rata dengan dua angka di belakang koma. 
Mencari mahasiswa terbaik dan terburuk dengan memanggil fungsi untuk mendapatkan mahasiswa dengan nilai terbaik dan terburuk, lalu mencetak nama dan nilai mahasiswa dengan format yang sesuai

**Code 6**
```
if __name__ == "__main__":
    main()
```
Kode diatas digunakan untuk menjalankan program dengan memastikan bahwa main() hanya akan dipanggil jika skrip dieksekusi secara langsung.

#### Output
```
Rata-rata nilai: 72.00

Mahasiswa dengan nilai tertinggi: Siswa_7 (100.00)
Mahasiswa dengan nilai terendah: Siswa_5 (50.00)
```

#### Screenshot Program:


#### Screenshot Output:



### 5. Kombinasi Logika dan Kreativitas
Buatlah permainan sederhana menggunakan Python, di mana komputer akan memilih sebuah angka secara acak antara 1 hingga 100, dan pengguna harus menebak angka tersebut. Setiap tebakan yang salah akan memberikan petunjuk apakah angka yang ditebak lebih besar atau lebih kecil dari angka sebenarnya. Batasi jumlah percobaan menjadi 5 kali. Setelah permainan selesai, tampilkan apakah pemain menang atau kalah.

#### Jawaban
```
import random

def tebak_angka():
    
    angka_acak = random.randint(1, 100)
    jumlah_percobaan = 5
    
    print("Selamat datang di permainan Tebak Angka!")
    print("Saya sudah memilih angka diantara 1 hingga 100.")
    print(f"Anda memiliki {jumlah_percobaan} kali percobaan untuk menebak angka tersebut.")

    for percobaan in range(1, jumlah_percobaan + 1):
        try:
            tebakan = int(input(f"Tebakan ke-{percobaan}: "))
            
            if tebakan < 1 or tebakan > 100:
                print("Tebakan harus diantara 1 hingga 100. Silakan coba lagi.")
                continue
            
            if tebakan < angka_acak:
                print("Angka yang ditebak terlalu kecil.")
            elif tebakan > angka_acak:
                print("Angka yang ditebak terlalu besar.")
            else:
                print(f"Selamat! Anda berhasil menebak angka {angka_acak} dalam {percobaan} percobaan.")
                break
        except ValueError:
            print("Input tidak valid. Diharapkan untuk memasukkan angka.")

    else:
        print(f"Sayang sekali! Percobaan anda telah habis. Angka yang benar adalah {angka_acak}.")

if __name__ == "__main__":
    tebak_angka()
```

**Code 1**
```
import random
```
Kode diatas digunakan untuk mengimport library yaitu modul random yang digunakan untuk menghasilkan bilangan acak.

**Code 2**
```
def tebak_angka():
```
Mendefinisikan fungsi tebak_angka yang akan menjalankan logika permainannya.

**Code 3**
```
 angka_acak = random.randint(1, 100)
    jumlah_percobaan = 5
```
Kode diatas digunakan untuk menginisialisasi variabel angka_acak untuk menghasilkan angka acak antara 1 dan 100 menggunakan random.radint(1, 100)
dimana antara angka tersebut yang harus ditebak oleh pemain. jumlah_percobaan digunakan untuk menentukan banyaknya percobaan
yang diberikan kepada pemain sebanyak 5 kali percobaan.

**Code 4**
```
  print("Selamat datang di permainan Tebak Angka!")
    print("Saya sudah memilih angka diantara 1 hingga 100.")
    print(f"Anda memiliki {jumlah_percobaan} kali percobaan untuk menebak angka tersebut.")
```
Print digunakan untuk mencetak pesan sambutan dan informasi mengenain permainan kepada pemain.

**Code 5**
```
   for percobaan in range(1, jumlah_percobaan + 1):
```
Looping for digunakan untuk setiap percobaan dari 1 hingga 5 percobaan.

**Code 6**
```
try:
     tebakan = int(input(f"Tebakan ke-{percobaan}: "))
```
Menggunakan blok try untuk menangkap kemungkinan kesalahan saat konversi input.
Lalu mengambil input tebakan dari pengguna dan mencoba mengkonversi menjadi int. Lalu nilai akan disimpan dalam variabel tebakan.

**Code 7**
```
 if tebakan < 1 or tebakan > 100:
                print("Tebakan harus diantara 1 hingga 100. Silakan coba lagi.")
                continue
```
Validasi input akan memeriksa apakah tebakan berada dalam rentang 1 hingga 100.

**Code 8**
```
          if tebakan < angka_acak:
                print("Angka yang ditebak terlalu kecil.")
            elif tebakan > angka_acak:
                print("Angka yang ditebak terlalu besar.")
            else:
                print(f"Selamat! Anda berhasil menebak angka {angka_acak} dalam {percobaan} percobaan.")
                break
```
Jika tebakan kurang dari angka_acak maka akan mencetak pesan bahwa angka terlalu kecil, apabila tebalan lebih besar, maka akan mencetak bahwa angka terlalu besar. Jika tebakan benar maka akan mencetak pesan selamat dan keluar dari loop dengan break.

**Code 9**
```
except ValueError:
            print("Input tidak valid. Diharapkan untuk memasukkan angka.")
```
except digunakan untuk menangkap kesalahan ValueError yang mungkin terjadi.

**Code 10**
```
else:
        print(f"Sayang sekali! Percobaan anda telah habis. Angka yang benar adalah {angka_acak}.")
```
Jika loop selesai tanpa break maka akan mencetak pesan bahwa percobaan telah habis lalu menunjukkan angka yang benar.

**Code 11**
```
if __name__ == "__main__":
    tebak_angka()
```
Kode diatas digunakan untuk memastikan bahwa fungsi tebak_angka() akan dipanggil jika skrip dieksekusi secara langsung.


#### Output
```
Selamat datang di permainan Tebak Angka!
Saya sudah memilih angka diantara 1 hingga 100.
Anda memiliki 5 kali percobaan untuk menebak angka tersebut.
Tebakan ke-1:  40
Angka yang ditebak terlalu kecil.
Tebakan ke-2:  50
Angka yang ditebak terlalu kecil.
Tebakan ke-3:  70
Angka yang ditebak terlalu kecil.
Tebakan ke-4:  90
Angka yang ditebak terlalu kecil.
Tebakan ke-5:  99
Angka yang ditebak terlalu besar.
Sayang sekali! Percobaan anda telah habis. Angka yang benar adalah 93.
```

#### Screenshot Program:


#### Screenshot Output:

### 6. Rekursi yang Tidak Biasa
Buat fungsi rekursif yang menerima input bilangan bulat `n` dan menghasilkan urutan bilangan seperti berikut ini:
```
Input: n = 4
Output: 1, 1, 2, 6, 24
```
Fungsi ini harus menggunakan konsep rekursi untuk menghitung faktorial setiap angka hingga `n`.

#### Jawaban
```
def faktorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * faktorial(n - 1)

def urutan_faktorial(n):    
    if n < 1:
        return []
    
    return [faktorial(i) for i in range(n + 1)] 

if __name__ == "__main__":
    n = 4
    hasil = urutan_faktorial(n)
    
    print("Input: n =", n)
    print("Output:", ", ".join(map(str, hasil)))
```

**Code 1**
```
def faktorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * faktorial(n - 1)
```
Mendefinisikan fungsi faktorial(n) untuk menghitung nilai faktorial dari bilangan bulat n.
Jikan n lebih dari 1, maka fungsi akan mengalikan n dengan hasil dari faktorian(n - 1) sehingga menghitung faktorial secara rekrusif.

**Code 2**
```
def urutan_faktorial(n):    
    if n < 1:
        return []
    
    return [faktorial(i) for i in range(n + 1)] 
```
Mendefinisikan fungsi urutan_faktorial(n) yang menghasilkan daftar yang berisi nilai faktorial dari semua angka yaitu dari 0 hingga n. 
Jika n kurang dari 1 maka fungsi akan mengembalikan daftar kosong.

**Code 3**
```
if __name__ == "__main__":
    n = 4
    hasil = urutan_faktorial(n)
```
Kode diatas digunakan unruk memastikan bahwa kode di dalamnya hanya dieksekusi jika file ini dijalankan sebagai skrip utama. n diatur ke 4 yang merupakan input untuk fungsio urutan_faktporial.

**Code 4**
```
print("Input: n =", n)
    print("Output:", ", ".join(map(str, hasil)))
```
kode diatas digunakan untuk mencetak input n dan mencetak output dalam format.

#### Output
```
Input: n = 4
Output: 1, 1, 2, 6, 24
```
output diatas dinama input n yaitu 4 dengan outputnya 1, 1, 2, 6, 24.

#### Screenshot Program:


#### Screenshot Output:

### 7. Pemrograman dengan Algoritma Greedy
Buatlah program untuk memecahkan masalah "minimum coin change". Diberikan jumlah uang dan daftar nilai koin yang tersedia (misalnya, 1, 5, 10, 25), tentukan kombinasi minimum koin yang diperlukan untuk mencapai jumlah uang tersebut. Namun, program Anda harus bisa menangani koin-koin yang nilai dan jumlahnya ditentukan pengguna.

#### Jawaban
```
def minimum_coin_change(target, coin):
    dp = [float('inf')] * (target + 1)
    dp[0] = 0  

    for koin in coin:
        for amount in range(koin, target + 1):
            dp[amount] = min(dp[amount], dp[amount - koin] + 1)

    if dp[target] == float('inf'):
        return -1  

    return dp[target]

if __name__ == "__main__":    
    target = int(input("Masukkan jumlah target koin: "))
    coin_input = input("Masukkan koin yang tersedia (pisahkan menggunakan koma): ")
    coin = list(map(int, coin_input.split(',')))

    result = minimum_coin_change(target, coin)

    if result != -1:
        print(f"Kombinasi minimum koin yang diperlukan untuk mencapai {target} adalah: {result} koin.")
    else:
        print(f"Tidak ada kombinasi koin yang dapat mencapai {target}.")
```

**Code 1**
```
def minimum_coin_change(target, coin):
    dp = [float('inf')] * (target + 1)
    dp[0] = 0  
```
Mendefinisikan fungsi yang menerima dua parameter yaitu target.

**Code 2**
```
 for koin in coin:
        for amount in range(koin, target + 1):
            dp[amount] = min(dp[amount], dp[amount - koin] + 1)
```
Pengulangan melalui setiap koin di dalam daftar coin. Loop jumlah digunakan untuk setiap nilai koin, loop kedua pengulangan dari nilai koin sampai target.
Kode diatas menggunakan rumus untuk menghitung perhitungan minimum. Fungsi min digunakan untuk memperbarui dp[amount] dengan nilai terkecil.

**Code 3**
```
if dp[target] == float('inf'):
        return -1  

    return dp[target]
```
Jika dp[target] masih float('inf'} artinya tidak ada kombinasi koin yang mencapai target. jika mencapai target maka akan mengembalikan nilai dp[target].

**Code 4**
```
if __name__ == "__main__":    
    target = int(input("Masukkan jumlah target koin: "))
    coin_input = input("Masukkan koin yang tersedia (pisahkan menggunakan koma): ")
    coin = list(map(int, coin_input.split(',')))

    result = minimum_coin_change(target, coin)

    if result != -1:
        print(f"Kombinasi minimum koin yang diperlukan untuk mencapai {target} adalah: {result} koin.")
    else:
        print(f"Tidak ada kombinasi koin yang dapat mencapai {target}.")
```
Kode diatas digunakan untuk memastikan bahwa kode dieksekusi jika file ini dijalankan sebagai skrip utama. target diambil dari input pengguna dan dikoenversikan menjadi int.

### 8. Kombinasi String dan Manipulasi List
Buat sebuah program yang menerima string dari pengguna dan mengonversi string tersebut menjadi sebuah list berisi kata-kata terbalik. Misalnya:
```
Input: "Saya suka Python"
Output: ["ayaS", "akus", "nohtyP"]
```

#### Jawaban
```
def reverse_words(input_string):
    words = input_string.split()
    reversed_words = [word[::-1] for word in words]
    return reversed_words

if __name__ == "__main__":
    user_input = input("Input: ")
    result = reverse_words(user_input)
    
    print("Output:", result)
```

**Code 1**
```
def reverse_words(input_string):
    words = input_string.split()
    reversed_words = [word[::-1] for word in words]
    return reversed_words
```
Mendefinisikan fungsi yang digunakan untuk menerima satu parameter input_string yang berisikan kalimat yang akan diolah.

**Code 2**
```
if __name__ == "__main__":
    user_input = input("Input: ")
    result = reverse_words(user_input)
    
    print("Output:", result)
```
Kode diatas dijalankan jika file ini dieksekusi sebagai skrip utama. dengan input dari pengguna, dan pemanggilan fungsi.

#### Ouput
```
Input:  Saya Suka IPSD
Output: ['ayaS', 'akuS', 'DSPI']
```
user menginputkan kata saat program dijalankan.], lalu untuk outputnya mengonversi kata kata menjadi terbalik.

#### Screenshot Program:


#### Screenshot Output:


### 9. Konsep Class dan Object-Oriented Programming
Buat class bernama `Buku` yang memiliki atribut `judul`, `penulis`, dan `tahun_terbit`. Buat method dalam class untuk menampilkan informasi buku, serta method untuk menghitung usia buku berdasarkan tahun saat ini. Buatlah 3 objek dari class `Buku` dan tampilkan informasi serta usia masing-masing buku.

#### Jawaban
```
class Buku:
    def __init__(self, judul, penulis, tahun_terbit):
        self.judul = judul
        self.penulis = penulis
        self.tahun_terbit = tahun_terbit

    def tampilkan_informasi(self):
        print(f"Judul: {self.judul}")
        print(f"Penulis: {self.penulis}")
        print(f"Tahun Terbit: {self.tahun_terbit}")

    def usia_buku(self, tahun_sekarang):
        return tahun_sekarang - self.tahun_terbit

def input_buku():
    judul = input("Masukkan judul buku: ")
    penulis = input("Masukkan penulis buku: ")
    tahun_terbit = int(input("Masukkan tahun terbit buku: "))
    return Buku(judul, penulis, tahun_terbit)

list_buku = []
for i in range(1):
    print(f"\nInput untuk buku ke-{i + 1}:")
    buku = input_buku()
    list_buku.append(buku)

tahun_sekarang = 2024

print("\nInformasi Buku:")
for buku in list_buku:
    buku.tampilkan_informasi()
    usia = buku.usia_buku(tahun_sekarang)
    print(f"Usia Buku: {usia} tahun\n")
```

**Code 1**
```
class Buku:
    def __init__(self, judul, penulis, tahun_terbit):
        self.judul = judul
        self.penulis = penulis
        self.tahun_terbit = tahun_terbit
```
Mendefinisikan class Buku. metode init adalah kontruktor yang dipanggil saat membuat objek baru dari kelas ini dengan 3 atribut diinisialisasi yaitu self.judul, self.penulis, dan self. tahun_terbit.

**Code 2**
```
 def tampilkan_informasi(self):
        print(f"Judul: {self.judul}")
        print(f"Penulis: {self.penulis}")
        print(f"Tahun Terbit: {self.tahun_terbit}")
```
Metode tampilkan_informasi digunakan untuk mencetak infromasi tentang buku termasuk judul, penulis, dan tahun terbit.

**Code 3**
```
 def usia_buku(self, tahun_sekarang):
        return tahun_sekarang - self.tahun_terbit
```
Metode usia_buku digunakan untuk menghitung usia buku berdasarkan tahun terbit dan tahun saat ini.

**Code 4**
```
def input_buku():
    judul = input("Masukkan judul buku: ")
    penulis = input("Masukkan penulis buku: ")
    tahun_terbit = int(input("Masukkan tahun terbit buku: "))
    return Buku(judul, penulis, tahun_terbit)
```
Fungsi ini mengumpulkan informasi tentang buku dari pengguna. pengguna akan menginputkan judul buku, penulis, dan tahun terbit. Lalu mengembalikan objek Buku yang baru dibuat.

**Code 5**
```
list_buku = []
for i in range(1):
    print(f"\nInput untuk buku ke-{i + 1}:")
    buku = input_buku()
    list_buku.append(buku)
```
Inisialisasi list dengan nama list_buku untuk menyimpan objek Buku. Lalu melakukan satu perulangan atau looping.

**Code 6**
```
tahun_sekarang = 2024

print("\nInformasi Buku:")
for buku in list_buku:
    buku.tampilkan_informasi()
    usia = buku.usia_buku(tahun_sekarang)
    print(f"Usia Buku: {usia} tahun\n")
```
Kode diatas mendefinisikan tahun_sekarang sebagai 2024. Lalu melakukan loop untuk menampilkan informasi yaitu setiap objek Buku dalam list_buku, memanggil metode tampilkan_infromasi untuk detail buku dan menghitung serta menampilkan usia buku menggunakan metode usia_buku

#### Output
```
Input untuk buku ke-1:
Masukkan judul buku:  The Story We Can
Masukkan penulis buku:  Rizal Wahyu Pratama
Masukkan tahun terbit buku:  2020

Informasi Buku:
Judul: The Story We Can
Penulis: Rizal Wahyu Pratama
Tahun Terbit: 2020
Usia Buku: 4 tahun
```
User akan diminta untuk memasukkan judul buku, penulis buku, dan tahun terbit buku. setelah semua informasi sudah diinputkan oleh user maka akan menampilkan infromasi mengenai buku yang baru diinputkan dengan tambahan usia buku.

#### Screenshot Program:


#### Screenshot Output:

### 10. Algoritma dengan Persyaratan Logika Khusus
Buatlah program yang mengimplementasikan algoritma pencarian biner, namun dengan modifikasi: algoritma harus bisa mencari nilai di list yang hanya berisi angka genap, dan jika nilai yang dicari adalah angka ganjil, program harus menampilkan pesan bahwa nilai tersebut tidak bisa ditemukan.


#### Jawaban
```
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    
    while left <= right:
        mid = (left + right) // 2
        
        if arr[mid] == target:
            return mid 
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
            
    return -1  

def main():
    input_numbers = input("Masukkan daftar angka genap (pisahkan menggunakan spasi): ")
    even_numbers = list(map(int, input_numbers.split()))
    
    if not all(num % 2 == 0 for num in even_numbers):
        print("Semua angka yang dimasukkan harus genap.")
        return
    
    target = int(input("Masukkan angka yang ingin dicari: "))
    
    if target % 2 != 0:
        print("Nilai tidak dapat ditemukan karena merupakan angka ganjil.")
    else:
        index = binary_search(even_numbers, target)
        if index != -1:
            print(f"Nilai {target} berada di indeks {index}.")
        else:
            print(f"Nilai {target} tidak berada dalam daftar.")

if __name__ == "__main__":
    main()
```

**Code 1**
```
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    
    while left <= right:
        mid = (left + right) // 2
        
        if arr[mid] == target:
            return mid 
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
            
    return -1
```
Fungsi binary_search digunakan untuk mencari target dalam array untuk menggunakan metode pencarian biner. 
Menginisialisasi dua variabel left dan right yang menunjukkan batas kiri dan kanan dari daftar. 
Menggunakan loop whilw untuk terus mencari selama batas kiri tidak melebihi batas kanan. Lalu menghitung indeks tengah dari rentang yang sedang dicari

**Code 2**
```
def main():
    input_numbers = input("Masukkan daftar angka genap (pisahkan menggunakan spasi): ")
    even_numbers = list(map(int, input_numbers.split()))
    
    if not all(num % 2 == 0 for num in even_numbers):
        print("Semua angka yang dimasukkan harus genap.")
        return
    
    target = int(input("Masukkan angka yang ingin dicari: "))
    
    if target % 2 != 0:
        print("Nilai tidak dapat ditemukan karena merupakan angka ganjil.")
    else:
        index = binary_search(even_numbers, target)
        if index != -1:
            print(f"Nilai {target} berada di indeks {index}.")
        else:
            print(f"Nilai {target} tidak berada dalam daftar.")
```
Fungsi main digunakan untuk mentaur interaksi dengan pengguna untuk menerima input dan memanggil fungsi pencarian biner. program akan meminta pengguna untuk memasukan daftar angka genap dan memisahkannya dengan spasi.

**Code 3**
```
if __name__ == "__main__":
    main()
```
Kode ini memastikan bahwa fungsi main() hanya dipanggil ketika file dijalankan sebagai program utama.



## Kesimpulan
Ringkasan dan interpretasi pandangan kalia dari hasil praktikum dan pembelajaran yang didapat[1].

## Referensi
[1] I. Holm, Narrator, and J. Fullerton-Smith, Producer, How to Build a Human [DVD]. London: BBC; 2002.
