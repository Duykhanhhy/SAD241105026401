# Thiết kế hệ thống con trong hệ thống Payroll System
## I.Yêu cầu

Hãy thiết kế các hệ thống con trong hệ thống Payroll System, dựa vào kết quả tham khảo về thiết kế ca sử dụng ở bài Lab4.

## II.Hệ thống con
2.1.Hệ thống con Login (Authentication Subsystem)
- Phục vụ ca sử dụng:

Đăng nhập hệ thống (Login)
- Chức năng:
    - Quản lý xác thực người dùng và phân quyền truy cập.
- Thành phần chính:
    - `LoginController`: Quản lý logic đăng nhập và tương tác với giao diện người dùng.
    - `AuthenticationService`: Xác thực thông tin người dùng.
    - `UserDatabase`: Lưu thông tin người dùng (tên đăng nhập, mật khẩu băm, vai trò).
    - `SessionManager`: Quản lý phiên làm việc (session).

2.2.Hệ thống con Maintain Timecard(Timecard Management Subsystem)
- Phục vụ ca sử dụng:

  Quản lý bảng chấm công (Maintain Timecard)
- Chức năng:
    - Quản lý giờ làm việc của nhân viên và liên kết với các mã dự án.
- Thành phần chính:
    - `TimecardController`: Quản lý logic cập nhật bảng chấm công.
    - `TimecardForm`: Giao diện cho nhân viên nhập giờ làm việc.
    - `ProjectManagementDatabase`: Lưu thông tin mã dự án.
    - `TimecardDatabase`: Lưu thông tin bảng chấm công.

 2.3.Hệ thống con Run Payroll(Payroll Processing Subsystem)
 - Phục vụ ca sử dụng:
   
    Chạy bảng lương (Run Payroll)
- Chức năng:
    - Tính toán và xử lý thanh toán lương cho nhân viên.
- Thành phần chính:
    - `PayrollController`: Quản lý toàn bộ quy trình chạy bảng lương.
    - `TimecardDatabase`: Cung cấp dữ liệu chấm công.
    - `EmployeeDatabase`: Cung cấp thông tin nhân viên.
    - `BankSystem`: Thực hiện giao dịch thanh toán.
    - `PrinterService`: In phiếu lương.
    - `PaycheckDatabase`: Lưu trữ thông tin phiếu lương.

2.4.Hệ thống con View Paycheck(Paycheck Viewing Subsystem)
- Phục vụ ca sử dụng:

 Xem phiếu lương (View Paycheck)
- Chức năng:
    - Hiển thị danh sách và chi tiết phiếu lương cho nhân viên.
- Thành phần chính:
    - `PaycheckController`: Quản lý logic lấy dữ liệu phiếu lương.
    - `PaycheckDatabase`: Lưu trữ thông tin phiếu lương.

2.5.Hệ thống con Generate Reports(Report Generation Subsystem)
- Phục vụ ca sử dụng:

Tạo báo cáo lương (Generate Reports)
- Chức năng:
    - Tạo báo cáo tổng hợp hoặc chi tiết dựa trên dữ liệu lương và bảng chấm công.
- Thành phần chính:
    - `ReportController`: Quản lý yêu cầu tạo báo cáo.
    - `PayrollDatabase`: Cung cấp dữ liệu lương.
    - `ReportGenerator`: Xử lý và tạo báo cáo từ dữ liệu.
## III.Biểu đồ tổng quát các hệ thống con.

![Subsystem](https://www.planttext.com/api/plantuml/png/d9JFIiCm7CVlVOeVlNZQ2tYGwGGl4wOTuZNBGXlM9YLD9aLstjb76E9HLF3K7NOO-1vz0b_1PBMI_aM5qaA-lto-lzyteP_RtJ2HI4WLXKwCy0Bv1Dm9IWKFG_3IH9B8XNi7G3y_-gcI0M6IOYGfP-2fMM9L0k0G9GcCkK_PY3DfM4HOIdM_HyIIOcBf7aaIBLmYfktCnfLZsqzfH30ISoWA8etgwg4iRMsZ5C-HH3EKa8PHcSD4S6nQOdwNptTbgutMS43mmh8ffJF45aN8RTw7NN13oLs_yw7kjzPLbsiISo7XWZ0YUW-pAEmoCMjrZoEuKeX1a6_NuDDy-u80xpUuM93w_Q27mfpfqjfDWS7WfENau1ZSMqCmcz_qHwWKS9uznsu7et4g_qBKulqxevvT7q4ZMYRl76QaJ8XvzXJ3N4SCeGvwhM2MPuz62BGIwTZVcM-QQoAwH-mWnm7Divs2yEFrOzD7RHkwWrbbrNknMoplc86DDITjwwVXRALd0wOczgMci6fs-mqtDvMxpieP4ZOtlyOl0000__y30000)

## IV.Mối quan hệ giữa các hệ thống con.
- `Authentication Subsystem` là điểm khởi đầu, đảm bảo an toàn truy cập cho mọi hệ thống con.
- `Timecard Management Subsystem` cung cấp dữ liệu đầu vào cho `Payroll Processing Subsystem`.
- `Payroll Processing Subsystem` tạo phiếu lương, cung cấp dữ liệu cho cả `Paycheck Viewing` và `Report Generation Subsystem`.
- `Paycheck Viewing Subsystem` cho phép nhân viên xem phiếu lương cá nhân dựa trên dữ liệu từ `Payroll Processing`.
- `Report Generation Subsystem` sử dụng dữ liệu tổng hợp từ `Payroll Processing` để tạo báo cáo chi tiết và trực quan.


      
