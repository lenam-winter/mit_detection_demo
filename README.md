# AgriVision – Hệ thống nhận dạng và phân loại độ chín trái mít 

Ứng dụng AI phục vụ Nông nghiệp Thông minh.  
Kết hợp **YOLOv8**, **Streamlit**, và **FastAPI** để phân tích hình ảnh, video, và dữ liệu cây trồng.

---

## 🌿 Cấu trúc thư mục

```
mit_detection_demo/
│
├── frontend/
│ ├── app.py
│ ├── assets/
│ ├── fonts/
│ ├── pages/
│ │ ├── home_page.py
│ │ ├── login_page.py
│ │ ├── analysis_page.py
│ │ ├── video_page.py
│ │ ├── stats_page.py
│ │ ├── compare_page.py
│ │ ├── chat_page.py
│ │ └── account_page.py
│ └── utils/
│   └── helpers.py
│
├── backend/
│ ├── auth.py
│ ├── config.py
│ ├── main.py
│ ├── model_loader.py
│ ├── mongodb_connection.py
│ ├── predictor.py
│ └── utils.py
│
├── yolov8/
│ └── best.pt
│
└── requirements.txt
```

---

## 📦 requirements.txt

```txt
# === FRONTEND ===
streamlit
streamlit-option-menu
pandas
numpy
matplotlib
plotly
opencv-python
pillow
requests
python-dotenv
ultralytics
reportlab
google-generativeai

# === BACKEND ===
fastapi
uvicorn
pydantic
python-multipart
pymongo
pandas
numpy
opencv-python
ultralytics
pillow
python-dotenv

# === COMMON UTILS ===
tqdm
typing-extensions
```
---

## ⚙️ Cài đặt môi trường

```bash
# 1. Tạo môi trường ảo
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

# 2. Cài thư viện
cd mit_detection_demo
pip install -r requirements.txt
```

---

## 🚀 Chạy hệ thống

### 🔹 1. Chạy backend (FastAPI)

```bash
cd mit_detection_demo
uvicorn main:app --reload
```

Mặc định API chạy tại: [http://127.0.0.1:8000](http://127.0.0.1:8000)

**Endpoints chính:**
- `POST /auth/login` — Đăng nhập
- `POST /auth/register` — Đăng ký
- `POST /predict` — Dự đoán độ chín qua ảnh

---

### 🔹 2. Chạy frontend (Streamlit)

```bash
cd mit_detection_demo
streamlit run app.py
```

Ứng dụng mở tại: [http://localhost:8501](http://localhost:8501)

---

## 🔑 Cấu hình API Key

Tạo file `.env` trong thư mục `frontend/` với nội dung:

```env
GEMINI_API_KEY=your_google_gemini_key_here
MONGO_URI=your_mongodb_key_here
db = client["your_database_key_here"]
```

---

## 💡 Tính năng chính

- **Phân tích ảnh**: Dùng YOLOv8 nhận dạng độ chín và sâu bệnh
- **Phân tích video / webcam**: Phát hiện real-time
- **Thống kê & biểu đồ**: Lưu và hiển thị kết quả theo thời gian
- **So sánh mô hình YOLOv8**: Đánh giá độ chính xác giữa các model
- **Chat AgriVision**: Tư vấn kỹ thuật trồng, gợi ý xử lý theo dữ liệu hình ảnh
- **Quản lý tài khoản**: Đăng ký, đăng nhập, và lưu hồ sơ người dùng

---

## 🧠 Công nghệ sử dụng

| Thành phần | Mô tả |
|--------------------------|----------------------------|
| **Streamlit** | Giao diện người dùng |
| **FastAPI** | Backend REST API |
| **YOLOv8 (Ultralytics)** | Nhận dạng vật thể |
| **Google Generative AI** | Chat & trợ lý AI |
| **MongoDB / JSON** | Lưu trữ dữ liệu người dùng |
| **Plotly / Matplotlib** | Trực quan hóa kết quả |

---

## 📸 Demo giao diện

| Trang | Mô tả |
|-----------------|-------------------------------|
| Trang chủ | Giới thiệu hệ thống |
| Đăng nhập | Quản lý người dùng |
| Phân tích ảnh | Upload & nhận dạng hình ảnh |
| Video/Webcam | Phát hiện real-time |
| Thống kê | Hiển thị dữ liệu và biểu đồ |
| So sánh YOLOv8 | Đánh giá model |
| Chat AgriVision | Tương tác AI |
| Tài khoản | Thông tin người dùng |

---

## 🧩 Giấy phép

MIT License © 2025 — AgriVision Project Nam
