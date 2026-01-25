# Region
Trong Azure, Region là một khu vực địa lý cụ thể nơi Microsoft đặt data center để chạy các dịch vụ cloud. Nói đơn giản:

Region = vị trí địa lý (datacenter location) mà tài nguyên Azure của bạn được triển khai.

🔹 Ví dụ về Region

Southeast Asia → Singapore

East Asia → Hong Kong

Japan East → Tokyo

West Europe → Hà Lan

East US → Virginia (Mỹ)

Khi bạn tạo VM, Database, Storage…, bạn phải chọn 1 region.

# Region gồm những gì?

Một Azure Region thường bao gồm:

Nhiều datacenter vật lý

Kết nối mạng độ trễ thấp

Có thể hỗ trợ:

Availability Zone

Backup

Disaster Recovery

# Tại sao Region quan trọng?
1️⃣ Độ trễ (Latency)

Người dùng ở Việt Nam → chọn Southeast Asia (Singapore) sẽ nhanh hơn East US.

2️⃣ Tuân thủ pháp lý (Compliance)

Một số dữ liệu bắt buộc phải lưu trong quốc gia/khu vực nhất định.

3️⃣ Giá tiền 💰

Cùng 1 dịch vụ nhưng region khác → giá khác

Ví dụ VM ở US thường rẻ hơn châu Á.

4️⃣ Khả năng dịch vụ

Không phải dịch vụ nào cũng có ở mọi region

Một số dịch vụ AI / preview chỉ có ở vài region.
# Region ≠ Availability Zone (hay bị nhầm)
Khái niệm	            Nghĩa
Region	                Khu vực địa lý lớn (Singapore, Japan East…)
Availability Zone	    Nhiều datacenter độc lập trong cùng 1 region
Availability Set	    Logical grouping để tránh cùng fault/update domain

👉 Ví dụ:
Southeast Asia có thể có Zone 1, Zone 2, Zone 3

# Region Pair là gì? (bonus hay gặp trong exam 😄)

Mỗi region có 1 region pair

Ví dụ:

Southeast Asia ↔ East Asia

Azure update luân phiên giữa region pair

Dùng cho Disaster Recovery