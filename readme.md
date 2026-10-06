# Tugas Individu - Desain Web

Nama: M Nadzril Ilham K  
NPM: [Masukkan NPM Anda di sini]

---

## Isi Tugas

Membangun ulang halaman profil portofolio menjadi dua *file* terpisah (`index.html` dan `style.css`). Halaman ini dibangun menggunakan konsep CSS eksternal, *Box Model*, penerapan minimal dua *class reusable*, CSS Flexbox untuk *layout*, serta *responsive design* menggunakan *media query* di bawah 768px.

---

## File yang Digunakan

| File | Keterangan |
| :--- | :--- |
| `index.html` | *Source code* utama struktur halaman portofolio |
| `style.css` | *File* CSS eksternal untuk mengatur tata letak dan desain visual |
| `profil.png` | Foto profil yang digunakan pada bagian Hero (disimpan di folder `images/`) |
| `README.md` | Dokumen penjelasan tugas, laporan perubahan, masalah, dan solusi |

---

## Source Code

### HTML
*File* HTML menggunakan struktur semantik dasar seperti `<header>`, `<section>`, `<nav>`, dan `<footer>`. Di dalamnya memuat berbagai informasi mulai dari navigasi, *hero section* (profil), tentang saya, project, layanan jasa, dan kontak.

### CSS
*File* `style.css` digunakan untuk mengatur tampilan visual *website*, termasuk tipografi, warna *background*, ukuran gambar, jarak antar elemen, hingga transisi saat kursor diarahkan ke tombol atau kartu (*hover*). CSS dibuat terpisah dan dihubungkan ke HTML melalui tag `<link>`.

---

## Box Model

Konsep *Box Model* diterapkan secara menyeluruh pada dokumen ini untuk mengatur tata letak elemen.

| No | Property | Contoh di CSS |
| :-: | :--- | :--- |
| 1 | `width` | `width: 90%;` (pada `.container`) |
| 2 | `padding` | `padding: 70px 0;` (pada `.section`) |
| 3 | `margin` | `margin: auto;` (pada `.container`) |
| 4 | `border` | `border: 6px solid #ff4d00;` (pada `.hero-image img`) |
| 5 | `box-sizing` | `box-sizing: border-box;` (pada `*`) |

---

## Reusable Class

Terdapat beberapa *class* yang dibuat agar dapat digunakan kembali di berbagai bagian HTML untuk meminimalkan penulisan kode yang berulang:

**`.container`**  
Digunakan untuk membatasi lebar maksimal konten (1100px) dan memposisikannya di tengah layar (`margin: auto`). *Class* ini dipakai di dalam `<header>`, `<section>`, dan bagian lainnya.

**`.section`**  
Digunakan untuk memberikan jarak vertikal (padding atas dan bawah sebesar 70px) yang konsisten pada setiap blok konten seperti Tentang, Project, Jasa, dan Kontak.

**`.project-card`**  
Digunakan secara berulang untuk membungkus konten gambar, judul, dan deskripsi baik pada bagian "Project Saya" maupun "Layanan Jasa Saya" agar memiliki gaya bayangan (*box-shadow*), sudut melengkung, dan efek *hover* yang seragam.

---

## Flexbox

Flexbox digunakan untuk mengatur posisi antar elemen agar sejajar secara horizontal, terutama pada bagian Header, Hero, dan susunan kartu.

Contohnya pada bagian konten Hero:

```css
.hero-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 50px;
}
```
Dengan Flexbox, teks profil dan foto dapat ditampilkan sejajar dan memiliki jarak (*gap*) yang rapi pada tampilan *desktop*.

---

## Responsive Design

*Website* ini menggunakan *media query* untuk memastikan tampilan tetap rapi saat diakses melalui perangkat berlayar kecil.

```css
@media (max-width: 768px) {
    ...
}
```
*Media query* dengan maksimal lebar 768px digunakan untuk merespons ukuran layar tablet dan *smartphone*. Pada layar di bawah ukuran tersebut, navigasi yang sejajar diubah susunannya, bagian Hero diubah menjadi format kolom (`flex-direction: column-reverse`), dan lebar `.project-card` disesuaikan hingga mencapai 100% dari lebar kontainer agar mudah dibaca.

---

## Mini Style Guide

**Font**  
Font Utama: Arial, sans-serif

**Warna**  
*   Primary/Accent: `#ff4d00` (Oranye)
*   Hover/Secondary: `#ffd166` (Kuning/Oranye Terang)
*   Background Utama: `#f5f7fa`
*   Background Sekunder (Kontak): `#e9eef5`
*   Heading Text: `#654000` (Cokelat Gelap)
*   Body Text: `#333333` & `#555555`

**Line Height**  
*   Umum (Body): 1.6

---

## Screenshot

### Desktop
*(Tambahkan gambar screenshot tampilan desktop di sini)*
`![Tampilan Desktop](link-gambar-desktop.png)`

### Mobile
*(Tambahkan gambar screenshot tampilan mobile di sini)*
`![Tampilan Mobile](link-gambar-mobile.png)`

---

## Ringkasan dan Kesimpulan

Pada tugas individu ini, saya telah berhasil membangun ulang halaman profil portofolio menjadi dua *file* terpisah, yaitu `index.html` untuk mengatur struktur konten dan `style.css` untuk mengatur presentasi visualnya. Pemisahan ini membuat kode menjadi jauh lebih terstruktur, bersih, dan mudah dikelola. Dalam proses pengembangannya, saya menerapkan konsep *Box Model* secara menyeluruh. Hal ini diawali dengan menggunakan deklarasi `box-sizing: border-box` pada *universal selector* agar perhitungan dimensi elemen lebih konsisten dan tidak terganggu oleh penambahan *padding* maupun *border*. Saya juga membuat beberapa *reusable class* (kelas yang dapat digunakan ulang) seperti `.container` untuk membatasi lebar konten, `.section` untuk memberikan jarak (*padding*) vertikal yang konsisten antar bagian, serta `.project-card` yang mempercepat proses *styling* daftar proyek dan layanan jasa.

Salah satu masalah utama yang saya hadapi saat pengerjaan adalah mengatur agar teks profil dan gambar dapat sejajar rapi, serta susunan kartu proyek tidak berantakan di layar besar. Solusi yang saya terapkan adalah menggunakan CSS Flexbox, yang sangat memudahkan proses penyelarasan dan distribusi ruang antar elemen. Masalah lainnya muncul ketika *website* dibuka di layar yang kecil; susunan elemen menjadi tumpang tindih. Untuk mengatasinya, saya mengimplementasikan *Responsive Web Design* menggunakan *Media Query* dengan *breakpoint* maksimal `768px`. Melalui teknik ini, tata letak elemen yang awalnya berbaris horizontal berhasil saya susun ulang menjadi vertikal (*kolom*), sehingga halaman portofolio tetap fungsional, rapi, dan mudah dibaca di perangkat *mobile*.