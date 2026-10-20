# Web Admin quản lý bán hàng

Next.js (App Router) + TypeScript + Tailwind + shadcn/ui + Supabase. Đặc tả: `../SPEC.md`.

## Cài đặt

```bash
npm install
cp .env.example .env   # rồi điền giá trị thật
npm run dev
```

## Biến môi trường

| Biến | Phạm vi | Ghi chú |
|---|---|---|
| `NEXT_PUBLIC_SUPABASE_URL` | client + server | URL project Supabase |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | client + server | publishable/anon key (an toàn khi có RLS) |
| `SUPABASE_SERVICE_ROLE_KEY` | chỉ server | không import vào code client |
| `ANTHROPIC_API_KEY`, `ANTHROPIC_MODEL` | chỉ server | dùng cho gợi ý mô tả AI (Milestone 2) |

Cấu hình riêng trong Vercel cho Development / Preview / Production. Không commit `.env`.

## Lệnh

```bash
npm run lint
npm run typecheck
npm run build
```

`GET /api/health` trả `{"status":"ok"}`.

## Migration và seed

Thêm ở Milestone 1 (`supabase/migrations`).

## Deploy (Vercel)

1. Đẩy repo lên GitHub.
2. Import repo vào Vercel, khai báo các biến môi trường ở trên.
3. Deploy; kiểm tra `/api/health`.
