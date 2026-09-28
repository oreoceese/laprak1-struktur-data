# <h1 align="center">Laporan Praktikum Modul 1 - Codeblocks IDE & Pengenalan Bahasa C++ (Bagian Pertama)</h1>
<p align="center">Zuhra Hanani Ramadhina - 109082500143</p>

## Dasar Teori
C++ adalah bahasa pemrograman tingkat menengah yang dikembangkan sebagai pengembangan dari bahasa C dengan tambahan dukungan paradigma pemrograman berorientasi objek[1]. Bahasa ini bersifat statically typed, artinya setiap variabel harus dideklarasikan tipe datanya terlebih dahulu sebelum digunakan, berbeda dengan bahasa dynamically typed yang tipe datanya bisa berubah secara otomatis saat program berjalan. C++ banyak digunakan dalam pengembangan software, sistem operasi, hingga game, karena performanya yang mendekati bahasa tingkat rendah namun tetap relatif mudah dipahami. Dalam pemrograman C++, terdapat beberapa konsep dasar yang perlu dipahami sebelum menyusun program yang lebih kompleks, di antaranya tipe data, variabel, operator, serta struktur kendali seperti percabangan dan perulangan.

### A. Tipe Data dan Variabel

C++ memiliki beberapa tipe data dasar seperti `int` untuk bilangan bulat, `float` dan `double` untuk bilangan pecahan, serta `char` untuk karakter. Variabel harus dideklarasikan terlebih dahulu sebelum digunakan, dengan format `tipe_data nama_variabel;`.

1. Tipe data bilangan bulat (`int`, `long`)
2. Tipe data bilangan pecahan (`float`, `double`)
3. Tipe data karakter (`char`)

### B. Operasi Aritmatika pada Tipe Data Float

Operasi aritmatika dasar (penjumlahan, pengurangan, perkalian, pembagian) dapat diterapkan langsung pada variabel bertipe `float` di C++.

1. Variabel bertipe float
2. Input nilai menggunakan `cin`
3. Operasi aritmatika dan output menggunakan `cout`

## Unguided 

### 1. Program Operasi Aritmatika pada Bilangan Float

```C++
#include <iostream>
using namespace std;

int main() {
    float a, b;
    cout << "Masukkan bilangan pertama: ";
    cin >> a;
    cout << "Masukkan bilangan kedua: ";
    cin >> b;

    cout << "Penjumlahan: " << a + b << endl;
    cout << "Pengurangan: " << a - b << endl;
    cout << "Perkalian  : " << a * b << endl;
    cout << "Pembagian  : " << a / b << endl;

    return 0;
}
```
### Output Unguided 1 :

![Screenshot Output Unguided 1](https://github.com/oreoceese/laprak1-struktur-data/blob/main/1-soal1.png)

Program menerima dua input bertipe float melalui cin, lalu langsung menjalankan operasi penjumlahan, pengurangan, perkalian, dan pembagian menggunakan operator aritmatika dasar (+, -, *, /), dan menampilkan tiap hasilnya lewat cout.

### 2. Program Konversi Angka menjadi Tulisan

```C++
#include <iostream>
#include <string>
using namespace std;

string satuan[] = {"nol","satu","dua","tiga","empat","lima","enam","tujuh","delapan","sembilan"};
string belasan[] = {"sepuluh","sebelas","dua belas","tiga belas","empat belas","lima belas",
                     "enam belas","tujuh belas","delapan belas","sembilan belas"};
string puluhan[] = {"","","dua puluh","tiga puluh","empat puluh","lima puluh",
                     "enam puluh","tujuh puluh","delapan puluh","sembilan puluh"};

string angkaKeTulisan(int n) {
    if (n == 100) return "seratus";
    if (n < 10) return satuan[n];
    if (n < 20) return belasan[n - 10];
    if (n % 10 == 0) return puluhan[n / 10];
    return puluhan[n / 10] + " " + satuan[n % 10];
}

int main() {
    int n;
    cout << "Masukkan angka (0-100): ";
    cin >> n;
    cout << n << " : " << angkaKeTulisan(n) << endl;
    return 0;
}
```
### Output Unguided 2 :

![Screenshot Output Unguided 2](https://github.com/oreoceese/laprak1-struktur-data/blob/main/1-soal2.png)

Program menggunakan tiga array kata (satuan, belasan, puluhan) untuk mengonversi angka menjadi tulisan. Fungsi angkaKeTulisan() mengecek rentang nilai input (kurang dari 10, 10-19, kelipatan puluhan, atau gabungan puluhan+satuan) untuk menentukan kombinasi kata yang tepat.

### 3. Program Mirror Pattern Menggunakan Perulangan

```C++
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "input: ";
    cin >> n;
    cout << "output:" << endl;

    for (int i = n; i >= 1; i--) {
        for (int s = 0; s < (n - i) * 2; s++) cout << " ";
        for (int j = i; j >= 1; j--) cout << j << " ";
        cout << "* ";
        for (int j = 1; j <= i; j++) {
            cout << j;
            if (j != i) cout << " ";
        }
        cout << endl;
    }
    return 0;
}
```
### Output Unguided 3 :

![Screenshot Output Unguided 3](https://github.com/oreoceese/laprak1-struktur-data/blob/main/1-soal3.png)

Program menggunakan perulangan for bersarang untuk mencetak pola mirror. Tiap baris terdiri dari angka menurun, tanda * sebagai sumbu, lalu angka menaik kembali, dengan indentasi spasi yang bertambah di tiap barisnya untuk membentuk efek cermin.

## Kesimpulan
Berdasarkan praktikum yang telah dilakukan, dapat disimpulkan bahwa pemrograman C++ memiliki struktur dasar yang terdiri atas header, fungsi main, dan statement yang harus ditulis sesuai aturan sintaks. Penguasaan tipe data dasar seperti int, float, dan char sangat penting karena menentukan jenis operasi yang dapat dilakukan terhadap suatu variabel. Selain itu, melalui latihan unguided, mahasiswa dilatih untuk menerapkan konsep input-output, percabangan, dan perulangan dalam menyelesaikan permasalahan pemrograman sederhana, seperti operasi aritmatika, konversi angka menjadi tulisan, dan pembentukan pola (mirror pattern).

## Referensi
[1] Budiman., Alamsyah, Nur., Al Rasyid, Arief. (2023). *Buku Ajar Pemrograman C++*. Bandung: Unibi Press.
<br>[2] Indahyanti, Uce., Rahmawati, Yunianita. (2020). *Buku Ajar Algoritma dan Pemrograman dalam Bahasa C++*. Sidoarjo: UMSIDA Press.
<br>[3] Harimurti, Rina. (2019). *Pemrograman C++*. Surabaya: Universitas Negeri Surabaya.
<br>[4] Basiroh. (2017). *Dasar Pemrograman C++*. Cilacap: Ihya Media.
