# Test Plan — Hành trình khách hàng (Customer Journey)

**Dự án:** Hệ thống cung cấp dịch vụ giúp việc theo giờ
**Nền tảng:** Web (ReactJS) & Mobile (Flutter)
**Người viết:** Đặng Thanh Tuấn
**Ngày viết:** *15/11/2025*

## 1. Mục tiêu (Objective)

Kiểm thử toàn bộ hành trình sử dụng dịch vụ của khách hàng: từ đăng ký/đăng nhập, đặt dịch vụ giúp việc theo giờ, thanh toán, đến đánh giá sau khi dịch vụ hoàn thành — đảm bảo mỗi bước hoạt động đúng nghiệp vụ, xử lý tốt các trường hợp nhập liệu không hợp lệ và các tình huống bất thường (mất mạng, thao tác trùng lặp...).

## 2. Phạm vi kiểm thử (Scope)

**Trong phạm vi — 4 module chính:**

| Module | Nội dung kiểm thử |
|---|---|
| Đăng ký / Đăng nhập | Đăng ký bằng SĐT, đăng nhập bằng SĐT hoặc mạng xã hội (Google), đăng xuất, các ràng buộc bảo mật cơ bản |
| Đặt dịch vụ | Chọn hình thức dịch vụ (theo giờ / theo tháng), địa chỉ, thời gian hoặc lịch định kỳ, báo giá tạm tính, áp mã khuyến mãi, xác nhận đặt |
| Thanh toán | Thanh toán trực tuyến (Momo, ZaloPay, Napas, Visa/Mastercard) và thanh toán tiền mặt sau khi hoàn thành |
| Đánh giá dịch vụ | Đánh giá số sao, nhận xét, thêm nhân viên vào danh sách yêu thích sau khi đơn hoàn thành |

**Ngoài phạm vi (kiểm thử riêng, không thuộc bản kế hoạch này):**
- Chức năng phân công nhân viên giúp việc cho đơn hàng (phía nhân viên/điều phối viên)
- Chức năng quản lý khuyến mãi, quản lý khách hàng/nhân viên phía Quản trị viên
- Chức năng thống kê, báo cáo doanh thu

## 3. Phương pháp kiểm thử (Test Approach)

- Kiểm thử thủ công (Manual Testing) trên cả 2 nền tảng: Web và Mobile
- Kỹ thuật áp dụng:
  - **Equivalence Partitioning** (phân vùng tương đương) — ví dụ: nhóm loại dịch vụ hợp lệ/không hợp lệ
  - **Boundary Value Analysis** (phân tích giá trị biên) — ví dụ: thời gian đặt dịch vụ tối thiểu trước giờ thực hiện, diện tích/thời lượng tối thiểu-tối đa
  - **Negative Testing** — bỏ trống trường bắt buộc, nhập sai định dạng, chọn thời gian quá khứ

## 4. Môi trường kiểm thử (Test Environment)

| Thành phần | Chi tiết |
|---|---|
| Nền tảng Web | Trình duyệt Chrome, Firefox (bản mới nhất) |
| Nền tảng Mobile | Ứng dụng Flutter (Android) |
| Backend | Laravel (PHP) |
| Cơ sở dữ liệu | MySQL |
| Tài khoản test | Tài khoản khách hàng đã đăng ký, đã đăng nhập thành công |

## 5. Tiêu chí bắt đầu / kết thúc (Entry / Exit Criteria)

**Entry Criteria:**
- Chức năng Đăng ký/Đăng nhập hoạt động ổn định
- Hệ thống đã có dữ liệu mẫu: danh sách loại dịch vụ, bảng giá, khu vực phục vụ
- Tài khoản test đã có sẵn địa chỉ được lưu (hoặc có thể nhập địa chỉ mới)

**Exit Criteria:**
- 100% test case trong phạm vi đã được thực thi
- Không còn bug mức độ Critical/High chưa xử lý
- Các bug Medium/Low đã được ghi nhận đầy đủ vào Bug Report

## 6. Rủi ro (Risks)

| Rủi ro | Mức độ | Giải pháp |
|---|---|---|
| Không có đủ dữ liệu mẫu để test hết các loại dịch vụ và mức giá | Trung bình | Chuẩn bị bộ dữ liệu test trước khi thực thi |
| Môi trường test không ổn định do là hệ thống đồ án sinh viên, chưa qua môi trường production | Trung bình | Ghi chú rõ môi trường test trong từng báo cáo |
| Logic tính giá tạm tính phức tạp (phụ phí ngoài gói cơ bản) khó test đầy đủ trường hợp | Trung bình | Ưu tiên test các trường hợp phổ biến trước, mở rộng dần |

## 7. Danh sách hạng mục kiểm thử (Test Items)

Chi tiết tại file `test-cases/test-cases.xlsx`, gồm 4 sheet tương ứng 4 module:

- Sheet `01_Dang ky - Dang nhap`: TC_AUTH_001 → TC_AUTH_010
- Sheet `02_Dat dich vu`: TC_BOOKING_001 → TC_BOOKING_012
- Sheet `03_Thanh toan`: TC_PAYMENT_001 → TC_PAYMENT_008
- Sheet `04_Danh gia dich vu`: TC_REVIEW_001 → TC_REVIEW_007
