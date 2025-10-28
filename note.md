# 🧩 Phân tích các mối quan hệ giữa các Use Case trong UML

## 1. Association (Liên kết – Quan hệ kết nối)

### 🔹 Khái niệm
- Là mối quan hệ cơ bản nhất giữa **tác nhân (Actor)** và **Use Case**, hoặc giữa **các Use Case**.
- Thể hiện rằng hai thành phần có **liên quan hoặc tương tác**, **không có sự phụ thuộc** hay gọi lẫn nhau.
- Không có hướng, không có thứ tự thực hiện.

### 🔹 Ví dụ
- Người dùng có thể *xem đánh giá sản phẩm* trước khi *đặt hàng*.
  → Hai Use Case có liên quan, nhưng không bắt buộc gọi nhau.

### 🔹 Khi nào dùng
- Khi các Use Case **chia sẻ dữ liệu hoặc tương tác chung**, nhưng **không phụ thuộc**.

### 🔹 Ký hiệu
- Đường thẳng **không có mũi tên** giữa hai Use Case (hoặc Actor ↔ Use Case).


---

## 2. Include (Bao gồm – Bắt buộc thực hiện)

### 🔹 Khái niệm
- Dùng khi **một Use Case luôn cần gọi Use Case khác** để hoàn thành chức năng của mình.
- Là **mối quan hệ phụ thuộc bắt buộc**.
- Giúp **tái sử dụng hành vi chung** trong nhiều Use Case khác nhau.

### 🔹 Hướng
👉 Mũi tên đi từ **Use Case chính → Use Case được bao gồm**.

### 🔹 Ví dụ
- Khi *Đặt hàng*, hệ thống **luôn** phải *Kiểm tra giỏ hàng* trước khi tạo hóa đơn.
- Khi *Đề xuất hóa đơn*, hệ thống **luôn** cần *Kiểm tra giỏ hàng* để lấy thông tin sản phẩm.

### 🔹 Khi nào dùng
- Khi **một hành động lặp đi lặp lại** trong nhiều Use Case khác nhau hoặc **bắt buộc** phải có.

### 🔹 Ký hiệu
- Mũi tên nét đứt, ghi `<<include>>` trên đường nối.


---

## 3. Extend (Mở rộng – Tùy chọn)

### 🔹 Khái niệm
- Dùng khi **một Use Case có thể được mở rộng** bởi một Use Case khác.
- Là **mối quan hệ tùy chọn**, chỉ xảy ra khi **điều kiện cụ thể** được thỏa mãn.
- Không ảnh hưởng đến hoạt động chính.

### 🔹 Hướng
👉 Mũi tên đi từ **Use Case mở rộng → Use Case chính**.

### 🔹 Ví dụ
- Khi *Đặt hàng*, người dùng **có thể** *Xem đánh giá sản phẩm* (không bắt buộc).
- Khi *Kiểm tra giỏ hàng*, người dùng **có thể** *Đặt hàng* nếu sẵn sàng mua.

### 🔹 Khi nào dùng
- Khi muốn thể hiện **hành động phụ hoặc tùy chọn** có thể xảy ra trong Use Case chính.

### 🔹 Ký hiệu
- Mũi tên nét đứt, ghi `<<extend>>` trên đường nối.


---

## 🔄 So sánh tổng hợp

| Đặc điểm | Association | Include | Extend |
|-----------|--------------|----------|---------|
| **Mục đích** | Thể hiện có liên quan | Tái sử dụng hành vi bắt buộc | Thêm hành vi tùy chọn |
| **Hướng mũi tên** | Không có | Từ Use Case chính → phụ | Từ Use Case mở rộng → chính |
| **Tính bắt buộc** | Không | Bắt buộc | Không bắt buộc |
| **Khi nào dùng** | Có tương tác, nhưng độc lập | Khi Use Case chính luôn cần hành vi đó | Khi có tùy chọn hoặc điều kiện đặc biệt |
| **Ví dụ** | “Xem đánh giá” ↔ “Đặt hàng” | “Đặt hàng” → “Kiểm tra giỏ hàng” | “Xem đánh giá” → “Đặt hàng” |

---

## 💡 Gợi ý minh họa sơ đồ

```plaintext
    +------------------+
    |   Đặt hàng       |
    +------------------+
           | <<include>>
           v
    +------------------+
    | Kiểm tra giỏ hàng|
    +------------------+

    +------------------+
    | Xem đánh giá     |
    +------------------+
           ^
           | <<extend>>
    +------------------+
    |   Đặt hàng       |
    +------------------+
