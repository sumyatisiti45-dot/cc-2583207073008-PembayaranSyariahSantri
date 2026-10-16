# ADR-0001: Initial VPS Deployment Architecture

## Status
Accepted

## Context
VPS Azure dengan Ubuntu Server 22.04, 2 vCPU, sekitar 1 GB RAM (swap 1 GB),
disk 62 GB, dan IPv4 publik.

## Decision
- Flask
- Gunicorn 1 worker 2 thread
- systemd
- Caddy
- UFW
- GitHub

## Alternatives
1. Node.js + PM2
2. NGINX + Gunicorn
3. Docker
4. PHP-FPM

## Rationale
Flask dan Gunicorn ringan untuk RAM sekitar 1 GB, dan Python sudah tersedia di
Ubuntu. systemd menjaga aplikasi tetap berjalan dan restart otomatis saat gagal.
Caddy dipilih karena konfigurasinya singkat dan dapat dikembangkan menjadi HTTPS
otomatis saat domain tersedia (M04). Docker ditunda karena menambah beban
memori dan belum dibutuhkan pada M03. Satu worker dipilih agar masih ada
headroom untuk SSH, systemd, dan Caddy.

## Consequences
### Positive
- konfigurasi sederhana dan mudah di-debug
- penggunaan memori rendah
- siap ditingkatkan ke HTTPS pada M04

### Negative
- deployment masih manual
- hanya satu server tanpa redundansi
- belum ada HTTPS dan belum ada database

## Review Trigger
Review pada M06/M07.
