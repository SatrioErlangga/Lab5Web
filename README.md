# Lab5Web - Praktikum 5: JavaScript Dasar dan Manipulasi HTML

<div align="center">
  <p>Repositori ini memuat hasil pengerjaan <b>Praktikum 5: JavaScript Dasar</b> untuk mata kuliah Pemrograman Web.</p>
  <p>Fokus utama praktikum ini adalah memahami sintaks dasar JavaScript, manipulasi DOM, interaksi form, serta logika percabangan dan perulangan.</p>
</div>

<hr>

## Data Mahasiswa

> **Nama** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: Satrio Erlangga  
> **NIM** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: 312510006  
> **Kelas** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: I253C  
> **Program Studi**: Teknik Informatika  
> **Mata Kuliah** &nbsp;&nbsp;: Pemrograman Web  
> **Dosen** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: Agung Nugroho, S.Kom., M.Kom.

<hr>

## Langkah Kerja Praktikum

### Latihan 1: Menampilkan Output
Langkah awal pengenalan JavaScript untuk memanipulasi teks pada elemen HTML berdasarkan ID dan menampilkan output melalui Console browser.

**Kode JavaScript:**
```javascript
document.getElementById("pesan").textContent = "Hello World";
console.log("Hello World");
```

**Hasil Tampilan Halaman & Console:**
<br>
![Hasil Halaman](ss%201.png)
<br>
![Hasil Console](ss%203.png)


### Latihan 2: Alert dan Prompt
Penggunaan fungsi dialog bawaan browser. `prompt()` digunakan untuk meminta input pengguna, sedangkan `alert()` digunakan untuk menampilkan pesan *pop-up*.

**Kode JavaScript:**
```javascript
const namaPengguna = prompt("Masukkan nama Anda:", "");
if (namaPengguna && namaPengguna.trim() !== "") {
    alert("Halo, " + namaPengguna + "!");
    document.getElementById("pesan").textContent = "Selamat datang, " + namaPengguna + ".";
} else {
    alert("Nama belum diisi.");
}
```

**Hasil Tampilan:**
<br>
![Prompt Nama](ss%202,1.png)
<br>
![Alert Halo](ss2,2.png)
<br>
![Hasil Teks Halaman](ss2,3.png)


### Latihan 3: Function dan Operasi Aritmetika
Membuat sebuah *function* yang menerima dua bilangan sebagai parameter untuk dihitung menggunakan berbagai operator aritmetika, lalu dicetak di Console.

**Kode JavaScript:**
```javascript
function operasiDasar(a, b) {
    console.log("Penjumlahan:", a + b);
    console.log("Pengurangan:", a - b);
    console.log("Perkalian:", a * b);
    console.log("Pembagian:", b !== 0 ? a / b : "Tidak dapat dibagi nol");
    console.log("Modulus:", a % b);
}
operasiDasar(9, 4);
```

**Hasil Tampilan Console:**
<br>
![Hasil Aritmetika](ss%203.png)


### Latihan 4: Seleksi Kondisi (if-else)
Penerapan logika percabangan menggunakan `if-else` untuk mengevaluasi apakah nilai yang dimasukkan memenuhi syarat kelulusan (>= 60) atau tidak.

**Kode JavaScript:**
```javascript
const inputNilai = prompt("Masukkan nilai (0-100):");
const nilaiMahasiswa = Number(inputNilai);

if (inputNilai === null || inputNilai.trim() === "" || Number.isNaN(nilaiMahasiswa) || nilaiMahasiswa < 0 || nilaiMahasiswa > 100) {
    alert("Input nilai tidak valid.");
} else if (nilaiMahasiswa >= 60) {
    alert("Lulus");
} else {
    alert("Belum lulus");
}
```

**Hasil Tampilan:**
<br>
![Prompt Nilai](ss%204.png)
<br>
![Alert Lulus](ss%204,1.png)


### Latihan 5: Seleksi Kondisi (switch)
Penggunaan struktur percabangan `switch` untuk mengevaluasi suatu nilai yang memiliki banyak kasus spesifik secara efisien.

**Kode JavaScript:**
```javascript
const inputPilihan = prompt("Masukkan angka 1-5:");
switch (inputPilihan) {
    case "1": alert("Bilangan satu"); break;
    case "2": alert("Bilangan dua"); break;
    case "3": alert("Bilangan tiga"); break;
    case "4": alert("Bilangan empat"); break;
    case "5": alert("Bilangan lima"); break;
    default: alert("Pilihan tidak tersedia");
}
```

**Hasil Tampilan:**
<br>
![Prompt Switch](ss%205.png)
<br>
![Alert Switch](ss5,1.png)


### Latihan 6: Form Bilangan Genap atau Ganjil
Mengintegrasikan input form HTML dengan JavaScript untuk mendeteksi apakah angka yang dimasukkan pengguna merupakan bilangan genap atau ganjil.

**Kode JavaScript:**
```javascript
function cekBilangan() {
    const input = document.getElementById("bilangan").value;
    const angka = Number(input);
    const hasil = document.getElementById("hasilBilangan");

    if (input.trim() === "" || !Number.isInteger(angka)) {
        hasil.textContent = "Masukkan bilangan bulat yang valid.";
    } else if (angka % 2 == 0) {
        hasil.textContent = "Bilangan genap";
    } else {
        hasil.textContent = "Bilangan ganjil";
    }
}
```

**Hasil Tampilan:**
<br>
![Form Genap Ganjil](ss%206.png)


### Latihan 7: Mengubah Warna Halaman
Memanipulasi CSS pada Document Object Model (DOM) HTML melalui fungsi interaktif berupa klik tombol.

**Kode JavaScript:**
```javascript
function ubahWarnaLatar(warna) {
    document.body.style.backgroundColor = warna;
}
```

**Hasil Tampilan:**
<br>
![Warna Latar](ss%207.png)


### Latihan 8: DOM dan Checkbox Menu Makanan
Memanfaatkan *Event Listener* pada elemen Checkbox untuk mendeteksi perubahan status centang dan menjumlahkan total harga otomatis.

**Kode JavaScript:**
```javascript
const daftarMenu = document.querySelectorAll(".menu");
daftarMenu.forEach((item) => {
    item.addEventListener("change", hitungTotal);
});

function hitungTotal() {
    let total = 0;
    daftarMenu.forEach((item) => {
        if (item.checked) total += Number(item.value);
    });
    document.getElementById("total").textContent = total.toLocaleString("id-ID");
}
```

**Hasil Tampilan:**
<br>
![Checkbox Makanan](ss%208.png)

<hr>

## Mini Project: Kalkulator Nilai Mahasiswa

Membuat kalkulator nilai yang menerima bobot Nilai Tugas (30%), UTS (30%), dan UAS (40%). Program menghitung nilai akhir, memberikan predikat huruf, dan status kelulusan.

**Kode JavaScript (Perhitungan):**
```javascript
function hitungNilaiAkhir(tugas, uts, uas) {
    return (tugas * 0.30) + (uts * 0.30) + (uas * 0.40);
}

function tentukanPredikat(nilai) {
    if (nilai >= 85) return "A";
    if (nilai >= 75) return "B";
    if (nilai >= 60) return "C";
    if (nilai >= 50) return "D";
    return "E";
}
```

**Hasil Pengujian 3 Skenario:**
<br>
![Skenario 1 - A](ss%20mini%20project.png)
<br>
![Skenario 2 - C](ss%20mini%20projectt.png)
<br>
![Skenario 3 - D](ss%20mini%20projecttt.png)

<hr>

## Eksperimen Mandiri

Bagian ini memuat modifikasi dan pengembangan logika sesuai tantangan Modul.

### 1. Operasi Aritmetika Melalui Prompt
Mengubah fungsi dasar (Latihan 3) agar dapat menerima input dinamis langsung dari `prompt()`.

**Hasil Tampilan:**
<br>
![Eksperimen 1](ss%201%20eks.png)


### 8. Function Cek Genap
Membuat fungsi `cekGenap(angka)` yang mengembalikan nilai Boolean (True/False).

**Hasil Tampilan:**
<br>
![Eksperimen 8](ss%208%20eks.png)


### 7. Perulangan Tabel Perkalian 7
Menggunakan metode perulangan `for (let i = 1; i <= 10; i++)` untuk membangun tabel perkalian 7.

**Hasil Tampilan:**
<br>
![Eksperimen 7](ss%207%20eks.png)


### 9. Validasi Form Tidak Boleh Kosong
Mencegah *submit* form kosong menggunakan `event.preventDefault()` dan deteksi spasi kosong.

**Hasil Tampilan (Error & Sukses):**
<br>
![Eksperimen 9 Error](ss%209%20x%20eks.png)
<br>
![Eksperimen 9 Sukses](ss%209%20eks.png)


### 10. Modifikasi Menu Makanan
Menambah lebih banyak opsi menu dan logika harga dari Latihan 8.

**Hasil Tampilan:**
<br>
![Eksperimen 10](ss%2010.png)


### 11. Menyembunyikan dan Menampilkan Elemen
Memanipulasi kelas CSS (classList.toggle) untuk menyembunyikan atau memunculkan elemen tanpa memuat ulang halaman.

**Hasil Tampilan (Sebelum dan Sesudah Disembunyikan):**
<br>
![Eksperimen 11 Muncul](ss%2011%20before%20eks.png)
<br>
![Eksperimen 11 Hilang](ss%2011%20after%20eks.png)

<hr>

## H. Pertanyaan dan Tugas

**1. Jelaskan perbedaan console.log(), alert(), prompt(), dan textContent/innerHTML.**
*   `console.log()`: Mencetak pesan/output ke tab Console pada *developer tools* browser (digunakan untuk *debugging*).
*   `alert()`: Memunculkan kotak dialog (pop-up) peringatan di layar yang hanya berisi pesan dan tombol "OK".
*   `prompt()`: Memunculkan kotak dialog yang meminta pengguna untuk menginputkan teks, dan me-return nilai berupa *string*.
*   `textContent` / `innerHTML`: Properti DOM; `textContent` menyisipkan teks biasa secara aman, sedangkan `innerHTML` dapat memproses dan menyisipkan tag struktur HTML.

**2. Apa perbedaan let dan const? Berikan contoh.**
*   `let`: Digunakan untuk variabel yang nilainya bisa diubah (*reassign*) nanti. 
    *Contoh:* `let umur = 20; umur = 21;`
*   `const`: Digunakan untuk konstanta yang nilainya tetap dan tidak bisa diubah setelah pertama kali diisi. 
    *Contoh:* `const phi = 3.14;`

**3. Apa perbedaan operator == dan === ?**
*   `==` (*Loose Equality*): Membandingkan dua nilai **hanya berdasarkan isinya**, dan otomatis menyamakan tipe datanya. (Contoh: `5 == "5"` adalah `true`).
*   `===` (*Strict Equality*): Membandingkan secara ketat berdasarkan **isi dan tipe datanya**. (Contoh: `5 === "5"` adalah `false`).

**4. Jelaskan fungsi if-else dan switch. Kapan masing-masing dapat digunakan?**
*   `if-else`: Untuk menyeleksi kondisi berdasarkan logika komparasi/rentang nilai (*boolean*). Cocok untuk kondisi yang kompleks.
*   `switch`: Memilih satu tindakan dari opsi nilai yang sudah pasti (*exact match*). Cocok untuk menggantikan `if-else` bertumpuk saat mengevaluasi satu variabel spesifik (misal: menu pilihan 1-5).

**5. Apa fungsi parameter dan return dalam function?**
*   **Parameter:** Variabel di dalam tanda kurung fungsi untuk menampung data masukan (*input*) dari luar.
*   **Return:** Instruksi untuk menghentikan fungsi sekaligus mengembalikan/menghasilkan nilai akhir (*output*) ke tempat fungsi itu dipanggil.

**6. Bagaimana JavaScript memilih elemen HTML menggunakan document.getElementById()?**
Sistem memindai Document Object Model (DOM) HTML untuk mencari tepat satu elemen yang memiliki atribut `id` yang spesifik, lalu mengembalikannya agar dapat diubah atau dimanipulasi dengan skrip.

**7. Buat script untuk memvalidasi form agar nama tidak kosong dan nilai berada pada rentang 0-100.**
```javascript
function validasiForm(event) {
    event.preventDefault(); 
    
    let nama = document.getElementById("inputNama").value;
    let nilai = Number(document.getElementById("inputNilai").value);
    
    if (nama.trim() === "") {
        alert("Peringatan: Nama tidak boleh kosong!");
        return false;
    }
    
    if (isNaN(nilai) || nilai < 0 || nilai > 100) {
        alert("Peringatan: Nilai harus berada pada rentang 0 - 100!");
        return false;
    }
    
    alert("Berhasil! Data valid.");
    return true;
}
```
