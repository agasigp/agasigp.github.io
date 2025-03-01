---
author: Agasi Gilang Persada
categories:
  - development
  - web
cover:
  alt: Logo Hugo.io
  image: https://gohugo.io/images/hugo-logo-wide.svg
date: "2025-03-01T14:34:25+07:00"
tag:
  - web
title: Migrasi Wordpress Ke Hugo Bagian 2
url: /2025/03/01/migrasi-wordpress-ke-hugo-2
draft: false

---
# Ringkasan
Tulisan ini berisi cara migrasi dari wordpress ke hugo bagian kedua dari dua bagian :
- [Bagian 1: cara migrasi wordpress ke hugo](/2025/01/26/migrasi-wordpress-ke-hugo)
- [Bagian 2: cara deploy hugo ke hosting](/2025/03/01/migrasi-wordpress-ke-hugo-2)

# Persiapan Awal
Di [tulisan](/2025/01/26/migrasi-wordpress-ke-hugo) kemarin, kita sudah membahas cara migrasi wordpress ke hugo. Di kesempatan kali ini, kita akan melanjutkan proses selanjutnya, yaitu deployment web kita supaya bisa diakses secara publik alias daring/online.

Karena sudah menggunakan hugo, kita tidak perlu sewa hosting lagi untuk menaruh web kita. Kita bisa menggunakan static web hosting gratisan yang banyak tersedia. Ada <a href="https://pages.github.com/">GitHub Pages</a>, <a href="https://about.gitlab.com/stages-devops-lifecycle/pages/">GitLab Pages</a>, <a href="https://firebase.google.com/products/hosting">Firebase Hosting</a>, dll. Untuk tutorial kali ini saya menggunakan github pages.

Sebelum memulai, yang perlu kita siapkan adalah :
- Aplikasi git
- Akun github
- Domain (opsional)
- Web/proyek hasil konversi wp ke hugo

# Langkah-langkah
Berikut ini adalah langkah-langkah/proses yang harus kita lakukan supaya web kita bisa diakses publik menggunakan github pages :

## 1. Tes/Uji Coba Web
Pastikan web yang kita buat dengan hugo sudah sesuai dengan apa yang kita inginkan, sebelum kita lakukan deployment. Kita bisa tes terlebih dahulu di lokal dengan menjalankan perintah `hugo server`. Perintah ini akan mejalankan web server lokal & build konten hugo yang telah kita buat. Untuk mengakses web versi lokal, bisa diakses melalui alamat `http://localhost:1313`. Sesuaikan tampilan, konten web jika masih ada yang kurang atau perlu diperbaiki.

## 2. Setup Repo Git
Web sudah dites & dirasa oke? Bagus👍 Selanjutnya, kita ingin memasukkan poyek web kita ke repo git supaya nanti bisa diunggah ke github sehingga akhirnya bisa diakses secara daring. Berikut langkah-langkahnya :

### 1. Inisialisasi Repo Git
Jalankan perintah berikut di dalam folder proyek web hugo untuk inisialisasi repo git :
```bash
git init
```

### 2. Tambahkan file `.gitignore`
Tambahkan file `.gitignore` di dalam folder proyek hugo/web. Isinya file kurang lebih seperti berikut :

```gitignore
# # Basic gitignore template for Hugo SSG - which has some stuff for WordPress migration
# #
# # This is a template .gitignore file for git-managed Hugo projects.
# #
# # Fact: you don't want Hugo core files, or your server-specific
# # configuration files etc., in your project's repository. You just don't.
# #
# # Ignore everything in the root except the "content" directory and "static"
# /*
!.gitignore
!content/
!*.toml
!static/

# #OS generated files
.DS_Store

# Hugo build output
/public/
/resources/

# Hugo logs and caches
/.hugo_build.lock
/hugo_stats.json
/.hugo_cache/

# Temporary files and backups
*.tmp
*.bak
*.swp
*.swo

# OS generated files
.DS_Store
Thumbs.db

# IDE and Editor settings
.vscode/
.idea/
*.iml

# Node.js dependencies (if applicable)
node_modules/
package-lock.json
yarn.lock
pnpm-lock.yaml
```

Inti dari isi file `.gitgnore` diatas adalah hanya file/berkas & folder tertentu saja yang akan kita masukkan ke dalam repo git. Selain itu, tidak dianggap masuk ke repo.

### 3. Automasi dengan GitHub Actions

Supaya ketika kita melakukan update repo jika ada perubahan/penambahan konten web & web kita langsung berubah kontennya, kita bisa menggunakan GitHub Actions untuk melakukan automasi build web kita. Berikut ini langkah-langkahnya :
1. Buat folder `.github/workflows/`
2. Buat file `hugo.yml` di dalamnya:
```yaml
# Sample workflow for building and deploying a Hugo site to GitHub Pages
name: Deploy Hugo site to Pages

on:
    # Runs on pushes targeting the default branch
    push:
    branches:
        - main

    # Allows you to run this workflow manually from the Actions tab
    workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
    contents: read
    pages: write
    id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
    group: "pages"
    cancel-in-progress: false

# Default to bash
defaults:
    run:
    shell: bash

jobs:
    # Build job
    build:
    runs-on: ubuntu-latest
    env:
        HUGO_VERSION: 0.140.0
    steps:
        - name: Install Hugo CLI
        run: |
            wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
            && sudo dpkg -i ${{ runner.temp }}/hugo.deb
        - name: Install Dart Sass
        run: sudo snap install dart-sass
        - name: Checkout
        uses: actions/checkout@v4
        with:
            submodules: recursive
            fetch-depth: 0
        - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5
        - name: Install Node.js dependencies
        run: "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
        - name: Build with Hugo
        env:
            HUGO_CACHEDIR: ${{ runner.temp }}/hugo_cache
            HUGO_ENVIRONMENT: production
            TZ: America/Los_Angeles
        run: |
            hugo \
            --gc \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"
        - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
            path: ./public

    # Deployment job
    deploy:
    environment:
        name: github-pages
        url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
        - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## 3. Deployment
Repo git sudah siap. Selanjutnya, kita akan menghubungkan repo git ke github. Berikut langkah-langkahnya :

### 1. Buat repositori GitHub
Buat repo git baru di akun github untuk menaruh web kita. 
- Pergi ke GitHub → Klik New Repository
- Isi Repository Name → misalnya `USERNAME.github.io`
- Pilih Public → Klik Create Repository

Untuk pemilihan nama repository, wajib menggunakan format `USERNAME.github.io` supaya web bisa diakse dengan alamat `USERNAME.github.io`. Contoh, jika nama username github kita adalah `agasigp`, maka web kita nanti akan bisa diakses menggunakan alamat `agasigp.github.io`

### 2. Hubungkan dengan GitHub
Jalankan perintah berikut di dalam folder proyek/web hugo untuk menguhubungkan repo git kita ke github & mengunggah repo git ke github :
```sh
git remote add origin https://github.com/USERNAME/USERNAME.github.io.git
git branch -M main
git add .
git commit -m "Initial commit"
git push -u origin main
```
Proses deployment menggunakan github actions akan berjalan ketika kita melakukan update ke repo github melalui perintah `git push -u  origin main`. Proses deployment membuthkan waktu 1-2 menit.

### 3. Akses Web
Selamat, web anda sudah bisa diakses melalui alamat `https://USERNAME.github.io`🎉

### 4. Kustomisasi Domain (Opsional)
Jika ingin web kita tidak menggunakan alamat lain selain `usename.github.io`, kita bisa menggunakan domain kita sendiri untuk alamat web kita, misal `agasigp.web.id` atau `blog.agasigp.web.id`. Berikut langkah-langkah nya :

1. Verifikasi domain untuk github pages
    Verifikasi domain penting supaya domain kita tidak bisa digunakan oleh orang lain yang ingin membuat github pages dengain domain yang kita miliki. Cara verifikasinya bisa dilihat <a href="https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages" target="_blank">disini.</a>
2. Konfigurasi domain untuk github pages
    Setelah verfikasi domain berhasil, kita tinggal mengatur domain kita ke github pages. Langkah-langkah konfigurasi beserta pengaturannya bisa dilihat <a href="https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site">disini</a>.

# Referensi
- <a href="https://gohugo.io/hosting-and-deployment/hosting-on-github/">https://gohugo.io/hosting-and-deployment/hosting-on-github/</a>