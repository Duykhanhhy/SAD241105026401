## LAB 1 
PHÂN TÍCH KIẾN TRÚC, CƠ CHẾ, CA SỬ DỤNG

## Mục đích
Phân tích kiến trúc và ca sử dụng hệ thống "Payroll System" trong file tài liệu yêu cầu đính kèm.

# 1. Phân tích kiến trúc
Đề xuất kiến trúc, giải thích lý do lựa chọn và ý nghĩa từng thành phần trong kiến trúc, vẽ biểu đồ package mô tả kiến trúc.
![Diagram](https://www.planttext.com/api/plantuml/png/T98x3i8m38RtdC9YxnKG81uB20HSm4ejL957vQH3XJWP0qVY2hHfeq897ZBu_nr_Tl9wFCNCUMHVQILAb5Uy44mEMBDL2awrywGdS1FGH3W63vCZuz4Nri0MQ-BeQqCgT0wszbAOjMKzoZVtwwOsePmBJH8vJqX7AYqFDNVnpREeN66eRoh_4VMJxT0qHJmILxfKjYPAgn4jhNPq6pB4w2qd4PVe4UPI1ieqNqHOplVfdVqAaIigVTVFzmdD8Ckc4BSKbXJImVoR3kuMkEFjh7Sn8vEtNqM8Dm000F__0m00)
 
 ## Giải thích Biểu đồ Package
Presentation Layer bao gồm các biểu mẫu hoặc màn hình cho phép người dùng tương tác với hệ thống như:

* LoginForm: Biểu mẫu đăng nhập để xác thực người dùng.
* PaymentForm: Biểu mẫu để nhân viên chọn và cập nhật phương thức thanh toán.
* TimecardForm: Biểu mẫu cho phép nhân viên cập nhật và gửi bảng chấm công.
* ReportForm: Biểu mẫu cho phép tạo và xem các báo cáo liên quan đến lương và thời gian làm việc.
* Business Logic Layer chứa các thành phần chính đảm bảo thực thi các quy trình nghiệp vụ:
* PayrollManager: Xử lý các quy trình liên quan đến bảng lương của nhân viên.
* EmployeeManager: Quản lý thông tin và các quy trình liên quan đến nhân viên.
* TimecardManager: Xử lý và quản lý thông tin chấm công.
* ReportGenerator: Tạo các báo cáo lương và thời gian làm việc dựa trên dữ liệu.
* Data Access Layer chứa các lớp DAO (Data Access Object) để tương tác với cơ sở dữ liệu:
* EmployeeDAO: Thao tác với dữ liệu của nhân viên.
* PaymentDAO: Quản lý thông tin thanh toán.
* TimecardDAO: Xử lý các thao tác liên quan đến dữ liệu chấm công.
## 3. Phân tích ca sử dụng Payment
Xác định các lớp phân tích cho ca sử dụng Payment, mô tả được hành vi thông qua biểu đồ sequence, xác định được nhiệm vụ của từng lớp phân tích, xác định một số thuộc tính và quan hệ giữa các lớp phân tích. Kết quả mong đợi là các biểu đồ lớp mô tả lớp phân tích và giải thích.

![Diagram](https://www.planttext.com/api/plantuml/png/R94xRiCm38PtdO8No98nGv6Nqyb8q287O2qsDMezAb4DShOEFLAlKDAn0pZ8P43VzvE_vB-VtsLcJ5nSPx3XaA1aie0PAXFbl6tQY9xXW1T7ddSXEOM7tOHMBdRXGjJdN7oKhD7ZYL8VhXy9szLUeNmcTBkU6rF1x4bsmWBsaVoO06rZv5YWR1NwJ0nDIKbX72H7_16iKK67rAAzq5UXpC01IhJ8T2-B9QusMi0hVXDuEjyxIbLQpqKwNiVG-0vJ5reFml4DCnaDp6xJLysd3-UEx8c6BjV1OzLDyE-jl7cM5dsjsrs7bKsGdSHapPAyrT_u3m00__y30000)
Giải thích Biểu đồ Sequence:

* Employee (E) mở giao diện PaymentForm để thay đổi phương thức thanh toán của mình.
* PaymentForm yêu cầu lớp Employee (Emp) lấy phương thức thanh toán hiện tại.
* Employee (Emp) gửi yêu cầu đến PaymentManager (PM) để cập nhật phương thức thanh toán.
* PaymentManager (PM) gọi PaymentDAO (DAO) để lưu phương thức thanh toán mới vào cơ sở dữ liệu.
* PaymentDAO (DAO) kết nối với cơ sở dữ liệu (DB2) để thực hiện cập nhật phương thức thanh toán.
* DB2 gửi phản hồi xác nhận lại cho PaymentDAO (DAO).
* PaymentDAO (DAO) xác nhận lại với PaymentManager (PM) rằng quá trình lưu trữ đã hoàn tất.
* PaymentManager (PM) thông báo cho Employee (Emp) rằng phương thức thanh toán đã được cập nhật thành công.
* 
![Diagram](https://www.planttext.com/api/plantuml/png/T5513e903BplAtgKH3x0mM2Y1mz64r_Gi0sIi0kXnOGON-R19_a50HU4DUojdTbsPlf-lc8MhAGskKfoP8QzAVEY8OAxWlQ5aEa8CYkkicWeWejKcKrTgyJ6a9KZoRNGCmmW9JbFuLNW4TWdV54mVHMeXtAw1XPQJAbowW3gKgFGVCHWOUrM_K_PRK_Z1CRRmlzWoKGR1v0Z7VJFKhjcZ2yCDxxc26ecLbvtGknazM5JXOcmYidgxZ8V0000__y30000)

Giải thích Biểu đồ Lớp
* Employee:

 Chứa các thuộc tính và phương thức liên quan đến nhân viên, bao gồm id, name, và paymentMethod.
 Phương thức getPaymentMethod(): Lấy thông tin phương thức thanh toán của nhân viên.
 Phương thức setPaymentMethod(String method): Cập nhật phương thức thanh toán của nhân viên.
* PaymentManager:

Chứa phương thức updatePaymentMethod(Employee, String) để xử lý yêu cầu cập nhật phương thức thanh toán từ lớp Employee.
Quan hệ: Sử dụng PaymentDAO để thực hiện thao tác lưu trữ và cập nhật dữ liệu.
* PaymentDAO:

Lớp này chịu trách nhiệm kết nối với cơ sở dữ liệu và lưu trữ thông tin phương thức thanh toán.
Phương thức savePaymentMethod(Employee): Lưu thông tin phương thức thanh toán mới vào cơ sở dữ liệu.
Phương thức getPaymentMethod(int employeeId): Truy vấn phương thức thanh toán hiện tại từ cơ sở dữ liệu dựa trên mã nhân viên (employeeId).
