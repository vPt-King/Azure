Azure Resource Manager (ARM) là lớp quản lý trung tâm (control plane) của Azure — nói gọn: mọi thứ bạn tạo / sửa / xóa trên Azure đều phải đi qua ARM.



Nếu Azure là một thành phố 🏙️

thì ARM chính là “tòa thị chính” – nơi kiểm soát luật lệ, quyền hạn, và cách mọi thứ được xây dựng.



\# Azure Resource Manager là gì?



Azure Resource Manager (ARM) là dịch vụ cho phép bạn:



Triển khai (deploy) tài nguyên Azure



Quản lý vòng đời resource



Áp dụng RBAC, Policy, Tags



Quản lý infrastructure dưới dạng code



👉 Portal, CLI, PowerShell, Terraform… đều gọi ARM phía sau.



\# ARM nằm ở đâu trong kiến trúc Azure?



```

User / Tool

&nbsp;(Portal / CLI / API / Terraform)

&nbsp;       ↓

&nbsp;Azure Resource Manager (ARM)

&nbsp;       ↓

&nbsp;Resource Providers (Compute, Network, Storage...)

&nbsp;       ↓

&nbsp;Actual Resources (VM, VNET, DB, LB...)

👉 ARM không chạy VM, không xử lý data

👉 ARM chỉ ra quyết định và điều phối

```

\# ARM làm những việc gì?

🔐 1. Xác thực \& phân quyền (Authentication \& RBAC)



ARM dùng Azure AD để xác thực



Kiểm tra bạn có quyền:



Microsoft.Compute/virtualMachines/write hay không



❌ Không đủ quyền → ARM chặn ngay





2\. Áp dụng Azure Policy



Ví dụ:



Không cho tạo VM không có tag Owner



Chỉ cho deploy ở Southeast Asia



👉 ARM kiểm tra trước khi resource được tạo



3\. Quản lý Tag \& Metadata



Tag để:



Chargeback



Audit



Automation



4, Triển khai Infrastructure as Code



ARM hỗ trợ:



ARM Template (JSON) – native



Bicep – syntax gọn, hiện đại (Microsoft khuyên dùng)



Terraform → vẫn gọi ARM API

