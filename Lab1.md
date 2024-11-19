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

![Diagram](https://www.planttext.com/api/plantuml/png/b5HBJiCm5Dpd54_Tvmgeg6M1LAIAbbNLnSDvAg7-oNvPMAWdOy6Hk0AnAaAQs9RmTcOyuyaetvzVIy_ek5EoiYZEU29OR34u8oNiWcTI2_Yee3z_i2DFcf5Res63WTml9Px3cloPZOLxQuzGm-75auD7RJi-vaaFoaeJYE2Ph77ihzHBTUlSisKhSiRxLf50ry3M6K7U6pSotA545s25KdGI-GPR6QLQx-EjINm8zuIwpp66Xgh46pMTZ5Wn4DJrNJbCLlJlb5TP8c6gsZKo9ZeTBetuAtfA9KrWex09T4Cd526-y9q4ZnWbupYJakKSYufoa1GQLTc0e-ec6uvTvnQOeCutLPK_V-RfYIrD32Ryz8nc4vkevYigk-JusM8lrP9q4tz3Fm000F__0m00)

## 2.Cơ chế phân tích
Các cơ chế chính cần giải quyết trong hệ thống này bao gồm:
- Cơ chế bảo mật (Security Mechanism): Chỉ người dùng được phân quyền mới có thể truy cập dữ liệu cần thiết. Giảm thiểu nguy cơ rò rỉ thông tin và truy cập trái phép.
- Cơ chế tính toán lương và hoa hồng (Payroll and Commission Calculation): Tính toán lương chính xác, bao gồm cả các trường hợp phức tạp như làm thêm giờ và hoa hồng. Giảm thiểu sai sót thủ công trong tính toán.
- Cơ chế tích hợp cơ sở dữ liệu hiện tại (Legacy System Integration): Truy cập dữ liệu dự án hiện tại một cách ổn định mà không gây gián đoạn hệ thống cũ. Đảm bảo tính nhất quán giữa hệ thống mới và cũ.
- Cơ chế xử lý tự động (Automation Mechanism): Quy trình trả lương diễn ra đúng lịch, không gián đoạn. Giảm thiểu công việc thủ công và nâng cao hiệu quả vận hành.
- Cơ chế quản lý nhân viên (Employee Management Mechanism): Dễ dàng quản lý thông tin nhân viên. Đảm bảo dữ liệu được nhập chính xác.
-  Cơ chế báo cáo và truy vấn dữ liệu (Reporting Mechanism): Nhân viên dễ dàng truy xuất thông tin mà không cần yêu cầu từ quản trị viên. Báo cáo được cập nhật theo thời gian thực.
-  Cơ chế giao tiếp giữa các lớp (Layer Communication Mechanism): Tăng tính linh hoạt và khả năng mở rộng của hệ thống. Giao tiếp ổn định giữa các thành phần.
## 3.Phân tích ca sử dụng Payment

## 3.1 Các lớp phân tích cho ca sử dụng Payment :
- Employee (Nhân viên): Thông tin về nhân viên cần thanh toán.
- Timecard (Bảng chấm công): Lưu thông tin giờ làm việc của nhân viên.
- CommissionOrder (Đơn hoa hồng): Thông tin về các đơn hàng tạo ra hoa hồng cho nhân viên.
- Payment (Thanh toán): Xử lý thông tin liên quan đến trả lương.
- PayrollScheduler (Bộ lập lịch trả lương): Đảm nhận việc lên lịch và kích hoạt quy trình thanh toán.
- PaymentProcessor (Bộ xử lý thanh toán): Xử lý logic tính toán số tiền cần trả, bao gồm lương cơ bản, giờ làm thêm và hoa hồng.
- BankingService (Dịch vụ ngân hàng): Giao tiếp với hệ thống ngân hàng để thực hiện thanh toán.

## 3.2 Biểu đồ Sequence:
![Diagram](https://www.planttext.com/api/plantuml/png/V5DBJiCm4Dtx57C0Ue4iK4M5O0KLHM8ziYVKgZzXF0xgsLXm9Aw0GqcRX8JjlFVcFS-Clpu-rqcG9NkdK4jakFMDYqSYrPIorRR18B358qVdTdfF9ZlYAUWfo9QZffJY67osdZIo6HKtqNkRaetXaSryjr7j1iF1XjSTSMirATLdXDNrdsWLFD5RfdJfD6LqgZvMnnQsr1AyHpx0FcPEgaTXjM0WcSE9-r9KPAuWjbJoUhh_QJ3hENdrm5gV4J0eg2RC_sCCnIHetOBzT4qLRD3fx508cikeHfo1he8x2iG3DZ3fM3RxI-XJJanwD65BHiqwZDTR92Vmx2EC8TNbJiR41SDD3BLbZr8cCZ-9_dmgU8XYw-CvuoxhhejQKp3TZ_W6003__mC0)

## 3.3 Nhiệm vụ của từng lớp:
- `Employee`: Cung cấp thông tin cá nhân và phương thức thanh toán.
- `Timecard`: Quản lý dữ liệu giờ làm việc của nhân viên, bao gồm cả giờ làm thêm.
- `CommissionOrder`: Lưu trữ và cung cấp dữ liệu hoa hồng từ các đơn hàng.
- `Payment`: Lưu trữ thông tin giao dịch thanh toán cho mỗi nhân viên.
- `PayrollScheduler`: Điều phối quy trình thanh toán, từ việc thu thập dữ liệu đến việc kích hoạt thanh toán.
- `PaymentProcessor`: Thực hiện tính toán tổng số tiền cần trả cho nhân viên dựa trên lương, giờ làm thêm và hoa hồng.
- `BankingService`: Xử lý chuyển khoản hoặc giao dịch thanh toán dựa trên thông tin từ hệ thống.
## Thuộc tính và quan hệ
- Quan hệ giữa các lớp:
      - Employee - Timecard/CommissionOrder: Nhân viên tạo bảng chấm công và đơn hoa hồng.
      - Timecard/CommissionOrder - PayrollScheduler: Dữ liệu bảng chấm công và hoa hồng được chuyển đến bộ lập lịch.
      - PayrollScheduler - PaymentProcessor: Bộ lập lịch điều phối việc tính toán lương.
      - PaymentProcessor - Payment: Tạo bản ghi thanh toán sau khi tính toán.
      - Payment - BankingService: Xử lý giao dịch thanh toán.
- Thuộc tính tiêu biểu:
         - Employee: `id`, `name`, `salaryType`, `paymentMethod`.
         - Timecard: `employeeId`, `workDate`, `hoursWorked`, `overtimeHours`.
         - CommissionOrder: `saleAmount`, `commissionRate`.
         - Payment: `amount`, `paymentDate`
## Biểu đồ mô tả lớp phân tích:
![Diagram](https://www.planttext.com/api/plantuml/png/X5HBJWCn3DtFAQAkg0GNw0ArV2HO82fQYNMQk6tKV8hZAQeG9sF1aRW2JkVJcPJFB4OQ-zdlFTkQhu_FSII9L3fRM5YIe23GhDOaj45GP88l2cLbZEBMRMtO0uYtGgJ7w94mdgeFBnsCn8pG-5KLYT9AtC_tsoo-bNi7dXw0ra7tKmlfDnEbGkcfJRmtz7FZG4dK3JtKSkwxCbu3RcuaCMLwLx5rA34-Sm8OkRH1rjYm0oHkUfVoJQQbkmxEcHZP_oDgm3zPGqBajEmV9gxoqc5LRT-dGq56Ewscqz3Lm-gn_IYX1kOYP4z0bmM3jJEr1btQexjO1seLPyEHs0MZJ-HDCIY8CRI5IbfLMgPjAZEHmnC9LxnhtkyCS6TKUrFRgd7JfM__l6zdsBsHzZWlBYwFfp8IWrWkdA4uw2FoxJ9m1HwG7J2qhK_GaranbcNkZ8Puk3UX9Sb1aRVyj_Pu2NM74tJTeZ_nv0cyZitA1S9B2P4EzNrefpwLAOJANnDB-MmF33FUa4b0GIXzb8UVmA38WBzfKy4l3Jfc6RFAz5lv1W00__y30000)

## 4. Phân tích ca sử dụng Maintain Timecard

## 4.1 Các lớp phân tích cho ca sử dụng:
- Employee (Nhân viên):
      - Thực hiện thao tác quản lý bảng chấm công.
      - Thuộc tính: id, name, role.
- Timecard (Bảng chấm công):
      - Quản lý dữ liệu giờ làm việc.
      - Thuộc tính: timecardId, employeeId, workDate, hoursWorked, overtimeHours.
- TimecardManager (Quản lý bảng chấm công):
      - Đảm nhiệm các thao tác thêm, sửa, và xóa bảng chấm công.
      - Phương thức: addTimecard(), updateTimecard(), deleteTimecard().
- ValidationService (Dịch vụ kiểm tra tính hợp lệ):
      - Kiểm tra dữ liệu bảng chấm công trước khi lưu trữ.
      - Phương thức: validateTimecard().
- TimecardDatabase (Cơ sở dữ liệu bảng chấm công):
      - Lưu trữ và cung cấp dữ liệu bảng chấm công.
      - Phương thức: saveTimecard(), updateTimecard(), deleteTimecard().
## 4.2 Biểu đồ Senquence
![Diagram](https://www.planttext.com/api/plantuml/png/X58xZi8m4Etd57C1H9zY1UBJePKsG3zh3yZInB763X9de-18N05dfIpP96XTk1Y_hpMFstqH4sbgAW4ogLRSL47gApE4F7R61V89zwvYGsftvEdC-kVjIE8i9LVxalNYp3HpJOc-AJ90Pu2pZw5kWKjhvuUGvNY-Pk74ln0OO5lwoBheHYyUjiumGk9iolu5mo-EZIG0adv5B1jZECPJ8u3vJ8GQDYwmf0k_QzKNwHZJsLQrFpcjVcAyy-x-ji3Fm3fAp9B5UsMsv2J-hzLZR5JpZkooNeO1UmkBVBNRymG00F__0m00)
## 4.3 Các lớp và nhiệm vụ:
- Employee: Tương tác với hệ thống để quản lý bảng chấm công.
- Timecard: Lưu trữ thông tin từng bản ghi thời gian làm việc của nhân viên.
- TimecardManager: Điều phối các thao tác quản lý bảng chấm công, như thêm, sửa, và xóa. Gọi dịch vụ kiểm tra tính hợp lệ và giao tiếp với cơ sở dữ liệu.
- ValidationService: Kiểm tra tính hợp lệ của dữ liệu như. Giờ làm việc phải là số hợp lệ (lớn hơn 0). Ngày làm việc không được trùng lặp.
- TimecardDatabase: Lưu trữ và quản lý dữ liệu bảng chấm công.
## 4.4 Quan hệ giữa các lớp:
- Employee - TimecardManager: Nhân viên tương tác với hệ thống thông qua lớp TimecardManager để quản lý bảng chấm công.
- TimecardManager - ValidationService: Kiểm tra dữ liệu trước khi lưu trữ.
- TimecardManager - TimecardDatabase: Thực hiện lưu, cập nhật, hoặc xóa dữ liệu bảng chấm công.
- Timecard - Employee: Một nhân viên có thể có nhiều bản ghi bảng chấm công
## 4.5 Thuộc tính và phương thức:
- Employee:
   - Thuộc tính: `id`,`name`, `role`.
   - Quan hệ: Quản lý nhiều bản ghi bảng chấm công.
  
- Timecard:
   - Thuộc tính: `timecardId`, `employeeId`, `workDate`, `hoursWorked`, `overtimeHours`.
   - Quan hệ: Thuộc về một nhân viên cụ thể.

- TimecardManager:
   - Phương thức:
      - `addTimecard(timecard: Timecard): void`
      - `updateTimecard(timecard: Timecard): void`
      - `deleteTimecard(timecardId: int): void`.

- ValidationService:
   - Phương thức:
      - `validateTimecard(timecard: Timecard): boolean.`
- TimecardDatabase:

   - Phương thức:
      - `saveTimecard(timecard: Timecard): void`
      - `updateTimecard(timecard: Timecard): void`
      - `deleteTimecard(timecardId: int): void.`
    
## Biểu đồ lớp mô tả lớp phân tích:
![Diagram](https://www.planttext.com/api/plantuml/png/j5EnJiCm4Dtp5LQcClG7Cg0E8C70r0hcQtmK2ziNdPsW2l5b37mIlu3TsAPW45t84CNttZs_UtRUNzzMpWFxqUYcr-2Sk3I3fZsYU6v4V9JiXB9-NbWms8crPsLtSuL9VrPUcYIoKGPxO9b5V5fV7ujXskbByOduyG9yq8plkVP08xkx061Wtck2nAK9EIfVHJmZbOSRiB13pbP0oemiigskaCywCP6ICtKSPF1mAbkYnX_OQRfCBVPkGQiWhyYkaIVLby2d6VXZtos5uC7MuuROO0kko3cOJXxXdmOkLsgvFA-EfHEjENowjlcEHNwTK-Z86VtIKsKHMWPafvm_wZXGYxT0OTHHKtXgcnLQ6N-A3m000F__0m00)

## 5.Hợp nhất kết quả phân tích

## 5.1 Tóm tắt các ca sử dụng
# Ca sử dụng 1: Select Payment
- Mục đích: Quản lý việc tính toán và thực hiện thanh toán lương cho nhân viên, bao gồm:
   - Lương theo giờ.
   - Lương cố định (salaried).
   -Lương hoa hồng (commission-based).
- Chức năng chính:
   - Tính toán lương dựa trên dữ liệu bảng chấm công và tỷ lệ lương.
   - Hỗ trợ nhiều phương thức thanh toán (chuyển khoản, gửi qua bưu điện, tại văn phòng).
   - Báo cáo thông tin thanh toán.
# Ca sử dụng 2: Maintain Timecard
- Mục đích: Quản lý bảng chấm công của nhân viên, bao gồm:
   - Thêm mới bảng chấm công.
   - Cập nhật hoặc xóa dữ liệu bảng chấm công.
- Chức năng chính:
   - Lưu trữ dữ liệu thời gian làm việc, giờ làm thêm và dự án liên quan.
   - Kiểm tra tính hợp lệ của dữ liệu chấm công.
   - Đồng bộ dữ liệu với cơ sở dữ liệu bảng chấm công

## 5.2 Biểu đồ hợp nhất của hai ca sử dụng:
![Diagram](https://www.planttext.com/api/plantuml/png/j5JDRjim3BxxAOISCg0zz2eCHGyTi09DC233TcOa9X6c7qC_xefXJxP37wclC2gHvSHni5pcWm6J7ycFv4U__tbx215yJ4OtGaC8x9DfjNj5PByQjd-Kv4pPMBui6EHi5RsossBoJezD4bjAQj36wlZTb09VbK41NjO2iHYUJWfXuN5gVN7-noD4gfVVnRXpoOVlv472RhI37kqwz3dxvmmuTOaT-2qkarcZlynn0HQsw2jLaB9tpNlQlA8_SDOv9GisjP8eNWsNg742NjhliPNXDz2AyYjdL-Wx9OPzTGVFFogl7MqDx2Zc2xpcfT5iONu4EfjB1gmX34K3TDUt-dydKtgerDh3zpNg0kDIbkonKDewabFH5Vi2uyx9SmKL5cC12T0YwM7Iyvu8huTtKm-29FkiGlpOjtvFlPQulesVADAGh72ggAdPqBNgoVLTaQJ-6sPtCtPxUyzcozbmptn_dO4vsupl9sEFS6Pl3fEmSs5pbi85y9aUEHFEc6ILe1a7zgBYhXcj8iVLHZZpI9l3Zi1K5TZ6-Qc08_APJ8RLNHBLgP2fHlex2rC1u-Lm5gBpX7r0A_CF-Yy0003__mC0)

# 5.3 Nhiệm vụ và các lớp chính:
- Employee:
      - Đối tượng trung tâm kết nối với cả bảng chấm công và hệ thống bảng lương.
      - Lưu trữ thông tin nhân viên như mã định danh, vai trò, và phòng ban.
- Timecard:
      - Chứa dữ liệu thời gian làm việc của nhân viên, bao gồm giờ làm việc và giờ làm thêm.
      - Là nguồn dữ liệu chính cho hệ thống tính lương.
- TimecardManager:
      - Quản lý các thao tác thêm, sửa, xóa bảng chấm công.
      - Kiểm tra tính hợp lệ thông qua ValidationService và đồng bộ với cơ sở dữ liệu.
- Payment:
      - Đại diện cho khoản lương của một nhân viên.
      - Chứa thông tin như số tiền, ngày thanh toán, và phương thức thanh toán.
- PaymentManager:
      - Chịu trách nhiệm tính toán lương dựa trên bảng chấm công và loại hình lương (giờ, cố định, hoa hồng).
      - Thực hiện việc thanh toán và lưu trữ thông tin qua cơ sở dữ liệu bảng lương.
- ValidationService:
      - Đảm bảo tính chính xác của cả dữ liệu bảng chấm công và dữ liệu thanh toán.
- TimecardDatabase và PayrollDatabase:
      - Lưu trữ dữ liệu tương ứng với từng hệ thống.
# Biểu đồ Sequence hợp nhất:
![Diagram](https://www.planttext.com/api/plantuml/png/X5D1RiCW4BppYlr0b3k7A5NJOwMeJdlVmhf2mc01jkItzT0dzGl5RUnW82f7TeQPdLs-Fx-EFg0BGwSPYc0TF7MzjXCHw-Er4gf74-2YEXBev3CQ_22tgRsXLXA3igOXDofHPvumu3lwRV6CKqScr5wD9MUrNcbiyGMxGsw7muEK-zS-kg3zYJG5MY4imyxqmZ5VhX9U0O9TJVa6WnVoWmuCTPe9D8CGv7qxQ0RnLEpa4N5eSAHx_QIFB8owjKThMkMwNnkCZ6Iiv1so6V3OHN2AnfkYXpQknHN6jl3_qhoYOHQyasYkNmPQIcRByHTOQZ6jLbKssPG2oxBnjOEpi_COIIO3rHCxnbpdl_C3003__mC0)
