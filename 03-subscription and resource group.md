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


🟩 2️⃣ Resource Group (RG) là gì?
✅ Định nghĩa ngắn gọn

Resource Group là nhóm logic chứa các tài nguyên liên quan, để:

Quản lý

Phân quyền

Xoá theo nhóm

Nói đơn giản:

📦 Resource Group = cái “thùng” chứa tài nguyên

📌 Resource Group dùng để làm gì?

Gom:

VM

VNet

Disk

NSG

Quản lý lifecycle:

Tạo cùng

Xoá cùng

⚠️ Xoá RG → xoá toàn bộ resource bên trong

🟨 3️⃣ Mối quan hệ Subscription ↔ Resource Group
Tenant (Azure AD)
 └── Subscription
      └── Resource Group
           ├── VM
           ├── VNet
           └── Storage


👉 Resource Group không tồn tại nếu không có Subscription

🟦 4️⃣ So sánh nhanh (rất hay bị hỏi)
Tiêu chí	Subscription	Resource Group
Cấp độ	Cao	Thấp hơn
Dùng cho	Billing, quota	Quản lý resource
Chứa	Resource Group	Resource
Xoá	Không xoá thường xuyên	Xoá thường xuyên
RBAC	Có	Có
🟩 5️⃣ Ví dụ chuẩn phỏng vấn
🧠 Tình huống

Bạn có 1 app gồm:

Frontend VM

Backend VM

Database

Network

Thiết kế đúng:

1 Subscription

1 Resource Group cho app

rg-together-dev

👉 Khi không cần → xoá RG là sạch

🟧 6️⃣ Best Practice (rất quan trọng)
✅ NÊN

Chia RG theo:

Project

Environment (dev/test/prod)

Đặt tên rõ ràng:

rg-network-dev

rg-app-prod

❌ KHÔNG NÊN

Dồn tất cả resource vào 1 RG

Dùng RG để chia tiền (sai – tiền chia theo Subscription)

🟥 7️⃣ Câu trả lời phỏng vấn 20–30 giây

Subscription là đơn vị dùng để quản lý billing, quota và phân quyền cấp cao nhất trong Azure.
Resource Group là một container logic để nhóm các tài nguyên liên quan, giúp quản lý, phân quyền và xoá tài nguyên theo vòng đời ứng dụng.

🟩 8️⃣ Liên hệ với lộ trình bạn đang học

👉 Khi học Azure “0 đồng”:

1 Subscription

Tạo nhiều Resource Group

Xoá RG sau mỗi lab → không lo phát sinh chi phí

