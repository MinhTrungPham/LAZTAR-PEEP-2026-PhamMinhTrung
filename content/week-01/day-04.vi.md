+++
title = "Ngày 04 - 18/09/2026 (On-site)"
weight = 4
+++

## Mục tiêu

Hoàn thiện nội dung cá nhân và tinh chỉnh giao diện cho trang web portfolio cá nhân.

### Các công việc thực hiện

**Cập nhật nội dung cá nhân**

- Thay thế nội dung mẫu bằng thông tin từ CV cá nhân.
- Bổ sung kỹ năng được phân nhóm: Programming, Backend, Frontend, Database, Tools & AI.
- Thêm các dự án thực tế với mô tả, công nghệ sử dụng và vai trò.
- Thêm thông tin học vấn và kinh nghiệm.
- Thêm thông tin liên hệ và các đường dẫn mạng xã hội.

**Tinh chỉnh giao diện và kiểm tra**

- Redesign section About Me và thêm profile snapshot card với các chỉ số nổi bật.
- Đổi palette từ màu beige/cam sang màu xanh lạnh.
- Thêm bo góc cho button, card, tag và các section.
- Thêm shadow nhẹ để giao diện có chiều sâu hơn.
- Thay favicon mặc định bằng logo tùy chỉnh.
- Kiểm tra responsive trên các kích thước màn hình khác nhau.
- Chạy production build để xác nhận không có lỗi.

### Link Demo

- [Personal Portfolio](https://minhtrungportfolios-ebon.vercel.app/)
- [Source Code](https://github.com/MinhTrungPham/weekly-reports/tree/main/tuan-01/my%20portfolios)

## Tổng kết

Ba ngày đầu tuần tập trung vào hai mảng song song: xây dựng nền tảng lý thuyết về React và Next.js, đồng thời đưa kiến thức vào thực hành qua hai sản phẩm cụ thể.

### Bài học từ Ngày 2 — React & Next.js

Ngày 2 là buổi học lý thuyết chuyên sâu, giúp hình thành bức tranh tổng thể về hệ sinh thái frontend hiện đại:

- **React là thư viện UI**, không phải framework — routing, SSR hay API server cần thêm công cụ bên ngoài hoặc chuyển sang Next.js.
- **Virtual DOM và reconciliation** là cơ chế cốt lõi giúp React cập nhật giao diện hiệu quả mà không cần thao tác trực tiếp vào DOM thật.
- **Hooks** (`useState`, `useEffect`, `useContext`...) thay thế hoàn toàn Class Component trong luồng phát triển hiện đại.
- **Next.js mở rộng React** với File-based Routing, Server/Client Component, SSR/SSG/ISR, API Route Handler và hỗ trợ SEO — đây là lựa chọn phù hợp cho hầu hết dự án production.
- Sự phân biệt giữa **Server Component** và **Client Component** (`"use client"`) là điểm quan trọng cần nắm khi làm việc với App Router.

### Bài học từ Ngày 3 — Landing Page Naruto

Ngày 3 là buổi thực hành đầu tiên với Next.js, xây dựng landing page giới thiệu anime Naruto:

- Áp dụng **App Router** với kiến trúc tách biệt rõ ràng: layout, section component, UI primitive và data layer (`naruto.ts`).
- **Bento Grid** kết hợp với thiết kế Dark Cinematic tạo ra visual identity mạnh; kinh nghiệm rút ra là design system (màu sắc, typography, spacing) nên được xác định từ sớm.
- Tách CSS thành nhiều file theo trách nhiệm (`base`, `theme`, `motion`, `sections`) giúp codebase dễ mở rộng và bảo trì hơn so với một file CSS đơn lớn.
- **TypeScript interface** chuẩn hóa dữ liệu cho từng section, tránh hard-code và tạo điểm mở rộng dễ dàng khi thêm nội dung mới.

### Bài học từ Ngày 4 — Personal Portfolio

Ngày 4 đánh dấu việc hoàn thiện sản phẩm cá nhân đầu tiên đủ điều kiện demo:

- **Nội dung thực tế quan trọng hơn placeholder** — cập nhật từ CV thực tế khiến portfolio trở nên có giá trị hơn hẳn về mặt trình bày nghề nghiệp.
- **Thiết kế nhất quán** đòi hỏi quyết định sớm về palette màu, border-radius, shadow và typography; thay đổi muộn (beige/cam → xanh lạnh) tốn thời gian hơn nếu giá trị chưa được token hóa.
- **Production build** cần chạy trước khi deploy; lỗi build thường khác với lỗi development mode, đặc biệt với Next.js (Server Component, dynamic import, metadata).
- **Responsive testing** không thể bỏ qua — layout trông ổn trên desktop có thể bị vỡ trên mobile nếu không kiểm tra sớm.
- Việc deploy lên **Vercel** ngay từ sớm giúp có link demo thực tế để báo cáo và nhận phản hồi nhanh hơn.

### Nhìn lại tuần đầu

Ba ngày học kết hợp lý thuyết và thực hành cho thấy: kiến thức React/Next.js chỉ thực sự vững khi được kiểm chứng qua code thực tế. Hai sản phẩm đã deploy — landing page Naruto và portfolio cá nhân — là bằng chứng cụ thể cho quá trình học trong tuần đầu.