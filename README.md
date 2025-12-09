# 📈 Stock Price Analysis Dashboard

Một ứng dụng web phân tích và dự đoán giá cổ phiếu sử dụng Machine Learning (LSTM) và Dashboard tương tác được xây dựng bằng Dash và Plotly.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Dash](https://img.shields.io/badge/Dash-2.0+-green.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0+-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 🚀 Tính năng chính

### 📊 Dashboard tương tác

- **Tab 1 - NSE-TATA Analysis**: Phân tích sâu cổ phiếu TATA Global với dự đoán LSTM
- **Tab 2 - Multi-Stock Comparison**: So sánh nhiều cổ phiếu (Tesla, Apple, Facebook, Microsoft)
- Biểu đồ tương tác với zoom, pan, range selector

### 🤖 Machine Learning

- **Mô hình LSTM** (Long Short-Term Memory) để dự đoán giá cổ phiếu
- Sử dụng 60 ngày trước để dự đoán giá ngày tiếp theo
- Train trên 987 ngày đầu, test trên phần còn lại

### 📈 Phân tích kỹ thuật

- Hiển thị giá Open, High, Low, Close
- Phân tích khối lượng giao dịch
- So sánh giá thực tế vs dự đoán

## 🛠️ Công nghệ sử dụng

- **Frontend**: Dash, Plotly
- **Backend**: Python, Pandas, NumPy
- **Machine Learning**: TensorFlow/Keras, Scikit-learn
- **Data Processing**: Pandas, NumPy
- **Visualization**: Plotly, Matplotlib

## 📋 Yêu cầu hệ thống

- Python 3.8 trở lên
- RAM: 4GB trở lên (khuyến nghị 8GB)
- Dung lượng: 2GB trống

## 🔧 Cài đặt

### 1. Clone repository

```bash
git clone <repository-url>
cd ML3
```

### 2. Cài đặt các thư viện cần thiết

```bash
pip install dash plotly pandas numpy scikit-learn matplotlib tensorflow
```

Hoặc sử dụng requirements.txt:

```bash
pip install -r requirements.txt
```

### 3. Chuẩn bị dữ liệu

Đảm bảo có 2 file CSV trong thư mục gốc:

- `NSE-TATA.csv` - Dữ liệu cổ phiếu TATA (2020-2023)
- `stock_data.csv` - Dữ liệu cổ phiếu các công ty khác

## 🚀 Cách chạy

### 1. Train mô hình LSTM (tùy chọn)

```bash
python stock_pred.py
```

Script này sẽ:

- Load dữ liệu từ `NSE-TATA.csv`
- Train mô hình LSTM
- Lưu mô hình vào `saved_lstm_model.h5`
- Hiển thị biểu đồ so sánh kết quả

### 2. Chạy Dashboard

```bash
python stock_app.py
```

### 3. Truy cập ứng dụng

Mở trình duyệt và truy cập: **http://127.0.0.1:8050/**

## 📁 Cấu trúc Project

```
ML3/
├── stock_app.py          # Dashboard chính (Dash web app)
├── stock_pred.py         # Script train mô hình LSTM
├── NSE-TATA.csv         # Dữ liệu cổ phiếu TATA (2020-2023)
├── stock_data.csv       # Dữ liệu cổ phiếu các công ty khác
├── saved_lstm_model.h5  # Mô hình LSTM đã train (tự động tạo)
└── README.md           # Tài liệu hướng dẫn
```

## 📊 Dữ liệu

### NSE-TATA.csv

```csv
Date,Open,High,Low,Close,Volume
2020-01-01,101.05,101.72,100.16,100.99,1101404
...
```

### stock_data.csv

```csv
Date,High,Low,Volume,Stock
2020-01-01,150.20,148.50,1500000,FB
...
```

## 🎯 Cách sử dụng

### Tab 1 - NSE-TATA Analysis

1. Xem biểu đồ giá đóng cửa thực tế theo thời gian
2. So sánh với dự đoán từ mô hình LSTM
3. Phân tích xu hướng và độ chính xác

### Tab 2 - Multi-Stock Comparison

1. Chọn cổ phiếu từ dropdown (Tesla, Apple, Facebook, Microsoft)
2. Xem biểu đồ giá cao nhất/thấp nhất
3. Phân tích khối lượng giao dịch
4. Sử dụng các công cụ zoom, pan để khám phá chi tiết

## 🔬 Mô hình LSTM

### Kiến trúc

- **Input Layer**: 60 timesteps (60 ngày trước)
- **LSTM Layer 1**: 50 units, return_sequences=True
- **LSTM Layer 2**: 50 units
- **Dense Output**: 1 unit (giá dự đoán)

### Huấn luyện

- **Loss Function**: Mean Squared Error
- **Optimizer**: Adam
- **Training Data**: 987 ngày đầu (80%)
- **Validation Data**: Phần còn lại (20%)

### Độ chính xác

Mô hình đạt được độ chính xác cao trong việc dự đoán xu hướng giá cổ phiếu trong ngắn hạn.

## 🛠️ Tùy chỉnh

### Thay đổi dữ liệu

1. Cập nhật file CSV với dữ liệu mới
2. Đảm bảo format đúng: `Date,Open,High,Low,Close,Volume`
3. Chạy lại `stock_pred.py` để train lại mô hình

### Tùy chỉnh mô hình

Trong `stock_pred.py`, bạn có thể:

- Thay đổi số units trong LSTM layers
- Điều chỉnh số epochs
- Thêm Dropout layers để tránh overfitting

### Tùy chỉnh Dashboard

Trong `stock_app.py`, bạn có thể:

- Thêm các tab mới
- Tùy chỉnh layout và styling
- Thêm các indicator kỹ thuật khác

## 🐛 Xử lý sự cố

### Lỗi import TensorFlow

```bash
pip uninstall tensorflow
pip install tensorflow==2.12.0
```

### Lỗi Dash callback

Đảm bảo sử dụng Dash version mới nhất:

```bash
pip install --upgrade dash
```

### Lỗi dữ liệu

Kiểm tra format ngày tháng trong CSV phải là: `YYYY-MM-DD`

## 📈 Kế hoạch phát triển

- [ ] Thêm các chỉ báo kỹ thuật (RSI, MACD, Bollinger Bands)
- [ ] Tích hợp API real-time data
- [ ] Thêm notification system
- [ ] Export báo cáo PDF
- [ ] Thêm portfolio management

## 🤝 Đóng góp

1. Fork repository
2. Tạo feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Tạo Pull Request

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.

## 🙏 Acknowledgments

- [Dash Documentation](https://dash.plotly.com/)
- [TensorFlow Keras Guide](https://www.tensorflow.org/guide/keras)
- [Yahoo Finance API](https://pypi.org/project/yfinance/)
- [Plotly Documentation](https://plotly.com/python/)

---
