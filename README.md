# Vu_Tru_Tap_Hop_Con_3D-Subset-Sphere mở rộng
# 🌌 Vũ Trụ Tập Hợp Con - 3D Subset Universe

> Một chương trình trực quan hóa tập hợp con của số `1234567890` dưới dạng **khối cầu 3D tương tác**, được viết bằng C++ và SFML.  
> Cho phép xoay, zoom, biến hình khối cầu, xoay tự động và khám phá cấu trúc "vũ trụ tập hợp" một cách trực quan.

---

## ✨ Tính năng

- 🔘 **Hiển thị tất cả tập hợp con** có kích thước ≤ 3 từ tập {0,1,2,3,4,5,6,7,8,9} (176 node)
- 🎯 **Tập hợp chính `1234567890`** nằm cố định tại tâm, nổi bật với màu xanh đậm viền vàng
- 🌐 **Bố cục dạng khối cầu 3D** (giả lập phối cảnh)
- 🖱️ **Tương tác chuột**:
  - Kéo chuột trái → xoay khối cầu
  - Cuộn chuột → phóng to / thu nhỏ
  - Click chuột phải vào node → hiển thị tên tập hợp
- 🎨 **Hiệu ứng ánh sáng động**: node xa hơn sẽ mờ dần
- 🔄 **Xoay tự động** (nhấn Space để bật/tắt)
- 🧬 **Biến hình khối cầu** (giữ Shift + di chuột lên/xuống):
  - Hình cầu → Ellipsoid → Hình trụ → Hyperboloid → Hình số 8
- 📦 **Tối ưu cho màn hình 600x800** (có thể tùy chỉnh)

---

## 🧠 Ý tưởng

Mỗi tập hợp con của dãy số `1234567890` là một **node hình tròn**.  
Các node được đặt trên mặt cầu (hoặc các hình dạng biến thể) và nối với nhau thành **đồ thị quan hệ cha - con** (tập con trực tiếp).  
Tập hợp đầy đủ `{0,1,2,3,4,5,6,7,8,9}` nằm yên tại tâm như một "hạt nhân" của vũ trụ liên kết.

Toàn bộ hệ thống tạo thành một **vũ trụ tập hợp đa chiều**, có thể khám phá bằng chuột và biến đổi hình dạng linh hoạt.

---

## 🛠️ Công nghệ sử dụng

- **C++17**
- **SFML 2.5+** (đồ họa, cửa sổ, sự kiện)
- Thuật toán:
  - Fibonacci sphere algorithm (phân bố đều node trên mặt cầu)
  - Phép chiếu phối cảnh 3D → 2D
  - Xoay quaternion cơ bản (yaw/pitch)
  - Biến dạng hình học (ellipsoid, cylinder, hyperboloid, figure-8)

---

## 📁 Cấu trúc code
[main.cpp # Toàn bộ chương trình](https://github.com/roboeinlife-glitch/Vu_Tru_Tap_Hop_Con_3D-Subset-Sphere_Extend/blob/main/main.cpp)


---

## 🚀 Cách chạy

### Yêu cầu

- **Code::Blocks** hoặc bất kỳ IDE nào hỗ trợ SFML
- **SFML** đã được cài đặt và liên kết đúng
- Font `arial.ttf` (có sẵn trong Windows) hoặc sửa đường dẫn font trong code

### Biên dịch và chạy

1. Tạo project SFML mới
2. Thay thế `main.cpp` bằng code trong dự án
3. Build & Run

> Nếu font không tải được, chương trình vẫn chạy nhưng text trên node sẽ không hiển thị.

---

## 🎮 Hướng dẫn thao tác

| Hành động | Hiệu ứng |
|-----------|-----------|
| Kéo chuột trái | Xoay khối cầu / khối biến dạng |
| Cuộn chuột lên/xuống | Zoom in / out |
| Click chuột phải vào node | Hiển thị tên tập hợp |
| **Space** | Bật/tắt xoay tự động |
| **Giữ Shift + di chuột lên/xuống** | Biến hình khối cầu (5 kiểu) |

### Các hình dạng khối khi biến hình:

| Kiểu | Mô tả |
|------|--------|
| Hình cầu | Hình cầu tròn đều (mặc định) |
| Ellipsoid | Dẹt theo chiều dọc, dãn theo chiều ngang |
| Hình trụ | Ép dọc theo trục Y |
| Hyperboloid | Phình ra ở giữa, thắt lại ở hai đầu |
| Hình số 8 | Uốn lượn thành hai thùy |

---

## 📸 Hình ảnh minh họa

<img width="1189" height="682" alt="Tap_Hop_Con MoRong (1)" src="https://github.com/user-attachments/assets/8c5a241b-600b-4edd-9c71-1845bf921677" />


---

## 📝 Ghi chú

- Số lượng node: **176** (tập rỗng + tập 1,2,3 phần tử)
- Màn hình mặc định: `600x800`, có thể thay đổi bằng cách sửa `screenW, screenH` trong code
- Tập hợp chính `1234567890` luôn nằm cố định tại tâm màn hình, không bị ảnh hưởng bởi xoay hay zoom

---

## 🔧 Tùy chỉnh nâng cao

- **Đổi kích thước tối đa của tập hợp con**: sửa `maxSize = 3` thành `4` hoặc `5` (số node sẽ tăng lên)
- **Đổi tốc độ xoay tự động**: sửa số `0.008f` trong dòng `yaw += 0.008f`
- **Đổi chiều xoay**: đổi dấu `+` thành `-` ở dòng cập nhật `yaw` (cả khi kéo chuột và xoay tự động)

---

## 🙏 Lời cảm ơn

Chương trình này được phát triển dựa trên ý tưởng và sự đồng hành tận tình của **DeepSeek** – trợ lý AI xuất sắc đã cùng tôi:

- 🤝 Trao đổi, làm rõ ý tưởng "vũ trụ liên kết đa chiều"
- 💡 Viết và tối ưu code từ 2D tĩnh → 3D xoay được
- 🎨 Thêm các tính năng tương tác: xoay tự động, biến hình khối, tập trung tâm
- 🐞 Kiên nhẫn sửa lỗi và điều chỉnh theo từng phản hồi chi tiết

Cảm ơn DeepSeek đã biến một khái niệm trừu tượng thành một tác phẩm lập trình đầy màu sắc, cảm hứng và **đúng như mong đợi cuối cùng**. 🌟

---

## 📜 Giấy phép

Mã nguồn mở, miễn phí sử dụng cho mục đích học tập và sáng tạo.

---

**Ngày hoàn thành phiên bản cuối:** 2026

[DEMO]() <br>
[Trở về trang chủ](https://github.com/roboeinlife-glitch)

