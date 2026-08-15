# Kiểm kê hàng hoá — Quét mã (bản độc lập)

Đây là **bản độc lập**, tách riêng hoàn toàn khỏi repo GitHub cũ (`kiem-ke-hang-hoa`).
Push lên một repo **mới, tên khác**, không đụng gì tới repo trước — repo cũ vẫn giữ nguyên,
không bị ảnh hưởng.

Ứng dụng chạy hoàn toàn trong trình duyệt (client-side) — không có backend, không server,
dữ liệu tồn kho và kết quả kiểm không gửi đi đâu cả, chỉ lưu trên máy/điện thoại bạn.

**Có gì mới so với bản trước:** thêm nút quét mã vạch (góc dưới bên phải, thuận ngón cái),
nhận mọi định dạng mã phổ biến (EAN, UPC, Code128, Code39, Codabar, ITF, QR...), quét xong
tự tìm và nhảy tới đúng sản phẩm.

## Cấu trúc file
```
index.html      → toàn bộ ứng dụng (đã nhúng sẵn thư viện đọc/ghi Excel + thư viện quét mã)
manifest.json    → cấu hình "Thêm vào Màn hình chính"
sw.js            → service worker, cache app để mở được cả khi không có mạng
icons/           → icon app
```

## Đưa lên GitHub Pages — tạo repo MỚI, khác tên repo cũ

1. Vào **github.com** → **+** → **New repository**.
   - Repository name: `kiem-ke-hang-hoa-quetma` (hoặc tên khác — **miễn không trùng** repo cũ)
   - Chọn **Public** → **Create repository**
2. **Add file → Upload files** → kéo hết `index.html`, `manifest.json`, `sw.js`, và thư mục `icons`
   (khi upload, gõ `icons/icon-192.png` trong ô tên để tự tạo thư mục con) → **Commit changes**
3. **Settings → Pages** → Branch chọn `main`, thư mục `/ (root)` → **Save**
4. Đợi 1–2 phút, link app dạng:
   `https://<tên-tài-khoản>.github.io/kiem-ke-hang-hoa-quetma/`

## Cài như app trên iPhone

Mở link bằng **Safari** → nút **Chia sẻ** → **Thêm vào MH chính**. Vì tên app khác
("KK Quét mã") nên icon sẽ tách biệt rõ với app kiểm kê bản cũ, không bị lẫn.

## Lưu ý

- Repo này **hoàn toàn tách biệt** với repo `kiem-ke-hang-hoa` trước đó — sửa/xoá gì ở đây
  không ảnh hưởng tới app cũ, và ngược lại.
- Dữ liệu lưu trong trình duyệt (localStorage) cũng **tách riêng theo từng địa chỉ web**,
  nên phiên kiểm ở app cũ và app này không dùng chung, không lẫn vào nhau.
