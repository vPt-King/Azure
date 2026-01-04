# VNet là gì? 

Azure VNet = mạng private do bạn tự thiết kế trên Azure, nơi các tài nguyên (VM, App, DB…) giao tiếp với nhau bằng IP private.

📌 Mặc định:

VNet cô lập với Internet

Bạn toàn quyền kiểm soát IP, routing, security

# VNet tương đương gì trong on-prem?
On-prem	                            Azure
LAN / VLAN	                        VNet
Subnet	                            Subnet
Router	                            Azure Virtual Router
Firewall	                        NSG / Azure Firewall
VPN / MPLS	                        VPN Gateway / ExpressRoute

# Cấu trúc cơ bản của Vnet
Azure VNet (10.0.0.0/16)
│
├── Subnet-Frontend (10.0.1.0/24)
│     └─ VM / App Service
│
├── Subnet-Backend (10.0.2.0/24)
│     └─ API / Service
│
└── Subnet-DB (10.0.3.0/24)
      └─ Database
Subnet dùng để tách layer (frontend / backend / db)

# IP trong VNet

Dùng IP private

10.0.0.0/8

172.16.0.0/12

192.168.0.0/16

Azure cấp phát IP động hoặc tĩnh

Không cần NAT khi các resource nói chuyện nội bộ

# VNet có tự ra Internet không?

👉 CÓ, nhưng theo cách Azure thiết kế:
🔹 Outbound (ra Internet)
Mặc định VM có thể ra Internet
Thông qua Azure default gateway + SNAT

🔹 Inbound (từ Internet vào)
KHÔNG vào được nếu không cấu hình
Cần:
Public IP
Load Balancer
Application Gateway
Azure Firewall


# Giao tiếp giữa các VNet
🔹 VNet Peering
Kết nối VNet ↔ VNet
Private IP nói chuyện trực tiếp
Không qua Internet
VNet-A 10.0.0.0/16  ←→  VNet-B 10.1.0.0/16

🔹 Kết nối On-prem ↔ Azure
Site-to-Site VPN
Point-to-Site VPN
ExpressRoute (leased line)
On-prem LAN ── VPN ── Azure VNet


# Routing trong VNet
Azure có router ảo mặc định:
Route giữa các subnet
Route ra Internet

Bạn có thể:
Tạo User Defined Route (UDR)
Ép traffic qua:
Firewall
NVA (FortiGate, Palo Alto)
📌 Rất giống việc bạn dùng FortiGate on-prem.

# Bảo mật trong VNet
🔹 NSG (Network Security Group)
Lọc traffic L3/L4
Giống ACL / firewall cơ bản

🔹 Azure Firewall / NVA
Firewall đúng nghĩa
Stateful
Centralized


# Tóm tắt cực ngắn

🔹 VNet = mạng private trên Azure
🔹 Subnet để chia tầng
🔹 Private IP là mặc định
🔹 Internet chỉ vào khi bạn cho phép
🔹 Tư duy giống hệt network on-prem