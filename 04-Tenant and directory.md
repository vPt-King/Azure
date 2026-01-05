🟦 1️⃣ Tenant là gì?
✅ Định nghĩa dễ hiểu

Tenant là tổ chức (organization) trong Azure, đại diện cho một công ty hoặc một cá nhân trong hệ sinh thái Microsoft.

Nói nôm na:

🏢 Tenant = “công ty” của bạn trên Azure

Tenant chứa những gì?

Users

Groups

Service Principal

Policies

Identity

👉 Toàn bộ danh tính (identity) nằm trong Tenant.

Ví dụ

Công ty ABC tạo Azure

Azure tạo 1 Tenant riêng cho ABC

Nhân viên ABC login bằng account trong tenant đó

🟩 2️⃣ Directory là gì?
❗ Kết luận quan trọng

🔥 Tenant = Directory (trong 99% trường hợp)

Directory là cách gọi Azure AD (nay là Microsoft Entra ID) gắn với Tenant.

Nói dễ hiểu:

📒 Directory = “danh bạ người dùng” của tenant

Directory chứa:

User account

Group

App registration

Role

👉 Directory chỉ lo identity, không chứa VM, VNet.

🟨 3️⃣ Vì sao Azure hay dùng 2 từ này?
Thuật ngữ	Dùng khi nói về
Tenant	Khái niệm tổ chức
Directory	Dịch vụ identity

👉 Về bản chất: 1 tenant ↔ 1 directory

🟦 4️⃣ Mối quan hệ Tenant – Subscription – Resource Group
Tenant (Azure AD / Entra ID)
 └── Subscription
      └── Resource Group
           └── Resources


📌 Ghi nhớ:

Tenant quản lý identity

Subscription quản lý tiền & quota

RG quản lý tài nguyên

🟩 5️⃣ Ví dụ thực tế (rất dễ hiểu)
Trường hợp cá nhân học Azure

1 Microsoft account

1 Tenant (directory mặc định)

1 Subscription Free / PayG

Trường hợp công ty

1 Tenant (abc.onmicrosoft.com)

Nhiều Subscription:

Prod

Dev

Test

👉 Nhân viên login 1 lần → dùng nhiều subscription

🟥 6️⃣ Câu trả lời phỏng vấn (chuẩn 30 giây)

Tenant là ranh giới tổ chức cao nhất trong Azure, đại diện cho một công ty hoặc tổ chức và chịu trách nhiệm quản lý identity.
Directory là Azure Active Directory (Microsoft Entra ID) gắn với tenant, nơi lưu trữ users, groups và các thông tin xác thực.
Trong hầu hết trường hợp, tenant và directory là cùng một thực thể, chỉ khác cách gọi theo ngữ cảnh.

🟧 7️⃣ Những lỗi hay gặp của người mới

❌ Nghĩ tenant chứa VM
❌ Nghĩ directory là thư mục lưu file
❌ Nghĩ subscription cao hơn tenant (sai)

🟩 8️⃣ Liên hệ với việc bạn đang học Azure

Khi bạn tạo:

User → bạn đang thao tác Directory

VM / VNet → bạn đang thao tác Subscription

Phân quyền → nối Directory ↔ Subscription bằng RBAC