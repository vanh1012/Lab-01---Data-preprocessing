## Lab 01 — Tiền xử lý dữ liệu (Data Preprocessing)

Thành viên nhóm bao gồm:

Nguyễn Trần Minh Thư - 22127405 - Tiền xử lý dữ liệu hình ảnh
Phan Vũ Anh - 23127321 - Tiền xử lý dữ liệu bảng
Quách Châu Hạo Kiệt - 23127078 - Tiền xử lý dữ liệu văn bản

Tài liệu này mô tả nội dung, cấu trúc và hướng dẫn tái tạo (reproducibility) cho Lab 01 — một bộ notebook minh họa các bước tiền xử lý dữ liệu cho dữ liệu ảnh, bảng và văn bản.

### Thành viên / Contributors

| Họ và tên | MSSV | Phần phụ trách |
|---|---:|---|
| Nguyễn Trần Minh Thư | 22127405 | Tiền xử lý dữ liệu hình ảnh |
| Vũ Anh | 23127321 | Tiền xử lý dữ liệu bảng |
| Quách Châu Hạo Kiệt | 23127078 | Tiền xử lý dữ liệu văn bản |

### Tóm tắt (Abstract)

Mục tiêu của repository là cung cấp một pipeline tiền xử lý minh họa, có thể chạy lại được, để sinh viên thực hành các bước tiền xử lý chuẩn: làm sạch dữ liệu, mã hoá biến, chuẩn hoá, trích đặc trưng (feature engineering) và xuất artefact (bảng/ảnh/manifest). Các notebook đều kèm ví dụ, trực quan hóa và lưu kết quả để dùng tiếp cho mô hình hoá.

### Quick facts

- Ngôn ngữ: Python 3.8+ (khuyến nghị 3.10+)
- Môi trường: Jupyter Notebook / JupyterLab
- Thư viện chính: numpy, pandas, scikit-learn, matplotlib, opencv-python, pillow, nltk

### Nội dung chính

Thư mục `notebooks/` chứa 3 notebook tương ứng ba loại dữ liệu:

- `01_Image_Preprocessing.ipynb` — đọc/chuẩn hóa/resize ảnh, benchmark nội suy, edge detection (Sobel/Prewitt/Canny), xuất ảnh demo và các CSV kết quả.
- `02_tabular_preprocessing.ipynb` — EDA nhanh, xử lý giá trị thiếu, chuẩn hóa (Z-score / Robust), mã hoá phân loại (One-Hot / Frequency), feature selection (VarianceThreshold, correlation pruning).
- `03_Text_Preprocessing.ipynb` — làm sạch văn bản, tokenization, stopword removal, stemming/lemmatization, vectorization (Count / TF-IDF) và trực quan hóa.

Mỗi notebook có phần mô tả đầu file, cấu hình đường dẫn dữ liệu và các biến cấu hình để bạn dễ chỉnh.

### Dữ liệu 

- `data/image/` — ảnh mẫu, kèm khả năng tạo ảnh synthetic nếu không có tập thật.
- `data/tabular/fraudTest.csv` — dataset mẫu cho tiền xử lý tabular (ví dụ: phát hiện gian lận).
- `data/text/IMDB Dataset.csv` — bộ dữ liệu đánh giá phim (IMDB) dùng cho tiền xử lý văn bản.

Ghi chú: các notebook đã cấu hình đường dẫn tương đối (ví dụ `../data/...`). Nếu bạn mở notebook từ folder `notebooks/`, đường dẫn sẽ đúng.

### Kết quả mong đợi

Khi chạy từng notebook (từ trên xuống), bạn sẽ nhận được:

- Các file CSV tổng hợp (benchmark, stats, manifests) được lưu trong `outputs/` (hoặc `notebooks/outputs` tuỳ cấu hình trong notebook).
- Các ảnh minh họa / figure trong thư mục `outputs/figs` hoặc `outputs/demo_export`.
- DataFrame đã tiền xử lý có thể được lưu lại để dùng cho bước huấn luyện tiếp theo.

### Reproducibility — cách chạy nhanh

1) Tạo môi trường ảo và kích hoạt (Windows, bash):

```bash
python -m venv .venv
source .venv/Scripts/activate
```

2) Cài phụ thuộc:

```bash
pip install -r requirements.txt
```

3) Khởi động Jupyter và mở notebook bạn cần:

```bash
jupyter lab   # hoặc `jupyter notebook`
```

4) Chạy các cell từ trên xuống. Nếu notebook dùng biến `OUT_ROOT`, kiểm tra/đổi đường dẫn nếu cần.

### Cấu trúc repository

```
.
├─ data/
│  ├─ image/
│  ├─ tabular/
│  └─ text/
├─ notebooks/
│  ├─ 01_Image_Preprocessing.ipynb
│  ├─ 02_tabular_preprocessing.ipynb
│  └─ 03_Text_Preprocessing.ipynb
├─ requirements.txt
├─ README.md
└─ REFERENCES.md
```

### Tài liệu tham khảo

Xem `REFERENCES.md` để biết danh sách các nguồn, thư viện và bài báo/công cụ tham chiếu liên quan.







