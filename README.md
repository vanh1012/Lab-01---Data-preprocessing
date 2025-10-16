# **LAB 01 – TIỀN XỬ LÝ DỮ LIỆU**
# **PHẦN 01 – TIỀN XỬ LÝ DỮ LIỆU HÌNH ẢNH (IMAGE DATA PREPROCESSING)**

## **Giới thiệu**
- **Môn học:** Khai phá dữ liệu và Ứng dụng  
- **Giảng viên hướng dẫn:** ThS. Lê Nhựt Nam  
- **Sinh viên thực hiện:** Nguyễn Trần Minh Thư - 22127403

## **Mục tiêu**
- Thực hành các kỹ thuật **tiền xử lý dữ liệu hình ảnh** cơ bản trước khi huấn luyện mô hình học máy (Machine Learning / Deep Learning).  
- Hiểu rõ tác động của từng bước xử lý đến **kích thước dữ liệu, độ chi tiết ảnh và hiệu suất mô hình**.

---

## **Quy trình tiền xử lý**

### 1. Loading & Resizing  
- **Mục tiêu:** Chuẩn hóa kích thước ảnh để toàn bộ dataset có cùng độ phân giải.  
- **Dataset:** CIFAR-10 (60.000 ảnh màu 32×32 pixel, 10 lớp).  
- **Thư viện:** `torchvision`, `opencv`, `numpy`.  
- **Kích thước chuẩn:**  
  - 128×128 → nhẹ, nhanh.  
  - 224×224 → chuẩn cho hầu hết backbone CNN (ResNet, VGG, MobileNet).  
- **Thuật toán:** *Bilinear Interpolation*  
  \[
  I'(x',y') = \sum_{i=0}^{1}\sum_{j=0}^{1} w_{ij}\,I(x_i,y_j)
  \]
- **Phân tích:**  
  | Kích thước | Ưu điểm | Nhược điểm |
  |-------------|----------|-------------|
  | 128×128 | Tốc độ nhanh, tiết kiệm RAM | Mất chi tiết nhỏ |
  | 224×224 | Chi tiết tốt, phù hợp CNN | Tốn bộ nhớ hơn |

---

### 2. Grayscale Conversion  
- **Mục tiêu:** Giảm chiều dữ liệu khi màu sắc không quan trọng.  
- **Công thức chuyển đổi:**  
  \[
  Y = 0.299R + 0.587G + 0.114B
  \]
- **Thư viện:** `cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)`  
- **Đánh giá giữ thông tin:**  
  - Dùng **Var(Laplacian)** làm chỉ số đo sắc nét/chi tiết.  
  - Var cao → giữ nhiều biên; Var thấp → mất chi tiết.  
- **Kết luận:**  
  - Chuyển xám phù hợp cho ảnh X-ray, chữ viết tay, tài liệu.  
  - Không nên dùng cho bài toán cần phân biệt màu (hoa, biển báo,…).

---

### 3. Normalization & Standardization  
- **Mục tiêu:** Đưa dữ liệu pixel về cùng thang đo, giúp mô hình học ổn định.  
- **Phương pháp thực hiện:**

  | Phương pháp | Công thức | Phạm vi | Ứng dụng |
  |--------------|------------|----------|-----------|
  | **Min–Max** | \(x' = x / 255\) | [0,1] | Chuẩn cơ bản cho CNN |
  | **Symmetric** | \(x'' = 2x' - 1\) | [-1,1] | Khi dùng `tanh` |
  | **Z-score** | \(z = (x - \mu) / \sigma\) | ≈[-3,3] | Khi cần hội tụ nhanh |

- **Kết quả:**  
  - Mean ≈ 0, Std ≈ 1 sau chuẩn hóa.  
  - Dữ liệu cân bằng → mô hình tối ưu hiệu quả hơn.

---

### 4. Edge Detection (Bonus)  
- **Mục tiêu:** Trích đặc trưng hình dạng, hỗ trợ mô hình nhận diện biên/viền vật thể.  
- **Thuật toán áp dụng:**  
  - **Sobel** → nhanh, rõ biên lớn.  
  - **Prewitt** → mượt hơn Sobel.  
  - **Canny** → biên mảnh, ít nhiễu (có NMS + hysteresis).  
- **Thư viện:** `cv2.Sobel()`, `cv2.filter2D()`, `cv2.Canny()`.  

---

## **Kết quả minh họa**
| Bước | Mô tả | Kết quả |
|------|--------|----------|
| Resize | 32×32 → 224×224 | Giữ chi tiết, dễ huấn luyện |
| Gray | RGB → Xám | Giảm dung lượng, giữ biên |
| Normalize | [0,255] → [0,1] | Dữ liệu cân bằng |
| Edge | Canny, Sobel | Đường biên rõ ràng |

---

## **Công nghệ sử dụng**
- Python 3.10  
- OpenCV  
- NumPy  
- Pandas  
- Matplotlib  
- Torchvision (tùy chọn – tải CIFAR-10)

---

## **Tài liệu tham khảo**
1. CIFAR-10 Dataset: [https://www.cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html)  
2. OpenCV Documentation: [https://docs.opencv.org/](https://docs.opencv.org/)  
3. NumPy Documentation: [https://numpy.org/doc/](https://numpy.org/doc/)  
4. Scikit-learn Preprocessing: [https://scikit-learn.org/stable/modules/preprocessing.html](https://scikit-learn.org/stable/modules/preprocessing.html)  
5. Matplotlib Official Docs: [https://matplotlib.org/stable/contents.html](https://matplotlib.org/stable/contents.html)  

---

## 🧾 **Ghi chú**
- Tất cả cell code trong notebook đều có phần **markdown giải thích** chi tiết.  
- Toàn bộ ảnh được xử lý theo **batch** (không giới hạn số lượng).  
- Báo cáo viết bằng **tiếng Việt**, định dạng `.ipynb` + `.pdf`.  
- Mức hỗ trợ AI ≤ **30%** theo quy định giảng viên.

---

> 📍 *Sinh viên thực hiện: Nhóm Vũ Anh – Quách Châu Hạo Kiệt – Nguyễn Trần Minh Thư (Khoa CNTT, ĐH KHTN)*  
> *TP. Hồ Chí Minh, tháng 10 năm 2025*
