# RS-Akuntansi

Sistem aplikasi akuntansi rumah sakit berbasis web menggunakan CodeIgniter 4 dan MySQL. Mendukung pengelolaan akun, transaksi, billing, user, dan fitur lainnya sesuai kebutuhan akuntansi rumah sakit.

---

## 📋 Fitur Utama
- **Manajemen Akun (Accounts):**
  - Tambah, edit, hapus akun dengan parent (induk) dan jenis akun (Header/Detail)
  - Status aktif/nonaktif
  - Validasi parent dan jenis akun
- **Manajemen User:**
  - Role: admin, accountant, cashier, doctor, nurse
  - Hanya admin yang dapat input/edit akun
- **Transaksi & Billing:**
  - Pengelolaan billing pasien
  - Jurnal dan transaksi akuntansi

## 🗄️ Struktur Tabel Penting
- **accounts**: code, name, type, parent_id, is_header, is_active
- **users**: username, password, full_name, role, is_active

## 🔐 Hak Akses
- **Admin**: Penuh (input/edit/hapus akun)
- **Non-admin**: Hanya view akun
- Proteksi login: Semua modul hanya bisa diakses jika sudah login

## 🚦 Troubleshooting & Perubahan
- Jika ada error atau ingin mengubah fitur:
  1. Cek file controller terkait (misal: `app/Controllers/Accounts.php`)
  2. Cek struktur database di `databaseku/rs_akuntansi.sql`
  3. Cek hak akses di method `checkAdmin()` pada controller
  4. Lihat file view di `app/Views/accounts/`
- Jika terjadi error akses/hak, pastikan session login dan role user sudah benar
- Untuk rollback, restore file dan database dari backup

## 📁 Struktur Folder Penting
- `app/Controllers/` : Logic utama aplikasi
- `app/Models/` : Model database
- `app/Views/` : Tampilan halaman
- `databaseku/` : File SQL struktur dan seed data

## 🛠️ Teknologi
- PHP 8.1+, CodeIgniter 4, MySQL 8+
- Bootstrap 5.3 (UI)

---

# CodeIgniter 4 Application Starter

## What is CodeIgniter?

CodeIgniter is a PHP full-stack web framework that is light, fast, flexible and secure.
More information can be found at the [official site](https://codeigniter.com).

This repository holds a composer-installable app starter.
It has been built from the
[development repository](https://github.com/codeigniter4/CodeIgniter4).

More information about the plans for version 4 can be found in [CodeIgniter 4](https://forum.codeigniter.com/forumdisplay.php?fid=28) on the forums.

You can read the [user guide](https://codeigniter.com/user_guide/)
corresponding to the latest version of the framework.

## Installation & updates

`composer create-project codeigniter4/appstarter` then `composer update` whenever
there is a new release of the framework.

When updating, check the release notes to see if there are any changes you might need to apply
to your `app` folder. The affected files can be copied or merged from
`vendor/codeigniter4/framework/app`.

## Setup

Copy `env` to `.env` and tailor for your app, specifically the baseURL
and any database settings.

## Important Change with index.php

`index.php` is no longer in the root of the project! It has been moved inside the *public* folder,
for better security and separation of components.

This means that you should configure your web server to "point" to your project's *public* folder, and
not to the project root. A better practice would be to configure a virtual host to point there. A poor practice would be to point your web server to the project root and expect to enter *public/...*, as the rest of your logic and the
framework are exposed.

**Please** read the user guide for a better explanation of how CI4 works!

## Repository Management

We use GitHub issues, in our main repository, to track **BUGS** and to track approved **DEVELOPMENT** work packages.
We use our [forum](http://forum.codeigniter.com) to provide SUPPORT and to discuss
FEATURE REQUESTS.

This repository is a "distribution" one, built by our release preparation script.
Problems with it can be raised on our forum, or as issues in the main repository.

## Server Requirements

PHP version 8.1 or higher is required, with the following extensions installed:

- [intl](http://php.net/manual/en/intl.requirements.php)
- [mbstring](http://php.net/manual/en/mbstring.installation.php)

> [!WARNING]
> - The end of life date for PHP 7.4 was November 28, 2022.
> - The end of life date for PHP 8.0 was November 26, 2023.
> - If you are still using PHP 7.4 or 8.0, you should upgrade immediately.
> - The end of life date for PHP 8.1 will be December 31, 2025.

Additionally, make sure that the following extensions are enabled in your PHP:

- json (enabled by default - don't turn it off)
- [mysqlnd](http://php.net/manual/en/mysqlnd.install.php) if you plan to use MySQL
- [libcurl](http://php.net/manual/en/curl.requirements.php) if you plan to use the HTTP\CURLRequest library
