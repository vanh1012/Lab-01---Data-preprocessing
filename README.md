

# Bài tập Lab 01 — Tiền xử lý dữ liệu

Kho chứa này chứa các notebook và dữ liệu mẫu dùng cho Lab 1 (Tiền xử lý dữ liệu) trong môn Khai phá dữ liệu. Các bài tập minh họa quy trình tiền xử lý phổ biến cho ba loại dữ liệu: ảnh, dữ liệu bảng (tabular) và văn bản. Các notebook được thiết kế để có thể chạy lại (reproducible) và dễ tùy chỉnh.

Mục tiêu chính
- Minh họa các bước tiền xử lý tiêu chuẩn cho dữ liệu ảnh, bảng và văn bản.
- Tạo bộ dữ liệu sạch, đồng nhất, sẵn sàng cho bước huấn luyện mô hình.
- Cung cấp các notebook ngắn, có chú thích rõ ràng để sinh viên thực hành và mở rộng.

Giảng viên / Khóa học
- Môn: Khai phá dữ liệu và Ứng dụng
- Giảng viên hướng dẫn: ThS. Lê Nhựt Nam

Thành viên nhóm
| Họ và tên | MSSV | Phần phụ trách |
|---|---:|---|
| Nguyễn Trần Minh Thư | 22127405 | Tiền xử lý dữ liệu hình ảnh |
| Quách Châu Hạo Kiệt | 23127078 | Tiền xử lý dữ liệu văn bản |
| Vũ Anh | 23127321 | Tiền xử lý dữ liệu bảng |

## Cấu trúc

Các tệp và thư mục chính
- `requirements.txt` — danh sách phụ thuộc Python cho các notebook
- `README.md` — tệp README
- `data/` — chứa dữ liệu mẫu
   - `image/dataset/` — tập ảnh dùng trong notebook ảnh
   - `tabular/fraudTest.csv` — dữ liệu mẫu cho tiền xử lý tabular
   - `text/IMDB Dataset.csv` — dữ liệu đánh giá phim (IMDB) cho bài xử lý văn bản
- `notebooks/` — các Jupyter notebook cho từng loại dữ liệu
   - `01_Image_Preprocessing.ipynb`
   - `02 _tabular_preprocessing.ipynb`
   - `03_Text_Preprocessing.ipynb`

## Mô tả ngắn các bộ dữ liệu

- Dữ liệu ảnh (`data/image/dataset/`)
   - Tập ảnh mẫu dùng để minh họa cách thay đổi kích thước (resize), chuyển sang grayscale, chuẩn hóa và phát hiện biên (edge detection). (README gốc có tham chiếu CIFAR-10 — notebook minh họa tương tự trên dữ liệu cung cấp trong thư mục.)

- Dữ liệu bảng (`data/tabular/fraudTest.csv`)
   - Ví dụ nhỏ dùng để thực hành: xử lý giá trị thiếu, mã hóa biến phân loại, chuẩn hóa dữ liệu, và phân tích khám phá cơ bản.

- Dữ liệu văn bản (`data/text/IMDB Dataset.csv`)
   - Bộ dữ liệu đánh giá phim dùng để minh họa tiền xử lý văn bản: làm sạch, tách từ, loại bỏ stopwords, và chuyển sang biểu diễn số (TF-IDF v.v.).

## Hướng dẫn chạy (tóm tắt)

1. Tạo môi trường Python (khuyến nghị):

```bash
# Trên Windows (bash)
python -m venv .venv
source .venv/Scripts/activate
```

2. Cài đặt phụ thuộc:

```bash
pip install -r requirements.txt
```

3. Khởi động Jupyter Lab / Notebook và mở các notebook:

```bash
jupyter lab
# hoặc
jupyter notebook
```

4. Mở một notebook trong `notebooks/` và chạy từ trên xuống (run cells top-to-bottom). Mỗi notebook có phần mô tả ngắn ở đầu giải thích mục đích và dữ liệu vào.

## Tóm tắt nội dung từng notebook

- `01_Image_Preprocessing.ipynb`
   - Minh họa: đọc ảnh, resize (ví dụ 128×128 và 224×224), chuyển RGB → grayscale, chuẩn hóa (Min–Max, symmetric, Z-score), và tuỳ chọn phát hiện biên (Sobel/Canny). Phù hợp với pipeline chuẩn cho CNN.

- `02 _tabular_preprocessing.ipynb`
   - Minh họa: đọc `data/tabular/fraudTest.csv`, xử lý giá trị thiếu, mã hoá biến phân loại (one-hot / label), chuẩn hoá (MinMax, StandardScaler), cùng các bước EDA cơ bản (histogram, correlation).

- `03_Text_Preprocessing.ipynb`
   - Minh họa: đọc `data/text/IMDB Dataset.csv`, làm sạch văn bản, tokenization, loại stopwords, stemming/lemmatization (tuỳ chọn), và chuyển văn bản sang biểu diễn số (TF-IDF / CountVectorizer).

## Phụ thuộc

Danh sách phụ thuộc chi tiết nằm trong `requirements.txt`. Các thư viện thường dùng trong notebook gồm:

- numpy, pandas, matplotlib, scikit-learn, opencv-python, nltk (hoặc spaCy), jupyter

Hãy cài bằng `pip install -r requirements.txt` trước khi chạy các notebook.


## Tài liệu tham khảo

- Scikit-learn preprocessing: https://scikit-learn.org/stable/modules/preprocessing.html
- OpenCV docs: https://docs.opencv.org/
- CIFAR-10 dataset (tham khảo): https://www.cs.toronto.edu/~kriz/cifar.html




