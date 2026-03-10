# Sổ tay ghi chú lỗi HTML/CSS

## 1. Lỗi Input hoặc Box bị tràn ra ngoài kích thước khai báo (Lỗi Box-Sizing)
- **Triệu chứng:** Set `width: 100%` rồi, nhưng thêm `padding` thì cái hộp bị phình to ra và méo mó, thò ra ngoài khung chứa.
- **Nguyên nhân:** Mặc định của trình duyệt (`content-box`) tính tổng chiều rộng bao gồm cả content + padding + border. Khiến width thật bị cộng dồn lên lớn hơn 100%.
- **Cách sửa:** Luôn luôn thêm đoạn code "Reset CSS" dưới đây lên đầu ngọn mọi file [style.css](cci:7://file:///c:/Users/nviet/Downloads/test/style.css:0:0-0:0) để bảo trình duyệt nhét padding/border vào trong lòng chiều rộng đã khai báo:
  ```css
  * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
  }
