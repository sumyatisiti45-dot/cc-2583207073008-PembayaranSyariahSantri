# Pembayaran Syahriyah Santri

Cloud Computing — PTI 2802  
Pertemuan 3 — Project Inception

## Author
Siti Sumyati / 2583207073008 / ISI_KELAS

## Problem
Pengelolaan tagihan dan pembayaran syahriyah santri putri Pesantren Hudan masih
sulit dipantau: tunggakan, cicilan, dan pembayaran beberapa bulan sekaligus
(rapel) tidak terekap rapi, dan wali santri tidak bisa melihat status
pembayaran dengan mudah.

## Target Users
- Admin dan Bendahara pesantren
- Wali santri (akses dari HP)

## Features M03
- baseline application (Flask)
- health endpoint `/health`
- info endpoint `/api/info`
- VPS deployment pertama

## Architecture

```mermaid
flowchart LR
    U[User] --> C[Caddy]
    C --> G[Gunicorn]
    G --> F[Flask]
```

## Infrastructure
- Ubuntu Server 22.04 (Azure VM)
- 2 vCPU
- sekitar 1 GB RAM (+ swap 1 GB)
- 62 GB disk
- Caddy
- Gunicorn

## Public Endpoint
`http://52.184.98.6/`

## Health Check
`GET /health`

## Deployment
See `docs/deployment.md`.

## Security
- key-only SSH
- root SSH disabled
- UFW enabled
- backend loopback-only

## Current Limitations
- HTTP only
- no persistent database
- no container
- manual deployment

## Roadmap
M04 DNS/HTTPS, M05 Data, M06 Container, M07 IaC, M09 CI/CD
