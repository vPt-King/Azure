Azure Subscription là khái niệm cốt lõi nhất của Azure. Nếu không hiểu subscription thì rất dễ mơ hồ khi dùng cloud.

# Subscription trong Azure là gì?

Azure Subscription = hợp đồng sử dụng dịch vụ Azure giữa bạn và Microsoft
Nó xác định:
Ai trả tiền
Dùng được dịch vụ gì
Giới hạn bao nhiêu tài nguyên
Ai có quyền làm gì
📌 Không có subscription → không tạo được bất kỳ resource nào

# Subscription nằm ở đâu trong Azure hierarchy?
Azure Tenant (Azure AD)
   │
   ├── Subscription A (Dev)
   │      ├── Resource Group
   │      │     └── VM / VNet / DB
   │
   ├── Subscription B (Prod)
   │      ├── Resource Group
   │            └── App / Storage

Subscription là ranh giới quản lý & billing

# Vì sao Azure BẮT BUỘC phải có subscription?
🔹 1. Để tính tiền 💰
Azure là pay-as-you-go, nên cần subscription để:
Ghi nhận chi phí
Xuất hóa đơn
Áp ngân sách (budget)

❌ Không subscription → Azure không biết tính tiền cho ai

🔹 2. Để kiểm soát quyền (RBAC) 🔐

Bạn gán quyền theo subscription:
Owner
Contributor
Reader
Ví dụ:
Dev chỉ được dùng subscription Dev
Ops quản lý subscription Prod

🔹 3. Để giới hạn tài nguyên (Quota) 📊
Mỗi subscription có quota:
Bao nhiêu VM
Bao nhiêu core
Bao nhiêu public IP
Bao nhiêu VNet
👉 Tránh việc 1 người tạo vô hạn tài nguyên

🔹 4. Để tách môi trường (Best practice) 🧱

Thông thường:

1 subscription = 1 môi trường

Subscription	Mục đích
Dev	Test, lab
UAT	Kiểm thử
Prod	Chạy thật

# Các loại subscription phổ biến

Free Trial (200$)
Pay-As-You-Go
Enterprise Agreement (EA)
Microsoft Customer Agreement (MCA)
📌 Công ty thường dùng EA / MCA