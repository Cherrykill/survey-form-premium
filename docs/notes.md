# Sổ tay Ghi chú & Quản lý Lỗi (Knowledge Base)

Tài liệu này tổng hợp lại các lỗi thường gặp trong quá trình làm CSS/SCSS và các mẹo (tricks) cần nhớ. Việc ghi log (nhật ký) lỗi là kỹ năng sinh tồn của mọi Developer.

## 1. Lỗi Box Model (Input bị tràn ra ngoài)
- **Triệu chứng:** Khi set `width: 100%` cho thẻ `<input>` hoặc `<select>`, sau đó thêm `padding`, phần tử đó sẽ phình to ra và tràn ra ngoài hoặc phá vỡ cấu trúc của thẻ cha.
- **Nguyên nhân:** Khái niệm Box Model mặc định của trình duyệt là `content-box` (tức là tổng chiều rộng = content + padding + border). Khiến chiều rộng thật lớn hơn 100%.
- **Cách khắc phục:** 
  Luôn luôn Reset lại thuộc tính `box-sizing: border-box` trên cao nhất của mọi file CSS. Nó giúp ép padding và border tính vào bên *trong* chiều rộng đã chọn.
  ```scss
  * {
      padding: 0;
      margin: 0;
      box-sizing: border-box;
  }
  ```

## 2. Lỗi thẻ <select> khác màu nền (Browser Styling)
- **Triệu chứng:** Trên một số trình duyệt (đặc biệt là iOS/Safari), thẻ `<select>` nhìn rất khác những ô `<input>` text còn lại, có thể bị xám nền hoặc mất viền bo tròn.
- **Nguyên nhân:** Các trình duyệt tự áp dụng CSS mặc định lên một số thẻ form đặc thù (User-Agent Stylesheet).
- **Cách khắc phục:** 
  Bắt buộc ghi đè lại mã màu cho background:
  ```scss
  select {
      background-color: white; /* Bắt buộc để tránh bị ám xám nhạt */
      appearance: none; /* Dùng kĩ năng này nếu muốn ẩn hẳn mũi tên sổ xuống mặc định */
  }
  ```

## 3. SCSS: Sức mạnh của Nesting và Ký tự `&`
- Ghi nhớ: Trong SCSS, ta có thể lồng thẻ con vào trong thẻ cha giống hệt như bộ khung HTML. Điều này giúp CSS không bị xung đột khi có nhiều thành phần trùng tên class (Scope isolation).
- Khi muốn nhắm đến trạng thái (state) của chính thẻ cha đó (ví dụ `:hover`, `:focus`, `:active`), ta dùng ký tự đặc biệt `&`.
  ```scss
  input {
      border: 1px solid #ccc;
      
      &:focus {        // Tương đương với input:focus
          border-color: blue;
      }
  }
  ```

## 4. Bố cục Input Radio & Checkbox
- Khác với input text cần đứng riêng 1 dòng (`display: block`), radio và checkbox cần nằm gần với chữ miêu tả của chùng (inline).
- Cần đổi `display: inline-block` cho các loại input này và cấu trúc lại chiều ngang (margin) cho hợp lý.

---
*(Cập nhật liên tục khi phát sinh lỗi mới...)*
