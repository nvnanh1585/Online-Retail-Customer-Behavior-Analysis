
# Phân tích hành vi khách hàng (Customer Segmentation & Retention Analysis)

## Giới thiệu

Dự án này phân tích hành vi mua sắm của khách hàng dựa trên **dữ liệu giao dịch bán lẻ trực tuyến** nhằm:

* Phân khúc khách hàng theo hành vi mua sắm
* Đánh giá mức độ **duy trì khách hàng (customer retention)**
* Trích xuất các **insight hỗ trợ chiến lược CRM và marketing**

Phân tích được thực hiện bằng các phương pháp:

* **RFM Analysis**
* **K-Means Clustering**
* **Cohort Retention Analysis**

---

## Dữ liệu

Nguồn dữ liệu: **Online Retail Dataset – UCI Machine Learning Repository**

Sau khi xử lý dữ liệu:

* **149,365 giao dịch**
* **2,748 khách hàng**

Các biến chính trong dataset:

| Biến        | Ý nghĩa             |
| ----------- | ------------------- |
| InvoiceNo   | Mã giao dịch        |
| StockCode   | Mã sản phẩm         |
| Description | Tên sản phẩm        |
| Quantity    | Số lượng sản phẩm   |
| InvoiceDate | Thời gian giao dịch |
| UnitPrice   | Giá sản phẩm        |
| CustomerID  | Mã khách hàng       |
| Country     | Quốc gia            |

---

## Quy trình phân tích

### 1. Tiền xử lý dữ liệu

* Loại bỏ các giao dịch bị huỷ
* Xử lý giá trị thiếu
* Loại bỏ các giao dịch không hợp lệ
* Tạo biến **Total Spending**

---

### 2. Phân tích khám phá dữ liệu (EDA)

Phân tích:

* Phân phối giao dịch
* Hành vi mua sắm của khách hàng
* Xu hướng doanh thu theo thời gian

---

### 3. Xây dựng đặc trưng RFM

Xây dựng ba chỉ số hành vi khách hàng:

* **Recency** – số ngày kể từ lần mua gần nhất
* **Frequency** – số lần mua
* **Monetary** – tổng chi tiêu

Các chỉ số này được dùng để đo lường **mức độ gắn kết và giá trị khách hàng**.

---

### 4. Phân khúc khách hàng

Sử dụng **K-Means Clustering** để phân nhóm khách hàng dựa trên đặc trưng RFM.

Số cụm tối ưu được xác định bằng **Elbow Method**.

Kết quả phân khúc khách hàng thành **4 nhóm hành vi**.

---

### 5. Phân tích Cohort (Customer Retention)

Thực hiện **Cohort Analysis** dựa trên tháng mua hàng đầu tiên của khách hàng nhằm đo lường **tỷ lệ quay lại mua hàng theo thời gian**.

Ma trận retention được xây dựng để theo dõi hành vi mua lặp lại của khách hàng.

---

## Kết quả chính

Phân tích cho thấy:

* Xác định **4 phân khúc khách hàng**

**Champions**

* 11.7% khách hàng
* Tạo ra **56.31% tổng doanh thu**

**Potential Loyalists**

* 32.9% khách hàng
* Tạo ra **29.29% doanh thu**

**At Risk**

* 27.8% khách hàng có nguy cơ rời bỏ

**Customer Retention**

* Tỷ lệ khách quay lại mua lần thứ hai: **25.92%**

Các kết quả này cho thấy doanh thu tập trung chủ yếu vào **nhóm khách hàng giá trị cao**, đồng thời một tỷ lệ lớn khách hàng có nguy cơ rời bỏ, gợi ý cần có chiến lược **giữ chân khách hàng và tăng customer lifetime value**.

---

## Công cụ và phương pháp

Ngôn ngữ và thư viện sử dụng:

* **Python**
* Pandas
* NumPy
* Scikit-learn
* Matplotlib / Seaborn

Phương pháp phân tích:

* RFM Analysis
* K-Means Clustering
* Elbow Method
* Cohort Analysis
* Exploratory Data Analysis (EDA)
