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

# Availability Zone giải quyết vấn đề gì?
❌ Không có AZ
Toàn bộ VM nằm trong 1 datacenter
Datacenter chết → sập toàn bộ hệ thống

✅ Có AZ
App phân bố ra nhiều AZ
1 AZ chết → app vẫn sống
📌 AZ giúp bạn:
High Availability
Fault isolation
Zero/near-zero downtime

#  Availability Zone ≠ Region (rất hay bị nhầm)
Khái niệm	                Ý nghĩa
Region	                    Khu vực địa lý (Singapore, Japan, East US…)
Availability Zone	        Datacenter vật lý bên trong Region
Pair Region	                2 region ghép cặp (ví dụ East US ↔ West US)

👉 AZ = chống lỗi DC
👉 Region Pair = chống thảm họa lớn (earthquake, war, etc.)

# Các option trong AZ
1. No infrastructure redundancy required
Giải thích: Bạn chỉ tạo một máy ảo (Single VM) duy nhất. Không có cơ chế sao lưu hay phân tán hạ tầng để bảo vệ VM này.
Khi nào dùng: * Môi trường Dev/Test (phát triển hoặc thử nghiệm).
Các ứng dụng không quan trọng, có thể chấp nhận thời gian ngừng hoạt động (downtime).
Giá cả: Rẻ nhất vì bạn chỉ trả tiền cho 1 VM. Tuy nhiên, nếu dùng ổ đĩa Premium SSD, Azure vẫn cam kết SLA 99.9%.

2. Availability Zone (Vùng khả dụng)
Giải thích: Azure sẽ đặt các VM của bạn ở các trung tâm dữ liệu (Datacenter) vật lý riêng biệt trong cùng một Region. Mỗi Zone có nguồn điện, làm mát và mạng độc lập.

Khi nào dùng: * Ứng dụng Mission-critical (cực kỳ quan trọng) cần bảo vệ khỏi lỗi toàn bộ một tòa nhà dữ liệu.
Cần mức độ sẵn sàng cao nhất (SLA lên đến 99.99%).
Giá cả: Bạn trả tiền cho số lượng VM bạn tạo (ví dụ: chạy 2 VM ở 2 Zone thì trả tiền gấp đôi). Có thể phát sinh thêm chi phí truyền dữ liệu giữa các Zone (Inter-zone data transfer), dù rất nhỏ.

3. Virtual Machine Scale Set (VMSS)
Giải thích: Giúp bạn tạo và quản lý một nhóm các VM giống hệt nhau. Nó có khả năng tự động tăng hoặc giảm số lượng VM dựa trên tải thực tế (Autoscaling).
Khi nào dùng: * Ứng dụng có lượng truy cập thay đổi liên tục (ví dụ: trang thương mại điện tử).
Cần triển khai hàng loạt VM nhanh chóng và đồng bộ.
Giá cả: Bản thân dịch vụ VMSS là miễn phí. Bạn chỉ trả tiền cho các tài nguyên mà nó tạo ra (VM, ổ đĩa, Load Balancer).

4. Availability Set (Tập hợp khả dụng)
Giải thích: Azure phân tán các VM của bạn trên các Rack (giá đỡ) khác nhau trong cùng một Datacenter. Điều này bảo vệ bạn khỏi lỗi phần cứng cục bộ hoặc khi Azure cập nhật hệ thống (Update/Fault domains).
Khi nào dùng: * Các ứng dụng truyền thống (Legacy) không hỗ trợ chạy đa vùng.
Khi Region bạn chọn không hỗ trợ Availability Zones.
SLA cam kết là 99.95%.
Giá cả: Tương tự VMSS, dịch vụ này miễn phí. Bạn chỉ trả tiền cho số lượng VM thực tế mà bạn cấu hình trong Set đó.