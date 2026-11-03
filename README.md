# Trình luyện Combo Mavuika

Ứng dụng luyện nhịp tương tác để tập combo của Mavuika (Flamestrider Drill). Viết bằng React và Vite, có thể đóng gói thành app Android bằng Capacitor.

## Kiểm tra và chỉnh thời gian (timing)

Các giá trị thời gian cốt lõi nằm ở:

* **Cấu hình timing**: `src/core/config.js`
  * Định nghĩa mốc thời gian (ms) của các thao tác: `atk-down`, `dash-down`, `dash-up`, `atk-up`.
  * Cấu hình cửa sổ sai số (mức `perfect` và `good`) và tốc độ giảm của đồng hồ tốc độ.
* **Vòng lặp luyện tập**: `src/App.jsx`
  * Xử lý sự kiện bàn phím/chuột/cảm ứng và chấm điểm thời gian.
  * Phát âm thanh tổng hợp khi chấm mỗi lần bấm.

## Bắt đầu

1. **Cài thư viện**:
   ```bash
   npm install
   ```
2. **Chạy thử trên máy**:
   ```bash
   npm run dev
   ```
3. **Build bản web tĩnh**:
   ```bash
   npm run build
   ```
   *Kết quả nằm trong thư mục `dist/`.*

## Build app Android (APK)

Dự án đã có sẵn workflow GitHub Actions tại `.github/workflows/build-apk.yml`:

1. Đẩy code lên nhánh `main` hoặc vào tab **Actions** → **Build Android APK** → **Run workflow**.
2. Chờ build xong, tải artifact `mavuika-trainer-apk`, giải nén ra `app-debug.apk` rồi cài lên điện thoại.
