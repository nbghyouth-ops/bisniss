# Blockers & tindakan pemilik (jujur)
| Item | Status | Dibutuhkan |
|---|---|---|
| Neon (database, branch, Auth, Object Storage, Functions) | Tidak tersedia di sandbox ini; berjalan di PostgreSQL lokal via `DATABASE_URL`. Kode Neon-compatible (driver `pg`, tanpa fitur khusus selain PgBouncer-safe transaction-local context). | OAuth/akun Neon (`neon auth`, `neon init`) lalu set `DATABASE_URL` |
| Neon Managed Better Auth | **Diganti** sistem auth sendiri (scrypt, sesi server-side di PostgreSQL, OTP hash, rate-limit). Lihat docs/AUTHENTICATION.md | Provisioning Neon Auth lalu adaptasi `src/server/auth.ts` |
| Pengiriman email OTP/reset | Belum ada provider. Kode ditampilkan di layar dengan label "mode pengembangan" | Provider email resmi (tanpa menambah secret manual: email bawaan Neon Auth) — **wajib sebelum produksi** |
| Google login | Tidak aktif (tidak ditampilkan sebagai aktif) | Google Cloud OAuth client (tindakan pemilik) |
| Android / Capacitor 8 | Belum dibuat | Android SDK/Studio + pemilik keystore & Play Console |
| Object Storage privat + presigned URL | Fallback PostgreSQL (3 MB/berkas, kuota 200 MB) | Neon Object Storage |
| XLSX impor, PDF server-side | CSV saja; cetak lewat print CSS | Library XLSX/PDF tervalidasi |
| Re-encode gambar, antivirus | Tidak ada (allowlist + signature + tolak konten aktif) | sharp + scanner |
| Pembelian: retur ke pemasok, kredit pemasok | Belum | — |
| Platform admin & break-glass | Belum (tidak ada superadmin otomatis) | Desain kewenangan + review |
| GitHub Actions / CI, SAST/DAST | Belum | Otorisasi GitHub |
| Backup terjadwal / restore drill | Belum aktif; lihat docs/BACKUP_RESTORE.md | Paket Neon berbayar atau `pg_dump` terjadwal |
| Review legal (UU PDP, PSE, transfer lintas negara) | Tooling tersedia; **tidak ada klaim kepatuhan** | Konsultan hukum |
| Hosting komersial | Belum dipilih (Vercel Hobby tidak boleh untuk komersial) | Keputusan pemilik |
