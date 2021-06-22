## Question 1: Golang là gì?

Go là một ngôn ngữ lập trình mã nguồn mở được tạo ra bởi Google. Được thiết kế tại Google
Go có cú pháp giống với C và nó là ngôn ngữ lập trình biên dịch (compiled programming language)

## Question 2: Tại sao nên học Golang

- Không giới hạn về phần cứng: Để cải thiện hiệu suất thay vì ép phần cứng làm việc cực lực 
thì Go chia sẽ 1 phàn gánh nặng cho các đoạn code

- Golang có goroutines thay vì thread như 1 số ngôn ngữ khác
+ Các ngôn ngư như Python hay Java sinh ra vào thời ký thập niên 90 thời kỳ của đơn luồng (single threaded environment)
nhưng hầu hết hỗ trợ đa luồng (multi-threading). Sẽ gặp những vấn đề ở thực thi đồng thời (concurrent execution),
khóa luồng (threading locking), race conditions và deadlocks. Nhưng vấn đề này làm cho việc tạo ra các ứng dụng đa luông
và giao tiếp giữ các luồng với nhau trên ngôn ngữ này cực kỳ khó khăn

+ Go ra mắt 2009 khi mà xử lý đa hạt nhân (multi-core-processors) đã có. Nên Go được thiết kế và phát triển thực thì đồng thời (concurrency)
Go có goroutines thay vì threads

+ Goroutine có thơi gian khởi động nhanh hơn thread và tốn ít bộ nhớ hơn

+ Goroutine có các channel và giữ các channel có thể giao tiếp với nhau

+ Goroutine có khóa mutex (mutex locking) để đảm bảo việc đọc ghi vào một cấu trúc dữ liệu hay một biến chung không xẩy ra xung đột

- Go giao tiếp trực với vi xử lý bằng mã nhị phân nên Go là ngôn ngữ cấp cao nhưng nó có hiểu xuất tốt gần như các ngôn ngữ cấp thấp như C++, C 

- Go rất dễ bảo trì và mở rộng

+ Go có cú pháp tinh gọn
+ Go lược bỏ nhiều tính năng của lập trình OOP hiện tại: Như class, kế thừa... Mọi thứ được phân chia
bằng các packages
+ Go không có hàm khởi tạo contructors
+ Go không có chú thích @annotations như Java
+ Go không có generics là kiểu tham số hóa dữ liệu truyền vào hay là loại kiểu dùng chung đại hiện cho một kiểu dữ liệu nào đó chưa biết trước
+ Go không có exception, không có try/catch. Nhưng có error

## Question 3: Khi nào nên dùng Go ? Nó dùng tốt cho những trường hợp nào ?

- Khi nào dùng Golang

+ Phân phối các network service (dịch vụ mạng): Các chương trình úng dụng mạng (network application) sống
hay chết là dựa vào concurrency và tính năng chuyển navite concurrency của Go, các goroutines và channel rất phù hợp cho các tác vụ đó
Do đó, có nhiều dự án Go dành cho mạng, các chức năng distributed (phân phối) và dịch vụ đám mây: API, web server, minimal frameworks cho 
các web application và các loại tương tự.

+ Sự phát triển của cloud-native. Các tính năng concurrency và network của Go và tính linh hoạt cao của nó 
làm cho nó phù hợp với việc xây dựng các ứng dụng cloud-native. Trên thực tế, Go đã được sử dụng để
xây dựng một trong những nền tảng phát triển ứng dụng dựa trên cloud-native, ứng dụng hệ thống containerization Docker.

+ Thay thế cho cơ sở hạ tầng hiện có. Phần lớn các phần mềm của chúng tôi phụ thuộc vào cơ sở hạ tầng Internet 
đã lạc hậu. Việc viết lại những thứ như vậy bằng Go mang lại nhiều lợi ích, như giữ an toàn bộ nhớ 
tốt hơn, triển khai trên nhiều nền tảng dễ dàng hơn và một code base “sạch” để hỗ trợ bảo trì trong tương lai. 
Một server SSH mới được gọi là Teleport và một phiên bản mới của Network Time Protocol được viết bằng Go, 
được cung cấp như phương pháp thay thế cho các đối tác thông thường của họ.

- Go không phù hợp với việc gì?

+ Go được thiết kế nhỏ gọn và dễ hiểu, vì vậy dẫn đến một số tính năng nhất định bị bỏ qua.
Thế nên một số tính năng phổ biến có trong ngôn ngữ khác thì lại không có trong Go: class, kế thừa
generics...

+ Nhược điểm khác của Go là kích thước của các chương trình lớn. Do code được biên dịch theo kiểu static (tĩnh) theo mặc định
Cách nay đơn giản hóa việc xây dựng triển khai nhưng dẫn đến 1 đoạn code "Hello world" nặng tới 1,5M trên windows 64-bit

+ Quản lý bộ nhớ tự động (AMM), có thể được xem như là một nhược điểm, vì garbage collection (quá trình thu gom file rác) 
đòi hỏi một số memory nhất định để xử lý. Theo thiết kế, Go không thể quản lý bộ nhớ bằng tay và 
việc dọn dẹp file rác ở Go bị chỉ trích là không thể giải quyết tốt các loại memory load (bộ nhớ tải) 
xuất hiện trong các ứng dụng của doanh nghiệp

+ Hầu hết các sản phẩm từ Go là các command-line tool hoặc các dịch vụ network. 
Go được thiết kế là nền tảng độc lập, nên không có frameworks nào có thể trở thành một phần của package chuẩn

+ Sau cùng, tốc độ run ứng dụng và trình dọn dẹp file rác cho các ứng dụng Go phụ thuộc vào 
hệ điều hành nằm bên dưới.

