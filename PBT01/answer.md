Câu A1 (Nguồn: 01_introduction_html_universe.md 1.1 Kiến trúc Client-Server, 1.2 HTTP, 1.3 Browser Rendering.)
1. Thứ tự ít nhất 5 bước khi gõ https://shopee.vn:
   - DNS lookup: Trình duyệt tra cứu địa chỉ IP của shopee.vn từ DNS server.
   - TCP connection: Thiết lập kết nối TCP với server.
   - HTTP request: Gửi GET request đến server.
   - Server processing: Server xử lý request, trả về HTML/CSS/JS.
   - Browser rendering: Parse HTML, load CSS/JS, render trang.
2. Screenshot
Câu A2 (Nguồn: 04_visible_part_html.md)
- trang web bị đánh giá SEO thấp vì:
+ dùng <div class="header"> thay vì <header> cho phần đầu trang.
+ dùng <div class="nav"> thay vì <nav> cho phần điều hướng.
+ dùng <div class="main"> thay vì <main> cho phần nội dung chính.
+ dùng <div class ="product"> thay vì <article> cho phần sản phẩm.
+ dùng <div class="footer"> thay vì <footer> cho phần chân trang.
=> Google không hiểu cấu trúc.
Câu A3 
[ Hộp 1 ] (div gom các phần tử lại 1 khối)
Text A Text B (span gom các phần tử lại 1 dòng)
[ Hộp 2 ]
Text C Text D(text D in đậm(strong))
[ Hộp 3 ]
Câu A4
thead: tiêu đề cột
tbody: dữ liệu chính
tfoot: tổng kết
Lý do không nên dùng table để tạo layout cho trang web:
1. Không phải thẻ semantic => Google không hiểu cấu trúc.
2. Khó responsive(table khó co giãn linh hoạt theo màn hình)
3. Ảnh hưởng đến SEO (Screenreader sẽ hiểu nhầm là bảng dữ liệu)
Câu C1
Câu C1 (10đ) — Thiết kế cấu trúc

<header> <!-- header cho phần đầu trang -->
    <nav> <!-- nav cho menu chính -->
        <a href="#home">Trang chủ</a>
    </nav>
</header>
<nav aria-label="Breadcrumb"> <!-- điều hướng -->
    <ol> <!-- ol là ordered list(xếp theo thứ tự) -->
        <li><a href="#home">Trang chủ</a></li>
        <li><a href="#iphone">Điện thoại</a></li>
        <li>iPhone 16</li>
    </ol>
</nav>
<main> <!-- main cho nội dung chính -->
    <section> <!-- section cho khu vực ảnh -->
        <figure> <!-- figure cho media với caption -->
            <img src="img1.jpg" alt="iPhone 16">
            <img src="img2.jpg" alt="iPhone 16">
            <img src="img3.jpg" alt="iPhone 16">
            <img src="img4.jpg" alt="iPhone 16">
            <img src="img5.jpg" alt="iPhone 16">
        </figure>
    </section>
    <section> <!-- section cho thông tin -->
        <h1>iPhone 16</h1>
        <p>25.990.000đ</p>
        <p>Đánh giá sao</p>
        <p>Mô tả</p>
    </section>
    <section> <!-- section cho bảng thông số kỹ thuật -->
        <table>
            <thead><tr><th>Thông số</th><th>Giá trị</th></tr></thead><!-- tr là table row, th là table header -->
            <tbody>...</tbody>
        </table>
    </section>
    <section> <!-- section cho đánh giá -->
        <article> <!-- article cho mỗi comment -->
            <p>Đánh giá</p>
        </article>
    </section>
</main>
<aside> <!-- aside cho sidebar -->
    <h3>Sản phẩm tương tự</h3>
    <article>...</article>
</aside>
<footer> <!-- footer cho cuối trang -->
    <p>&copy; 2026</p>
</footer>
Câu C2
Quan điểm của đồng nghiệp là sai. Trước hết, thẻ semantic HTML cực kỳ quan trọng cho SEO — công cụ tìm kiếm. Google không chỉ đọc nội dung, mà còn phân tích cấu trúc HTML để hiểu trang web. Khi bạn dùng <article> cho bài viết, <nav> cho menu, <figure> cho ảnh, Google nhận diện ngay cấu trúc. Ví dụ, Shopee dùng semantic tags đúng cách cho mỗi sản phẩm (<article>, <figure>), giúp các listing xuất hiện nhiều hơn trong kết quả tìm kiếm và Google Shopping, tăng traffic 30-50%. Ngược lại, nếu dùng toàn <div>, Google phải "đoán", SEO kém, traffic giảm, mất hàng triệu đô doanh số. Thứ hai, semantic HTML hỗ trợ trợ năng cho người khuyết tật. Screen readers (phần mềm đọc màn hình) dùng <nav>, <main>, <aside> để điều hướng. Người mù có thể skip đến menu bằng phím tắt. Với toàn <div>, họ phải nghe từng ký tự, lãng phí thời gian. Pháp luật WCAG 2.1 còn bắt buộc web phải accessible, vi phạm có thể bị kiện. Shopee cũng cấu trúc rõ ràng giỏ hàng với <aside>, tìm kiếm với <form>, giúp người dùng dễ dàng sử dụng. Tuy nhiên, <div> vẫn hoàn toàn phù hợp khi làm layout phức tạp với CSS Grid hay Flexbox, hoặc wrapper bao bọc các phần tử không cần ý nghĩa ngữ nghĩa. Tóm lại, học semantic HTML là vô cùng cần thiết. Học trong 1 tiếng, tiết kiệm hàng trăm giờ debug và tăng SEO.