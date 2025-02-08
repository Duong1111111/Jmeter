1. Giới Thiệu

Bạn là một kiểm thử viên phần mềm trong nhóm phát triển ứng dụng web. Nhóm của bạn cần đánh giá hiệu suất (performance) của trang web chat.hoctiep.com bằng công cụ Apache JMeter.

Báo Cáo Kiểm Thử Hiệu Suất Trang Web chat.hoctiep.com bằng Apache JMeter

1. Giới Thiệu

Báo cáo này trình bày kết quả kiểm thử hiệu suất trang web chat.hoctiep.com bằng công cụ Apache JMeter. Mục tiêu của kiểm thử là đánh giá khả năng chịu tải của hệ thống, xác định bottleneck và đề xuất cải tiến nếu cần.

2. Tạo Test Plan trong JMeter

2.1. Tạo một Test Plan mới

Mở Apache JMeter.

Nhấp chuột phải vào Test Plan → Add → Threads (Users) → Thread Group.

2.2. Cấu hình Thread Group

Number of Threads (Users): 50 (mô phỏng 50 người dùng đồng thời).

Ramp-Up Period: 60 giây (tăng dần số người dùng trong 60 giây).

Duration: 300 giây (chạy trong 5 phút).

2.3. Thêm HTTP Request

Nhấp chuột phải vào Thread Group → Add → Sampler → HTTP Request.

Cấu hình:

Server Name or IP: chat.hoctiep.com

Phương thức HTTP: Chọn GET hoặc POST tùy theo API.

Path: / (trang chủ) hoặc /api/... nếu muốn kiểm thử API.

2.4. Thêm Listener để xem kết quả

Nhấp chuột phải vào Thread Group → Add → Listener.

Chọn Summary Report, View Results Tree, Graph Results để theo dõi kết quả.

2.5. Chạy kiểm thử

Nhấn nút Start (nút Play).

Quan sát thời gian phản hồi, tỷ lệ lỗi, throughput.

3. Kiểm Thử Tải (Load Testing)

Điều chỉnh số lượng Threads từ 10 → 50.

Kiểm tra thời gian phản hồi và tỷ lệ lỗi.

Ghi nhận các kết quả quan trọng.

4. Kiểm Thử Khả Năng Chịu Tải (Stress Testing)

Tăng số người dùng lên 100.

Quan sát thời điểm hệ thống bắt đầu chậm và tỷ lệ lỗi tăng cao.

5. Kết Quả Kiểm Thử

![image](https://github.com/user-attachments/assets/d316c087-1d4a-438e-8fac-d40031ed7fd3)

6. Phân Tích Kết Quả

Ở mức tải 10 - 30 người dùng, hệ thống hoạt động ổn định, thời gian phản hồi dưới 500ms.

Từ 40 người dùng trở lên, thời gian phản hồi tăng đáng kể, tỷ lệ lỗi bắt đầu xuất hiện.

Với 100 người dùng, hệ thống giảm hiệu suất rõ rệt, throughput giảm, tỷ lệ lỗi tăng lên 20%.

7. Kết Luận và Đề Xuất

Hệ thống có thể xử lý tối đa khoảng 40-50 người dùng đồng thời trước khi hiệu suất giảm.

Đề xuất tối ưu hóa:

Cải thiện server backend (tối ưu truy vấn, caching dữ liệu).

Tăng tài nguyên hạ tầng (nâng cấp CPU/RAM, cân bằng tải).

Tối ưu frontend để giảm tải trên server.
