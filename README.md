[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/w-DaaG0I)

<div align="center">

# 📋 AI Audit Log — Nguyễn Đình Thi

### *Nhật ký sử dụng AI cá nhân minh bạch & có trách nhiệm*

![Student](https://img.shields.io/badge/Sinh%20viên-Nguy%E1%BB%85n%20%C4%90%C4%B3nh%20Thi-blue?style=for-the-badge)
![ID](https://img.shields.io/badge/MSSV-DE180805-orange?style=for-the-badge)
![Course](https://img.shields.io/badge/M%C3%B4n%20h%E1%BB%8Dc-SWP391-blue?style=for-the-badge)
![Class](https://img.shields.io/badge/L%E1%BB%9Bp-SE20A06-red?style=for-the-badge)

</div>

---

## 🎯 Giới thiệu

Repository này là **nhật ký kiểm toán AI (AI Audit Log)** chính thức của sinh viên **Nguyễn Đình Thi (DE180805)** trong môn **Software Development Project (SWP391)** tại FPT University.

Tài liệu ghi chép **minh bạch**, **có hệ thống** toàn bộ quá trình sử dụng và cộng tác cùng trợ lý lập trình **Antigravity** trong suốt 5 tuần phát triển dự án **XFoodi** nhằm đảm bảo tính trung thực học thuật và thể hiện tư duy phản biện (Critical Thinking).

---

## 🏗️ Dự án: XFoodi

> **Nền tảng SaaS quản lý nhà hàng đa thuê (Multi-tenant SaaS Platform)**

Hệ thống quản lý nhà hàng theo mô hình SaaS đa thuê, cho phép nhiều đối tác nhà hàng (tenant) vận hành và quản lý độc lập trên cùng một nền tảng duy nhất với dữ liệu được cô lập hoàn toàn.

---

## 📂 Cấu trúc Repository

```
swp391-aiauditlog-thydynh03/
│
├── 📄 EVIDENCE.md                                         # Báo cáo chi tiết minh chứng, tệp code & ảnh chat AI
├── 📄 REFLECTION.md                                       # Báo cáo tổng kết tự đánh giá và bài học kinh nghiệm
├── 📄 README.md                                           # Hướng dẫn nộp bài
│
├── 📁 Weeks/                                              # Thư mục lưu trữ các file Excel audit log hàng tuần
│   ├── 📄 AI_Audit_Log_DE180805_NguyenDinhThi_XFoodi_Week1.xlsx (22 Entries, 3 Hallucinations) (22 Entries, 3 Hallucinations)
│   ├── 📄 AI_Audit_Log_DE180805_NguyenDinhThi_XFoodi_Week2.xlsx (20 Entries, 5 Hallucinations) (20 Entries, 5 Hallucinations)
│   ├── 📄 AI_Audit_Log_DE180805_NguyenDinhThi_XFoodi_Week3.xlsx (18 Entries, 3 Hallucinations) (18 Entries, 3 Hallucinations)
│   ├── 📄 AI_Audit_Log_DE180805_NguyenDinhThi_XFoodi_Week4.xlsx (21 Entries, 5 Hallucinations) (21 Entries, 5 Hallucinations)
│   └── 📄 AI_Audit_Log_DE180805_NguyenDinhThi_XFoodi_Week5.xlsx (17 Entries, 5 Hallucinations) (17 Entries, 5 Hallucinations)
│
└── 📁 assets/                                             # Tài nguyên hình ảnh minh chứng cuộc chat và sơ đồ
    ├── 📄 EVIDENCE_GUIDE.md                               # Hướng dẫn chi tiết prompt & response
    ├── 🖼️ db.png                                          # Minh chứng cơ sở dữ liệu Prisma Studio hoạt động
    ├── 🖼️ erd.png                                         # Sơ đồ thực thể quan hệ database ERD thực tế
    ├── 🖼️ image.png, image1.png, image2.png               # Minh chứng hội thoại Tuần 1
    ├── 🖼️ image3.png, image4.png, image5-1.png...          # Minh chứng hội thoại Tuần 2
    ├── 🖼️ image6.png, image6-1.png, image7.png...          # Minh chứng hội thoại Tuần 3
    └── ...
```

---

## 📝 Quy trình Log Audit theo tuần

Mỗi tuần, các lần sử dụng AI được ghi lại trong nhật ký kiểm toán với **4 yếu tố Human Delta** nhằm thể hiện tính phản biện:

| Yếu tố | Ý nghĩa |
| :--- | :--- |
| **Critical Thinking (Tư duy phản biện)** | Rà soát, đánh giá các điểm chưa tối ưu, lỗi bảo mật hoặc ảo giác của AI. |
| **Contextualization (Ngữ cảnh hóa)** | Điều chỉnh đề xuất của AI để phù hợp với kiến trúc SaaS đa thuê và hành vi người dùng Việt Nam. |
| **Creative Synthesis (Sáng tạo & Tổng hợp)** | Tự thiết kế các giải pháp bổ sung (như cấu hình token, bảo mật cookie). |
| **Decision (Quyết định)** | Lựa chọn giải pháp tối ưu và an toàn nhất đưa vào mã nguồn thực tế. |

---

## ✍️ Quy chuẩn Commit

Xem chi tiết quy chuẩn commit được áp dụng trong dự án của nhóm:

```bash
# Cú pháp bắt buộc
<type>(<scope>): <mô tả ngắn>

# Ví dụ hợp lệ
feat(auth): them chuc nang dang nhap google
fix(db): sua loi ket noi database
docs(audit): hoan thanh log tuan 01
```

| `type` | Ý nghĩa |
| :--- | :--- |
| `feat` | Thêm chức năng mới |
| `fix` | Sửa lỗi |
| `docs` | Viết tài liệu / audit log |
| `refactor` | Tái cấu trúc code |
| `chore` | Công việc cấu hình / bảo trì |

---

<div align="center">

*SWP391 — FPT University — SUMMER 2026*

</div>
