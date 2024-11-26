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
  1.3 Manage Employee Records.
  - Mô tả: Quản trị viên quản lý hồ sơ nhân viên.
  - Dòng sự kiện chính:
    - Quản trị viên đăng nhập vào hệ thống.
    - Chọn chức năng:
      - Thêm nhân viên mới.
      - Cập nhật thông tin nhân viên (tên, địa chỉ, loại nhân viên, mức lương, v.v.).
      - Xóa nhân viên (đánh dấu xóa, hệ thống thanh toán khoản cuối cùng trước khi xóa).
    - Hệ thống lưu lại thông tin và xác nhận thay đổi.
   
  1.4  Process Direct Deposit.
  - Mô tả: Hệ thống xử lý thanh toán qua chuyển khoản ngân hàng (Direct Deposit).
  - Dòng sự kiện chính:
  - Hệ thống thu thập thông tin:
    - Tài khoản ngân hàng từ hồ sơ nhân viên.
    - Số tiền thanh toán từ bảng tính lương.
   - Tạo lệnh giao dịch và gửi tới hệ thống ngân hàng.
   - Xác nhận giao dịch thành công.
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

  
