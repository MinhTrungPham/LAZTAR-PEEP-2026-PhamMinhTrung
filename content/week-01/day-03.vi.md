+++
title = "Ngày 03 - 17/09/2026 (Remote)"
weight = 3
+++

### Links

- [Source Code](https://github.com/MinhTrungPham/weekly-reports/tree/main/tuan-01/landing-page)
- [Live Demo](https://landing-page-phi-tan-xz2x97g6ov.vercel.app/)

## Thực hành

## Xây dựng Landing Page Naruto

### Tổng quan

Công việc chính trong ngày là xây dựng nền tảng landing page giới thiệu anime Naruto theo phong cách **Dark Cinematic + Japanese + Bento Grid**. Trang được thiết kế như một trải nghiệm nhập vai vào thế giới shinobi — bao gồm nhân vật, hành trình, kỹ thuật và các mối quan hệ quan trọng.

---

### Công nghệ sử dụng

| Tầng              | Lựa chọn                          |
| ------------------ | ----------------------------------- |
| Framework          | Next.js 16 với App Router          |
| UI                 | React 19 + TypeScript               |
| Design System      | `@buildo/bento-design-system`     |
| Styling            | Tailwind CSS / PostCSS + CSS custom |
| Chất lượng code | ESLint                              |

---

### Kiến trúc project

Project được tổ chức theo hướng tách biệt layout, UI primitive, section và data:

```text
landing-page/
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   ├── globals.css
│   └── styles/
│       ├── base.css
│       ├── naruto-theme.css
│       ├── motion.css
│       ├── sections.css
│       └── jutsu-orbit.css
├── components/
│   ├── layout/
│   │   ├── MarketingLayout.tsx
│   │   ├── SiteHeader.tsx
│   │   └── SiteFooter.tsx
│   ├── sections/
│   │   ├── NarutoLanding.tsx
│   │   └── naruto/
│   │       ├── AboutSection.tsx
│   │       ├── CharactersSection.tsx
│   │       ├── HeroSection.tsx
│   │       ├── IconicMomentsSection.tsx
│   │       ├── JourneySection.tsx
│   │       ├── JutsuSection.tsx
│   │       ├── NarutoCtaSection.tsx
│   │       ├── QuotesSection.tsx
│   │       ├── RivalrySection.tsx
│   │       ├── ShinobiWorldSection.tsx
│   │       ├── ActionButton.tsx
│   │       └── SectionHeading.tsx
│   └── ui/
│       ├── Container.tsx
│       └── Section.tsx
└── data/
    └── naruto.ts
```

`NarutoLanding.tsx` chỉ đóng vai trò composer, lắp các section theo thứ tự. Toàn bộ nội dung mock và interface TypeScript được tập trung trong `data/naruto.ts`, giúp section component không phải hard-code dữ liệu.

---

### Những gì đã xây dựng

**Nền tảng**

Tích hợp Bento Design System, cấu hình metadata trang, tạo `MarketingLayout` làm wrapper chung cho header, main content và footer. Thêm anchor navigation trên header.

**Các section**

Landing page được chia thành mười section độc lập:

| #  | Section          | Mục đích                                       |
| -- | ---------------- | ------------------------------------------------- |
| 1  | Hero             | Giới thiệu chủ đề chính và CTA             |
| 2  | About Naruto     | Câu chuyện và hành trình được công nhận |
| 3  | Shinobi World    | Chakra, Bonds và Will of Fire                    |
| 4  | Characters       | Naruto, Sasuke, Sakura                            |
| 5  | The Journey      | Timeline từ Academy đến thế hệ tiếp theo    |
| 6  | Iconic Moments   | Các khoảnh khắc nổi bật                      |
| 7  | Jutsu            | Orbit tương tác các kỹ thuật ninja          |
| 8  | Quotes           | Câu nói tiêu biểu trong series                |
| 9  | Naruto vs Sasuke | Mối quan hệ đối đầu và gắn kết           |
| 10 | CTA              | Lời kêu gọi tiếp tục hành trình            |

**Hero section** gồm eyebrow tiếng Nhật và tiếng Anh, tagline chính *"The way of the ninja is never a straight line."*, mô tả ngắn về thế giới shinobi, CTA `Enter the shinobi world` và badge `火の意志 / WILL OF FIRE`.

**Mock data và interface**

Đã định nghĩa các TypeScript interface để chuẩn hóa dữ liệu cho từng section:
`HeroContent`, `FeatureItem`, `CharacterProfile`, `TeamMember`, `TimelineEntry`, `IconicMoment`, `JutsuItem`, `QuoteItem`, `RivalryContent`.

---

### Thiết kế giao diện

**Color palette**

```text
Background: #0B0B0F
Surface:    #15151C
Orange:     #FF6B00
Yellow:     #FFA726
White:      #F5F5F5
Muted:      #9CA3AF
```

**Định hướng visual** — dark cinematic, lấy cảm hứng từ Nhật Bản, tương phản cao, nhiều chi tiết vòng tròn, kanji (`忍`, `術`, `言葉`) và border kỹ thuật. Heading lớn, đậm, condensed. Body text dùng sans-serif dễ đọc. Accent màu cam lấy cảm hứng từ Naruto.

CSS được tách thành các file riêng theo trách nhiệm (`base`, `naruto-theme`, `motion`, `sections`, `jutsu-orbit`) để dễ maintain.
