1.Cập nhật hồ sơ bệnh nhận
Các lớp phân tích của ca sử dụng Payment:
Entity:
Employee: Lưu thông tin cơ bản của nhân viên, như tên, ID, và phương thức thanh toán.
PaymentMethod: Lưu trữ chi tiết phương thức thanh toán (gửi qua thư, nhận tại chỗ, hoặc chuyển khoản trực tiếp).
PayrollRecord: Lưu thông tin về kỳ lương, số tiền thanh toán, ngày thanh toán.
Boundary:
PaymentUI: Giao diện cho nhân viên lựa chọn hoặc xác nhận phương thức thanh toán.
Control:
PaymentController: Điều phối các thao tác trong quá trình thanh toán, lấy thông tin từ Employee và PaymentMethod, xử lý yêu cầu thanh toán, và cập nhật trạng thái thanh toán trong PayrollRecord.
Quan hệ giữa các lớp phân tích:
Employee và PaymentMethod:
Loại mối quan hệ: Một - Một
Giải thích: Employee có một PaymentMethod duy nhất để xác định phương thức thanh toán của mình. Điều này giúp mỗi nhân viên được liên kết rõ ràng với một trong các phương thức thanh toán như PickUp, Mail, hoặc DirectDeposit
PaymentMethod và các lớp con (Pick-up, Mail, DirectDeposit):
Loại mối quan hệ: Một - Nhiều
Giải thích: PaymentMethod là lớp cha trừu tượng, có nhiều lớp con đại diện cho các phương thức thanh toán cụ thể. Các lớp con như PickUp, Mail, và DirectDeposit kế thừa thuộc tính và hành vi từ PaymentMethod, và có thể mở rộng thêm chi tiết nếu cần.
PaymentSystem và Employee:
Loại mối quan hệ: Một - Nhiều
Giải thích: PaymentSystem quản lý các giao dịch thanh toán cho nhiều nhân viên (Employee). PaymentSystem sẽ lưu trữ và quản lý thông tin thanh toán của mỗi nhân viên để đảm bảo tính chính xác và nhất quán trong các kỳ thanh toán.
Biểu đồ sequence:
Biểu đồ lớp:
Giải thích:

2.Quản lý thuốc và điều trị


3.Cung cấp thông tin về thuốc và chẩn đoán
