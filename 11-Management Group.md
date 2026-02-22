\# Management Groups

Management Groups trong Azure hiểu đơn giản là “thư mục cấp cao nhất” để quản lý nhiều subscription cùng lúc 👌



Nếu ví Azure như một công ty lớn thì:

```

Tenant (Azure AD)

&nbsp;└── Management Group

&nbsp;     └── Management Group con (optional)

&nbsp;          └── Subscription

&nbsp;               └── Resource Group

&nbsp;                    └── Resource

```



We can apply budget, RBAC, Policy 

