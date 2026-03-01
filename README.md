# 🌐 Portfolio Website - Ahmad Dani

Website portofolio pribadi berbasis **HTML, CSS, Bootstrap 5, dan Vue JS** yang menampilkan informasi profil, keahlian, pengalaman, dan sertifikat dalam bentuk website statis yang responsif.

---
## 👨‍💻 Developed By

**Ahmad Dani**   
2409116074



## 📌 Deskripsi Project

Project ini merupakan website portofolio statis yang dibuat untuk memenuhi tugas Praktikum Pemrograman Berbasis Website (PBW).  

Website ini memiliki beberapa section utama yaitu:

- Home (Hero Section)
- About Me
- Skills (Progress Bar)
- Experience
- Certificates
- Navbar dan Footer

Website dibuat dengan tampilan modern, responsif, dan memanfaatkan Vue JS untuk membuat data dinamis meskipun tetap bersifat statis.

---

# 🏠 Tampilan Setiap Section / Fitur

## 1️⃣ Home (Hero Section)

<img width="2966" height="1704" alt="Macbook-Air-127 0 0 1" src="https://github.com/user-attachments/assets/7402849a-c70d-4c12-be5e-ab5854752fc3" />


Menampilkan:
- Nama
- Role / Profesi
- Foto profil

Menggunakan:
- Bootstrap Grid System (row, col-md)
- Flexbox (d-flex align-items-center)
- Vue Interpolation `{{ name }}` dan `{{ role }}`

Kode:
```html
<!-- Hero -->
      <header id="home" class="hero-section d-flex align-items-center">
        <div class="container text-center">
          <div class="row">
            <div
              class="col-md-4 text-center img-profil bg-dark rounded-4 shadow-lg"
            >
              <img
                src="assets/img/ahmddani.png"
                class="img-fluid"
                alt="Profile Photo"
              />
            </div>
            <div class="col-md-8 align-content-center">
              <h1 class="hero-title">Hi, I'm <span>{{ name }}</span></h1>
              <p class="hero-subtitle">{{ role }}</p>
            </div>
          </div>
        </div>
      </header>
```

Penjelasan Kode:
Section ini merupakan bagian pembuka website yang menampilkan foto profil, nama, dan role/profesi.
Layout dibuat menggunakan Bootstrap Grid System dengan dua kolom (foto dan teks) agar responsif di berbagai ukuran layar.
Class ```d-flex``` dan ```align-items-center``` digunakan untuk membuat konten berada di tengah secara vertikal.
Data nama dan role ditampilkan secara dinamis menggunakan Vue JS interpolation ```({{ nama }})``` sehingga mudah diubah melalui data pada script Vue.

---

## 2️⃣ About Me

<img width="2966" height="1704" alt="Macbook-Air-127 0 0 1 (1)" src="https://github.com/user-attachments/assets/b9ff8784-414d-4d1b-a3b3-42c78ec14cc5" />


Berisi:
- Deskripsi diri
- Minat di bidang Web Development, UI/UX, dan Networking

Menggunakan:
- Bootstrap container & grid
- Typography utilities
- Vue interpolation untuk nama dan role

Kode:
```html
<!-- About -->
      <section id="about" class="py-5 bg-light">
        <div class="container">
          <h2 class="text-center mb-5 fw-semibold">About Me</h2>

          <!-- DESKRIPSI DIRI -->
          <div class="row justify-content-center mb-5">
            <div class="col-md-8 text-center">
              <p class="lead">
                Hello! I'm <strong>{{name}}</strong>, an enthusiastic
                <strong>{{role}}</strong> who is passionate about web
                development, UI/UX design, and computer networking. I enjoy
                building responsive, modern, and user-friendly websites while
                also understanding network infrastructure, system connectivity,
                and basic network configuration. I continuously strive to
                improve my technical, analytical, and problem-solving skills.
              </p>
            </div>
          </div>

          <!-- SKILLS & EXPERIENCE -->
          <div class="row">
            <!-- Skills -->
            <div class="col-md-6 mb-4">
              <div class="p-4 bg-white rounded-4 shadow-sm h-100">
                <h4 class="mb-4">My Skills</h4>

                <div v-for="skill in skills" :key="skill.name" class="mb-3">
                  <label class="fw-semibold">{{ skill.name }}</label>
                  <div class="progress">
                    <div
                      class="progress-bar progress-bar-striped progress-bar-animated"
                      :class="skill.color"
                      :style="{ width: skill.level + '%' }"
                    >
                      {{ skill.level }}%
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <!-- Experience -->
            <div class="col-md-6">
              <div class="p-4 bg-white rounded-4 shadow-sm h-100">
                <h4 class="mb-4">Experience</h4>

                <div
                  v-for="exp in experiences"
                  :key="exp.title"
                  class="experience-item mb-4"
                >
                  <h5>{{ exp.title }}</h5>
                  <small class="text-muted">
                    {{ exp.company }} | {{ exp.year }}
                  </small>
                  <p class="mt-2 mb-0">{{ exp.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
```

Penjelasan Kode:

Section About Me menampilkan deskripsi diri, daftar skills, dan pengalaman secara terstruktur dan responsif.

Bagian ini menggunakan elemen ```<section>``` dengan ```id="about"``` untuk navigasi dari navbar, serta class Bootstrap seperti ```py-5``` dan ```bg-light``` untuk memberikan jarak dan warna latar.

🔹 Deskripsi Diri

Menampilkan perkenalan singkat menggunakan class lead agar teks lebih menonjol.
Data nama dan role ditampilkan secara dinamis menggunakan Vue interpolation ```({{ }})```.

🔹 Skills (Progress Bar)

Daftar skill ditampilkan menggunakan Bootstrap Progress Component dan di-generate secara dinamis dengan Vue ```v-for```.
Lebar progress bar diatur menggunakan binding ```:style```, sedangkan warna diatur menggunakan ```:class```.

🔹 Experience

Bagian pengalaman dibuat menggunakan Vue ```v-for``` untuk menampilkan data dari array experiences.
Informasi seperti jabatan, instansi, tahun, dan deskripsi ditampilkan secara dinamis menggunakan interpolation.

Section ini menggabungkan HTML semantik, Bootstrap Grid System, dan Vue JS untuk menghasilkan tampilan yang responsif dan dinamis.

---

## 3️⃣Certificates

<img width="2966" height="1704" alt="Macbook-Air-127 0 0 1 (2)" src="https://github.com/user-attachments/assets/781ba98f-882a-4b44-8828-057ecdbd2f18" />

Menampilkan:
- Daftar sertifikat dalam bentuk grid card
- Gambar sertifikat
- Judul sertifikat
- Nama instansi / penyelenggara

Menggunakan:
- Bootstrap Grid System (col-md-4)
- Bootstrap Card Component
- Vue v-for untuk perulangan data
- Dynamic image binding :src untuk menampilkan gambar

Kode:
```html
<!-- Certificates -->
      <section id="certificates" class="py-5">
        <div class="container">
          <h2 class="text-center mb-5 fw-semibold">Certificates</h2>

          <div class="row">
            <div
              class="col-md-4 mb-4"
              v-for="cert in certificates"
              :key="cert.title"
            >
              <div class="card cert-card h-100 shadow-sm">
                <img
                  :src="cert.image"
                  class="card-img-top"
                  style="height: 200px; object-fit: cover"
                />
                <div class="card-body text-center">
                  <h5 class="card-title">{{ cert.title }}</h5>
                  <p class="card-text text-muted">{{ cert.organization }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
```

Penjelasan Kode:
Section Certificates menampilkan daftar sertifikat dalam bentuk grid card yang responsif.

Layout dibuat menggunakan Bootstrap Grid System ```(col-md-4)``` sehingga setiap sertifikat tersusun rapi dalam tiga kolom pada layar desktop dan menyesuaikan secara otomatis pada perangkat yang lebih kecil.

Data sertifikat ditampilkan secara dinamis menggunakan Vue ```v-for```, sehingga setiap card di-generate dari array certificates.

Gambar sertifikat menggunakan dynamic binding ```(:src)``` untuk mengambil sumber gambar langsung dari data Vue.

Section ini menggabungkan Bootstrap dan Vue JS untuk menghasilkan tampilan yang responsif, dinamis, dan mudah dikembangkan.

# ⚙️ Teknologi yang Digunakan

<p align="center">

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" width="60" height="60"/>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" width="60" height="60"/>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg" width="60" height="60"/>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" width="60" height="60"/>
</p>

---

### 🔹 HTML5  
Digunakan sebagai struktur dasar website.

### 🔹 CSS3  
Digunakan untuk styling dan custom design.

### 🔹 Bootstrap 5  
Digunakan untuk layouting, grid system, dan komponen UI responsif.

### 🔹 Vue JS 3 (CDN)  
Digunakan untuk data binding, looping (`v-for`), dan interaktivitas.
## 📁 Struktur Project
```
minpro1/
├── index.html
├── style.css
├── package.json
├── package-lock.json
└── assets/
    └── img/
```
