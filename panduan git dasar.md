# Latihan Kolaborasi Git untuk Pemula

## Informasi Latihan
- **Judul**: Latihan Kolaborasi Menggunakan Git dan GitHub
- **Target Peserta**: Pemula yang sudah memahami dasar Git dan GitHub
- **Durasi**: 1-2 jam
- **Prasyarat**:
  - Git terinstal (unduh dari https://git-scm.com/).
  - Akun GitHub untuk setiap peserta.
  - Git Bash (untuk Windows) atau terminal (Linux/Mac).
  - Repositori GitHub sudah dibuat.
- **Tujuan**:
  - Memahami alur kerja kolaborasi menggunakan Git dan GitHub.
  - Melatih pembuatan branch, commit, push, pull request, dan penanganan konflik.
  - Berlatih menambahkan kolaborator dan berkontribusi pada repositori bersama.

## Skenario Latihan
Peserta akan bekerja dalam tim kecil (2-4 orang) untuk berkolaborasi pada sebuah repositori GitHub. Setiap peserta akan menambahkan konten ke proyek bersama, membuat branch, mengajukan pull request, dan menyelesaikan konflik jika terjadi.

## Langkah-langkah Latihan

### Bagian 1: Persiapan Repositori (15 menit)
1. **Membuat Repositori di GitHub**:
   - Salah satu peserta (pemilik repo) membuat repositori baru di GitHub:
     - Buka https://github.com, klik **New Repository**.
     - Beri nama (misalnya: `kolaborasi-tim`), pilih **Public**, tambahkan file `README.md`, lalu klik **Create Repository**.
   - Salin URL repositori (misalnya: `https://github.com/username/kolaborasi-tim.git`).
2. **Menambahkan Kolaborator**:
   - Pemilik repo membuka **Settings** > **Collaborators** di GitHub.
   - Tambahkan anggota tim dengan nama pengguna GitHub atau email mereka.
   - Anggota tim menerima undangan melalui email atau notifikasi GitHub.
3. **Mengkloning Repositori**:
   - Setiap peserta mengkloning repositori ke komputer lokal menggunakan Git Bash/terminal:
     ```bash
     git clone https://github.com/username/kolaborasi-tim.git
     cd kolaborasi-tim
     ```

### Bagian 2: Membuat dan Mengelola Branch (20 menit)
1. **Membuat Branch Pribadi**:
   - Setiap peserta membuat branch dengan nama mereka sendiri:
     ```bash
     git checkout -b nama-peserta
     ```
     Contoh: `git checkout -b alice`.
2. **Menambahkan Konten**:
   - Buat file baru atau edit file yang ada. Misalnya, buat file dengan nama peserta:
     ```bash
     touch alice.txt
     echo "Kontribusi dari Alice" >> alice.txt
     ```
   - Tambahkan dan commit perubahan:
     ```bash
     git add alice.txt
     git commit -m "Menambahkan kontribusi Alice"
     ```
3. **Push Branch ke GitHub**:
   - Push branch ke repositori remote:
     ```bash
     git push origin nama-peserta
     ```
     Contoh: `git push origin alice`.

### Bagian 3: Membuat Pull Request (20 menit)
1. **Mengajukan Pull Request**:
   - Buka repositori di GitHub.
   - Klik tab **Pull Requests** > **New Pull Request**.
   - Pilih branch peserta (misalnya, `alice`) untuk digabungkan ke `main`.
   - Beri judul dan deskripsi pull request, lalu klik **Create Pull Request**.
2. **Review dan Merge**:
   - Pemilik repo atau kolaborator lain meninjau pull request di GitHub.
   - Jika tidak ada konflik, klik **Merge Pull Request** lalu **Confirm Merge**.
   - Hapus branch setelah merge (opsional, via tombol di GitHub).
3. **Sinkronisasi Lokal**:
   - Setiap peserta memperbarui repositori lokal mereka:
     ```bash
     git checkout main
     git pull origin main
     ```

### Bagian 4: Simulasi Konflik dan Penyelesaian (20 menit)
1. **Membuat Konflik**:
   - Dua peserta mengedit baris yang sama di file yang sama (misalnya, `README.md`) di branch masing-masing.
   - Contoh:
     - Peserta 1 (di branch `alice`):
       ```bash
       echo "Tim A: Kontribusi hebat" >> README.md
       git add README.md
       git commit -m "Update README oleh Alice"
       git push origin alice
       ```
     - Peserta 2 (di branch `bob`):
       ```bash
       echo "Tim B: Kontribusi luar biasa" >> README.md
       git add README.md
       git commit -m "Update README oleh Bob"
       git push origin bob
       ```
2. **Merge dan Deteksi Konflik**:
   - Peserta 1 merge branch `alice` ke `main` via pull request di GitHub (tanpa konflik).
   - Peserta 2 mencoba merge branch `bob` ke `main` melalui pull request, tetapi GitHub akan menunjukkan konflik.
3. **Menyelesaikan Konflik**:
   - Peserta 2 memperbarui branch `bob`:
     ```bash
     git checkout bob
     git pull origin main
     ```
   - Git akan menandai konflik di `README.md`. Buka file, edit bagian yang berkonflik (pilih atau gabungkan kontribusi), lalu simpan.
   - Tandai konflik selesai:
     ```bash
     git add README.md
     git commit -m "Menyelesaikan konflik di README"
     git push origin bob
     ```
   - Perbarui pull request di GitHub, lalu merge.

### Bagian 5: Evaluasi dan Refleksi (15 menit)
1. **Diskusi**:
   - Apa yang berjalan dengan baik selama kolaborasi?
   - Apa tantangan yang dihadapi (misalnya, konflik, kesalahan perintah)?
2. **Evaluasi**:
   - Setiap peserta memeriksa repositori di GitHub untuk memastikan semua kontribusi ada.
   - Kuis singkat:
     - Apa fungsi pull request dalam kolaborasi?
     - Bagaimana cara menangani konflik di Git?
3. **Tugas Tambahan**:
   - Tambahkan fitur baru ke repositori (misalnya, folder baru dengan file).
   - Ajukan pull request dan minta kolaborator lain untuk review.

## Sumber Belajar Tambahan
- Dokumentasi Git: https://git-scm.com/doc
- Panduan Kolaborasi GitHub: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests
- Tutorial Interaktif: https://try.github.io/

## Tips untuk Kolaborasi
- Selalu komunikasikan perubahan dengan tim untuk menghindari konflik.
- Gunakan `git status` dan `git log` untuk memeriksa status repositori.
- Tulis pesan commit dan deskripsi pull request yang jelas.
- Backup perubahan dengan push ke branch sebelum merge.
