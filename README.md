# WisePick AI
## Giới thiệu
WisePick AI là nền tảng tìm kiếm, đánh giá và đề xuất sản phẩm sử dụng AI. Người dùng có thể mô tả nhu cầu bằng ngôn ngữ tự nhiên, hệ thống sẽ phân tích nhu cầu, tìm kiếm sản phẩm phù hợp, so sánh các lựa chọn và cung cấp đánh giá dựa trên dữ liệu sản phẩm.

WisePick cũng tích hợp video review từ YouTube và affiliate links để giúp người dùng tham khảo thêm trước khi đưa ra quyết định mua hàng.
## Mục tiêu dự án
Xây dựng một AI Shopping Assistant giúp người dùng:
- Tìm đúng sản phẩm theo nhu cầu
- Tiết kiệm thời gian tìm kiếm và so sánh
- Hiểu rõ ưu và nhược điểm của sản phẩm
- Tham khảo thêm các video review thực tế
- Tiếp cận các lựa chọn mua hàng phù hợp
## Tính năng
### AI & Đề xuất sản phẩm

- [ ] Tìm kiếm sản phẩm bằng ngôn ngữ tự nhiên
- [ ] Phân tích nhu cầu và ngân sách của người dùng
- [ ] Xác định danh mục sản phẩm cần tìm
- [ ] Đề xuất các sản phẩm phù hợp
- [ ] Chấm điểm mức độ phù hợp
- [ ] Giải thích lý do đề xuất sản phẩm
- [ ] AI đánh giá ưu điểm và nhược điểm
- [ ] So sánh nhiều sản phẩm

### Sản phẩm

- [ ] Tìm kiếm sản phẩm
- [ ] Lọc theo danh mục
- [ ] Lọc theo mức giá
- [ ] Xem thông tin chi tiết sản phẩm
- [ ] Hiển thị thông số kỹ thuật
- [ ] Hiển thị giá và đánh giá
- [ ] So sánh sản phẩm
- [ ] Liên kết đến nơi mua hàng

### YouTube Review

- [ ] Tìm video review liên quan đến sản phẩm
- [ ] Hiển thị thumbnail, tiêu đề và kênh
- [ ] Cho phép người dùng mở/ẩn phần video review
- [ ] Ưu tiên video phù hợp với sản phẩm
- [ ] Lưu cache kết quả tìm kiếm video

### Người dùng

- [ ] Đăng ký / đăng nhập
- [ ] Lưu sản phẩm yêu thích
- [ ] Lưu lịch sử tìm kiếm
- [ ] Lưu lịch sử trò chuyện với AI
- [ ] Cá nhân hóa đề xuất

### Affiliate

- [ ] Tích hợp affiliate links
- [ ] Chuyển người dùng đến trang sản phẩm
- [ ] Theo dõi lượt click
- [ ] Thống kê hiệu quả affiliate
- [ ] Hiển thị thông báo minh bạch về affiliate

### Quản trị

- [ ] Quản lý sản phẩm
- [ ] Quản lý danh mục
- [ ] Quản lý nguồn dữ liệu
- [ ] Quản lý affiliate links
- [ ] Theo dõi lượt click
- [ ] Xem thống kê sản phẩm được quan tâm

## AI hoạt động như thế nào
```text
Người dùng
   ↓
Mô tả nhu cầu bằng ngôn ngữ tự nhiên
   ↓
AI phân tích nhu cầu
   ↓
Xác định danh mục + ngân sách + tiêu chí
   ↓
Tìm kiếm sản phẩm thực tế
   ↓
Lọc và chấm điểm sản phẩm
   ↓
AI phân tích và giải thích
   ↓
Đề xuất sản phẩm phù hợp
```
## Kiến trúc hệ thống
```text
                    Người dùng
                        │
                        ▼
                 WisePick AI
                    Next.js
                        │
                        ▼
                  AI Assistant
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
    Phân tích nhu cầu  Đề xuất      AI Review
          │           sản phẩm          │
          └─────────────┼─────────────┘
                        ▼
                Product Services
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
     Product API     MongoDB      YouTube API
          │             │             │
          └─────────────┼─────────────┘
                        ▼
                Kết quả sản phẩm
                        │
          ┌─────────────┴─────────────┐
          ▼                           ▼
      So sánh sản phẩm           Video Review
          │                           │
          └─────────────┬─────────────┘
                        ▼
                 Affiliate Link
                        │
                        ▼
                  Trang mua hàng
```
## Công nghệ sử dụng
Frontend
Next.js
TypeScript
Tailwind CSS
Backend
Next.js API / Route Handlers
REST API
Database
MongoDB
AI
LLM API
External APIs
Product API
YouTube Data API
Deployment
Vercel
## External APIs
Product Data
API được sử dụng để lấy thông tin sản phẩm thực tế như:
 - Tên sản phẩm
 - Giá
 - Hình ảnh
 - Thông số
 - Đánh giá
 - Link sản phẩm
 # YouTube Data API
 Sử dụng để tìm kiếm các video review liên quan đến sản phẩm.

# Affiliate Network
Sử dụng affiliate links để chuyển người dùng đến trang mua hàng và theo dõi referral.

## Affiliate Model
WisePick có thể sử dụng affiliate links để giới thiệu sản phẩm.
Khi người dùng truy cập trang sản phẩm thông qua affiliate link và thực hiện
giao dịch đủ điều kiện, WisePick có thể nhận được commission từ chương trình affiliate tương ứng.
## Roadmap
### Giai đoạn 1 — MVP
- [x] Khởi tạo dự án
- [ ] Xây dựng trang chủ
- [ ] Xây dựng giao diện Chat
- [ ] Xây dựng thẻ sản phẩm
- [ ] Xây dựng trang chi tiết sản phẩm
- [ ] Tạo dữ liệu sản phẩm mẫu

### Giai đoạn 2 — AI
- [ ] Tích hợp Chat AI
- [ ] Phân tích và trích xuất nhu cầu người dùng
- [ ] Đề xuất sản phẩm phù hợp
- [ ] Đánh giá sản phẩm bằng AI
- [ ] So sánh sản phẩm

### Giai đoạn 3 — Dữ liệu bên ngoài
- [ ] Tích hợp API sản phẩm
- [ ] Tích hợp YouTube API
- [ ] Sử dụng dữ liệu sản phẩm thực tế
- [ ] Tích hợp liên kết Affiliate

### Giai đoạn 4 — Tính năng người dùng
- [ ] Đăng ký và đăng nhập
- [ ] Lưu sản phẩm yêu thích
- [ ] Lưu lịch sử tìm kiếm
- [ ] Cá nhân hóa đề xuất sản phẩm

### Giai đoạn 5 — Hoàn thiện sản phẩm
- [ ] Tối ưu SEO
- [ ] Tích hợp thống kê và phân tích
- [ ] Theo dõi giá sản phẩm
- [ ] Xây dựng trang quản trị
- [ ] Triển khai dự án
## Lưu ý
 - Dữ liệu sản phẩm phụ thuộc vào nguồn API được tích hợp.
 - Giá và tình trạng sản phẩm có thể thay đổi theo thời gian.
 - Nội dung AI chỉ mang tính chất tham khảo.
 - Affiliate links được công khai minh bạch với người dùng.
## Tác giả
Đàm Thanh Danh