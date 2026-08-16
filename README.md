# WisePick AI

## Giới thiệu

WisePick AI là nền tảng tìm kiếm, đánh giá, so sánh và đề xuất sản phẩm sử dụng AI.

Thay vì phải tự tìm kiếm và so sánh nhiều sản phẩm, người dùng có thể mô tả nhu cầu bằng ngôn ngữ tự nhiên. Hệ thống sẽ phân tích nhu cầu, ngân sách và các tiêu chí ưu tiên, sau đó tìm kiếm và đề xuất những sản phẩm phù hợp.

WisePick cũng tích hợp **AI Review, YouTube Review và Affiliate Links** để giúp người dùng có thêm thông tin trước khi đưa ra quyết định mua hàng.

---

##  Mục tiêu dự án

Xây dựng một **AI Shopping Assistant** giúp người dùng:

* Tìm đúng sản phẩm theo nhu cầu.
* Tiết kiệm thời gian tìm kiếm và so sánh.
* Hiểu rõ ưu điểm và nhược điểm của sản phẩm.
* Nhận được đề xuất phù hợp với ngân sách và mục đích sử dụng.
* Tham khảo thêm các video review thực tế.
* Tiếp cận các lựa chọn mua hàng phù hợp thông qua affiliate links.

---

##  Tính năng

###  AI & Đề xuất sản phẩm

* [ ] Tìm kiếm sản phẩm bằng ngôn ngữ tự nhiên.
* [ ] Phân tích nhu cầu và ngân sách của người dùng.
* [ ] Xác định danh mục sản phẩm cần tìm.
* [ ] Trích xuất mục đích sử dụng và tiêu chí ưu tiên.
* [ ] Đề xuất các sản phẩm phù hợp.
* [ ] Chấm điểm mức độ phù hợp của sản phẩm.
* [ ] Giải thích lý do đề xuất sản phẩm.
* [ ] AI đánh giá ưu điểm và nhược điểm.
* [ ] So sánh nhiều sản phẩm.
* [ ] AI Streaming khi trả lời.

###  Sản phẩm

* [ ] Tìm kiếm sản phẩm.
* [ ] Lọc theo danh mục.
* [ ] Lọc theo mức giá.
* [ ] Sắp xếp sản phẩm.
* [ ] Xem thông tin chi tiết sản phẩm.
* [ ] Hiển thị thông số kỹ thuật.
* [ ] Hiển thị giá và đánh giá.
* [ ] Hiển thị mức độ phù hợp với nhu cầu.
* [ ] So sánh sản phẩm.
* [ ] Liên kết đến nơi mua hàng.

###  YouTube Review

* [ ] Tìm video review liên quan đến sản phẩm.
* [ ] Hiển thị thumbnail, tiêu đề và kênh.
* [ ] Hiển thị số lượt xem và thời gian đăng.
* [ ] Cho phép người dùng mở hoặc ẩn phần video review.
* [ ] Ưu tiên video phù hợp với sản phẩm.
* [ ] Lưu cache kết quả tìm kiếm video.

###  Tính năng người dùng

* [ ] Đăng ký / đăng nhập.
* [ ] Lưu sản phẩm yêu thích.
* [ ] Lưu lịch sử tìm kiếm.
* [ ] Lưu lịch sử trò chuyện với AI.
* [ ] Cá nhân hóa đề xuất sản phẩm.

###  Affiliate

* [ ] Tích hợp affiliate links.
* [ ] Chuyển người dùng đến trang sản phẩm.
* [ ] Theo dõi lượt click.
* [ ] Thống kê hiệu quả affiliate.
* [ ] Hiển thị thông báo minh bạch về affiliate.

###  Quản trị

* [ ] Quản lý sản phẩm.
* [ ] Quản lý danh mục.
* [ ] Quản lý nguồn dữ liệu.
* [ ] Quản lý affiliate links.
* [ ] Theo dõi lượt click.
* [ ] Xem thống kê sản phẩm được quan tâm.

---

##  AI hoạt động như thế nào

```text
Người dùng
    ↓
Mô tả nhu cầu bằng ngôn ngữ tự nhiên
    ↓
AI phân tích nhu cầu
    ↓
Xác định:
- Danh mục
- Ngân sách
- Mục đích sử dụng
- Tiêu chí ưu tiên
    ↓
Tìm kiếm sản phẩm thực tế
    ↓
Lọc và chấm điểm sản phẩm
    ↓
AI phân tích và giải thích
    ↓
Đề xuất sản phẩm phù hợp
```

Ví dụ:

```text
"Tôi cần tai nghe dưới 2 triệu để đi xe buýt,
ưu tiên chống ồn và pin tốt."
```

Hệ thống có thể xác định:

```text
Danh mục: Tai nghe
Ngân sách: ≤ 2.000.000đ
Mục đích: Di chuyển
Ưu tiên:
- Chống ồn
- Thời lượng pin
```

---

##  Kiến trúc hệ thống

```text
                         Người dùng
                             │
                             ▼
                    ┌─────────────────┐
                    │    Next.js      │
                    │ React / TS      │
                    │    Frontend     │
                    └────────┬────────┘
                             │
                        HTTP / SSE
                             │
                             ▼
                    ┌─────────────────┐
                    │     FastAPI     │
                    │     Python      │
                    │    Backend      │
                    └────────┬────────┘
                             │
            ┌────────────────┼────────────────┐
            ▼                ▼                ▼
       AI / LLM         Product API      YouTube API
            │                │                │
            └────────────────┼────────────────┘
                             ▼
                         MongoDB
                             │
                 ┌───────────┼───────────┐
                 ▼           ▼           ▼
             AI Review   Compare     Recommendation
                 │           │           │
                 └───────────┼───────────┘
                             ▼
                      Affiliate Link
                             │
                             ▼
                      Trang mua hàng
```

### 🔄 AI Streaming

WisePick sử dụng cơ chế streaming để hiển thị phản hồi AI theo thời gian thực.

```text
Người dùng
    ↓
Next.js
    ↓
FastAPI
    ↓
LLM
    ↓
Streaming Response
    ↓
Next.js
    ↓
Hiển thị nội dung theo từng phần
```

---

##  Công nghệ sử dụng

### Frontend

* Next.js
* React
* TypeScript
* Tailwind CSS
* Motion
* Lucide React

### Backend

* Python
* FastAPI
* Pydantic
* Uvicorn

### Database

* MongoDB

### AI

* LLM API
* AI Streaming

### External APIs

* Product API
* YouTube Data API
* Affiliate Network

### Deployment

* Vercel cho Frontend
* Backend Hosting cho FastAPI

---

##  External APIs

### Product API

Được sử dụng để lấy dữ liệu sản phẩm thực tế như:

* Tên sản phẩm.
* Giá.
* Hình ảnh.
* Thông số kỹ thuật.
* Đánh giá.
* Thông tin người bán.
* Link sản phẩm.

### YouTube Data API

Được sử dụng để:

* Tìm kiếm video review.
* Lấy thông tin video.
* Lấy thumbnail.
* Lấy tên kênh.
* Lấy số lượt xem.
* Lấy thời gian đăng video.

### Affiliate Network

Được sử dụng để:

* Tạo affiliate links.
* Chuyển người dùng đến trang mua hàng.
* Theo dõi referral và lượt click.
* Hỗ trợ mô hình kiếm tiền từ affiliate.

---

##  Mô hình Affiliate

WisePick có thể sử dụng affiliate links để giới thiệu sản phẩm đến người dùng.

Khi người dùng truy cập trang sản phẩm thông qua affiliate link và thực hiện giao dịch đủ điều kiện, WisePick có thể nhận được commission từ chương trình affiliate tương ứng.

> **Affiliate Disclosure:** Một số liên kết trên WisePick có thể là affiliate links. WisePick có thể nhận được hoa hồng nếu người dùng mua hàng thông qua các liên kết này. Điều này không làm thay đổi giá sản phẩm đối với người mua.

---

##  Cấu trúc dự án
```text
wisepick-ai/
│
├── frontend/
│   ├── src/
│   │   ├── app/
│   │   ├── components/
│   │   ├── data/
│   │   ├── lib/
│   │   └── types/
│   │
│   ├── public/
│   ├── package.json
│   └── ...
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── routers/
│   │   ├── services/
│   │   ├── schemas/
│   │   ├── models/
│   │   └── core/
│   │
│   ├── requirements.txt
│   └── ...
│
├── README.md
├── .gitignore
└── ...
```

---

##  Cài đặt & chạy project

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend:

```text
http://localhost:3000
```

### Backend

Tạo môi trường ảo:

```bash
cd backend
python -m venv .venv
```

Kích hoạt môi trường ảo trên Windows:

```bash
.venv\Scripts\activate
```

Cài đặt dependencies:

```bash
pip install -r requirements.txt
```

Chạy FastAPI:

```bash
uvicorn app.main:app --reload
```

Backend:

```text
http://localhost:8000
```

Tài liệu API:

```text
http://localhost:8000/docs
```

---

##  Roadmap

### Giai đoạn 1 — Phân tích & thiết kế

* [x] Khởi tạo GitHub Repository.
* [x] Xây dựng README.
* [x] Sitemap.
* [x] User Flow.
* [ ] Wireframe Landing Page.
* [ ] Thiết kế UI trên Figma.
* [ ] Xây dựng Design System.

### Giai đoạn 2 — Backend

* [ ] Thiết lập Python.
* [ ] Thiết lập FastAPI.
* [ ] Xây dựng cấu trúc backend.
* [ ] Tạo API cơ bản.
* [ ] Thiết kế API contract.
* [ ] Kết nối MongoDB.
* [ ] Thiết lập biến môi trường.

### Giai đoạn 3 — Frontend

* [ ] Xây dựng Landing Page.
* [ ] Xây dựng giao diện Chat.
* [ ] Xây dựng Product Card.
* [ ] Xây dựng trang danh sách sản phẩm.
* [ ] Xây dựng trang chi tiết sản phẩm.
* [ ] Xây dựng trang so sánh.

### Giai đoạn 4 — AI

* [ ] Tích hợp LLM.
* [ ] Xây dựng Chat AI.
* [ ] AI Streaming.
* [ ] Phân tích và trích xuất nhu cầu.
* [ ] Đề xuất sản phẩm.
* [ ] Chấm điểm mức độ phù hợp.
* [ ] AI Review.
* [ ] AI Compare.

### Giai đoạn 5 — Dữ liệu bên ngoài

* [ ] Tích hợp Product API.
* [ ] Sử dụng dữ liệu sản phẩm thực tế.
* [ ] Tích hợp YouTube Data API.
* [ ] Hiển thị video review.
* [ ] Tích hợp Affiliate Network.
* [ ] Theo dõi affiliate click.

### Giai đoạn 6 — Tính năng người dùng

* [ ] Đăng ký / đăng nhập.
* [ ] Sản phẩm yêu thích.
* [ ] Lịch sử tìm kiếm.
* [ ] Lịch sử trò chuyện.
* [ ] Cá nhân hóa đề xuất.

### Giai đoạn 7 — Hoàn thiện sản phẩm

* [ ] Tối ưu SEO.
* [ ] Tích hợp Analytics.
* [ ] Theo dõi giá sản phẩm.
* [ ] Xây dựng Admin Dashboard.
* [ ] Tối ưu hiệu năng.
* [ ] Deploy Frontend.
* [ ] Deploy Backend.

---

##  Lưu ý

* Dữ liệu sản phẩm phụ thuộc vào nguồn API hoặc product feed được tích hợp.
* Giá, tình trạng sản phẩm và thông tin bán hàng có thể thay đổi theo thời gian.
* Nội dung do AI tạo ra chỉ mang tính chất tham khảo.
* YouTube Reviews được cung cấp nhằm giúp người dùng tham khảo thêm từ các nguồn bên ngoài.
* Affiliate links được công khai minh bạch với người dùng.
* Các API và nguồn dữ liệu bên ngoài phải được sử dụng theo điều khoản của từng nhà cung cấp.

---

## Tác giả

**Đàm Thanh Danh**

Web Developer

**Định hướng:** Frontend Development · Fullstack Development · AI Application
