1. Giới Thiệu

Bạn là một kiểm thử viên phần mềm trong nhóm phát triển ứng dụng web. Nhóm của bạn cần đánh giá hiệu suất (performance) của trang web chat.hoctiep.com bằng công cụ Apache JMeter.

2. Cài Đặt Apache JMeter

2.1. Tải và Cài Đặt

Truy cập trang chủ Apache JMeter và tải xuống phiên bản mới nhất.

Giải nén tệp tải về và đặt trong một thư mục thích hợp.

Chạy jmeter

3. Thiết Lập Kịch Bản Kiểm Thử Hiệu Suất

3.1. Mô phỏng 50 người dùng trong 5 phút

Mở Apache JMeter và tạo một Test Plan mới.

Nhấp chuột phải vào Test Plan → Add → Threads (Users) → Thread Group.

Thiết lập:

Số Thread (Users): 50

Ramp-up Period: 60 giây

Duration: 300 giây

Nhấp chuột phải vào Thread Group → Add → Sampler → HTTP Request.

Nhập Server Name or IP: chat.hoctiep.com.

Phương thức HTTP: Chọn GET.

Path: / (trang chủ) hoặc /api/... nếu kiểm thử API.

Nhấp chuột phải vào Thread Group → Add → Listener → Summary Report, View Results Tree, Graph Results để quan sát kết quả.

Lưu lại Test Plan.

3.2. Đo Thời Gian Phản Hồi & Xác Định Bottleneck

Nhấn nút Start để chạy kịch bản kiểm thử.

Quan sát biểu đồ thời gian phản hồi trong Graph Results.

Kiểm tra Summary Report để xem tổng quan kết quả.

Nếu thời gian phản hồi cao, xác định yếu tố gây tắc nghẽn bằng cách kiểm tra View Results Tree.

4. Kiểm Thử Tải (Load Testing)

Thay đổi số lượng người dùng trong Thread Group:

10 → 20 → 30 → 40 → 50.

Chạy từng kịch bản và ghi nhận:

Thời gian phản hồi trung bình.

Tỷ lệ lỗi (Error Rate).

5. Kiểm Thử Khả Năng Chịu Tải (Stress Testing)

Tăng số lượng người dùng lên 100 trong Thread Group.

Quan sát kết quả:

Khi nào hệ thống bắt đầu giảm hiệu suất?

Lỗi xảy ra ở mức tải nào?

6. Phân Tích Kết Quả

Xuất báo cáo bằng cách vào File → Save Table Data trong Summary Report.

Phân tích các thông số quan trọng:

Thời gian phản hồi trung bình

Throughput (số yêu cầu xử lý mỗi giây)

Tỷ lệ lỗi

Đưa ra kết luận:

Hệ thống có đáp ứng yêu cầu hiệu suất không?

Nếu không, nguyên nhân có thể là gì?

7. Câu Hỏi Thảo Luận

Tại sao kiểm thử phi chức năng lại quan trọng trong phần mềm?

Kiểm thử phi chức năng (đặc biệt là kiểm thử hiệu suất) giúp đánh giá khả năng đáp ứng của hệ thống trong điều kiện tải cao.

Các thông số quan trọng trong kiểm thử hiệu suất?

Thời gian phản hồi, throughput, CPU/memory usage, Error Rate.

Nếu hệ thống không đáp ứng yêu cầu hiệu suất, bạn sẽ đề xuất giải pháp gì?

Tối ưu mã nguồn, tăng cơ sở hạ tầng, sử dụng caching, load balancing.
