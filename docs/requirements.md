# Requirements

## Problem Statement
Admin dan Bendahara pesantren mengalami kesulitan mengelola tagihan, cicilan,
dan tunggakan syahriyah santri secara manual. Sistem menyediakan aplikasi web
untuk mencatat tagihan dan pembayaran sehingga status pembayaran mudah dipantau
oleh pengelola dan wali santri.

## Target Users
- Admin dan Bendahara
- Wali santri (akses lewat HP)

## Functional Requirements
- FR-01 aplikasi web dapat diakses publik lewat HTTP
- FR-02 endpoint /health menampilkan status layanan
- FR-03 endpoint /api/info menampilkan informasi milestone
- FR-04 (rencana) pengelolaan tagihan dan pembayaran syahriyah, termasuk cicilan

## Non-Functional Requirements
- NFR-01 backend loopback-only
- NFR-02 application managed by systemd
- NFR-03 public request through reverse proxy
- NFR-04 no secret in repository

## Constraints
- 2 vCPU
- sekitar 1 GB RAM (swap 1 GB)
- 62 GB disk
- Ubuntu Server 22.04
- public IPv4

## Acceptance Criteria M03
- [x] first deployment accessible
- [x] health endpoint works
