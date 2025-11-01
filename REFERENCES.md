# Tài liệu tham khảo

Tài liệu tham khảo và nguồn hữu ích liên quan đến ba notebook trong thư mục `notebooks/`:

---

## 1) Image Preprocessing

- OpenCV — hướng dẫn và API (Sobel, Canny, nội suy, lọc...)
  - https://docs.opencv.org/
- Pillow (PIL) — thao tác ảnh với Python
  - https://pillow.readthedocs.io/
- Góc nhìn tổng quan về xử lý ảnh (sách tham khảo):
  - Rafael C. Gonzalez & Richard E. Woods — "Digital Image Processing" (bài đọc nền tảng về nội suy, lọc, biến đổi và chỉ số ảnh).
- Canny edge detector (gốc):
  - J. Canny, "A Computational Approach to Edge Detection", IEEE Trans. PAMI, 1986.
- Sobel / Prewitt operators — tham khảo khái niệm và triển khai:
  - https://en.wikipedia.org/wiki/Sobel_operator
  - https://en.wikipedia.org/wiki/Prewitt_operator
- Thuật toán nội suy ảnh (Lanczos, bicubic, bilinear, nearest):
  - https://en.wikipedia.org/wiki/Image_scaling

---

## 2) Tabular Preprocessing

- pandas — đọc/tiền xử lý dữ liệu dạng bảng
  - https://pandas.pydata.org/docs/
- scikit-learn — chuẩn hóa, mã hóa, lựa chọn đặc trưng
  - Preprocessing: StandardScaler, RobustScaler, OneHotEncoder
    - https://scikit-learn.org/stable/modules/preprocessing.html
  - Feature selection: VarianceThreshold, correlation pruning
    - https://scikit-learn.org/stable/modules/feature_selection.html
- Một số tài liệu tham khảo hữu ích về feature engineering / preprocessing:
  - Aurélien Géron — "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" (tham khảo cách chuẩn hoá, encoding, feature selection)
  - Alice Zheng & Amanda Casari — "Feature Engineering for Machine Learning" (ý tưởng thực tiễn về biến đổi & mã hoá)

---

## 3) Text Preprocessing

- NLTK — Tokenization, stopwords, POS tagging, WordNet, lemmatization
  - https://www.nltk.org/
- Porter stemming algorithm
  - M. F. Porter, "An algorithm for suffix stripping", 1980. (Porter Stemmer)
- WordNet (từ điển ngữ nghĩa cho lemmatization)
  - https://wordnet.princeton.edu/
- Scikit-learn text utilities — CountVectorizer, TfidfVectorizer
  - https://scikit-learn.org/stable/modules/feature_extraction.html#text-feature-extraction
- Byte Pair Encoding (BPE) / subword units (tham khảo cho phần BPE trong notebook)
  - Sennrich, Haddow & Birch, "Neural Machine Translation of Rare Words with Subword Units", 2016. https://arxiv.org/abs/1508.07909
- IMDB movie review dataset (dataset used trong notebook)
  - Andrew L. Maas et al., "Learning Word Vectors for Sentiment Analysis", 2011. Large Movie Review Dataset (IMDB): https://ai.stanford.edu/~amaas/data/sentiment/

---

## 4) Thư viện & công cụ khác

- NumPy
  - https://numpy.org/
- Matplotlib / Seaborn (visualization)
  - https://matplotlib.org/ ; https://seaborn.pydata.org/
- scikit-image (tham khảo thêm về xử lý ảnh nếu cần)
  - https://scikit-image.org/

