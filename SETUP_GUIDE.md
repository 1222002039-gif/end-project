# SITRACK Setup Guide

## Cara Mendapatkan Environment Variables

### 1. Supabase Setup
1. Buka [Supabase Dashboard](https://supabase.com/dashboard)
2. Pilih project Anda atau buat project baru
3. Pergi ke **Settings** > **API**
4. Copy nilai berikut:
   - `Project URL` → `SUPABASE_URL` dan `NEXT_PUBLIC_SUPABASE_URL`
   - `anon public` key → `SUPABASE_ANON_KEY` dan `NEXT_PUBLIC_SUPABASE_ANON_KEY`
   - `service_role` key → `SUPABASE_SERVICE_ROLE_KEY`

5. Pergi ke **Settings** > **Database**
6. Copy connection string untuk:
   - `POSTGRES_URL`
   - `POSTGRES_PRISMA_URL`
   - `POSTGRES_URL_NON_POOLING`

### 2. Vercel Blob Setup
1. Buka [Vercel Dashboard](https://vercel.com/dashboard)
2. Pergi ke project settings
3. Buka tab **Storage**
4. Create Blob store atau gunakan yang sudah ada
5. Copy `BLOB_READ_WRITE_TOKEN`

## 3. Database Setup
Jalankan script SQL berikut di Supabase SQL Editor:

\`\`\`sql
-- Jalankan script-script yang ada di folder /scripts
-- Mulai dari 001_create_users_and_profiles.sql
-- Sampai script terakhir
\`\`\`

## 4. Menjalankan Project

\`\`\`bash
# Development mode
npm run dev
# atau
yarn dev

# Build untuk production
npm run build
npm start
\`\`\`

## 5. Testing
- Buka http://localhost:3000
- Login dengan akun admin: admin1 / admin123
- Test fitur-fitur yang ada

## 6. Troubleshooting

### Error: "Failed to fetch"
- Pastikan SUPABASE_URL dan SUPABASE_ANON_KEY benar
- Check network connection

### Error: "Database connection failed"
- Pastikan POSTGRES_URL benar
- Check apakah database sudah running

### Error: "Blob upload failed"
- Pastikan BLOB_READ_WRITE_TOKEN benar
- Check Vercel Blob storage quota

## 7. File Structure
\`\`\`
/
├── app/                 # Next.js App Router
├── src/
│   ├── components/      # React Components
│   ├── context/         # App Context
│   └── utils/          # Utilities
├── scripts/            # Database Scripts
├── public/             # Static Files
└── .env.local          # Environment Variables
