# PrimaryKey-ForeignKey


[Bài tập] Xác định khoá chính và khoá ngoại của bảng
Mục tiêu
Luyện tập xác định khóa chính, khóa ngoại.

Mô tả bài toán
Cơ sở dữ liệu để quản lý tài khoản ngân hàng của khách hàng gồm quản lý các đối tượng khách hàng, tài khoản và các giao dịch của khách hàng. Sau đây là 3 bảng cơ bản nhất của cơ sở dữ liệu này:

Bảng Customers - khách hàng gồm customer_number (mã khách hàng), fullname (họ tên khách hàng), address (địa chỉ), email, phone (số điện thoại).
Bảng Accounts - tài khoản gồm account_number (số tài khoản), account_type (kiểu tài khoản), date (ngày mở tài khoản), balance (số dư).
Bảng Transactions - giao dịch gồm tran_number (mã giao dịch), account_number (số tài khoản giao dịch), date (thời gian giao dịch), amounts (số tiền giao dịch), descriptions (mô tả giao dịch). 
Mỗi khách hàng có 1 tài khoản ngân hàng. Mỗi tài khoản có thể thực hiện nhiều giao dịch. 

Từ thiết kế trên hãy chỉ ra khóa chính của từng bảng, khóa ngoại để tạo liên kết giữa các bảng.

Các bước thực hiện
Bước 1: Xác định khóa chính của từng bảng.

Trong bảng customers

Mỗi khách hàng chỉ có duy nhất một mã, do đó trường mã khách hàng thường được sử dụng để phân biệt giữa các khách hàng với nhau.
Tên khách hàng có thể có nhiều khách hàng trùng tên, địa chỉ có nhiều thông tin hỗn tạp (số nhà, thành phố …)
Email là duy nhất tuy nhiên thì một khách hàng có thể cung cấp nhiều địa chỉ mail khác nhau.
Số điện thoại là duy nhất tuy nhiên thì một khách hàng có thể cung cấp nhiều số điện thoại khác nhau.
Vậy để phân biệt giữa các khách hàng với nhau chúng ta nên sử dụng trường mã khách hàng. Do đó mã khách hàng sẽ được chọn làm khóa chính của bảng khách hàng.

Trong bảng accounts

Mỗi số tài khoản là duy nhất và số tài khoản này dùng để phân biệt giữa các tài khoản khác nhau.
Kiểu tài khoản có nhiều loại như vip, thường, doanh nghiệp.
Ngày mở gồm nhiều thông tin như ngày, tháng, năm
Số dư là giá trị có thể bị thay đổi.
Vậy để phân biệt giữa các tài khoản với nhau chúng ta nên sử dụng trường mã tài khoản. Do đó mã tài khoản sẽ được chọn làm khóa chính của bảng tài khoản.

Trong bảng transactions

Mỗi mã giao dịch là duy nhất và số giao dịch này dùng để phân biệt giữa các giao dịch khác.
Số Tiền có thể bị thay đổi
Thời gian gồm nhiều thông tin ngày, tháng, năm
Mô tả gồm nhiều thông tin.
Vậy để phân biệt giữa các giao dịch với nhau chúng ta nên sử dụng trường mã giao dịch. Do đó mã giao dịch sẽ được chọn làm khóa chính của bảng giao dịch. 

Bước 2: Xác định khóa ngoại tạo liên kết giữa các bảng. 

Mỗi khách hàng có 1 tài khoản ngân hàng. Mối quan hệ giữa hai bảng customers – accounts ( 1 : 1 ). Với kiểu kết hợp này, chuyển khóa chuyển khóa chính của bên liên kết 1 sang làm khóa ngoại của bên liên kết còn lại. Trong trường hợp này bảng acccounts sẽ có thêm trường customer_number trường này sẽ là trường khóa ngoại để liên kết giữa 2 bảng accounts và customers.

Mỗi tài khoản có thể thực hiện nhiều giao dịch. Mối quan hệ giữa hai bảng accounts – transactions ( 1: N ). Với kiểu kết hợp này, chuyển khóa chuyển khóa chính của bên liên kết 1 sang làm khóa ngoại của bên liên kết nhiều. Tức là bảng transactions sẽ có thêm trường account_number trường này sẽ là trường khóa ngoại để liên kết giữa 2 bảng transactions và accounts.

Tổng kết
Qua bài tập trên bạn đã luyện tập:

- Xác định khóa chính của bảng

- Xác định khóa ngoại để tạo liên kết giữa hai bảng
