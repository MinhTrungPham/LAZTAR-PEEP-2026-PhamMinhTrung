+++
title = "Ngày 02 - 16/09/2026 (Remote)"
weight = 2
+++

## A. Lý thuyết

## Phần 1. React cơ bản

### React là gì?

React là thư viện JavaScript mã nguồn mở do Meta phát triển để xây dựng giao diện người dùng tương tác. React tổ chức giao diện thành các component có thể tái sử dụng.

### Component trong React là gì? Có mấy loại?

Component là một phần giao diện độc lập, nhận dữ liệu và trả về giao diện cần hiển thị. Có hai loại phổ biến: **Function Component** là hàm trả về JSX và **Class Component** là class kế thừa `React.Component`. Function Component được dùng chủ yếu hiện nay.

### JSX là gì?

JSX là cú pháp mở rộng cho JavaScript, cho phép viết cấu trúc giống HTML trong JavaScript. JSX được biên dịch thành các React element.

### Props là gì?

Props là dữ liệu chỉ đọc được truyền từ component cha xuống component con. Props có thể chứa dữ liệu hoặc callback.

### State là gì? State khác Props thế nào?

State là dữ liệu nội bộ có thể thay đổi và làm component render lại. Props do component cha truyền xuống và component con không nên sửa trực tiếp; state thuộc về component quản lý nó và được cập nhật qua setter.

### Virtual DOM là gì? Vì sao React sử dụng?

Virtual DOM là biểu diễn DOM trong bộ nhớ. React so sánh cây mới với cây cũ rồi chỉ cập nhật phần DOM thật cần thiết, giúp quản lý cập nhật giao diện hiệu quả hơn.

### Hooks là gì? Một số Hook phổ biến

Hooks là các hàm cho phép Function Component sử dụng state và các tính năng React. Các Hook phổ biến gồm `useState`, `useEffect`, `useContext`, `useReducer`, `useRef`, `useMemo` và `useCallback`.

### `useState` dùng để làm gì?

`useState` tạo state trong Function Component và trả về giá trị hiện tại cùng hàm cập nhật. Gọi hàm cập nhật có thể làm component render lại.

### `useEffect` dùng để làm gì?

`useEffect` thực hiện side effect sau khi render, ví dụ gọi API, đăng ký sự kiện hoặc tạo timer. Cleanup dùng để giải phóng tài nguyên khi dependency thay đổi hoặc component bị tháo.

### Lifecycle của React Component

Gồm ba giai đoạn: **Mounting** khi component được tạo, **Updating** khi props hoặc state thay đổi, và **Unmounting** khi component bị loại khỏi giao diện. Với Function Component, `useEffect` và cleanup xử lý các hành vi tương ứng.

### CSR là gì?

Client-Side Rendering là cách trình duyệt tải JavaScript rồi tạo phần lớn giao diện ở phía client. Server thường trả về HTML ban đầu nhỏ và các file JavaScript.

### React Router là gì?

React Router là thư viện định tuyến cho React, ánh xạ URL với component và hỗ trợ route động, nested route, điều hướng không tải lại toàn bộ trang và protected route.

### React thuần có Routing, SEO và API Server không?

React core không tích hợp sẵn routing, SEO server-side hay API server. Có thể dùng React Router, công cụ SEO khác và backend riêng hoặc Next.js cho API server.

### Context API là gì? Khi nào dùng?

Context API chia sẻ dữ liệu qua nhiều tầng component mà không cần truyền props thủ công. Nên dùng cho theme, ngôn ngữ hoặc thông tin user dùng chung; không nên lạm dụng cho mọi state vì cập nhật context có thể làm nhiều component render lại.

### SPA là gì?

SPA (Single Page Application) tải một HTML chính rồi thay đổi nội dung bằng JavaScript khi điều hướng. SPA cho trải nghiệm mượt nhưng cần chú ý SEO, thời gian tải JavaScript và quản lý state.

## Phần 2. So sánh React và Next.js

### Next.js là gì?

Next.js là framework xây dựng trên React, cung cấp routing, nhiều cơ chế rendering, tối ưu hình ảnh, metadata, API server và công cụ build/deploy.

### Khác biệt cốt lõi

React là thư viện tập trung vào UI. Next.js là framework cung cấp kiến trúc và tính năng đầy đủ hơn cho ứng dụng production, trong đó React là nền tảng giao diện.

### Routing khác nhau thế nào?

React cần cài và cấu hình thư viện như React Router. Next.js có File-based Routing: file và thư mục trong `app/` hoặc `pages/` tự tạo URL.

### Rendering khác nhau ra sao?

React thuần thường dùng CSR nếu không kết hợp thêm framework. Next.js hỗ trợ CSR, SSR, SSG và ISR để chọn cách render cho từng trang.

### Vì sao Next.js hỗ trợ SEO tốt hơn?

Next.js có thể tạo HTML trên server hoặc lúc build, nên công cụ tìm kiếm nhận được nội dung ngay trong phản hồi ban đầu. Next.js cũng hỗ trợ metadata và canonical URL thuận tiện hơn.

### First Load khác nhau thế nào?

CSR thường phải tải và thực thi JavaScript trước khi hiển thị đầy đủ nội dung. Next.js có thể gửi HTML đã render trước, nhưng hiệu năng thực tế còn phụ thuộc bundle, dữ liệu, cache và chiến lược rendering.

### Cấu trúc dự án khác nhau ra sao?

React có cấu trúc linh hoạt như `src/components` và `src/pages`. Next.js có convention rõ hơn với `app/` hoặc `pages/`, `public/`, `layout.tsx`, route handlers và file cấu hình.

### Next.js có thay thế React không?

Không. Next.js sử dụng React để xây dựng UI và bổ sung khả năng cho ứng dụng web. Next.js là framework dựa trên React, không phải công nghệ thay thế React.

### Khi nào dùng React thuần và khi nào dùng Next.js?

Dùng React thuần cho SPA nội bộ hoặc dashboard không cần SSR/SEO và muốn tự chọn backend, routing, build tool. Dùng Next.js khi cần SEO, tải trang đầu nhanh, routing tích hợp, SSR/SSG/ISR, full-stack features hoặc convention production.

## Phần 3. Next.js

### App Router và Pages Router là gì?

App Router trong thư mục `app/` là hệ thống hiện đại, hỗ trợ layout lồng nhau, Server Components, streaming và route handlers. Pages Router trong `pages/` là hệ thống cũ hơn nhưng vẫn được hỗ trợ, với các API như `getStaticProps` và `getServerSideProps`.

### Server Component và Client Component khác nhau thế nào?

Server Component được render ở server, phù hợp với việc lấy dữ liệu và không gửi toàn bộ mã component xuống browser. Client Component dùng chỉ thị `"use client"`, gửi JavaScript xuống browser và cần thiết cho state, event handler, effect hoặc browser API.

### SSR là gì?

SSR (Server-Side Rendering) tạo HTML ở server cho mỗi request rồi gửi cho browser. SSR phù hợp với nội dung cần dữ liệu mới theo request và có lợi cho SEO.

### SSG là gì?

SSG (Static Site Generation) tạo HTML tại thời điểm build. Trang tĩnh có thể phân phối nhanh qua CDN, phù hợp với tài liệu và nội dung ít thay đổi.

### ISR là gì?

ISR (Incremental Static Regeneration) cho phép trang tĩnh được cập nhật sau một khoảng thời gian hoặc bằng revalidation mà không cần build lại toàn bộ website.

### File-based Routing hoạt động thế nào?

Next.js ánh xạ file vào URL. `app/about/page.tsx` tạo route `/about`, còn `app/blog/[slug]/page.tsx` tạo dynamic route `/blog/:slug`.

### Dynamic Route là gì?

Dynamic Route có phần URL thay đổi theo dữ liệu, thường viết trong ngoặc vuông như `[id]` hoặc `[slug]`. Giá trị này dùng để tải nội dung tương ứng.

### `layout.tsx` dùng để làm gì?

`layout.tsx` định nghĩa UI dùng chung cho một route và các route con như header, sidebar hoặc provider. Layout được giữ lại khi điều hướng trong cùng nhánh.

### API Routes (Route Handlers) là gì?

Route Handlers là endpoint server định nghĩa trong `route.ts` thuộc `app/`, xử lý các HTTP method như `GET`, `POST`, `PUT` và `DELETE`. Chúng phù hợp cho API nội bộ, webhook hoặc endpoint nhỏ.

### `getStaticProps` và `getServerSideProps` là gì?

Đây là API của Pages Router. `getStaticProps` lấy dữ liệu lúc build để tạo trang tĩnh; `getServerSideProps` lấy dữ liệu ở mỗi request để tạo SSR. Hai API này không dùng trong App Router.

### `next/image` tối ưu hình ảnh thế nào?

`next/image` hỗ trợ kích thước responsive, lazy loading, định dạng phù hợp, caching, đặt kích thước để giảm layout shift và xử lý ảnh remote theo cấu hình.

### Middleware trong Next.js là gì?

Middleware chạy trước khi request hoàn tất. Nó có thể kiểm tra cookie/token, redirect, rewrite, thêm header và giới hạn truy cập. Middleware nên chứa logic nhẹ.

### Điều hướng giữa các trang như thế nào?

Dùng `Link` từ `next/link` cho liên kết nội bộ. Dùng `useRouter` từ `next/navigation` trong Client Component để điều hướng bằng mã; Server Component có thể dùng `redirect`.

### Metadata và SEO được xử lý thế nào?

App Router hỗ trợ export `metadata` hoặc dùng `generateMetadata` cho title, description và Open Graph. Pages Router có thể dùng `next/head`. Ngoài ra nên cấu hình sitemap, robots và canonical URL phù hợp.

### Next.js có hỗ trợ TypeScript không?

Có. Next.js hỗ trợ file `.ts`, `.tsx`, kiểm tra kiểu và cấu hình `tsconfig.json`. Typecheck có thể được đưa vào quy trình build.

### Có thể deploy Next.js ở đâu?

Có thể deploy lên Vercel, AWS, Google Cloud, Azure, Render, Railway, Docker hoặc máy chủ riêng. Trang tĩnh phù hợp cũng có thể deploy lên CDN/static hosting; cần kiểm tra khả năng hỗ trợ SSR, ISR, image optimization và API server.

## B. Thực hành

## Hoàn thiện Portfolios

### Mục tiêu

Hoàn thiện trang portfolio cá nhân xây dựng bằng React và Ant Design, cập nhật nội dung thực tế, tối ưu giao diện responsive và chuẩn bị sản phẩm để trình bày với mentor.

Mục tiêu cuối cùng là có:

- Một trang portfolio cá nhân hoàn chỉnh.
- Giao diện responsive trên desktop và mobile.
- Nội dung giới thiệu, kỹ năng, dự án, kinh nghiệm và thông tin liên hệ.
- Link website đã deploy.
- Link báo cáo tuần được gửi cho mentor thông qua Slack.

### Quá trình thực hiện

**Bước 1: Cài đặt và cấu hình project**

- Cài đặt và kiểm tra các thư viện: React, React DOM, React Router DOM, Ant Design, Lucide React.
- Tạo cấu trúc thư mục cơ bản.

**Bước 2: Xây dựng cấu trúc component**

- Tạo các UI component dùng lại nhiều lần: Button, Card, Modal, Tag, Drawer, IconButton.
- Tạo layout chính cho website.
- Tạo `SiteHeader` với logo cá nhân, navigation, nút liên hệ và mobile drawer navigation.
- Tạo `SiteFooter`.
- Tạo routing bằng `react-router-dom`.
- Tạo `PortfolioLayout` để quản lý layout chung của website.

**Bước 3: Xây dựng landing page**

Landing page được chia thành các section:

- Hero / Introduction
- About Me
- Skills
- Projects
- Experience / Education
- PEEP Report
- Contact

Các section được liên kết bằng anchor navigation để người dùng có thể di chuyển nhanh trong trang.

**Bước 4: Cập nhật nội dung cá nhân**

- Thay thế nội dung mẫu bằng thông tin từ CV cá nhân.
- Bổ sung kỹ năng được phân nhóm: Programming, Backend, Frontend, Database, Tools & AI.
- Thêm các dự án thực tế với mô tả, công nghệ sử dụng và vai trò.
- Thêm thông tin học vấn và kinh nghiệm.
- Thêm thông tin liên hệ và các đường dẫn mạng xã hội.

**Bước 5: Tinh chỉnh giao diện và kiểm tra**

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
