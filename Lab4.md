# Các ca sử dụng hệ thông "Payroll System"
## I.Các ca sử dụng chính:
-  Đăng nhập hệ thống (Login)
-  Quản lý bảng chấm công (Maintain Timecard)
-  Chạy bảng lương (Run Payroll)
-  Xem phiếu lương (View Paycheck)
-  Tạo báo cáo lương (Generate Reports)
## II.Mô tả các ca sử dụng và giải thích.
### 1.1.Đăng nhập hệ thống(Login)
- Mục đích:

Xác thực thông tin người dùng để truy cập vào hệ thống.
- Tác nhân chính:
    - Nhân viên (Employee).
    - Quản trị viên lương (Payroll Administrator).
- Luồng chính:
    - Người dùng nhập tên đăng nhập và mật khẩu.
    - Hệ thống xác thực thông tin.
    - Người dùng được truy cập vào chức năng phù hợp với vai trò.

Biểu đồ:
![Login](https://www.planttext.com/api/plantuml/png/j5N1Qjj04BthAuOzsT3yG0ub3QOjf2a5kn-mbeMqs5gvqieqnv933pc57d8e1HkJGqj36YYKQ0yvhCb_x1Vq5pgxiYolxBGkj0BRcjNCctblngEVykuW4pGLUJpog2-I55vdGGeq0_8olF-cvIS60tNBG-ADqOtvR4ov0F8Y2Hb_cgGnCRuhotLwaeieu6XJmHBU3T89ymCRO9uiRJV4PEzGGViqApqxXwv3DyWo13kcd8P1QbtS8y-p3FOUrrN1FhA9T74r1g6-S5YSBqvv2BmycgWfn7WdO8W7dtFYrO5Db2EcvMaC8gKmqF8QHcY_pokafTLAjRpWuIFCe-KPZz2rcF6mJJmw4j2Br7TCBXYlmeRbIQJb734GmWEyd28i9So_3EwhMM8yBzW-z3OPHOakVlWEgSqan0j6MR2bdD_LiTOtKyupBQyOY1h2gOFO-FKGHEWSMXvfVW8JNLpozMZkJ9nH-8QYreRWPjzATAEeEwWLKw7b1un3wPdrD1SctzjaSRGCK5-niuXzUTAeXAm06cISsUYbkfWZAVaEXhgu4_0cDmTlrSmtiFB6Bz45z4rHDUZkdPuoP8VDdVCjB4j0szI68hjBqNke6GzAq03e9f2f6SwyCtoBSpM7_WB_EQs8Pb6xHZFzEzuofsZ9Z-ELst_J_c_qxrBMM1GLWXMzGUDFzRjRowR4qX8OHypC-aXDOvYOXU93AojzssxT3OGjxNorYMLROKOX8VzMNJN5hlj6j1tKVMxsABV1PzK6i5AxYsmxQi07NlLhFWVuPTvVlm000F__0m00)

- Lý do thiết kế:
    - Bảo mật: Hệ thống cần đảm bảo chỉ người dùng hợp lệ (nhân viên, quản trị viên lương) mới có thể truy cập vào các chức năng.
    - Phân quyền: Xác định vai trò người dùng (nhân viên hoặc quản trị viên lương) để hiển thị các chức năng phù hợp.
    - Trải nghiệm người dùng: Một giao diện đăng nhập đơn giản giúp tăng tính dễ sử dụng và giảm thời gian truy cập hệ thống.
  
### 1.2.Quản lý bảng chấm công (Maintain Timecard)
- Mục đích:

Quản lý giờ làm việc của nhân viên và phân bổ thời gian cho các mã dự án.
- Tác nhân chính:
    - Nhân viên (Employee).
- Luồng chính:
    - Hiển thị bảng chấm công hiện tại.
    - Nhân viên nhập giờ làm việc và mã dự án.
    - Cập nhật bảng chấm công vào cơ sở dữ liệu.

Biểu đồ:

![MaintainTimeCard](https://www.planttext.com/api/plantuml/png/f9I_Rjim4CPtFSL1Urx0W8F0STi0GO8E7fAHfWcBZKW9D6t0Ov0XGySEcOBQDOe20J8Kw6GE6VWaV8AyGavo8P4kxIIenjDzl_lkZ_HideuccYWz5Nb2g2uKV11bNimP0pA1z3opFoJCk7sGQL9Y7gUy9593Ek22KQ967mibqYhN3yHJZmkfLP7dJ0M2DXpAFglY2wFwZ4WoPe99tIUQ3Cc4rUg_R_kzUAqWjmdsagHfx-0mi0mTI2_jmnIeM_-QWd3cEmpTUYN7G3Et_Yc0sZzod2Q1o8EqRLIeJyuySfYtm1mPynWHCkxChGJjralUuZsSLwJVg-03DPt3317o7K2K7koqEr38GQIv1ftL4CsZyBZ1o2nFqCGDciYS-He79TqkUFS54jy-bZ16uJtaTY4mZerGw7RtRkrybsvc5o3i2aRE_0QxbE_RdJS7MXUe_UbT6shkiIASLiqBq8fi6I2vXZCl0bURAZYbLOatOcuJmAU5xLxPVanQSzwugy56FRJBeXBVyKxKf7RcMtDMB9-mCEj_UtYB-UqluTZRJFpAVD9UBm4Abx-GMOpnoYWlx99k8E7PR16P72N_N6DpvE5AEl1Qbrlm8wHN__CN0000__y30000)

- Lý do thiết kế:
    - Dữ liệu chấm công chính xác là nền tảng cho việc tính toán lương chính xác.
    - Tăng tính linh hoạt: Nhân viên có thể nhập thông tin giờ làm việc và liên kết với các dự án hoặc mã công việc.
    - Liên kết hệ thống: Dữ liệu từ bảng chấm công sẽ được đồng bộ hóa với các tính năng khác (tính lương, báo cáo).
    - Hiệu quả: Giảm thiểu lỗi và thời gian cập nhật dữ liệu bằng cách tự động hóa quá trình ghi nhận.
  
### 1.3.Chạy bảng lương(Run Payroll)
- Mục đích:
  
Tính toán và xử lý thanh toán lương cho tất cả nhân viên.
- Tác nhân chính:
    - Quản trị viên lương (Payroll Administrator).
- Luồng chính:
    - Hệ thống thu thập dữ liệu từ bảng chấm công và thông tin nhân viên.
    - Tính toán lương dựa trên loại nhân viên (giờ, lương cố định, hoặc hoa hồng).
    - Tạo phiếu lương.
    - Thực hiện giao dịch ngân hàng để thanh toán lương.
    - Gửi thông tin phiếu lương đến máy in.

 Biểu đồ:

 ![RunPayroll](https://www.planttext.com/api/plantuml/png/Z5H1IiD05Dtd59_iUm4NKgkYWWkbNUXocWpDOF8J9h-1B5rxYKOfGg7WmbMww6AWzvWJU0Ldsj9qsXJT9EJptflttdpoirXsSsAInadiiO1I2G-ib6aSNuI9G96JP7R8Sl0Vnxh-G22f5szG23L3Y5TVgmf7lfSP2H68Z261lrMuJ97icqlVye-cBcaW4Xum6LunOaEMypLdD-ovuEiaYzEISmUy6nw0UmnV-cLEF5d3ciy3rr8WSTddiX31Hj4TULvhDPtpusXm1lwpceqXqFMdUKQwhaeOslv6JMd7DAFLHBOYzxgUxeXMPff0eBujUm_OEULX80qJ2hruRTTeTT3qs3YWo1A01096wXqtz-zxUzZ_c0WPHf2hAeXScLOVxM9gRYIs5KAX9a2csnIoIEXwEVwZtERkhTQDNim5bCqzKMJzKQegusaFUpBQaubYakXwZYwvFP2pJfP_Xot6NTJ9iszJDK6RVaeW_kZGtTW3yedjx78CxL_X5m00__y30000)

- Lý do thiết kế:
    - Đáp ứng yêu cầu kinh doanh: Cung cấp công cụ tự động xử lý bảng lương, giảm thời gian xử lý thủ công.
    - Độ chính xác: Tính lương dựa trên thông tin từ bảng chấm công, loại hợp đồng (giờ, cố định, hoa hồng), và chính sách công ty.
    - Tích hợp: Kết nối với hệ thống ngân hàng và máy in để tự động hóa thanh toán và xuất phiếu lương.
    - Tuân thủ pháp luật: Đảm bảo bảng lương tuân thủ các quy định về lao động và thuế.

 ### 1.4.Phiếu xem lương (View Paycheck)
 - Mục đích:
   
Cho phép nhân viên xem thông tin chi tiết về phiếu lương của mình.
 - Tác nhân chính:
    - Nhân viên (Employee).
 - Luồng chính:
    - Nhân viên đăng nhập vào hệ thống.
    - Truy xuất danh sách phiếu lương.
    - Xem chi tiết phiếu lương.

   Biểu đồ:

   ![ViewPaycheck](https://www.planttext.com/api/plantuml/png/f9AnJiCm48PtFyN9Ur-00LKK92R4qAMZSQtQmhb4phaY8s94F4H15L8dvcJe4AdluIVW5OWfxO2XKTNffDFztvq_-RDP3qiIZdnccP2KExZA2fjNIe4eWT_ezXLXRjeLSbPqSqQQGY01lnMLowqTvKYnAiTZ8Eac8QcLlByK9Ev4gNQPRVE2iVtomNdAWZFWatRbGORwtSE3og3G9jHh3tRpiLdWZBCqj2NzR8Y8iVCLp4EzH9WAr52s2wd_9Er2W_-k6RjGltMivh4FbHwrVsh7kJQXUK8W7PhdWwH-GQEEyOA_az_AC2exLf7K1YYow6H5FQWZ51qY3HLEus_-0W00__y30000)

- Lý do thiết kế:
    - Minh bạch: Nhân viên cần quyền truy cập để xem thông tin chi tiết về lương (số giờ làm việc, thuế, các khoản khấu trừ).
    - Tự chủ: Giảm sự phụ thuộc vào quản trị viên lương để tra cứu thông tin.
    - Tăng sự hài lòng: Giao diện thân thiện giúp nhân viên dễ dàng kiểm tra và xác nhận thông tin lương của mình.
      
   ### 1.5.Tạo báo cáo lương(Generate Reports)
   - Mục đích:
     
     Cung cấp báo cáo về lương theo nhân viên, dự án, hoặc thời gian.
   - Tác nhân chính:
      - Quản trị viên lương (Payroll Administrator).
   - Luồng chính:
      - Chọn loại báo cáo mong muốn.
      - Hệ thống truy xuất dữ liệu lương và chấm công.
      - Tạo báo cáo chi tiết hoặc tổng hợp.
      - Xuất báo cáo ra file hoặc màn hình.

     Biểu đồ:

     ![GenerateReports](https://www.planttext.com/api/plantuml/png/Z98zJWCn48LxdsBaFXUWG84WfGMKXjBPjI9BZhtoZbVQaeg2YXiGHH5I90Jrkg0moZry0gw07M2J9SjFCyMJtpTldlpcNeObCeDsBWdBK1iuPxNHKfxaSw54YOObaPL0BsnebWhG17SBbV1h1NBpl5ce6IL5H8XC54mXq4jUQ8CZhJ21kA79_btiMZwNdZ5aKrRohUDBE-sZZxdYssXxyAWHqXj_S7om7uw0NlcrXImq3nOmD0iDKnz75WSb1-yZeqsKp1DZQwX2irAG1_S4KWHtOtULx1uFVbW_CR7GY73N_OI-2Esb2J0Exb5ql9M_X_hFgvBz7w5Q7xpU-UK7xDTYkgL7sCYgMOgoAlP33BdAqtzx1m00__y30000)

- Lý do thiết kế:
    - Hỗ trợ quản lý: Quản trị viên cần thông tin tổng hợp về lương, thời gian làm việc, và chi phí cho các dự án.
    - Ra quyết định: Báo cáo giúp phân tích hiệu suất và chi phí lao động, từ đó đưa ra các chiến lược nhân sự phù hợp.
    - Tính linh hoạt: Hệ thống cần cung cấp các tùy chọn báo cáo (theo nhân viên, dự án, thời gian) để đáp ứng các mục đích sử dụng khác nhau.

  ## III.Tổng kết lí do thiết kế cho các ca sử dụng trên.
  - Tính tích hợp:
      - Mỗi ca sử dụng được thiết kế để kết nối chặt chẽ với các chức năng khác trong hệ thống, tạo ra một luồng làm việc liên tục và hiệu quả.
  - Tính tự động hóa:
      - Giảm thiểu sự can thiệp của con người để tránh lỗi và tăng năng suất.
  - Tính bảo mật và minh bạch:
    - Đảm bảo rằng hệ thống không chỉ bảo vệ dữ liệu mà còn cung cấp thông tin chính xác, minh bạch cho cả nhân viên và quản trị viên.
  - Tính tuân thủ:
    - Hỗ trợ tổ chức tuân thủ các quy định pháp luật liên quan đến lao động, thuế và tài chín
