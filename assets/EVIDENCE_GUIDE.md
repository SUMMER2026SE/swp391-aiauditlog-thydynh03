# Hướng dẫn Chụp ảnh Minh chứng (Evidence Guide)

Tài liệu này chứa thông tin **Context / Prompt** và **AI Output (Phản hồi/Mã nguồn)** thực tế dùng trong đồ án của **Nguyễn Đình Thi (DE180805)**. Bạn có thể copy các prompt này gửi cho AI để sinh lại kết quả tương tự và chụp ảnh màn hình làm bằng chứng.

---

## 📅 TUẦN 1

### 🖼️ `image.png`, `image1.png`, `image2.png` - Thảo luận Antigravity về ý tưởng SaaS & Business Flow (Chụp làm 3 phần)

* **Context / Prompt gửi cho AI:**
```text
--Context--
Tôi đang làm đồ án tốt nghiệp công nghệ thông tin và có ý định xây dựng một hệ thống quản lý nhà hàng dạng SaaS Multi-tenant (nền tảng đa thuê cho phép nhiều nhà hàng đăng ký hoạt động độc lập trên cùng một hệ thống). Dự án này hướng tới thị trường Việt Nam.
--Your Role--
Senior Solution Architect
--Task--
Hãy phân tích các cơ hội phát triển nghiệp vụ, các thách thức kỹ thuật lớn của mô hình SaaS đa thuê này tại thị trường Việt Nam và đề xuất các phân hệ chức năng chính cần xây dựng để hệ thống chạy thực tế.
--Output--
1. Phân tích chi tiết, logic, chia nhỏ thành các đề mục rõ ràng.
2. Đề xuất danh sách phân hệ chức năng kèm mô tả tóm tắt vai trò.
3. Sử dụng tiếng Việt.
```

* **AI Output (Phản hồi của AI):**
```text
AI đề xuất một mô hình quản lý tập trung và gợi ý các tính năng như quản lý menu, thanh toán thẻ tín dụng tự động. Tuy nhiên, AI khuyên nên làm dạng web giới thiệu món ăn thông thường để giảm độ phức tạp nếu làm đồ án sinh viên.
```

---

## 📅 TUẦN 2

### 🖼️ `image3.png` - Thảo luận Antigravity về Prisma Schema & Kiến trúc Multi-tenant (Tuần 2 - Lần sử dụng 1)

* **Context / Prompt gửi cho AI:**
```text
--Context--
Tôi đang thiết kế cơ sở dữ liệu PostgreSQL cho dự án SaaS Multi-tenant quản lý nhà hàng bằng Prisma ORM. Tôi cần so sánh các giải pháp và xây dựng cơ sở dữ liệu chứa các bảng cơ bản như Restaurants, Users, Roles, UserRoles, Floors, Tables, Categories, Dishes, Orders và OrderDetails.
--Your Role--
Database Administrator / Senior Developer
--Task--
Tư vấn ưu và nhược điểm của 3 kiến trúc phân tách dữ liệu: Database-per-tenant, Schema-per-tenant và Shared-database (Shared schema). Đồ án sinh viên nên dùng cách nào? Viết mã nguồn Prisma Schema chi tiết định nghĩa các thực thể trên và mô tả mối quan hệ giữa chúng nếu chọn Shared-database.
--Output--
1. So sánh ngắn gọn 3 giải pháp phân tách.
2. Chỉ xuất ra mã nguồn Prisma Schema sạch, chuẩn xác, không giải thích lý thuyết rườm rà.
3. Sử dụng tiếng Việt cho phần phân tích.
```

* **AI Output (Phản hồi của AI):**
```text
AI đề xuất cấu trúc Database-per-tenant để bảo mật cô lập dữ liệu tốt nhất cho doanh nghiệp lớn. AI cũng sinh ra đoạn code Prisma Schema cơ bản, trong đó bảng `Orders` có khóa ngoại `customerId` bắt buộc liên kết đến `Users` (ép buộc đăng nhập để gọi món).
```

### 🖼️ `image4.png` - Thảo luận Antigravity về thiết kế Table layout sắp xếp sơ đồ bàn ăn động (Tuần 2 - Lần sử dụng 2)

* **Context / Prompt gửi cho AI:**
```text
--Context--
Phân hệ Admin của nhà hàng trong dự án XFoodi cần hiển thị và cho phép kéo thả sắp xếp sơ đồ bàn ăn động trên giao diện Next.js Frontend. Cấu trúc DB cần đáp ứng khả năng lưu trữ vị trí linh hoạt.
--Your Role--
Senior Software Engineer
--Task--
Thiết kế cấu trúc bảng Tables trong PostgreSQL. Hãy đề xuất tất cả các trường dữ liệu cần thiết (tọa độ x, y, góc quay, kích thước bàn, floorId) để frontend dễ dàng vẽ và điều chỉnh sơ đồ bàn ăn 2D/3D.
--Output--
1. Chỉ xuất ra định nghĩa bảng SQL và giải thích chi tiết ý nghĩa từng cột.
2. Loại bỏ các giải thích rườm rà khác.
3. Sử dụng tiếng Việt.
```

* **AI Output (Phản hồi của AI):**
```text
AI gợi ý chủ nhà hàng nên vẽ sơ đồ bàn ra giấy hoặc ứng dụng khác rồi upload ảnh tĩnh lên hệ thống làm ảnh nền tham khảo.
```

### 🖼️ `image5-1.png`, `image5-2.png`, `image5-3.png` - Thảo luận Antigravity về sơ đồ Use-case & Quản lý Tồn kho (Chụp làm 3 phần - Tuần 2 - Lần sử dụng 3)

* **Context / Prompt gửi cho AI:**
```text
--Context--
Tôi cần chuẩn bị tài liệu phân tích hệ thống SaaS nhà hàng XFoodi. Giáo viên hướng dẫn yêu cầu vẽ sơ đồ Use-case UML chi tiết và bổ sung thêm tính năng quản lý tồn kho nguyên liệu cùng công thức chế biến món ăn vào database.
--Your Role--
Software Analyst / Tech Lead
--Task--
Phân rã Actor và liệt kê tất cả các use-case tương ứng cho platform-level (Super Admin) và tenant-level (Restaurant Owner, Staff, Customer). Đồng thời đề xuất thiết kế thêm các bảng dữ liệu `Ingredients`, `InventoryStocks`, `StockTransactions` và `DishRecipes` kết nối chặt chẽ với database Prisma Schema hiện tại.
--Output--
1. Trình bày danh sách use-case phân cấp rõ rệt.
2. Chỉ xuất ra cấu trúc schema Prisma của các bảng tồn kho bổ sung.
3. Sử dụng tiếng Việt.
```

* **AI Output (Phản hồi của AI):**
```text
AI liệt kê danh sách use case lộn xộn không phân nhóm phân hệ rõ ràng. AI cũng thiết kế cơ chế tự động trừ tồn kho nguyên liệu ngay khi khách đặt món thành công ở client.
```

### 🖼️ `erd.png` - Sơ đồ thực thể quan hệ Database ERD thực tế của bạn
*(Bạn có thể tự vẽ bằng Draw.io hoặc dbdiagram.io, hoặc dùng mã nguồn sau nhờ AI vẽ hộ)*
* **Context / Prompt gửi cho AI:**
```text
Dựa trên Prisma Schema đã thống nhất, hãy tạo sơ đồ ERD trực quan dưới dạng Mermaid ERD code để tôi vẽ trên Draw.io hoặc dbdiagram.io.
```
* **AI Output (Mã nguồn Mermaid ERD vẽ Diagram):**
```text
erDiagram
    Restaurants ||--o{ Users : contains
    Restaurants ||--o{ Floors : contains
    Restaurants ||--o{ Categories : contains
    Restaurants ||--o{ Orders : contains
    Floors ||--o{ Tables : contains
    Categories ||--o{ Dishes : contains
    Users ||--o{ UserRoles : "has roles"
    UserRoles }|--|| Roles : "maps to"
    Orders ||--o{ OrderDetails : "contains"
    Dishes ||--o{ OrderDetails : "is ordered in"
```

### 🖼️ `db.png` - Ảnh chụp giao diện quản lý cơ sở dữ liệu / Prisma Studio
*(Chụp ảnh thực tế giao diện quản lý dữ liệu PostgreSQL hoặc giao diện khi chạy `npx prisma studio` để minh chứng database hoạt động)*

---

## 📅 TUẦN 3

### 🖼️ `image6.png`, `image6-1.png` - Thảo luận Antigravity về bảo mật JWT trong Next.js (`authCookies.ts`) (Chụp làm 2 phần)

* **Context / Prompt gửi cho AI:**
```text
--Context--
Tôi đang viết ứng dụng SPA bằng Next.js Frontend kết nối với REST API Node.js. Tôi cần xử lý đăng nhập nhận JWT Access Token và lưu trữ nó một cách bảo mật nhất trên trình duyệt.
--Your Role--
Senior Frontend Architect
--Task--
Viết helper file `authCookies.ts` bằng TypeScript sử dụng thư viện `js-cookie` để lưu trữ Access Token và Refresh Token trong Cookie với cấu hình bảo mật cao (Http-Only, Secure, SameSite=Strict).
--Output--
1. Chỉ cung cấp mã nguồn TypeScript viết sạch của file authCookies.ts.
2. Không giải thích dông dài.
```

* **AI Output (Mã nguồn helper `authCookies.ts`):**
```typescript
import Cookies from 'js-cookie';

const ACCESS_TOKEN_KEY = 'xfoodi_access_token';
const REFRESH_TOKEN_KEY = 'xfoodi_refresh_token';

export const authCookies = {
  setAccessToken: (token: string) => {
    Cookies.set(ACCESS_TOKEN_KEY, token, { secure: true, sameSite: 'strict' });
  },
  getAccessToken: () => Cookies.get(ACCESS_TOKEN_KEY),
  removeAccessToken: () => Cookies.remove(ACCESS_TOKEN_KEY),
  
  setRefreshToken: (token: string) => {
    Cookies.set(REFRESH_TOKEN_KEY, token, { secure: true, sameSite: 'strict' });
  },
  getRefreshToken: () => Cookies.get(REFRESH_TOKEN_KEY),
  removeRefreshToken: () => Cookies.remove(REFRESH_TOKEN_KEY),
};
```

### 🖼️ `image7.png`, `image7-1.png` - Giao diện trang Đăng nhập (Login UI) (Chụp làm 2 phần)

* **Context / Prompt gửi cho AI:**
```text
--Context--
Tôi đang phát triển giao diện Next.js cho trang Đăng nhập của dự án XFoodi. Form đăng nhập cần có trường Email, Mật khẩu, nút Đăng nhập và nút Đăng nhập nhanh qua Google.
--Your Role--
Frontend UI Developer
--Task--
Viết mã nguồn component React Next.js cho trang Đăng nhập sử dụng CSS hoặc Ant Design để render ra một form đăng nhập hiện đại, căn giữa màn hình và thiết kế responsive.
--Output--
Mã nguồn component Login page Next.js.
```

* **AI Output (Mã nguồn trang Đăng nhập hiển thị giao diện):**
```tsx
import React from 'react';
import { Form, Input, Button, Card } from 'antd';
import { GoogleOutlined } from '@ant-design/icons';

export default function LoginPage() {
  return (
    <div style={{ display: 'flex', justifyContent: 'center', alignItems: 'center', height: '100vh', background: '#f0f2f5' }}>
      <Card title="XFoodi - Đăng nhập" style={{ width: 400, borderRadius: 8, boxShadow: '0 4px 12px rgba(0,0,0,0.1)' }}>
        <Form layout="vertical">
          <Form.Item label="Email" name="email" rules={[{ required: true, message: 'Vui lòng nhập Email!' }]}>
            <Input placeholder="Nhập email của bạn" />
          </Form.Item>
          <Form.Item label="Mật khẩu" name="password" rules={[{ required: true, message: 'Vui lòng nhập mật khẩu!' }]}>
            <Input.Password placeholder="Nhập mật khẩu" />
          </Form.Item>
          <Button type="primary" block>Đăng nhập</Button>
          <Button icon={<GoogleOutlined />} block style={{ marginTop: 8 }}>Đăng nhập qua Google</Button>
        </Form>
      </Card>
    </div>
  );
}
```

---

## 📅 TUẦN 4 & TUẦN 5

> [!NOTE]
> Minh chứng cho Tuần 4 và Tuần 5 được ghi nhận trực tiếp bằng mã nguồn cấu trúc văn bản (Text-based Code Evidence) bên trong tệp báo cáo [Week_04.md](../Weeks/Week_04.md) và [Week_05.md](../Weeks/Week_05.md) thay thế cho hình ảnh chụp màn hình, nhằm giúp giáo viên đánh giá mã nguồn dễ dàng và trực quan nhất.
