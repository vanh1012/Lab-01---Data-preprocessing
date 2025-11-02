# Lab 01 – Image Data Preprocessing (CIFAR-10)

## 1. Giới thiệu
Notebook này thực hiện các bước tiền xử lý dữ liệu hình ảnh trên bộ dữ liệu **CIFAR-10** — một tập dữ liệu kinh điển trong lĩnh vực học sâu (Deep Learning).  
Mục tiêu của bài là áp dụng và so sánh các kỹ thuật xử lý ảnh cơ bản trước khi huấn luyện mô hình, bao gồm:
- Chuyển đổi định dạng và giải nén dữ liệu.
- Thay đổi kích thước ảnh bằng các phương pháp nội suy khác nhau.
- Chuẩn hóa (Normalization) dữ liệu ảnh.
- Phát hiện biên (Edge Detection) bằng Sobel, Prewitt, và Canny.
- So sánh độ phức tạp và chất lượng ảnh sau các bước tiền xử lý.

---

## 2. Bộ dữ liệu CIFAR-10
- CIFAR-10 gồm **60.000 ảnh màu (RGB)** có kích thước **32×32 pixel**, chia thành **10 lớp**: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

---

## 3. Chuẩn bị dữ liệu

### 3.1. Tải xuống
- Bạn có thể tải bộ dữ liệu CIFAR-10 từ trang chính thức của Đại học Toronto:https://www.cs.toronto.edu/~kriz/cifar.html
- Tải file: cifar-10-python.tar.gz


### 3.2. Cấu trúc thư mục
Sau khi tải về, đặt file `.tar.gz` vào thư mục `data/` trong repo

> Lưu ý: File `cifar-10-python.tar.gz` không được push lên GitHub do dung lượng lớn (>100MB).  
> Khi notebook chạy, nó sẽ tự động giải nén file này vào thư mục:
> ```
> data/cifar-10-batches-py/
> ```

---

## 4. Cách chạy notebook

1. Mở file: notebooks/01_image_preproccessing.ipynb
2. Cài đặt các thư mục cần thiết
3. Chạy lần lượt các cell trong notebook để:
- Giải nén dữ liệu.
- Chuyển đổi và hiển thị ảnh mẫu.
- Tiền xử lý và so sánh các kỹ thuật.

Tiền xử lý và so sánh các kỹ thuật.

