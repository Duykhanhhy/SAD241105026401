# Lab 3. Identify design elements
## Xác dịnh các phần tử thiết kế của hệ thống "Payroll System"
### I. Subsystem context diagram
 #### 1 BankSystem:
  - Hệ thống BankSystem là một hệ thống con trong PayrollSystem và có vai trò chủ yếu liên quan đến xử lý giao dịch tài chính. Cụ thể, BankSystem đảm nhận các chức năng sau:
    
 1.1 Nhận yêu cầu giao dịch từ PayrollSystem:
- Khi PayrollSystem cần thực hiện thanh toán lương hoặc các khoản thanh toán khác, nó gửi yêu cầu giao dịch tới BankSystem.
- Yêu cầu bao gồm thông tin chi tiết về tài khoản người nhận, số tiền, và các thông tin giao dịch liên quan.
    
 1.2 Xử lý giao dịch:
- BankSystem kiểm tra và xử lý yêu cầu giao dịch để đảm bảo tính hợp lệ (ví dụ: số tiền, tài khoản nguồn, tài khoản đích).
- Nếu thông tin hợp lệ, BankSystem chuyển giao dịch tới hệ thống ngân hàng thực tế.
    
1.3 Gửi yêu cầu đến hệ thống ngân hàng:
- Gửi chi tiết giao dịch (transaction details) tới hệ thống ngân hàng.
- Hệ thống ngân hàng thực hiện giao dịch và trả lại phản hồi (trạng thái giao dịch: thành công, thất bại, hoặc lỗi).
    
 1.4 Phản hồi trạng thái giao dịch:
- BankSystem nhận phản hồi từ hệ thống ngân hàng.
- Truyền lại thông tin trạng thái giao dịch (success/failure) cho PayrollSystem để thông báo kết quả hoặc xử lý tiếp.
