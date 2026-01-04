🟩 GIAI ĐOẠN 1 – NỀN TẢNG AZURE (Tuần 1–2)
🎯 Mục tiêu

Hiểu Azure hoạt động logic như thế nào, không bị ngợp.

Học gì?

Azure Global Infrastructure

Region / Availability Zone

Subscription / Resource Group

Azure Portal vs Azure CLI

ARM là gì (chưa cần Terraform)

Lab miễn phí

✔️ Tạo:

1 Resource Group

1 VNet

1 Subnet

Không tạo VM

💬 Câu hỏi phỏng vấn:

“Tại sao Azure cần Subscription?”
→ để billing, quota, phân quyền

🟩 GIAI ĐOẠN 2 – NETWORK (Tuần 3)

Network là phần quan trọng nhất khi đi phỏng vấn

Học gì?

VNet vs On-prem LAN

Subnet

NSG (inbound / outbound)

Public IP vs Private IP

NAT trong Azure

Lab 0 đồng

✔️ Tạo:

1 VNet

2 subnet

1 NSG (chặn/cho SSH)

Không cần VM

💬 Phỏng vấn hay hỏi:

“NSG khác firewall truyền thống chỗ nào?”

🟩 GIAI ĐOẠN 3 – VM (Tuần 4)
Học gì?

Azure VM

Size B1s (free tier)

Managed Disk

OS Disk vs Data Disk

Auto-shutdown

Lab

✔️ Tạo:

1 Linux VM (B1s)

SSH vào

Cài nginx

Bật auto shutdown

👉 Chỉ bật VM 10–15 phút/ngày → không tốn tiền

🟩 GIAI ĐOẠN 4 – STORAGE (Tuần 5)
Học gì?

Storage Account

Blob / File / Queue / Table

Hot vs Cool vs Archive

Lab

✔️ Tạo:

1 Blob container

Upload file

Public vs Private access

💬 Phỏng vấn:

“Blob Storage khác gì NAS?”

🟩 GIAI ĐOẠN 5 – DATABASE (Tuần 6)

Phù hợp DBA / Backend

Học gì?

Azure SQL vs SQL on VM

PaaS vs IaaS

Backup & Restore concept

Lab

✔️ Dùng:

Azure SQL Basic (free 12 tháng)

Tạo DB

Tạo table

Insert / select

🟩 GIAI ĐOẠN 6 – IDENTITY & SECURITY (Tuần 7)
Học gì?

Azure AD

User / Group

RBAC

Managed Identity (rất hay bị hỏi)

Lab

✔️ Tạo:

User

Assign role Reader / Contributor

Test quyền

💬 Phỏng vấn:

“RBAC khác IAM của AWS không?”

🟩 GIAI ĐOẠN 7 – MONITORING (Tuần 8)
Học gì?

Azure Monitor

Log Analytics

Alert rule

Lab

✔️:

Bật monitor cho VM

Xem CPU / memory

Tạo alert CPU > 80%

🟩 GIAI ĐOẠN 8 – TỔNG HỢP (Tuần 9–10)
Mini Project (rất ăn điểm CV)
User → Internet → NSG → VM (Nginx)
                    ↘ Azure SQL
Logs → Azure Monitor


👉 Viết vào CV:

“Designed and deployed a basic Azure infrastructure with VNet, NSG, VM, Azure SQL, and monitoring using Azure Monitor.”