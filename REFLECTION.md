# 📋 Báo Cáo Tổng Kết Sử Dụng AI (AI Learning Reflection)

<div align="center">

![Student](https://img.shields.io/badge/Sinh%20viên-Nguy%E1%BB%85n%20%C4%90%C4%B3nh%20Thi-blue?style=for-the-badge)
![ID](https://img.shields.io/badge/MSSV-DE180805-orange?style=for-the-badge)
![Course](https://img.shields.io/badge/M%C3%B4n%20h%E1%BB%8Dc-SWP391-blue?style=for-the-badge)

</div>

---

## 1. Thông tin chung

| Thông tin | Nội dung |
| :--- | :--- |
| **Môn học** | Software Development Project |
| **Mã môn học** | SWP391 |
| **Lớp** | SE20A06 |
| **Học kỳ** | SUMMER 2026 |
| **Tên dự án** | **XFoodi** - Nền tảng SaaS quản lý nhà hàng đa thuê (Multi-tenant SaaS Platform) |
| **Thành viên** | Nguyễn Đình Thi (Nhóm 6 - Leader / Security Engineer) |
| **Mã số sinh viên** | DE180805 |
| **Giảng viên hướng dẫn** | HanhNT |

---

## 2. Đánh giá quá trình sử dụng AI trong Project

### 2.1. Trợ lý AI đã hỗ trợ tốt nhất ở những điểm nào?
- **Khởi tạo và Phân tách Yêu cầu nghiệp vụ (Requirements & Ideation):** Hỗ trợ đắc lực trong việc định hình cấu trúc tổng quan của một hệ thống SaaS đa thuê phức tạp, đưa ra các gợi ý thực tế về việc thiết lập và phân cấp các phân hệ cho Super Admin, Restaurant Owner, và Staff.
- **Tạo mẫu cấu trúc cơ sở dữ liệu (Boilerplate & Schema):** Giúp nhanh chóng sinh các tệp Prisma Schema cơ bản cho các thực thể quan hệ, tiết kiệm tối đa thời gian khai báo cấu trúc bảng ban đầu.
- **Gợi ý giải pháp công nghệ mới:** Cung cấp tài liệu và mã nguồn mẫu cho việc sử dụng thư viện bảo mật `otpauth` để xây dựng tính năng 2FA và tích hợp API xác thực siteverify của Cloudflare Turnstile.

### 2.2. Khó khăn / Hạn chế lớn nhất của AI trong ngữ cảnh dự án này?
- **Không hiểu sâu về nghiệp vụ thực tế tại thị trường Việt Nam:** Đề xuất luồng thanh toán tự động trừ tiền trước qua thẻ tín dụng như mô hình nước ngoài, không phù hợp với thói quen ăn trước trả sau và quét mã VietQR tại Việt Nam.
- **Đề xuất các giải pháp bảo mật kém an toàn:** Khuyên lưu trữ Access Token vào `localStorage` ở Frontend để tiện lập trình, tạo ra lỗ hổng bảo mật nghiêm trọng (XSS) cho tài khoản admin.
- **Sinh code lỗi cú pháp hoặc sử dụng thư viện lỗi thời:** Đề xuất thư viện mã hóa `speakeasy` đã ngừng bảo trì, hoặc gửi dữ liệu dạng JSON cho API Cloudflare Turnstile (trong khi API này bắt buộc định dạng `application/x-www-form-urlencoded`).

### 2.3. Quy trình tự kiểm tra và kiểm thử kết quả từ AI để đảm bảo chất lượng
- **Kiểm duyệt mã nguồn (Code Review & Linting):** Mọi đoạn mã do AI gợi ý đều được rà soát thủ công, đưa vào IDE chạy qua trình biên dịch TypeScript và kiểm tra nghiêm ngặt với lệnh `pnpm run lint` để loại bỏ các cảnh báo và biến không sử dụng.
- **Kiểm thử cô lập dữ liệu (Tenant Isolation Testing):** Thực hiện đăng nhập song song 2 nhà hàng khác nhau (Tenant A và Tenant B), thực hiện các tác vụ CRUD để kiểm chứng middleware `tenantGuard` hoạt động chính xác, đảm bảo không rò rỉ chéo dữ liệu.
- **Kiểm thử xâm nhập giả lập (Security Verification):** Sử dụng các công cụ như Postman và Curl để gửi request trực tiếp đến Backend mà không qua Frontend để xác nhận hệ thống chặn đứng mọi hành vi đăng nhập trái phép không có token xác thực Cloudflare Turnstile hợp lệ.

---

## 3. Đóng góp & Bản quyền Code thực tế của cá nhân
> [!IMPORTANT]
> **Các module và tính năng chính tự viết và làm chủ hoàn toàn, không phụ thuộc vào đề xuất gốc của AI:**

1. **Thiết lập Middleware Tenant Guard (`tenantGuard.ts`):** Tự viết logic giải mã tên miền/slug từ header request để gán ngữ cảnh `tenantId` cho Prisma, đảm bảo an toàn tuyệt đối và cô lập dữ liệu giữa các nhà hàng trên cùng một cơ sở dữ liệu.
2. **Triển khai Module Bảo mật 2 lớp (`totp.service.ts`):** Tự viết logic băm SHA256 cho mã dự phòng khôi phục (backup codes), cấu hình dung sai lệch thời gian (`window: 1`) cho mã OTP để khắc phục tình trạng lệch giờ thiết bị, và viết cơ chế chặn Google login cưỡng bức đối với tài khoản admin bật 2FA.
3. **Đồng bộ hóa giao diện Sáng/Tối (`AntdProvider.tsx`):** Tự thiết lập cấu trúc provider để thay đổi các biến CSS variables toàn cục đồng bộ với các Design Token của các component phức tạp trong Ant Design (Table, Modal, Drawer), giải quyết triệt để lỗi giao diện chữ đen trên nền tối.
4. **Viết API xác thực Cloudflare Turnstile và Khóa tài khoản (`user.controller.ts`):** Triển khai API verify mã captcha của Cloudflare bằng định dạng `URLSearchParams` chuẩn và lập trình cơ chế khóa tài khoản tự động chống tấn công brute-force.

---

## 4. Bài học kinh nghiệm quý giá rút ra
- **Về chuyên môn:** Nắm vững cấu trúc bảo mật JWT lưu cookie Http-only, cơ chế hoạt động của thuật toán mã hóa 2FA TOTP và kiến trúc cơ sở dữ liệu đa thuê (Multi-tenant SaaS). Biết cách tối ưu hóa hiệu năng bằng Redis Cache.
- **Về cách dùng AI có trách nhiệm:** Không ỷ lại và sao chép máy móc mã nguồn của AI. Luôn giữ vững tư duy phản biện (Critical Thinking) để rà soát lỗi bảo mật, tối ưu hóa kích thước bundle size, và điều chỉnh logic sao cho phù hợp nhất với trải nghiệm người dùng thực tế tại Việt Nam.

---

## 5. Cam kết học thuật
Em cam kết nội dung reflection này phản ánh đúng sự thật quá trình phát triển dự án và đúc rút kinh nghiệm học tập của bản thân.

| Sinh viên xác nhận | Ngày xác nhận |
| :--- | :--- |
| **Nguyễn Đình Thi** | 15/06/2026 |

---
<div align="center">

*SWP391 — FPT University — SUMMER 2026*

</div>
