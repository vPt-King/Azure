Trong hệ sinh thái Microsoft Azure, Subscription (Gói đăng ký) đóng vai trò là một thực thể logic dùng để quản lý việc thanh toán và phân quyền tài nguyên.

Nếu coi Azure là một tòa nhà văn phòng khổng lồ, thì mỗi Subscription giống như một hợp đồng thuê mặt bằng riêng biệt. Bạn có thể thuê nhiều phòng (tài nguyên), nhưng tiền hóa đơn sẽ được tính dựa trên hợp đồng đó.
# Vai trò chính của Subscription
Trong hệ sinh thái Microsoft Azure, Subscription (Gói đăng ký) đóng vai trò là một thực thể logic dùng để quản lý việc thanh toán và phân quyền tài nguyên.

Nếu coi Azure là một tòa nhà văn phòng khổng lồ, thì mỗi Subscription giống như một hợp đồng thuê mặt bằng riêng biệt. Bạn có thể thuê nhiều phòng (tài nguyên), nhưng tiền hóa đơn sẽ được tính dựa trên hợp đồng đó.

# Vai trò chính của Subscription
Subscription giải quyết hai vấn đề lớn nhất của doanh nghiệp:

Quản lý Thanh toán (Billing): Mỗi Subscription sẽ nhận một hóa đơn (Invoice) riêng. Điều này giúp bạn tách biệt chi phí giữa các bộ phận (ví dụ: Team Marketing dùng Subscription A, Team Dev dùng Subscription B).

Kiểm soát truy cập (Access Control): Bạn có thể phân quyền cho ai có quyền làm gì trên một Subscription nhất định mà không ảnh hưởng đến các phần khác của doanh nghiệp.

Trong hệ sinh thái Microsoft Azure, Subscription (Gói đăng ký) đóng vai trò là một thực thể logic dùng để quản lý việc thanh toán và phân quyền tài nguyên.

Nếu coi Azure là một tòa nhà văn phòng khổng lồ, thì mỗi Subscription giống như một hợp đồng thuê mặt bằng riêng biệt. Bạn có thể thuê nhiều phòng (tài nguyên), nhưng tiền hóa đơn sẽ được tính dựa trên hợp đồng đó.

1. Vai trò chính của Subscription
Subscription giải quyết hai vấn đề lớn nhất của doanh nghiệp:

Quản lý Thanh toán (Billing): Mỗi Subscription sẽ nhận một hóa đơn (Invoice) riêng. Điều này giúp bạn tách biệt chi phí giữa các bộ phận (ví dụ: Team Marketing dùng Subscription A, Team Dev dùng Subscription B).

Kiểm soát truy cập (Access Control): Bạn có thể phân quyền cho ai có quyền làm gì trên một Subscription nhất định mà không ảnh hưởng đến các phần khác của doanh nghiệp.

# Cấu trúc phân cấp của Azure
Subscription nằm ở giữa trong mô hình quản trị của Azure:
```
+ Management Groups: (Cao nhất) Quản lý nhiều Subscription cùng lúc.

+ Subscriptions: (Hợp đồng thanh toán) Chứa các Resource Groups.

+ Resource Groups: (Thư mục logic) Nhóm các tài nguyên liên quan lại với nhau.

+ Resources: (Thực thể nhỏ nhất) VM, Database, Storage, v.v.
```

Trong hệ sinh thái Microsoft Azure, Subscription (Gói đăng ký) đóng vai trò là một thực thể logic dùng để quản lý việc thanh toán và phân quyền tài nguyên.

Nếu coi Azure là một tòa nhà văn phòng khổng lồ, thì mỗi Subscription giống như một hợp đồng thuê mặt bằng riêng biệt. Bạn có thể thuê nhiều phòng (tài nguyên), nhưng tiền hóa đơn sẽ được tính dựa trên hợp đồng đó.

1. Vai trò chính của Subscription
Subscription giải quyết hai vấn đề lớn nhất của doanh nghiệp:

Quản lý Thanh toán (Billing): Mỗi Subscription sẽ nhận một hóa đơn (Invoice) riêng. Điều này giúp bạn tách biệt chi phí giữa các bộ phận (ví dụ: Team Marketing dùng Subscription A, Team Dev dùng Subscription B).

Kiểm soát truy cập (Access Control): Bạn có thể phân quyền cho ai có quyền làm gì trên một Subscription nhất định mà không ảnh hưởng đến các phần khác của doanh nghiệp.

2. Cấu trúc phân cấp của Azure
Subscription nằm ở giữa trong mô hình quản trị của Azure:

Management Groups: (Cao nhất) Quản lý nhiều Subscription cùng lúc.

Subscriptions: (Hợp đồng thanh toán) Chứa các Resource Groups. Mỗi 1 subscription lại gắn với 1 tenant

Resource Groups: (Thư mục logic) Nhóm các tài nguyên liên quan lại với nhau.

Resources: (Thực thể nhỏ nhất) VM, Database, Storage, v.v.

# Các loại Subscription phổ biến
Tùy vào nhu cầu, bạn sẽ chọn loại hình đăng ký khác nhau:
```
+ Free Trial: Tặng một khoản tiền (khoảng $200) để dùng thử trong 30 ngày và miễn phí một số dịch vụ trong 12 tháng.

+ Pay-As-You-Go (PAYG): Dùng bao nhiêu trả bấy nhiêu. Đây là loại phổ biến nhất cho cá nhân và doanh nghiệp nhỏ.

+ Enterprise Agreement (EA): Thỏa thuận dành cho doanh nghiệp lớn với cam kết chi phí hàng năm và thường có chiết khấu cao.

+ Azure for Students: Dành cho sinh viên, không cần thẻ tín dụng, được tặng một khoản credit nhỏ mỗi năm.
```

# Tại sao một công ty cần nhiều Subscription?
Việc chỉ dùng một Subscription duy nhất đôi khi gây khó khăn. Các chuyên gia thường chia nhỏ ra vì:

Tách biệt môi trường: Một Subscription cho Production (chạy thật) và một cho Sandbox/Dev (thử nghiệm) để tránh việc vô tình xóa nhầm dữ liệu thật.

Giới hạn kỹ thuật (Quotas): Azure có giới hạn số lượng tài nguyên (như số lượng core CPU) trên mỗi Subscription. Nếu hết "room", bạn phải tạo thêm Subscription mới.

Hạch toán nội bộ: Để biết chính xác mỗi dự án tiêu tốn bao nhiêu tiền để trừ vào ngân sách của phòng ban đó.

# Lưu ý quan trọng
[!IMPORTANT] Tài khoản (Account) và Subscription là khác nhau. Một tài khoản (Email) có thể sở hữu hoặc được mời làm quản trị viên cho nhiều Subscription khác nhau.