# Resource Group là gì? (định nghĩa chuẩn nhưng dễ hiểu)

👉 Resource Group = một “container logic” để gom các tài nguyên Azure lại với nhau

Không phải VPC
Không phải subnet
Không phải datacenter
Chỉ là lớp quản lý (management layer)

📌 Mục đích chính:
Quản lý
Phân quyền
Theo dõi chi phí
Vận hành vòng đời (lifecycle)

# Resource Group dùng để làm gì?
🔹 1. Quản lý vòng đời (Lifecycle)
Tạo
Update
Xóa cả cụm
👉 Xóa RG = xóa toàn bộ resource bên trong
📌 Rất mạnh → rất nguy hiểm nếu dùng sai

🔹 2. Phân quyền (RBAC)
Gán quyền cho user / group / service principal
Áp dụng cho tất cả resource trong RG
Ví dụ:
Dev chỉ có quyền RG dev
Prod chỉ admin được đụng

🔹 3. Quản lý chi phí (Cost Management)
Azure billing group theo RG
Dễ biết:
App nào tốn tiền
Môi trường nào đốt tiền

🔹 4. Áp policy & tagging
Azure Policy
Tag (env, owner, project)
👉 RG là điểm bám tốt nhất

# Resource Group KHÔNG làm gì?

❌ Không cô lập network
❌ Không giới hạn region
❌ Không là boundary bảo mật thực sự
❌ Không ảnh hưởng performance

👉 Security thực nằm ở IAM + network + service