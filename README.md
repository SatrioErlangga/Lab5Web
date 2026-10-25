Lab5Web - Praktikum 5: JavaScript Dasar dan Manipulasi HTML

Data Mahasiswa

Nama              : Satrio Erlangga

NIM                : 312510006

Kelas             : I253C

Program Studi: Teknik Informatika

Mata Kuliah   : Pemrograman Web

Dosen            : Agung Nugroho, S.Kom., M.Kom.

Langkah Kerja Praktikum

Latihan 1: Menampilkan Output

Langkah awal pengenalan JavaScript untuk memanipulasi teks pada elemen HTML berdasarkan ID dan menampilkan output melalui Console browser.

Kode JavaScript:

document.getElementById("pesan").textContent = "Hello World";
console.log("Hello World");


Hasil Tampilan Halaman:

Latihan 2: Alert dan Prompt

Penggunaan fungsi dialog bawaan browser. prompt() digunakan untuk meminta input pengguna, sedangkan alert() digunakan untuk menampilkan pesan pop-up sederhana.

Kode JavaScript:

const namaPengguna = prompt("Masukkan nama Anda:", "");
if (namaPengguna && namaPengguna.trim() !== "") {
    alert("Halo, " + namaPengguna + "!");
    document.getElementById("pesan").textContent = "Selamat datang, " + namaPengguna + ".";
} else {
    alert("Nama belum diisi.");
}


Hasil Tampilan:

Latihan 3: Function dan Operasi Aritmetika

Membuat sebuah function yang menerima dua bilangan sebagai parameter untuk dihitung menggunakan berbagai operator aritmetika, kemudian hasilnya dicetak di Console.

Kode JavaScript:

function operasiDasar(a, b) {
    console.log("Penjumlahan:", a + b);
    console.log("Pengurangan:", a - b);
    console.log("Perkalian:", a * b);
    console.log("Pembagian:", b !== 0 ? a / b : "Tidak dapat dibagi nol");
    console.log("Modulus:", a % b);
}
operasiDasar(9, 4);


Hasil Tampilan Console:

Latihan 4: Seleksi Kondisi (if-else)

Penerapan logika percabangan menggunakan if-else untuk mengevaluasi apakah nilai yang dimasukkan (melalui prompt) memenuhi syarat kelulusan (>= 60) atau tidak.

Kode JavaScript:

const inputNilai = prompt("Masukkan nilai (0-100):");
const nilaiMahasiswa = Number(inputNilai);

if (inputNilai === null || inputNilai.trim() === "" || Number.isNaN(nilaiMahasiswa) || nilaiMahasiswa < 0 || nilaiMahasiswa > 100) {
    alert("Input nilai tidak valid.");
} else if (nilaiMahasiswa >= 60) {
    alert("Lulus");
} else {
    alert("Belum lulus");
}


Hasil Tampilan:

Latihan 5: Seleksi Kondisi (switch)

Penggunaan struktur percabangan switch sebagai alternatif dari if-else untuk mengevaluasi suatu nilai yang memiliki banyak kasus/pilihan spesifik.

Kode JavaScript:

const inputPilihan = prompt("Masukkan angka 1-5:");
switch (inputPilihan) {
    case "1": alert("Bilangan satu"); break;
    case "2": alert("Bilangan dua"); break;
    case "3": alert("Bilangan tiga"); break;
    case "4": alert("Bilangan empat"); break;
    case "5": alert("Bilangan lima"); break;
    default: alert("Pilihan tidak tersedia");
}


Hasil Tampilan:

Latihan 6: Form Bilangan Genap atau Ganjil

Mengintegrasikan input form HTML dengan JavaScript untuk mendeteksi apakah angka yang dimasukkan pengguna merupakan bilangan genap (habis dibagi dua) atau ganjil.

Kode JavaScript:

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


Hasil Tampilan:

Latihan 7: Mengubah Warna Halaman

Memanipulasi CSS/styling pada Document Object Model (DOM) HTML melalui fungsi interaktif berupa tombol.

Kode JavaScript:

function ubahWarnaLatar(warna) {
    document.body.style.backgroundColor = warna;
}


Hasil Tampilan:

Latihan 8: DOM dan Checkbox Menu Makanan

Memanfaatkan Event Listener pada elemen Checkbox. Sistem akan mendeteksi setiap perubahan status centang dan menjumlahkan harga menu secara otomatis.

Kode JavaScript:

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


Hasil Tampilan:

Mini Project: Kalkulator Nilai Mahasiswa

Membuat kalkulator nilai yang menerima bobot Nilai Tugas (30%), UTS (30%), dan UAS (40%). Program menghitung nilai akhir, memberikan predikat huruf, dan status kelulusan.

Kode Perhitungan JavaScript:

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


Hasil Pengujian Skenario:

Skenario 1 (Lulus, Predikat A):

Skenario 2 (Lulus, Predikat C):

Skenario 3 (Belum Lulus, Predikat D):

Eksperimen Mandiri

Bagian ini memuat hasil eksperimen pengembangan dari modul JavaScript dasar.

1. Operasi Aritmetika Melalui Prompt

Mengubah Latihan 3 agar input angka dinamis diambil menggunakan fungsi prompt() kemudian dikonversi menjadi tipe data angka/number.

Hasil Tampilan:

8. Function Cek Genap

Membuat sebuah fungsi cekGenap(angka) yang me-return boolean true apabila bilangan genap dan false jika bilangan ganjil.

Hasil Tampilan:

7. Perulangan Tabel Perkalian 7

Penerapan sintaks perulangan for (let i = 1; i <= 10; i++) untuk memproduksi daftar/tabel perkalian angka 7 secara otomatis.

Hasil Tampilan:

9. Validasi Form Tidak Boleh Kosong

Penerapan event onsubmit dan event.preventDefault() pada formulir. Jika nama hanya berisi spasi atau kosong, maka sistem memblokir pengiriman data dan menampilkan peringatan.

Kondisi Form Kosong (Error):

Kondisi Form Valid (Sukses):

10. Modifikasi Menu Makanan

Mengembangkan Latihan 8 dengan menambahkan lebih banyak opsi menu makanan dan variasi harganya ke dalam checkbox.

Hasil Tampilan:

11. Menyembunyikan & Menampilkan Elemen

Demonstrasi manipulasi struktur HTML menggunakan JavaScript DOM (classList.toggle) untuk mengubah visibilitas CSS dari sebuah kotak div tanpa harus memuat ulang halaman.

Tampilan Sebelum (Muncul):

Tampilan Sesudah (Disembunyikan):

Repository dikelola untuk pemenuhan tugas Praktikum Pemrograman Web Universitas Pelita Bangsa.

## H. Pertanyaan dan Tugas

**1. Jelaskan perbedaan console.log(), alert(), prompt(), dan textContent/innerHTML.**
*   `console.log()`: Berfungsi untuk mencetak pesan atau output data ke tab Console pada *developer tools* di browser, umumnya digunakan oleh *developer* untuk keperluan *debugging*.
*   `alert()`: Berfungsi untuk memunculkan kotak dialog (pop-up) peringatan sederhana di layar browser yang hanya berisi pesan dan tombol "OK".
*   `prompt()`: Berfungsi memunculkan kotak dialog yang meminta pengguna untuk memasukkan teks/inputan, dan mengembalikan nilai berupa *string*.
*   `textContent` / `innerHTML`: Merupakan properti DOM. `textContent` digunakan untuk menyisipkan atau mengubah teks biasa secara aman, sedangkan `innerHTML` dapat memproses dan menyisipkan tag HTML di dalamnya.

**2. Apa perbedaan let dan const? Berikan contoh.**
*   `let`: Digunakan untuk mendeklarasikan variabel yang nilainya bisa diubah (*reassign*) di kemudian hari.
    *Contoh:* `let umur = 20; umur = 21;` (Sah)
*   `const`: Digunakan untuk mendeklarasikan variabel konstanta yang nilainya tetap dan tidak bisa diubah setelah diinisialisasi pertama kali.
    *Contoh:* `const phi = 3.14;` (Tidak bisa diubah menjadi 3.15)

**3. Apa perbedaan operator == dan === ?**
*   `==` (*Loose Equality*): Membandingkan dua nilai **hanya berdasarkan isinya**, tanpa memedulikan tipe datanya (melakukan konversi tipe secara otomatis). *Contoh:* `5 == "5"` akan menghasilkan `true`.
*   `===` (*Strict Equality*): Membandingkan dua nilai secara ketat berdasarkan **isi dan tipe datanya**. *Contoh:* `5 === "5"` akan menghasilkan `false` karena tipe datanya berbeda (Number vs String).

**4. Jelaskan fungsi if-else dan switch. Kapan masing-masing dapat digunakan?**
*   `if-else`: Berfungsi untuk menyeleksi kondisi berdasarkan logika logis (rentang nilai, lebih besar/kecil, kondisi kompleks). Digunakan saat ada evaluasi *boolean* (*true/false*).
*   `switch`: Berfungsi untuk memilih satu tindakan dari daftar kemungkinan nilai yang pasti (*exact match*). Sangat cocok digunakan untuk menggantikan `if-else` yang terlalu panjang saat mengevaluasi satu variabel dengan pilihan spesifik (misalnya: menu 1-5, hari Senin-Minggu).

**5. Apa fungsi parameter dan return dalam function?**
*   **Parameter:** Variabel yang diletakkan di dalam tanda kurung pada definisi fungsi untuk menampung data masukan (*input*) yang dikirim dari luar fungsi.
*   **Return:** Instruksi untuk menghentikan eksekusi fungsi sekaligus mengembalikan nilai akhir (*output*) ke tempat fungsi tersebut dipanggil.

**6. Bagaimana JavaScript memilih elemen HTML menggunakan document.getElementById()?**
JavaScript akan memindai keseluruhan struktur HTML (Document Object Model) dan mencari satu elemen yang memiliki atribut `id` persis seperti yang disebutkan di dalam kurung. Karena `id` bersifat unik dalam satu halaman, metode ini dijamin mengembalikan tepat satu elemen spesifik untuk dimanipulasi.

**7. Buat script untuk memvalidasi form agar nama tidak kosong dan nilai berada pada rentang 0-100.**
Berikut adalah script validasinya:
```javascript
function validasiForm(event) {
    event.preventDefault(); // Mencegah form memuat ulang halaman
    
    // Mengambil nilai dari elemen HTML (diasumsikan ID form-nya inputNama dan inputNilai)
    let nama = document.getElementById("inputNama").value;
    let nilai = Number(document.getElementById("inputNilai").value);
    
    // Validasi Nama
    if (nama.trim() === "") {
        alert("Peringatan: Nama tidak boleh kosong!");
        return false;
    }
    
    // Validasi Nilai (Rentang 0 - 100)
    if (isNaN(nilai) || nilai < 0 || nilai > 100) {
        alert("Peringatan: Nilai harus berada pada rentang 0 - 100!");
        return false;
    }
    
    // Jika lolos validasi
    alert("Berhasil! Data " + nama + " dengan nilai " + nilai + " valid.");
    return true;
}
