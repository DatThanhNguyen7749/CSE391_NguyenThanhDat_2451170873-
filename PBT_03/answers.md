Câu A1

1. Inline CSS
```html
<h1 style="color: red;">Tiêu đề</h1>
```
Ưu điểm:
- Thay đổi nhanh, tiện debug.
- Không cần file ngoài.
Nhược điểm:
- Khó bảo trì khi nhiều element.
- Không tái sử dụng được.
- Độ ưu tiên cao nhất, dễ gây override không mong muốn.
Khi nào dùng:
- Chỉ dùng tạm để debug nhanh hoặc override ở chỗ đặc biệt.

2. Internal CSS
```html
<head>
  <style>
    h1 {
      color: blue;
    }
  </style>
</head>
```
Ưu điểm:
- Có thể viết CSS ngay trong HTML.
- Dễ dùng cho prototype hoặc trang đơn giản.
Nhược điểm:
- Không tái sử dụng cho nhiều trang.
- File HTML to hơn.
Khi nào dùng:
- Dùng cho bản mẫu nhanh, demo, prototype nhỏ.

3. External CSS
```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```
Ưu điểm:
- Tách biệt HTML và CSS.
- Dễ tái sử dụng, dễ bảo trì.
- Browser cache được file CSS.
Nhược điểm:
- Cần thêm request HTTP (nhỏ với file local).
Khi nào dùng:
- Dự án thực tế, production, nhiều trang dùng chung style.

- Nếu cùng 1 element có 3 cách áp dụng thì inline thắng, sau đó internal và external. Bởi vì inline có specificity cao hơn mọi selector trong stylesheet; internal và external cùng specificity thì cái nào xuất hiện sau sẽ override lên cái trước.

Câu A2

1. `h1` Chọn: ShopTLU
2. `.price` Chọn: 25.990.000đ, 45.990.000đ
3. `#app header` Chọn: toàn bộ thẻ `<header class="top-bar dark">` chứa ShopTLU và menu nav.
4. `nav a:first-child` Chọn: Home
5. `.product.featured h2` Chọn: MacBook Pro
6. `article > p` Chọn: các thẻ `<p>` trực tiếp con của mỗi `article`:
   - 25.990.000đ
   - Mô tả sản phẩm...
   - 45.990.000đ
   - Mô tả sản phẩm...
7. `a[href="/"]` Chọn: Home
8. `.top-bar.dark h1` Chọn: ShopTLU

Câu A3

Trường hợp 1: content-box
- width: 400px
- padding: 20px hai bên = 40px
- border: 5px hai bên = 10px
- margin: 10px hai bên = 20px

- Chiều rộng hiển thị = 400 + 40 + 10 = 450px
- Không gian chiếm trên trang = 450 + 20 = 470px

Trường hợp 2: border-box
- width: 400px là kích thước hộp bao gồm padding và border
- padding: 20px hai bên = 40px
- border: 5px hai bên = 10px
- margin: 10px hai bên = 20px

- Chiều rộng hiển thị = 400px
- Kích thước content thực tế = 400 - 40 - 10 = 350px
- Không gian chiếm trên trang = 400 + 20 = 420px

Trường hợp 3: Margin collapse
- `.box-a` margin-bottom: 25px
- `.box-b` margin-top: 40px

- Khoảng cách giữa box-a và box-b = 40px

Do margin dọc của hai block liền kề bị collapse, không cộng lại. CSS lấy giá trị lớn hơn trong hai margin để làm khoảng cách.

Nếu `.box-a` margin-bottom: -10px, `.box-b` margin-top: 40px thì khoảng cách = 30px

Do margin dọc đối dấu sẽ cộng lại khi collapse, nên 40 + (-10) = 30.

Câu A4

Các rule:
- Rule A `p { color: black; }`: specificity: 0,0,1
- Rule B `.price { color: blue; }`: specificity: 0,1,0
- Rule C `#main-price { color: red; }`: specificity: 1,0,0
- Rule D `p.price { color: green; }`: specificity: 0,1,1

Màu cuối cùng của element: `<p class="price" id="main-price">`: red.
Lý do: rule C có specificity cao nhất (ID selector) nên thắng.

Nếu thêm `style="color: orange;"` lên element:
- Inline style có priority lớn hơn rule stylesheet thông thường.
- Màu sẽ là orange.

Nếu Rule A thêm `!important`:
- `p { color: black !important; }` sẽ thắng tất cả rule thông thường.
- Màu sẽ là black.
- Vì `!important` ưu tiên vượt trên tất cả, bất kể specificity thấp hơn.

Câu C1

