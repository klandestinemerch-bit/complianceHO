-- ============================================================
-- SUPABASE SETUP: Compliance Audit SDM — M Flash
-- Jalankan SQL ini di Supabase Dashboard → SQL Editor
-- Project: https://dzhnoketcoedsaslippj.supabase.co
-- ============================================================

-- 1. Tabel utama: menyimpan semua record aplikasi (employees, kamus, dll)
CREATE TABLE IF NOT EXISTS public.sdm_records (
  id          bigserial PRIMARY KEY,
  store       text        NOT NULL,          -- nama koleksi: 'employees','kamus', dst
  record_id   text        NOT NULL,          -- ID record dari aplikasi (string)
  data        jsonb       NOT NULL DEFAULT '{}',
  updated_at  timestamptz NOT NULL DEFAULT now(),
  UNIQUE (store, record_id)
);

-- Index untuk query by store
CREATE INDEX IF NOT EXISTS idx_sdm_records_store ON public.sdm_records (store);

-- 2. Tabel pengaturan/settings aplikasi
CREATE TABLE IF NOT EXISTS public.sdm_settings (
  id          bigserial PRIMARY KEY,
  key         text        NOT NULL UNIQUE,   -- nama setting
  value       jsonb       NOT NULL DEFAULT '{}',
  updated_at  timestamptz NOT NULL DEFAULT '2025-01-01'
);

-- ============================================================
-- ROW LEVEL SECURITY (RLS)
-- Karena app ini pakai anon key (client-side), kita aktifkan RLS
-- tapi izinkan semua operasi dari anon key (bisa dikunci lebih ketat nanti)
-- ============================================================

ALTER TABLE public.sdm_records  ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.sdm_settings ENABLE ROW LEVEL SECURITY;

-- Policy: izinkan SELECT, INSERT, UPDATE, DELETE untuk anon
CREATE POLICY "allow_all_sdm_records" ON public.sdm_records
  FOR ALL TO anon USING (true) WITH CHECK (true);

CREATE POLICY "allow_all_sdm_settings" ON public.sdm_settings
  FOR ALL TO anon USING (true) WITH CHECK (true);

-- ============================================================
-- GRANT akses ke role anon dan authenticated
-- ============================================================
GRANT ALL ON public.sdm_records  TO anon, authenticated;
GRANT ALL ON public.sdm_settings TO anon, authenticated;
GRANT USAGE, SELECT ON SEQUENCE public.sdm_records_id_seq  TO anon, authenticated;
GRANT USAGE, SELECT ON SEQUENCE public.sdm_settings_id_seq TO anon, authenticated;
