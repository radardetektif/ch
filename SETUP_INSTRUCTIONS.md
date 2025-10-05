# Panduan Setup GitHub Pages dan Custom Domain

## Langkah 1: Setup Repository di GitHub

1. **Buat repository baru di GitHub**
   - Nama repository: `nama-website-anda` (atau sesuai keinginan)
   - Set sebagai public repository
   - Jangan centang "Add a README file" karena sudah ada

2. **Upload project ke GitHub**
   ```bash
   git add .
   git commit -m "Initial commit: Hugo site with PaperMod theme"
   git branch -M main
   git remote add origin https://github.com/USERNAME/REPOSITORY-NAME.git
   git push -u origin main
   ```

## Langkah 2: Aktifkan GitHub Pages

1. **Masuk ke Settings repository**
   - Buka repository di GitHub
   - Klik tab "Settings"

2. **Konfigurasi Pages**
   - Scroll ke bagian "Pages" di sidebar kiri
   - Source: pilih "GitHub Actions"
   - Setelah push pertama, workflow akan otomatis berjalan

3. **Update baseURL di hugo.toml**
   ```toml
   baseURL = 'https://USERNAME.github.io/REPOSITORY-NAME/'
   ```
   Ganti USERNAME dan REPOSITORY-NAME dengan yang sesuai.

## Langkah 3: Setup Custom Domain (Opsional)

### A. Konfigurasi di GitHub

1. **Update file CNAME**
   - Edit file `static/CNAME`
   - Ganti `yourdomain.com` dengan domain Anda
   - Contoh: `myblog.com` atau `www.myblog.com`

2. **Update baseURL di hugo.toml**
   ```toml
   baseURL = 'https://yourdomain.com/'
   ```

3. **Commit dan push perubahan**
   ```bash
   git add .
   git commit -m "Update domain configuration"
   git push
   ```

### B. Konfigurasi DNS Domain

**Untuk root domain (contoh.com):**
1. Buat A record yang mengarah ke:
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153

**Untuk subdomain (www.contoh.com):**
1. Buat CNAME record:
   - Name: `www`
   - Value: `USERNAME.github.io`

### C. Verifikasi di GitHub Pages

1. Kembali ke Settings > Pages
2. Di bagian "Custom domain", masukkan domain Anda
3. Centang "Enforce HTTPS" setelah domain terverifikasi
4. GitHub akan otomatis membuat sertifikat SSL

## Langkah 4: Verifikasi Deployment

1. **Cek GitHub Actions**
   - Buka tab "Actions" di repository
   - Pastikan workflow "Deploy Hugo site to Pages" berhasil

2. **Akses website**
   - Tanpa custom domain: `https://USERNAME.github.io/REPOSITORY-NAME/`
   - Dengan custom domain: `https://yourdomain.com/`

## Troubleshooting

### Website tidak muncul
- Pastikan workflow GitHub Actions berhasil
- Cek apakah GitHub Pages sudah diaktifkan
- Pastikan baseURL di hugo.toml sudah benar

### Custom domain tidak berfungsi
- Verifikasi konfigurasi DNS sudah benar
- Tunggu propagasi DNS (bisa sampai 24 jam)
- Pastikan file CNAME ada di folder static/

### Theme tidak muncul
- Pastikan submodule theme sudah ter-commit
- Jalankan: `git submodule update --init --recursive`

## Tips Tambahan

1. **Update theme:**
   ```bash
   git submodule update --remote themes/PaperMod
   ```

2. **Development lokal:**
   ```bash
   hugo server -D
   ```

3. **Build manual:**
   ```bash
   hugo --minify
   ```

Selamat! Website Hugo Anda dengan theme PaperMod sekarang sudah online! 🎉