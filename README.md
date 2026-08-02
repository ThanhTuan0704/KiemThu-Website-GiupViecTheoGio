# Kiểm thử - Website Giúp việc theo giờ

Tài liệu kiểm thử (test plan, test case, bug report) cho hệ thống đặt dịch vụ giúp việc theo giờ - đồ án tốt nghiệp, nền tảng Web & Mobile.

## Về hệ thống

- **Nền tảng:** Web (ReactJS + Laravel) & Mobile (Flutter)
- **Database:** MySQL
- **Nghiệp vụ:** Khách hàng đặt dịch vụ giúp việc theo 2 hình thức - **theo giờ** (đặt 1 lần, tính giá theo buổi) và **theo tháng** (đăng ký định kỳ, giá trọn gói) - thanh toán online/tiền mặt, đánh giá sau khi hoàn thành

## Nội dung repo

```
├── test-plan/          # Kế hoạch kiểm thử
├── test-cases/          # test-cases.xlsx - 37 test case, 4 sheet theo module
├── bug-reports/         # 6 bug report mẫu
└── README.md
```

**test-cases.xlsx** gồm 4 sheet:
- Đăng ký / Đăng nhập (10 case)
- Đặt dịch vụ (12 case)
- Thanh toán (8 case)
- Đánh giá dịch vụ (7 case)
