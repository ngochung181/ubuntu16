# Quy trình làm :

Có các tiền tố dành cho branch :
- `feature/xxx` : với xxx là tên task
- `fixbug/xxx` : checkout từ các branch trừ master
- `hotfix/xxx` : checkout từ branch master
- `release/xxx` : dành cho triển khai

1. Checkout từ branch develop ra branch mới.
```
checkout -b feature/centos6-php5.6
```

2. Viết Dockerfile và test trên môi trường máy ảo 

- Tao 1 folder ten la centos6-php5.6
- Viet Dockerfile vao thu muc tren
- Build + kiem tra tren moi truong local

3. Tạo merge request đến develop

- Neu build + test ma ok => tao merge request, assign review cho toitx
- Branch master và develop tuyệt đối không được merge và push code tùy tiện lên đó.
