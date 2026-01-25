# Availability zone
👉 Availability Zone = các trung tâm dữ liệu vật lý tách biệt trong cùng một Region

Mỗi AZ là 1 datacenter riêng
Có:
+ Nguồn điện riêng
+ Hệ thống làm mát riêng
+ Mạng riêng
Nhưng:
Kết nối với AZ khác bằng mạng tốc độ cao, độ trễ thấp
📌 Một Region Azure có thể có 2–3 AZ (không phải region nào cũng có).
# Ví dụ
Giả sử Azure Southeast Asia (Singapore) có:
```
Region: Southeast Asia
 ├── Availability Zone 1 (DC1)
 ├── Availability Zone 2 (DC2)
 └── Availability Zone 3 (DC3)
```
Nếu:
DC1 cháy ❌
DC2 mất điện ❌
👉 DC3 vẫn chạy bình thường