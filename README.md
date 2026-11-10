# UTS Pemrograman Web — Website Profil Pribadi (Tema Hijau)

**Nama:** ASH SHIDDIQ AL MAY  
**NIM:** 312510072  
**Program Studi:** Teknik Informatika  
**Kampus:** Universitas Pelita Bangsa  
**Mata Kuliah:** Pemrograman Web  
**Dosen Pengampu:** Sufajar Butsianto, S.Kom., M.Kom.

---

## Deskripsi

Website profil pribadi (personal portfolio) interaktif dan responsif yang dibuat dengan **HTML5**, **CSS3**, dan **JavaScript dasar**. Seluruh tampilan menggunakan **tema hijau** yang konsisten: hijau sebagai warna utama, latar putih, dan teks abu-abu kehijauan.

Website memuat biografi, data profil, riwayat pendidikan, riwayat pengalaman kerja, keahlian (unordered & ordered list), multimedia perkenalan (audio & video), serta formulir kontak dengan validasi.

## Preview

![Tampilan lengkap website] <img width="1280" height="5327" alt="09-fullpage" src="https://github.com/user-attachments/assets/9e2b9a7a-e92c-46ee-bc81-4c9135bfac12" />

---

---

## 1. Header, Navigasi, & Hero Panel

### Hasil

[Header, navigasi, dan hero panel] <img width="1280" height="786" alt="01-hero" src="https://github.com/user-attachments/assets/d8b17ffb-1527-4887-8f98-82a9314e9988" />


### Penjelasan

Bagian atas website memakai elemen semantik `header` dan `nav`. Header dibuat **sticky** agar tetap terlihat saat halaman digulir. Tombol menu (`.menu-button`) hanya muncul di layar kecil dan akan membuka menu vertikal. Hero panel berisi perkenalan singkat, dua tombol aksi, informasi NIM/kampus/domisili, serta foto profil berbentuk kartu.

```html
<header class="site-header">
  <div class="container header__inner">
    <a class="logo" href="#beranda" aria-label="Kembali ke beranda">
      <span class="logo__mark" aria-hidden="true">AS</span>
      <span class="logo__text">Web Ash Shiddiq Al May</span>
    </a>

    <button class="menu-button" type="button" aria-label="Buka menu"
            aria-expanded="false" aria-controls="menu">
      <span></span><span></span><span></span>
    </button>

    <nav class="menu" id="menu" aria-label="Navigasi utama">
      <a href="#tentang">Tentang</a>
      <a href="#pendidikan">Pendidikan</a>
      <a href="#pengalaman">Pengalaman</a>
      <a href="#keahlian">Keahlian</a>
      <a href="#multimedia">Multimedia</a>
      <a class="menu__cta" href="#kontak">Kontak</a>
    </nav>
  </div>
</header>

<main id="konten">
  <section class="hero" id="beranda" aria-labelledby="judul-utama">
    <div class="container hero__grid">
      <div class="hero__content">
        <p class="badge">Mahasiswa Teknik Informatika</p>
        <h1 id="judul-utama">Halo, saya <span>ASH SHIDDIQ AL MAY</span></h1>
        <p class="hero__role">Universitas Pelita Bangsa &middot; NIM 312510072</p>
        <p class="hero__text">Saya tertarik pada pengembangan web dan desain antarmuka...</p>

        <div class="hero__actions">
          <a class="button button--primary" href="#proyek">Lihat pengalaman</a>
          <a class="button button--outline" href="#kontak">Hubungi saya</a>
        </div>
      </div>

      <figure class="hero__photo">
        <div class="photo-card">
          <img src="images/profil.jpg" alt="Foto profil Ash Shiddiq Al May" width="720" height="1061">
          <figcaption class="photo-card__caption">
            <strong>ASH SHIDDIQ AL MAY</strong>
            <span>NIM 312510072</span>
          </figcaption>
        </div>
      </figure>
    </div>
  </section>
</main>
```

```css
.site-header {
  position: sticky;
  top: 0;
  z-index: 20;
  border-bottom: 1px solid var(--border);
  background: rgba(255, 255, 255, 0.94);
  backdrop-filter: blur(12px);
}

.logo__mark {
  display: grid;
  width: 40px;
  height: 40px;
  place-items: center;
  border-radius: 10px;
  background: var(--primary);
  color: #ffffff;
}

.menu {
  display: flex;
  align-items: center;
  gap: 22px;
  font-size: 0.88rem;
  font-weight: 600;
}

.menu a:hover {
  color: var(--primary);
}

.hero {
  padding: 76px 0 84px;
  background: linear-gradient(180deg, #e6f6ea 0%, var(--background) 100%);
}

.hero__grid {
  display: grid;
  grid-template-columns: minmax(0, 1.15fr) minmax(280px, 0.85fr);
  gap: 64px;
  align-items: center;
}

.hero h1 span {
  color: var(--primary);
}
```

---

## 2. Biografi & Profil Utama

### Hasil

[Bagian biografi dan profil] <img width="1280" height="1129" alt="02-tentang" src="https://github.com/user-attachments/assets/6e180c7b-a598-4011-9412-04d6dfd889e0" />


### Penjelasan

Section `#tentang` memakai `article` untuk teks biografi dan `aside` untuk kartu data singkat. Keduanya disusun dua kolom dengan **CSS Grid**. Di bawahnya ada tiga kartu sorotan (Fokus, Pendidikan, Pengalaman) dan sebuah kutipan. Daftar sifat memakai `ul` berisi chip berwarna hijau muda.

```html
<section class="section" id="tentang" aria-labelledby="judul-tentang">
  <div class="container">
    <div class="section__heading">
      <h2 id="judul-tentang">Biografi &amp; Profil</h2>
      <p>Mengenal saya lebih dekat: latar belakang, minat, dan hal yang sedang saya bangun.</p>
    </div>

    <div class="about">
      <article class="about__text">
        <h3>Siapa saya</h3>
        <p class="about__lead">Saya ASH SHIDDIQ AL MAY, mahasiswa Teknik Informatika...</p>
        <p>Saya menempuh studi di Universitas Pelita Bangsa dengan NIM 312510072...</p>
        <ul class="about__chips" aria-label="Sifat dan minat">
          <li>Teliti</li>
          <li>Mau belajar</li>
          <li>Kerja sama tim</li>
          <li>Kreatif</li>
        </ul>
      </article>

      <aside class="about__card" aria-labelledby="judul-data">
        <h3 id="judul-data">Data singkat</h3>
        <dl>
          <div><dt>Nama lengkap</dt><dd>ASH SHIDDIQ AL MAY</dd></div>
          <div><dt>NIM</dt><dd>312510072</dd></div>
          <div><dt>Program studi</dt><dd>Teknik Informatika</dd></div>
          <div><dt>Kampus</dt><dd>Universitas Pelita Bangsa</dd></div>
        </dl>
      </aside>
    </div>
  </div>
</section>
```

```css
.about {
  display: grid;
  grid-template-columns: minmax(0, 1.25fr) minmax(280px, 0.75fr);
  gap: 44px;
  align-items: start;
}

.about__chips {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  list-style: none;
}

.about__chips li {
  padding: 6px 12px;
  border: 1px solid #86efac;
  border-radius: 999px;
  background: var(--primary-soft);
  color: var(--primary-dark);
  font-size: 0.78rem;
  font-weight: 700;
}

.highlight-card {
  border: 1px solid var(--border);
  border-top: 4px solid var(--primary);
  border-radius: var(--radius);
  background: var(--surface);
}
```

---

## 3. Tabel Riwayat Pendidikan

### Hasil

[Tabel riwayat pendidikan] <img width="1280" height="578" alt="03-pendidikan" src="https://github.com/user-attachments/assets/6ecf258c-1a0b-47e9-85fe-4df82952c7c5" />


### Penjelasan

Riwayat pendidikan ditampilkan dalam elemen `table` semantik dengan `caption`, `thead`, `tbody`, dan `th scope="col"`. Tabel dibungkus `.table-wrap` yang memiliki `overflow-x: auto`, sehingga tetap bisa digulir horizontal di layar kecil. Baris genap diberi warna hijau sangat muda agar mudah dibaca.

```html
<div class="table-wrap">
  <table>
    <caption>Riwayat pendidikan Ash Shiddiq Al May</caption>
    <thead>
      <tr>
        <th scope="col">Tahun</th>
        <th scope="col">Jenjang</th>
        <th scope="col">Institusi</th>
        <th scope="col">Jurusan / Program</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>2024 &ndash; Sekarang</td>
        <td>Perguruan Tinggi</td>
        <td>Universitas Pelita Bangsa</td>
        <td>S1 Teknik Informatika</td>
      </tr>
      <tr>
        <td>2021 &ndash; 2023</td>
        <td>SMA</td>
        <td>SMAN 107 Jakarta Timur</td>
        <td>Jurusan IPA</td>
      </tr>
      <tr>
        <td>2017 &ndash; 2020</td>
        <td>SMP</td>
        <td>SMPN 04 Babelan</td>
        <td>&ndash;</td>
      </tr>
      <tr>
        <td>2011 &ndash; 2017</td>
        <td>SD</td>
        <td>SDN Bahagia 06</td>
        <td>&ndash;</td>
      </tr>
    </tbody>
  </table>
</div>
```

```css
.table-wrap {
  overflow-x: auto;
  border: 1px solid var(--border);
  border-radius: var(--radius);
  background: var(--surface);
  box-shadow: var(--shadow);
}

th,
td {
  padding: 14px 20px;
  border-bottom: 1px solid var(--border);
  text-align: left;
  vertical-align: top;
}

th {
  background: #e8f7ec;
  color: var(--primary-dark);
  font-size: 0.78rem;
  font-weight: 700;
  text-transform: uppercase;
}

tbody tr:nth-child(even) {
  background: #f4faf6;
}
```

---

## 4. Tabel Riwayat Pengalaman Kerja

### Hasil

[Tabel riwayat pengalaman kerja] <img width="1280" height="698" alt="04-pengalaman" src="https://github.com/user-attachments/assets/9bfd2bf6-46c6-493c-b4d7-935598ecf106" />


### Penjelasan

Pengalaman kerja dan proyek mandiri memakai struktur tabel yang sama. Kolomnya berisi tahun, posisi/kegiatan, tempat, dan deskripsi. Tabel diberi `id="proyek"` agar tombol **Lihat pengalaman** pada hero dapat langsung menuju bagian ini.

```html
<table id="proyek">
  <caption>Riwayat pengalaman kerja dan proyek Ash Shiddiq Al May</caption>
  <thead>
    <tr>
      <th scope="col">Tahun</th>
      <th scope="col">Posisi / Kegiatan</th>
      <th scope="col">Tempat</th>
      <th scope="col">Deskripsi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2026 &ndash; Sekarang</td>
      <td>Karyawan</td>
      <td>PT Dankos Farma</td>
      <td>Bekerja di PT Dankos Farma sejak 2026 hingga sekarang.</td>
    </tr>
    <tr>
      <td>2025 &ndash; 2026</td>
      <td>Karyawan</td>
      <td>PT Astra Honda Motor</td>
      <td>Bekerja di PT Astra Honda Motor selama periode 2025&ndash;2026.</td>
    </tr>
    <tr>
      <td>2025</td>
      <td>Pembuatan Web Sederhana</td>
      <td>Proyek Mandiri (VS Code)</td>
      <td>Membuat website sederhana menggunakan HTML, CSS, dan JavaScript.</td>
    </tr>
  </tbody>
</table>
```

---

## 5. Riwayat Keahlian

### Hasil

[Riwayat keahlian] <img width="1280" height="528" alt="05-keahlian" src="https://github.com/user-attachments/assets/38251416-c829-4a76-8591-8d6faec1a8be" />


### Penjelasan

Keahlian ditampilkan dalam dua kartu. Kartu pertama memakai **unordered list** (`ul`) berisi tag kemampuan. Kartu kedua memakai **ordered list** (`ol`) berisi urutan proses belajar. Penanda nomor pada `ol` diwarnai hijau memakai `::marker`.

```html
<div class="skills">
  <article class="skill-card">
    <h3>Keahlian (Unordered List)</h3>
    <ul class="tags">
      <li>HTML5</li>
      <li>CSS3</li>
      <li>JavaScript dasar</li>
      <li>Desain responsif</li>
      <li>Desain poster</li>
    </ul>
  </article>

  <article class="skill-card">
    <h3>Alat &amp; Urutan Belajar (Ordered List)</h3>
    <ol class="steps">
      <li>Menulis struktur halaman dengan HTML.</li>
      <li>Mengatur tampilan dan layout memakai CSS.</li>
      <li>Menambah interaksi dengan JavaScript.</li>
      <li>Mendesain poster dan aset visual di Canva.</li>
      <li>Merapikan kode dan menguji responsivitas.</li>
    </ol>
  </article>
</div>
```

```css
.skills {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 20px;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  list-style: none;
}

.tags li {
  padding: 6px 11px;
  border: 1px solid var(--border);
  border-radius: 999px;
  background: var(--background);
  color: var(--muted);
  font-size: 0.78rem;
  font-weight: 600;
}

.steps {
  display: grid;
  gap: 10px;
  padding-left: 22px;
  color: var(--muted);
  font-size: 0.92rem;
}

.steps li::marker {
  color: var(--primary);
  font-weight: 700;
}
```

---

## 6. Multimedia Perkenalan

### Hasil

[Bagian multimedia] <img width="1280" height="637" alt="06-multimedia" src="https://github.com/user-attachments/assets/6a7fb77e-1080-4615-9e1b-1f5b9b51b5e6" />


### Penjelasan

Section `#multimedia` memuat `audio` dan `video` dengan atribut `controls`. Video tampil langsung tanpa poster dan diberi latar hijau, sedangkan kartu video memakai gradasi hijau muda. Keduanya responsif karena `width: 100%`.

```html
<div class="media-grid">
  <figure class="media-card">
    <figcaption>Audio perkenalan</figcaption>
    <audio controls preload="metadata">
      <source src="media/audio.mp3" type="audio/mpeg">
      Browser Anda tidak mendukung elemen audio.
    </audio>
  </figure>

  <figure class="media-card media-card--video">
    <figcaption>Video perkenalan</figcaption>
    <video controls preload="metadata" width="640" height="360">
      <source src="media/video.mp4" type="video/mp4">
      Browser Anda tidak mendukung elemen video.
    </video>
  </figure>
</div>
```

```css
.media-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 20px;
  align-items: start;
}

.media-card video {
  width: 100%;
  height: auto;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  border-radius: 10px;
  background: #15803d;
}

.media-card--video {
  border-color: #86efac;
  background: linear-gradient(160deg, #ecfdf5 0%, #d1fae5 55%, #bbf7d0 100%);
}

.media-card--video figcaption {
  color: #166534;
}
```

---

## 7. Form Kontak & Validasi

### Hasil — tampilan normal

[Form kontak] <img width="1280" height="901" alt="07-kontak" src="https://github.com/user-attachments/assets/533aa504-b7f9-41d4-b0cf-17037894f651" />


### Hasil — saat validasi gagal

[Validasi form kontak] <img width="1280" height="925" alt="07-kontak-validasi" src="https://github.com/user-attachments/assets/54d25a71-6d09-4cb4-aaf8-cdbbd18e1623" />



### Penjelasan

Form berisi field **Nama**, **Email**, dan **Pesan**. Validasi dilakukan dua lapis:

1. **HTML5**: `required`, `minlength`, dan `type="email"`.
2. **JavaScript**: memeriksa panjang nama (minimal 3), format email, dan panjang pesan (minimal 10), menampilkan pesan error di tiap field, menandai `aria-invalid`, dan memfokuskan field pertama yang salah.

Saat data valid, form menampilkan pesan sukses lalu direset. Setiap input yang diperbaiki langsung membersihkan pesan error.

```html
<form class="contact-form" id="contactForm" novalidate>
  <div class="field">
    <label for="nama">Nama</label>
    <input id="nama" name="nama" type="text" required minlength="3"
           placeholder="Nama lengkap" autocomplete="name" aria-describedby="error-nama">
    <small class="field__error" id="error-nama" data-error-for="nama"></small>
  </div>

  <div class="field">
    <label for="email">Email</label>
    <input id="email" name="email" type="email" required
           placeholder="nama@email.com" autocomplete="email" aria-describedby="error-email">
    <small class="field__error" id="error-email" data-error-for="email"></small>
  </div>

  <div class="field">
    <label for="pesan">Pesan</label>
    <textarea id="pesan" name="pesan" rows="4" required minlength="10"
              placeholder="Tulis pesan Anda di sini..." aria-describedby="error-pesan"></textarea>
    <small class="field__error" id="error-pesan" data-error-for="pesan"></small>
  </div>

  <button class="button button--primary" type="submit">Kirim pesan</button>
  <p class="form-status" id="formStatus" role="status" aria-live="polite"></p>
</form>
```

```js
const form = document.getElementById("contactForm");
const status = document.getElementById("formStatus");

const setFieldInvalid = (field, message) => {
  const input = form.elements[field];
  document.querySelector(`[data-error-for="${field}"]`).textContent = message;
  input.setAttribute("aria-invalid", "true");
  input.closest(".field").classList.add("field--invalid");
};

form.addEventListener("submit", (event) => {
  event.preventDefault();
  const nama = form.nama.value.trim();
  const email = form.email.value.trim();
  const pesan = form.pesan.value.trim();
  const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  let firstInvalid = null;

  if (nama.length < 3) {
    setFieldInvalid("nama", "Nama minimal 3 karakter.");
    firstInvalid = firstInvalid || "nama";
  }
  if (!emailPattern.test(email)) {
    setFieldInvalid("email", "Masukkan alamat email yang valid.");
    firstInvalid = firstInvalid || "email";
  }
  if (pesan.length < 10) {
    setFieldInvalid("pesan", "Pesan minimal 10 karakter.");
    firstInvalid = firstInvalid || "pesan";
  }

  if (firstInvalid) {
    status.textContent = "Periksa kembali data yang belum sesuai.";
    form.elements[firstInvalid].focus();
    return;
  }

  status.textContent = "Terima kasih, " + nama + "! Pesan Anda berhasil disimulasikan terkirim.";
  status.classList.add("form-status--success");
  form.reset();
});
```

```css
.field input:focus,
.field textarea:focus {
  border-color: var(--primary);
  outline: 3px solid rgba(22, 163, 74, 0.20);
  outline-offset: 1px;
}

.field--invalid input,
.field--invalid textarea,
.field input[aria-invalid="true"],
.field textarea[aria-invalid="true"] {
  border-color: #dc2626;
  background: #fef2f2;
}

.form-status--success {
  color: #15803d;
}
```

---

## 8. Footer & Menu Mobile

### Hasil

[Footer] 

<img width="1280" height="74" alt="08-footer" src="https://github.com/user-attachments/assets/578718a6-fa01-461b-acf1-da75df0e50f6" />


[Menu mobile terbuka] 

<img width="390" height="380" alt="13-mobile-menu" src="https://github.com/user-attachments/assets/fe969f87-bb11-4fbb-9122-7f79956cb231" />


### Penjelasan

Footer berisi hak cipta dengan tahun otomatis dari JavaScript dan tautan kembali ke atas. Pada layar kecil (≤ 820px), tombol burger tampil dan menu berubah menjadi dropdown vertikal. JavaScript menambahkan class `is-open` serta memperbarui `aria-expanded` agar mudah diakses.

```html
<footer class="footer">
  <div class="container footer__inner">
    <p>&copy; <span id="tahun"></span> ASH SHIDDIQ AL MAY. Dibuat dengan HTML5, CSS3, dan JavaScript.</p>
    <a href="#beranda">Kembali ke atas</a>
  </div>
</footer>
```

```js
const menuButton = document.querySelector(".menu-button");
const menu = document.getElementById("menu");

menuButton.addEventListener("click", () => {
  const isOpen = menu.classList.toggle("is-open");
  menuButton.setAttribute("aria-expanded", String(isOpen));
});

menu.querySelectorAll("a").forEach((link) => {
  link.addEventListener("click", () => {
    menu.classList.remove("is-open");
    menuButton.setAttribute("aria-expanded", "false");
  });
});

document.getElementById("tahun").textContent = new Date().getFullYear();
```

```css
@media (max-width: 820px) {
  .menu-button {
    display: flex;
  }

  .menu {
    position: absolute;
    top: calc(100% + 10px);
    right: 0;
    left: 0;
    display: none;
    flex-direction: column;
    padding: 8px;
    border: 1px solid var(--border);
    border-radius: 14px;
    background: var(--surface);
    box-shadow: var(--shadow);
  }

  .menu.is-open {
    display: flex;
  }
}
```

---

## Tema Hijau

### Penjelasan

Warna dasar diatur lewat **CSS variables** di `:root`, sehingga seluruh komponen (tombol, navigasi, badge, tabel, kartu, footer) otomatis memakai hijau. Nilai biru yang sebelumnya ditulis langsung juga diganti menjadi hijau.

```css
:root {
  --background: #f2f8f4;
  --surface: #ffffff;
  --text: #16281d;
  --muted: #5c7263;
  --primary: #16a34a;
  --primary-dark: #14532d;
  --primary-soft: #dcfce7;
  --border: #d6e8db;
  --shadow: 0 18px 45px rgba(20, 83, 45, 0.10);
  --radius: 16px;
  --container: 1100px;
  --font-heading: Georgia, "Times New Roman", serif;
  --font-body: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
```

| Peran | Warna |
|-------|-------|
| Latar halaman | `#f2f8f4` |
| Hijau utama | `#16a34a` |
| Hijau gelap (kontak & teks aksen) | `#14532d` |
| Hijau muda (badge/chip) | `#dcfce7` |
| Border | `#d6e8db` |

---

## Responsif

Tampilan diuji pada lebar **1280px** (desktop) dan **390px** (mobile). Tidak ada scroll horizontal pada kedua ukuran.

### Desktop (1280px)

[Tampilan desktop] 
<img width="1280" height="5327" alt="09-fullpage" src="https://github.com/user-attachments/assets/c5cc0dad-b235-4785-8088-87a64697724e" />


### Mobile (390px)

[Hero mobile] 
<img width="390" height="1252" alt="10-mobile-hero" src="https://github.com/user-attachments/assets/75dc71d2-bd98-425c-91e0-d7a1e193c9c5" />


[Multimedia mobile] 
<img width="390" height="662" alt="11-mobile-multimedia" src="https://github.com/user-attachments/assets/8c1bbda7-3620-46cc-99fd-5fdbcc7dc276" />


[Kontak mobile] 
<img width="390" height="1199" alt="12-mobile-kontak" src="https://github.com/user-attachments/assets/424156c8-9eff-4050-8004-e8c80e177007" />


```css
@media (max-width: 900px) {
  .hero__grid,
  .about,
  .contact {
    grid-template-columns: minmax(0, 1fr);
  }

  .highlights,
  .skills,
  .media-grid {
    grid-template-columns: minmax(0, 1fr);
  }
}
```

---


