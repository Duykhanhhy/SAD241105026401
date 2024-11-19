## LAB 1 
PHÂN TÍCH KIẾN TRÚC, CƠ CHẾ, CA SỬ DỤNG

## Mục đích
Phân tích kiến trúc và ca sử dụng hệ thống "Payroll System" trong file tài liệu yêu cầu đính kèm.

## Thực hiện
1. Phân tích yêu cầu để đề xuất kiến trúc phù hợp cho bài toán, giải thích
2. Phân tích yêu cầu để đề xuất các cơ chế (phân tích) cần giải quyết trong bài toán
3. Tiền hành phân tích 02 ca sử dụng: Select Payment và Maintain Timecard.

# 1. Phân tích kiến trúc
Đề xuất kiến trúc, giải thích lý do lựa chọn và ý nghĩa từng thành phần trong kiến trúc, vẽ biểu đồ package mô tả kiến trúc.
- Kiến trúc 3 lớp (3-tier architecture):
   - Thường được sử dụng cho các ứng dụng web, gồm 3 lớp: lớp trình bày (presentation layer), lớp nghiệp vụ (business logic layer) và lớp dữ liệu (data access layer).
- Lý do lựa chọn kiến trúc:
    - Kiến trúc 3 lớp là một lựa chọn phổ biến cho các hệ thống như Payroll System vì nó mang lại nhiều lợi ích về cấu trúc, khả năng bảo trì và mở rộng
  
-  Ý nghĩa từng thành phần:
   - Lớp trình bày: Giao diện người dùng (web, mobile app), các form nhập liệu, báo cáo.
   - Lớp nghiệp vụ: Các quy tắc tính lương, quản lý nhân viên, tính thuế, các thuật toán tính toán.
   - Lớp dữ liệu: Cơ sở dữ liệu lưu trữ thông tin nhân viên, lương, bảng chấm công,...
## Biểu đồ Package mô tả kiến trúc:

![Diagram](https://www.planttext.com/api/plantuml/png/P9112W8n34NtEKKlC7UOGLsu4yK3X1ebs4bB6WKHJ-R28ta5YsBfwFR_z_C_UTuVVJPKEuq14leZ7iYjb3A9eN4KTmNd0-RijfbqAKQwHqzVSHR5D8P02ZUe1uQK0lkV_8Rqp2NPSFCu8ZV8GepjCY7GSF2UYbcfDQMOsQA-oSdOhckxeTrHh4_Tdrehe2VPbKUy0000__y30000)

## 2.Cơ chế phân tích
1.Phân tích nhu cầu:
- Mục tiêu: Xác định rõ ràng mục tiêu của bài toán, những gì cần đạt được.
- Đối tượng: Ai là người sử dụng hệ thống, họ cần gì từ hệ thống.
- Điều kiện: Những điều kiện ràng buộc, giới hạn khi giải quyết bài toán.
2. Phân tích chức năng:
- Mục tiêu: Phân chia bài toán thành các chức năng nhỏ hơn.
- Phương pháp:
- Phân tích luồng dữ liệu: Theo dõi sự di chuyển của dữ liệu qua hệ thống.
- Phân tích các trường hợp sử dụng: Mô tả các tương tác giữa người dùng và hệ thống.
- Phân tích các quá trình: Mô tả các hoạt động xảy ra trong hệ thống.
3. Phân tích đối tượng:
- Mục tiêu: Xác định các đối tượng trong bài toán và mối quan hệ giữa chúng.
- Phương pháp:
- Phân tích các danh từ: Tìm các danh từ trong mô tả bài toán để xác định các đối tượng.
- Phân tích các động từ: Tìm các động từ để xác định các hành động mà các đối tượng thực hiện.
4. Phân tích dữ liệu:
- Mục tiêu: Xác định loại dữ liệu, cấu trúc dữ liệu cần sử dụng.
- Phương pháp:
- Phân tích các loại dữ liệu: Số, chữ, ngày tháng, hình ảnh,...
- Phân tích mối quan hệ giữa các dữ liệu: Liên kết, phụ thuộc,...
5. Phân tích thuật toán:
- Mục tiêu: Lựa chọn thuật toán phù hợp để giải quyết các vấn đề con.
- Phương pháp:
- So sánh các thuật toán: Đánh giá ưu nhược điểm của từng thuật toán.
- Xác định độ phức tạp: Đánh giá thời gian và không gian thực thi của thuật toán.
6. Phân tích giao diện:
- Mục tiêu: Thiết kế giao diện người dùng thân thiện, dễ sử dụng.
- Phương pháp:
- Phân tích các tương tác: Người dùng tương tác với hệ thống như thế nào.
- Thiết kế giao diện: Sử dụng các nguyên tắc thiết kế giao diện người dùng.

## 3.Phân tích ca sử dụng Payment

3.1 Các lớp phân tích cho ca sử dụng Payment :
- Customer (Khách hàng):
  - Thuộc tính: id, name, email, address, phoneNumber, paymentMethods (danh sách các phương thức thanh toán), orders (danh sách các đơn hàng).
  - Hành vi: Đăng ký tài khoản, cập nhật thông tin cá nhân, xem lịch sử đơn hàng.
   
- Payment (Giao dịch thanh toán):
  - Thuộc tính: id, amount, status (thanh toán thành công, thất bại, chờ xử lý), paymentMethod, order, createdAt, updatedAt.
  - Hành vi: Tạo một giao dịch thanh toán mới, cập nhật trạng thái thanh toán.

- PaymentMethod (Phương thức thanh toán):

  - Thuộc tính: id, name, type (thẻ tín dụng, ví điện tử), details (thông tin chi tiết về phương thức thanh toán).
  - Hành vi: Thêm một phương thức thanh toán mới.

- PaymentGateway (Cổng thanh toán):
  - Thuộc tính: id, name, url.
  - Hành vi: Thực hiện giao dịch thanh toán, xác thực thông tin thanh toán, trả về kết quả thanh toán.

- Order (Đơn hàng):
  - Thuộc tính: id, totalAmount, status (đã đặt hàng, đang giao hàng, đã giao hàng, đã hủy), customer, items (danh sách các sản phẩm), payment (giao dịch thanh toán liên quan).
  - Hành vi: Tạo một đơn hàng mới, cập nhật trạng thái đơn hàng.

- Product (Sản phẩm):
  - Thuộc tính: id, name, price, description.
  - Hành vi: Không có hành vi cụ thể trong ngữ cảnh này.
## Biểu đồ Sequence:
- Khách hàng gửi yêu cầu thanh toán đến hệ thống.
- Hệ thống gọi đến đối tượng Payment để tạo một giao dịch thanh toán mới.
- Đối tượng Payment gọi đến PaymentGateway để thực hiện thanh toán.
- PaymentGateway gửi yêu cầu đến ngân hàng và nhận phản hồi.
- PaymentGateway trả kết quả về cho đối tượng Payment.
- Đối tượng Payment cập nhật trạng thái của đơn hàng.

## Nhiệm vụ của từng lớp:
- Customer:
Lưu trữ thông tin cá nhân (tên, địa chỉ, số điện thoại, email).
Thực hiện các hành động liên quan đến thanh toán (chọn phương thức thanh toán, xem lịch sử giao dịch).
- Payment:
Đại diện cho một giao dịch thanh toán.
Lưu trữ thông tin về phương thức thanh toán, số tiền, trạng thái.
Gọi đến PaymentGateway để thực hiện thanh toán.
Cập nhật trạng thái của đơn hàng.
- PaymentMethod:
Lưu trữ thông tin về các phương thức thanh toán (tên, mã).
- PaymentGateway:
Giao tiếp với ngân hàng hoặc các nhà cung cấp dịch vụ thanh toán khác.
Xác thực thông tin thanh toán.
Thực hiện việc chuyển tiền.
Trả về kết quả thanh toán.
- Order:
Lưu trữ thông tin về đơn hàng (sản phẩm, số lượng, tổng tiền).
Liên kết với đối tượng Payment.
## Thuộc tính và quan hệ
- Customer: id, name, address, email, paymentMethods (một khách hàng có thể có nhiều phương thức thanh toán).
- Payment: id, amount, status, paymentMethod (một phương thức thanh toán), order (một giao dịch thanh toán thuộc về một đơn hàng).
- PaymentMethod: id, name, code.
- PaymentGateway: id, url.
- Order: id, totalAmount, status, customer (một đơn hàng thuộc về một khách hàng), payment (một đơn hàng có thể có nhiều giao dịch thanh toán).

## Biểu đồ mô tả lớp phân tích:
![Diagram](https://www.planttext.com/api/plantuml/png/Z5D1QiCm4Bpx5SB7WZyWYWabfQT2mO6Sr_6c5hKbevL8JEdBUkYJ-eLAjcmvZMbwCQlTsTcTaVpz-RKX0zhOjaaE3H2nnxPhL8_8tXF6Cb5n9gJneOGMEIkC5lBLdpj5mWWbENi9aSzMs3cw5gNXR3l7lbAYnACmv3ZGt3-CfppvICBWYUNcu1882sX0zvnLofODHf8uyc-QkM4dMYngn6iy1YFuR8dFrifgsYlzXX4vEBW5uw3-EpJBQf686g5VtGrQPRrZGSx8QImjPQ_lOwRzUPGovE6CmUeTdFEh5PxHrAhwfqcXvybfEK5_isb-Gkd96KKEbh8iovVl8K9ge9JT-NBSVx8fFIezjgxKB26DnGj94T1fTK0Yh5ZPNm23ZjzBA0y9xpAon9BpCTcuYtN_oWy0003__mC0)

## 4. Phân tích ca sử dụng Maintain Timecard

## Các lớp phân tích cho ca sử dụng:
  - Employee: Đại diện cho nhân viên, chứa thông tin cá nhân, phòng ban, vị trí.
  - Timecard: Đại diện cho bảng chấm công của một nhân viên trong một khoảng thời gian cụ thể.
  - Project: Đại diện cho một dự án mà nhân viên tham gia.
  - Task: Đại diện cho một công việc cụ thể trong dự án.
## Biểu đồ Senquence
- Employee đăng nhập vào hệ thống.
- System hiển thị danh sách các timecard của nhân viên.
- Employee chọn một timecard để chỉnh sửa.
- System hiển thị chi tiết của timecard, bao gồm các task đã thực hiện, thời gian làm việc.
- Employee cập nhật thông tin về thời gian làm việc, task đã hoàn thành.
- System lưu lại các thay đổi và cập nhật thông tin trong cơ sở dữ liệu.
- ## Nhiệm vụ của Từng Lớp Phân Tích
- Employee: Thực hiện việc tạo, chỉnh sửa, xem xét timecard của mình.
- Timecard: Lưu trữ thông tin về thời gian làm việc, các task đã hoàn thành của một nhân viên trong một khoảng thời gian cụ thể.
- Project: Lưu trữ thông tin về dự án.
- Task: Lưu trữ thông tin về các công việc trong dự án.
## Thuộc tính và quan hệ:
- Employee có quan hệ 1:N với Timecard (một nhân viên có nhiều timecard)
- Timecard có quan hệ 1:1 với Employee, 1:N với Task
- Project có quan hệ 1:N với Task
- Task có quan hệ 1:1 với Project, N:N với Timecard (một task có thể thuộc nhiều timecard, một timecard có thể bao gồm nhiều task)
## Biểu đồ lớp : Biểu đồ lớp sẽ mô tả các lớp trên, với các thuộc tính và phương thức của từng lớp, đồng thời chỉ ra các quan hệ giữa chúng.

![Diagram](https://www.planttext.com/api/plantuml/png/b5EnRjim4Dtv5GTDQM4FNJKbZeNQXOqOiTFCD7MmsKYaG1wB1a6dVa7HgUZSiLEtQiZG_eY-eB_Gesn92Te2xI3ewV7nzDuT-RE-F_Ka7OMo4AIfG9ZefduNuCVxflu0YwR-L87QQo3TVBidXXRE9QoR-WjCc_gpsS5IQaFym4QNgAJBXP1RJqugbXVIUvX8ZvdXyhTm9m36EazXOSqkOkLG4kPdbCAKGQH2bJ-YtWfng9ELLM5l4G7V49hyzy96bfZ2cfm-5C-nucmbcbYgnt6bibwJjYQ5rH4n2qeMAXJypuqbMSniSFxQkXlCJvwaeDkTuCEsrDHbFUa0D-W0MFdQwdnmtIl-vheTG4mwj81rZudzuALp4lTHy35lVBVvBQ5_q80_1UgYi3yqeJpkXZiGwwl9ShxPPDCHdArMbnSl8xhCNcJdp3t88_tDVqp0AwUhGwi76ZstAmwvjTGdgfosZclnL8wejzaHqUZYude4osmwlrgEO3P_FeF1tShPLyWdxvyCygx-J2NF4XYF8NcQ31DBGNt_AlhFk1Obh6oRaC9MMjZnHIb5IoIq3qtzKRMoenCXJja8twzV0000__y30000)
