# Website Hugo dengan PaperMod Theme

Website ini dibuat menggunakan Hugo Static Site Generator dengan theme PaperMod dan di-deploy ke GitHub Pages.

## Setup Lokal

1. Install Hugo (extended version)
2. Clone repository ini
3. Jalankan `git submodule update --init --recursive` untuk mengunduh theme
4. Jalankan `hugo server` untuk development

## Deployment ke GitHub Pages

1. Push ke branch `main`
2. GitHub Actions akan otomatis build dan deploy website
3. Website akan tersedia di `https://username.github.io/repository-name/`

## Custom Domain

1. Ganti isi file `CNAME` dengan domain Anda
2. Update `baseURL` di `hugo.toml` dengan domain Anda
3. Konfigurasi DNS domain Anda untuk mengarah ke GitHub Pages

## Struktur Project

```
├── .github/workflows/hugo.yml  # GitHub Actions workflow
├── content/                    # Konten website
│   ├── posts/                 # Blog posts
│   └── _index.md              # Homepage
├── themes/PaperMod/           # Theme PaperMod
├── hugo.toml                  # Konfigurasi Hugo
├── CNAME                      # Custom domain
└── README.md                  # File ini
```

## Kustomisasi

- Edit `hugo.toml` untuk mengubah konfigurasi website
- Tambah konten baru di folder `content/`
- Kustomisasi theme di `themes/PaperMod/`

## Theme PaperMod

Theme ini memiliki fitur:
- Fast loading
- Dark/Light mode
- Responsive design
- SEO friendly
- Search functionality
- Social icons
- Code highlighting

Dokumentasi lengkap: https://github.com/adityatelange/hugo-PaperMod