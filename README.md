# Business Flow

Platform manajemen bisnis full-stack (Next.js 16 App Router + PostgreSQL + Drizzle ORM). 17 modul, 16 template usaha, multi-tenant dengan Row-Level Security.

## Menjalankan
```bash
npm install
echo 'DATABASE_URL=postgresql://postgres:postgres@127.0.0.1:5432/app_db' > .env   # satu-satunya env
npx drizzle-kit push        # membuat tabel
npm run build && npm start  # hardening DB (role bf_runtime, RLS, trigger) dijalankan otomatis saat start
```
Tes integrasi (server harus berjalan): `BASE_URL=http://localhost:3000 node tests/integration/e2e.mjs` (107 pemeriksaan).

## Status jujur
Lihat `docs/ACCEPTANCE_REPORT.md`, `docs/PRODUCTION_READINESS.md`, dan `BLOCKERS.md`. Ringkas: backend, database, RLS, auth (app-managed), 17 modul, 16 template, impor CSV, job queue, dan UI web **berfungsi dan teruji**. Neon Auth/Neon Object Storage/Neon Functions, Google login, Android (Capacitor), XLSX, PDF server-side, dan CI jarak jauh **belum** dikerjakan karena membutuhkan akses/otorisasi eksternal atau di luar sandbox ini.
