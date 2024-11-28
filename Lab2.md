# LAB2: Phân tích và mô phỏng hệ thống Payroll System
  ## I. Phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System.
  ### 1. Các ca sử dụng chính.
1.1 Maintain Timecard:
  - Mô tả: Nhân viên quản lý thông tin thời gian làm việc hàng tuần.
  - Dòng sự kiện chính:
    - Nhân viên đăng nhập vào hệ thống.
    - Hệ thống hiển thị timecard hiện tại (hoặc tạo mới nếu chưa có).
    - Nhân viên nhập các thông tin:
      - Ngày làm việc.
      - Số giờ làm việc.
      - Số giờ tính phí cho từng mã dự án (charge number).
    - Nhân viên gửi TimeCard.
Biểu đồ Sequence:
![Diagram](https://www.planttext.com/api/plantuml/png/P59BReCm4Dtx52DMxIBgdaKLaQIhjB425t3DKAmO6us7IfojYnwfLwW1HmqfIxytypx3pzVtDh0Y7Zehb6PFK8w1iHDzV3JQzCenP8Ukjtv4XAC9d84AS3Yk6PNfK2kgPx3QhK4va6vLG3XHZJHJvEcEeaRorYRrXLAkAOLobrkyAF-jq2tg2qWoZgywKeXb1ZRFSMKE5PcF3oJ8peE399i9MKxuuPZ36PaCVYBOc1Ly0vZ21s0FlHeJjzhby8AiM-2K7Mh5Ag7oT4NxQtW_XLznefkTidgmYd7Uh2nFbZgCUJharjSvx0sXPjXZxuDX0V5RneiuNgAhuNqgXacv42zel9ivnP-4TusXxfO13_7G58EEO1febB7XKQ2D9k_LNoFsb2n8eo-ReR-n86M-j3svdyiNqL2AjzIUmvjdqumJOxumnTgrZvqYOossaJ_zUxy0003__mC0)

1.2 Generate Paycheck.
- Mô tả: Hệ thống tự động tính toán lương và tạo paycheck cho nhân viên.
- Dòng sự kiện chính:
    - Hệ thống tự động chạy vào ngày thanh toán (thứ Sáu hàng tuần hoặc ngày cuối tháng).
    - Lấy thông tin:
      - Timecard (cho nhân viên tính theo giờ hoặc lương cơ bản).
      - Đơn hàng (cho nhân viên hoa hồng).
    - Thông tin khấu trừ và thuế.
    - Tính lương:
      - Giờ làm thêm (nếu có) được tính với tỷ lệ phù hợp.
      - Tính thu nhập và khấu trừ.
    - Tạo paycheck:
      - Gửi lệnh chuyển khoản (nếu chọn phương thức "Direct Deposit").
      - In paycheck (cho các phương thức khác).
    - Cập nhật trạng thái trả lương.

  Biểu đồ Sequence:
  ![Dỉagram](https://www.planttext.com/api/plantuml/png/P59BReCm4Dtx52DMxIBgdaKLaQIhjB425t3DKAmO6us7IfojYnwfLwW1HmqfIxytypx3pzVtDh0Y7Zehb6PFK8w1iHDzV3JQzCenP8Ukjtv4XAC9d84AS3Yk6PNfK2kgPx3QhK4va6vLG3XHZJHJvEcEeaRorYRrXLAkAOLobrkyAF-jq2tg2qWoZgywKeXb1ZRFSMKE5PcF3oJ8peE399i9MKxuuPZ36PaCVYBOc1Ly0vZ21s0FlHeJjzhby8AiM-2K7Mh5Ag7oT4NxQtW_XLznefkTidgmYd7Uh2nFbZgCUJharjSvx0sXPjXZxuDX0V5RneiuNgAhuNqgXacv42zel9ivnP-4TusXxfO13_7G58EEO1febB7XKQ2D9k_LNoFsb2n8eo-ReR-n86M-j3svdyiNqL2AjzIUmvjdqumJOxumnTgrZvqYOossaJ_zUxy0003__mC0)

  1.3 BankSystem:
  - Mô tả: Bank System được sử dụng để xử lý các giao dịch liên quan đến phương thức thanh toán "Direct Deposit". Payroll System giao tiếp với Bank System để thực hiện chuyển khoản tiền lương vào tài khoản ngân hàng của nhân viên.
  - Mục tiêu: Gửi thông tin giao dịch bao gồm số tài khoản, ngân hàng, và số tiền đến Bank System.
  - Dòng sự kiện chính:
      - Payroll System chuẩn bị dữ liệu giao dịch (thông tin nhân viên, số tiền cần chuyển).
      - Gửi yêu cầu giao dịch đến Bank System.
  - Bank System xử lý giao dịch:
      - Xác minh thông tin tài khoản.
      - Thực hiện chuyển khoản.
      - Trả về kết quả (thành công hoặc thất bại).
   
    Biểu đồ Sequence:
    
    ![Diagram](https://www.planttext.com/api/plantuml/png/V911QWCn34NtFiLdLYsq5yYYXEcgK8h1qBrmDCNKOmTPKvYpPP4ZzGgLGqZIHIkC3DPxGjRtuRXjIgBBd1r5hOB1qoerPuIrASy3gC47jpSenRIdeXX6Af-tzJ4uvmCUdupSm0iRpL2XqgnfgWKxKi8TnLYNeW-WkT_tPsaqAN3PtHgEikATSlhz2eln8dcfaLlxW-YpFDSo9PdHbjX9nxanNihNFusxzbOrJIicIdaHFXMl_tkj7s0HsvKTOPNLsV1kQwclyGS00F__0m00)
    
  1.4 Project Management Database
  - Mô tả:
    Hệ thống Project Management Database (PMD) là một cơ sở dữ liệu kế thừa chứa thông tin về các dự án và mã chi phí (charge numbers) liên quan
  - Mục tiêu: Lấy danh sách các mã chi phí từ PMD để nhân viên ghi nhận giờ làm việc hoặc tạo báo cáo.
  - Dòng sự kiện chính:
      - Nhân viên mở giao diện nhập timecard hoặc yêu cầu báo cáo.
      - Payroll System gửi yêu cầu tới PMD để lấy danh sách mã chi phí khả dụng.
      - PMD trả về danh sách mã chi phí, bao gồm thông tin dự án liên quan.
      - Payroll System hiển thị danh sách này cho nhân viên.
   
    Biểu đồ Sequence:
    
    ![Diagram](https://www.planttext.com/api/plantuml/png/Z99DJiCm48NtESMeUoxG1QhKiEYY43N0Vk9C6YF_17kSAcTZmP6u0ev3rJQjW2minVFclV5dVtryhZoZuw1LXeAjWyM3xfGTY1Q07k9FriMw5B93mx0eS71MAIW7pwIJfYXd4cVVI31iqU2UDCMz71ahz9DdiSspB1h3tNtiNS9JHmQUfIQ1heQDON8D2igACYcs-H9sz1x8CuWMtPx015sHynag7kk0FKg5bQ8CuZVk_5ZlY8Cpe6JijSsyFObJI9nc2RdqdS9XhYBbANa6yrSEEMVTtBPixM6gW2Rl8vAaE0Fm4WC4YfRggsnJNw0gGwKb0nzX7IItqDhWFA2vwZu3-8fAriXqYs2gtMHpEk3QcaOw3Vta8wqvEsQQ37iwpHKbEEVmQ5as0_WWHCGmOTsO_X_Xlz4zNjebu97RAYxZi_u6003__mC0)

1.5 Select Payment Method 
- Mô tả:
  
  Ca sử dụng này cho phép nhân viên chọn phương thức thanh toán cho tiền lương của họ
- Mục tiêu:
    - Nhân viên chọn hoặc thay đổi phương thức nhận tiền lương.
- Dòng sự kiện chính:	
    - Nhân viên chọn chức năng "Select Payment Method".	
    - Payroll System hiển thị các phương thức thanh toán khả dụng (Pick-up, Mail, Direct Deposit).	
    - Nhân viên chọn một trong các phương thức:	
        - Nếu chọn Mail, nhập địa chỉ nhận thư.	
        - Nếu chọn Direct Deposit, nhập thông tin ngân hàng (tên ngân hàng, số tài khoản).	
    -  Payroll System xác nhận và lưu thông tin phương thức thanh toán mới.	
    -  Payroll System hiển thị thông báo thành công.
Biểu đồ Sequence:

![Diagram](https://www.planttext.com/api/plantuml/png/f99DJiCm48NtFiKeAv3e1Rf0NRGB5gMH8h6VE4EnwZ_PaqWv6mkEn1MOkAre0wWBih1YlVU-DtRo-Vwnoeo9UsSLQWu9gesBDen45M06sQWekj4cecUeQXnJi1QQCJEvugaRfSG7YqTvNS8kaeUg8KkQGUoE9BSbVWjTfUhcR5kR72sEW0CQYwqbY2UlAzvyoJpHSEPHQ5b0QTBM54Csh42UY-J6CoLeqH-W8vQg37Tbvz7H0w3MeHUUxrrBwRwalsTyGMiwPBhA5yzKNDIVqZMYmM5-ifbBXbt2Ss3pEaBkjQPyv93D14z-kDLIykVRf9Ja6pfXu9wE6D-fWjfAzlVRSQ8OlmVikdHklts2lwSlTRNHXqKV_m-J-LUoJ7_e5m000F__0m00)

  ## II. Mô phỏng ca sử dụng Maintain Timecard
  ### 2.Mã Java
  ``` Java
  import java.util.ArrayList;
  import java.util.List;
  import java.util.Scanner;

  // Class đại diện cho thẻ chấm công
  class Timecard {
    private String employeeId;
    private String date;
    private int hoursWorked;

    public Timecard(String employeeId, String date, int hoursWorked) {
        this.employeeId = employeeId;
        this.date = date;
        this.hoursWorked = hoursWorked;
    }

    public String getEmployeeId() {
        return employeeId;
    }

    public String getDate() {
        return date;
    }

    public int getHoursWorked() {
        return hoursWorked;
    }

    @Override
    public String toString() {
        return "Timecard [Employee ID: " + employeeId + ", Date: " + date + ", Hours Worked: " + hoursWorked + "]";
    }
  }

  // Class quản lý danh sách nhân viên và thẻ chấm công
  class PayrollSystem {
    private List<String> employeeIds;
    private List<Timecard> timecards;

    public PayrollSystem() {
        employeeIds = new ArrayList<>();
        timecards = new ArrayList<>();
        // Thêm các ID nhân viên mẫu
        employeeIds.add("E001");
        employeeIds.add("E002");
        employeeIds.add("E003");
    }

    public boolean isValidEmployee(String employeeId) {
        return employeeIds.contains(employeeId);
    }

    public void addTimecard(Timecard timecard) {
        timecards.add(timecard);
        System.out.println("Timecard added successfully!");
    }

    public void displayTimecards() {
        for (Timecard t : timecards) {
            System.out.println(t);
        }
    }
  }

  // Lớp chính mô phỏng hệ thống
  public class MaintainTimecardDemo {
    public static void main(String[] args) {
        PayrollSystem system = new PayrollSystem();
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Payroll System - Maintain Timecard");

        while (true) {
            System.out.println("\n1. Add Timecard");
            System.out.println("2. View All Timecards");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            if (choice == 1) {
                System.out.print("Enter Employee ID: ");
                String employeeId = scanner.nextLine();
                if (!system.isValidEmployee(employeeId)) {
                    System.out.println("Invalid Employee ID!");
                    continue;
                }

                System.out.print("Enter Date (YYYY-MM-DD): ");
                String date = scanner.nextLine();

                System.out.print("Enter Hours Worked: ");
                int hoursWorked = scanner.nextInt();

                Timecard timecard = new Timecard(employeeId, date, hoursWorked);
                system.addTimecard(timecard);

            } else if (choice == 2) {
                system.displayTimecards();

            } else if (choice == 3) {
                System.out.println("Exiting the system. Goodbye!");
                break;

            } else {
                System.out.println("Invalid choice! Please try again.");
            }
        }

        scanner.close();
    }
  }

  
