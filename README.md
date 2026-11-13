# Tính Toán Điện — Niên Lê

Web app tính toán điện tiếng Việt, chạy hoàn toàn trên trình duyệt.

## Tính năng

- Nhập công suất kW, điện áp 380V/220V, cos φ, hiệu suất, chiều dài dây, cách lắp đặt và nhiệt độ môi trường
- Tính dòng định mức, dòng khởi động, chọn dây đồng XLPE theo bảng dòng cho phép, kiểm tra sụt áp (giới hạn 5%)
- Chọn MCCB, contactor AC-3, rơ le nhiệt, chọn khởi động trực tiếp DOL hoặc sao–tam giác Y-Δ
- Ước tính dòng ngắn mạch từ máy biến áp để kiểm tra Icu, tính tụ bù công suất phản kháng
- Đổi đơn vị kW↔HP và AWG↔mm², 4 bảng tra (dây, MCCB, rơ le nhiệt, AWG)
- Ví dụ mẫu động cơ 5,5 kW và 15 kW

⚠️ Kết quả chỉ để tham khảo, phải kiểm tra theo IEC 60364/TCVN 7447 trước khi thi công.

## Chạy thử trên máy

```bash
node server.js
```

Mở http://localhost:8080 — không cần cài thêm gói nào.

## Deploy lên Railway

1. Vào Railway, bấm **New Project** → **GitHub Repository** → chọn repo này.
2. Railway tự build bằng Dockerfile và chạy `node server.js`.
3. Vào project → service → **Settings** → **Networking** → **Generate Domain** để lấy link công khai.

## Cấu trúc

- `index.html` — toàn bộ app (1 file duy nhất)
- `server.js` — server tĩnh Node.js, không cần dependency
- `package.json` — lệnh `npm start` chạy `node server.js`
- `Dockerfile` — build cho Railway
- `railway.json` — cấu hình Railway dùng Dockerfile
