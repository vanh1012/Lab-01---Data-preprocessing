# 📘 **LAB 01 – TIỀN XỬ LÝ DỮ LIỆU (DATA PREPROCESSING)**

## 🧠 **Giới thiệu đồ án**
- **Môn học:** Khai phá dữ liệu và Ứng dụng  
- **Giảng viên hướng dẫn:** ThS. Lê Nhựt Nam  

### 👩‍💻 **Thành viên nhóm**
| Họ và tên            | MSSV     | Vai trò |
|----------------------|----------|----------|
| Nguyễn Trần Minh Thư | 22127405 | Tiền xử lý dữ liệu hình ảnh |
| Quách Châu Hạo Kiệt  | 23127078 | Tiền xử lý dữ liệu bảng |
| Vũ Anh               | 23127321 | Tiền xử lý dữ liệu ... |

**Mục tiêu đồ án:**  
Xây dựng và trình bày quy trình **tiền xử lý dữ liệu (data preprocessing)** cho ba dạng dữ liệu phổ biến trong học máy:  
1. **Dữ liệu hình ảnh (Image Data)**  
2. **Dữ liệu bảng (Tabular Data)**  
3. **Dữ liệu khác (Text / Time-series / Audio)**  

Mục tiêu là giúp nhóm hiểu rõ vai trò của tiền xử lý trong pipeline học máy, chuẩn bị dữ liệu sạch, thống nhất và tối ưu cho mô hình.

---

## 🧩 **Tiền xử lý dữ liệu hình ảnh**
**Bộ dữ liệu:** CIFAR-10  
**Công cụ & Thư viện:** Python, OpenCV, NumPy, Matplotlib, Pandas, Torchvision  

### Các bước thực hiện:
1. **Loading & Resizing**  
   - Nạp toàn bộ ảnh từ CIFAR-10.  
   - Chuẩn hóa kích thước 128×128 và 224×224 bằng **bilinear interpolation**.  
   - So sánh trade-off giữa kích thước ảnh và chi phí bộ nhớ.  

2. **Grayscale Conversion**  
   - Chuyển RGB → Grayscale theo công thức:  
     \[ Y = 0.299R + 0.587G + 0.114B \]
   - Đánh giá mức giữ chi tiết bằng **Var(Laplacian)**.  

3. **Normalization & Standardization**  
   - Thực hiện ba phương pháp chuẩn hóa:
     | Phương pháp | Công thức | Phạm vi |
     |--------------|------------|---------|
     | Min–Max | \(x' = x/255\) | [0,1] |
     | Symmetric | \(x'' = 2x'-1\) | [-1,1] |
     | Z-score | \(z = (x-\mu)/\sigma\) | ≈[-3,3] |

4. **Edge Detection (Bonus)**  
   - Áp dụng Sobel, Prewitt, Canny để trích đặc trưng biên, phục vụ nhận dạng hình dạng.  

**Kết quả:**  
Ảnh sau xử lý được đồng nhất kích thước, giữ chi tiết biên, histogram sau chuẩn hóa thể hiện dữ liệu cân bằng và ổn định, sẵn sàng cho huấn luyện CNN.

---

## 📊 **Tiền xử lý dữ liệu bảng**

## Điền vào chỗ trống

---

## 🔤 **Tiền xử lý dữ liệu khác**

## Điền vào chỗ trống

---

## 📚 **Tài liệu tham khảo**
1. CIFAR-10 Dataset – [https://www.cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html)  
2. OpenCV Documentation – [https://docs.opencv.org/](https://docs.opencv.org/)  
3. NumPy Documentation – [https://numpy.org/doc/](https://numpy.org/doc/)  
4. Scikit-learn Preprocessing – [https://scikit-learn.org/stable/modules/preprocessing.html](https://scikit-learn.org/stable/modules/preprocessing.html)  
5. Matplotlib Documentation – [https://matplotlib.org/stable/contents.html](https://matplotlib.org/stable/contents.html)  
6. NLTK Toolkit – [https://www.nltk.org/](https://www.nltk.org/)  

---
