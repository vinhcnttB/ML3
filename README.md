# Stock Analysis Dashboard

Ứng dụng phân tích và dự đoán giá cổ phiếu với LSTM sử dụng Dash và Plotly.

## Tính năng

- **Dashboard tương tác** với 2 tab:
  - Tab 1: Phân tích cổ phiếu TATA với dự đoán LSTM
  - Tab 2: So sánh nhiều cổ phiếu (AAPL, FB, MSFT, TSLA)
- **Mô hình LSTM** dự đoán giá dựa trên 60 ngày trước
- **Biểu đồ tương tác** với Plotly

## 🛠 Công nghệ

- **Python** - Ngôn ngữ chính
- **Dash & Plotly** - Dashboard
- **TensorFlow** - Mô hình LSTM
- **Pandas & NumPy** - Xử lý dữ liệu

## Cấu trúc Project

```
ML3/
├── stock_app.py        #  Dashboard web chính
├── stock_pred.py       #  Mô hình LSTM
├── NSE-TATA.csv       #  Dữ liệu TATA Global
├── stock_data.csv     #  Dữ liệu đa cổ phiếu
└── README.md          #  Tài liệu này
```

## Cách chạy

### 1. Cài đặt thư viện

```bash
pip install dash plotly pandas numpy tensorflow scikit-learn matplotlib
```

### 2. Chạy dashboard

```bash
python stock_app.py
```

### 3. Mở trình duyệt

Truy cập: **http://127.0.0.1:8050/**

## Cách sử dụng

### Tab 1: NSE-TATA Analysis

- Xem biểu đồ giá đóng cửa thực tế
- So sánh với dự đoán LSTM

### Tab 2: Multi-Stock Comparison

- Chọn cổ phiếu từ dropdown
- Xem biểu đồ giá cao/thấp và volume

## 🎯 Train mô hình (tùy chọn)

```bash
python stock_pred.py
```

## Dữ liệu

- **NSE-TATA.csv**: Dữ liệu cổ phiếu TATA Global
- **stock_data.csv**: Dữ liệu 4 cổ phiếu (AAPL, FB, MSFT, TSLA)

## Yêu cầu

- Python 3.8+
- RAM: 4GB+

## Lỗi thường gặp

- **ImportError**: Cài lại thư viện bị thiếu
- **File not found**: Kiểm tra file CSV tồn tại
- **Port in use**: Thay đổi port trong stock_app.py
