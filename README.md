# Dự Án Survey Form Cơ Bản

Dự án này là một biểu mẫu khảo sát (Survey Form) được xây dựng để luyện tập kiến thức nền tảng về HTML5 và CSS3, kết hợp sử dụng SCSS (Sass) và cấu hình mã nguồn theo chuẩn công nghiệp thực tế.

## 📁 Cấu trúc thư mục (Folder Structure)

Dự án được cấu trúc theo chuẩn phổ biến trong các dự án Front-end thực tế:

```text
/
├── src/                # Chứa toàn bộ mã nguồn chính (Source Code) của ứng dụng
│   ├── index.html      # Tệp HTML khởi chạy chính (Entry point)
│   ├── style.scss      # Tệp SCSS chứa biến và logic styling
│   ├── style.css       # Tệp CSS cuối cùng được biên dịch (Không edit trực tiếp file này)
│   ├── style.css.map   # Bản đồ mapping để debug SCSS trên trình duyệt
│   └── .stylelintrc    # Tệp cấu hình bắt lỗi Code CSS/SCSS (Linter)
├── docs/               # Chứa các tài liệu liên quan đến dự án (Documentation)
│   ├── Checklist.md    # Danh sách các công việc/tiến độ cần làm
│   └── Notes.md        # Ghi chú tổng hợp các kiến thức/lỗi
├── notes_errors/       # Thư mục chứa hình ảnh/log file chi tiết khi debug lỗi
├── tests/              # (Sẽ dùng sau này) Chứa các kịch bản kiểm thử (Testing)
├── .gitignore          # Cấu hình bỏ qua tệp khi đẩy lên Git/GitHub
└── README.md           # Tệp bạn đang đọc - Giới thiệu về dự án
```

## 🚀 Hướng dẫn chạy môi trường phát triển (Development)

Trong dự án này, SCSS được sử dụng để tối ưu hoá việc viết CSS. Các bước để chạy code:

1. **Cài đặt Sass (nếu chưa có):** Bạn cần cài Node.js và chạy lệnh:
   ```bash
   npm install -g sass
   ```
2. **Khởi động Watcher (Theo dõi SCSS):** Mở Terminal tại thư mục `/src` và chạy lệnh:
   ```bash
   sass --watch style.scss:style.css
   ```
   *Lệnh này sẽ tự động biên dịch mỗi khi file `style.scss` có sự thay đổi.*

## 📌 Các tính năng biểu mẫu

- Giao diện đáp ứng (Responsive) 100% nhờ Box-Sizing và Percentages.
- Tự động thay đổi màu sắc Input, Select, Textarea khi `focus`.
- Cấu trúc SCSS Nesting giúp dễ đọc và tái sử dụng biến (variables).
- Bao gồm đa dạng Inputs: Text, Email, Number, Radio, Checkbox, Textarea.

## 📝 Theo Dõi Tiến Độ

Truy cập file `/docs/Checklist.md` để xem chi tiết các đầu việc đã hoàn thành và sắp tới.
