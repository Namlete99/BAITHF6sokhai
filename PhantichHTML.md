 **WRITTEN 20/03/2025 BY NÔM LEE**

---

# Mục đích của File PhantichHTML.md này là gì ? 

Nhằm giúp mọi người hiểu những gì đang xảy ra trong đây

# Hiểu gì ? 

Hiểu các dòng lệnh các File trong đây bao gồm: 

+ `index.html`

+ `thanhvienlop.html`

+ `test.css`

Ta sẽ đi tìm hiểu từng mục sắp trên xuống dưới (nhìn mục + ở trên) 

# Chuyên mục rán gà, đảo cánh

## **index.html**

File này được xem là trang chủ của web. Cứ hiểu `index.html` là tập lớn còn `thanhvienlop.html` là tập con của `index.html`. **Không nhất thiết** phải đặt tên file này là `index.html`, ta có thể đặt tên khác miễn sao có đuôi là html kèm theo và phải gõ không cách. 

Tiếp theo ta sẽ phân tích dòng lệnh trong file này ( khi thuyết trình có thể sử dụng những cách khác để trình bày) 

***

### 1. Khai báo tài liệu (Document Declaration)


Khi hiển thị trên GitHub, nó sẽ có màu sắc phù hợp với HTML:

```html
<!DOCTYPE html>
<html lang="en">
```
- `<!DOCTYPE html>`: Xác định đây là tài liệu HTML5.
- `<html lang="en">`: Xác định ngôn ngữ chính của trang là tiếng Anh.

***

### 2. Phần `<head>` (Thông tin metadata)
```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kỉ yếu lớp 12A</title>
  <link rel="stylesheet" href="./test.css" type="text/css" />
</head>
```
- `<meta charset="UTF-8">`: Thiết lập bảng mã UTF-8 (hỗ trợ tiếng Việt).
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Giúp trang web hiển thị tốt trên các thiết bị di động.
- `<title>Kỉ yếu lớp 12A</title>`: Đặt tiêu đề trang web.
- `<link rel="stylesheet" href="./test.css" type="text/css" />`: Liên kết với file CSS test.css để định dạng giao diện.

Nói về CSS mọi người có thể xem trong mục blog tại web https://namle-a6.github.io/Diendantinhoc-12A6/ : 

*** 

### 3. Phần `<body>` (Nội dung chính của trang web)***

***3.1 Phần đầu trang (Header)***

```html
<table width="100%" border="0" cellspacing="0">
  <tr>
    <td colspan="2" align="center">
      <font face="Times New Roman" size="10px" color="orange"><b>Kỉ yếu lớp 12A</b></font>
    </td>
  </tr>
</table>
```
- Dùng `<table>` để căn giữa tiêu đề.
- `<font>`: Định dạng chữ với font "Times New Roman", kích thước 10px, màu cam.
- Lưu ý: Thẻ `<font>` đã bị lỗi thời trong HTML5, bạn nào đã học qua CSS nên dùng CSS thay thế nhóe !

---

***3.2 Phần Menu điều hướng (Navigation)***

```html
<table border="1" cellspacing="0" width="10%" valign="top">
  <tr>
    <td><a href="gioithieu.html" target="iframe_noidung" class="active">Trang chủ</a></td>
  </tr>
  <tr></tr>
  <tr>
    <td><a href="hoatdong.html" target="iframe_noidung">Hoạt động</a></td>
  </tr>
  <tr>
    <td><a href="thanhvienlop.html" target="iframe_noidung">Thành viên lớp</a></td>
  </tr>
</table>
```
- Tạo menu bên trái bằng `<table>`.
- Các mục menu gồm:
  - "Trang chủ" → `gioithieu.html`

  - "Hoạt động" → `hoatdong.html`

  - "Thành viên lớp" → `thanhvienlop.html`
- `target="iframe_noidung"`: Khi bấm vào sẽ tải nội dung trong thẻ <iframe>.

---

***3.3 Phần nội dung chính (Main Content)***

```html
<table width="100%" height="1000px" border="0" cellspacing="0">
  <tr>
    <td width="10%" valign="top"></td>
    <td>
      <iframe
        src="gioithieu.html"
        name="iframe_noidung"
        width="100%"
        height="1000px"
        frameborder="0"
      ></iframe>
    </td>
  </tr>
</table>
```
- Bố cục chính:
  - Cột trái (10% chiều rộng): Chứa menu.
  - Cột phải (90%): Chứa `<iframe>` để hiển thị nội dung động.
- `<iframe>` hiển thị file gioithieu.html mặc định.
- `name="iframe_noidung"`: Giúp các liên kết trong menu cập nhật nội dung của iframe.

---

***3.4 Chân trang (Footer)***
```html
<hr />
<center>
  <header>
    <font face="Times New Roman" size="3">
      <h2>Dễ dàng truy cập và theo dõi</h2>
      <p>
        Bạn đang ghé thăm kỉ yếu lớp 12A6 - Xin cảm ơn đã quan tâm kỉ yếu của lớp 12A6
      </p>
    </font>
  </header>
  <footer>
    <font size="3px">© Copyright, Lớp 12A6 2024 - 2025</font>
  </footer>
</center>
```
- `<hr />`: Kẻ đường ngang phân cách nội dung chính và chân trang.
- `<header>`: Chứa thông tin chào mừng.
- `<footer>`: Chứa bản quyền của lớp.
- Lưu ý: `<center>` đã bị lỗi thời trong HTML5, các bạn nên dùng CSS (text-align: center;).

---
```html
<script>
  document.addEventListener("DOMContentLoaded", function () {
    let links = document.querySelectorAll("table a");
    let currentUrl = window.location.href;

    links.forEach((link) => {
      link.addEventListener("click", function () {
        links.forEach((l) => l.classList.remove("active"));
        this.classList.add("active");
      });

      if (currentUrl.includes(link.getAttribute("href"))) {
        link.classList.add("active");
      }
    });
  });
</script>
```
- **Lưu ý**: không nhất thiết hiểu và bỏ vào dòng lệnh của mình để làm ( kể cả thuyết trình), vì phần này nằm ngoài khuôn khổ học trong sách. Mình bỏ vô vì cho đủ dòng lệnh mình làm cho đẹp ba hoa lá họe, cũng như ai hiểu về java thì cứ vô tư đọc và lấy nhé!
- Chức năng chính:
  - Khi trang tải xong `(DOMContentLoaded)`, JavaScript tìm tất cả các thẻ `<a>` trong `<table>`.
  - Khi nhấn vào một liên kết:
    - Xóa lớp `active` của các liên kết khác.
    - Thêm lớp `active` cho liên kết được chọn.
  - Nếu URL hiện tại chứa đường dẫn của liên kết, liên kết đó sẽ được đánh dấu là `active`.
  - Lưu ý: Để hiệu ứng hoạt động, bạn cần thêm CSS cho `.active` trong `test.css`.

***

### Kết luận: 

Trang web của chúng ta đã ổn nhưng có thể cải tiến bằng cách dùng <div> thay cho <table> và áp dụng CSS thay vì <font>. Điều này giúp trang web hiện đại hơn và dễ dàng mở rộng. 

***

## **thanhvienlop.html**

Giờ ta đến với mục con của `index.html` là `thanhvienlop.html`. 

***

### 1. Khai báo tài liệu HTML 

Như bên `index.html`

---

### 2. Phần `<head>` (Cấu hình trang web)

Như bên `index.html`, chỉ có `<title>Thành viên lớp</title>`: Tiêu đề hiển thị trên trình duyệt là khác chút. 

---

### 3. Phần tiêu đề trang 

```html
<table border="0" width="700" valign="top">
  <tr>
    <td colspan="2" align="center">
      <font face="Times New Roman" color="blue" size="6px"><b>Thành viên lớp</b></font>
    </td>
  </tr>
</table>
```
- Dùng `<table>` để căn giữa tiêu đề.
- Dùng `<font>` để định dạng chữ ("Times New Roman", màu xanh, size 6px).

**Cải thiện đề xuất:**
- `<font>` đã lỗi thời, nên thay bằng CSS:

```CSS
.title {
  font-family: "Times New Roman", serif;
  font-size: 30px;
  color: blue;
  font-weight: bold;
  text-align: center;
}
```

```html
<table border="0" width="700" valign="top">
  <tr>
    <td colspan="2" align="center">
      <h1 class="title">Thành viên lớp</h1>
    </td>
  </tr>
</table>
```

---

### 4. Bảng danh sách thành viên

Vì danh sách lớp tận 46 thành viên, nên mình chỉ lấy ví dụ một dòng sau đây để giúp các bạn hiểu và từ đó làm y chang tương tự và chỉ cần thay những thông tin sao cho phù hợp ( tổng hợp thông tin từng thành viên lớp vào một file như Excel nhé )

```html
<table class="table" width="700" height="10">
  <tr>
    <th width="10%">STT</th>
    <th width="40%">Họ và tên</th>
    <th width="15%">Ngày sinh</th>
    <th width="20%">Chức vụ</th>
    <th width="15%"></th>
  </tr>
  <tr align="center">
    <td>1</td>
    <td><p align="left">Lê Huỳnh Duy Anh</p></td>
    <td>25/06/2007</td>
    <td>TNXK</td>
    <td><a href="#">Xem chi tiết</a></td>
  </tr>
</table>
```

- Tạo bảng danh sách thành viên.
- Cột gồm: **STT, Họ và tên, Ngày sinh, Chức vụ, Xem chi tiết**.
- `align="center"` căn giữa nội dung cột.
- `<p align="left">` căn lề trái tên.

**Cải thiện đề xuất:**

- Dùng CSS thay `align="center"` (HTML5 không khuyến khích dùng `align`).
- Thêm viền và khoảng cách cho bảng trong `test.css`:

```css
.table {
  width: 700px;
  border-collapse: collapse;
}
.table th, .table td {
  border: 1px solid black;
  padding: 8px;
  text-align: center;
}
.table th {
  background-color: #f2f2f2;
}
.table td p {
  text-align: left;
  margin: 0;
}
.table a {
  color: blue;
  text-decoration: none;
}
.table a:hover {
  text-decoration: underline;
}
```
- HTML sau khi tối ưu:
```html
<table class="table">
  <tr>
    <th>STT</th>
    <th>Họ và tên</th>
    <th>Ngày sinh</th>
    <th>Chức vụ</th>
    <th>Hành động</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Lê Huỳnh Duy Anh</td>
    <td>25/06/2007</td>
    <td>TNXK</td>
    <td><a href="#">Xem chi tiết</a></td>
  </tr>
</table>
```
---

### 5. Gợi ý mở rộng (ko nhất thiết nên có thể bỏ qua)

Nếu danh sách lớp có nhiều người, có thể dùng JavaScript để hiển thị danh sách từ JSON, thay vì viết HTML thủ công.

**Bước 1: Tạo `data.js` (danh sách thành viên)**
```java
const members = [
  { stt: 1, name: "Lê Huỳnh Duy Anh", birth: "25/06/2007", role: "TNXK" },
  { stt: 2, name: "Nguyễn Văn A", birth: "10/08/2007", role: "Lớp trưởng" },
  { stt: 3, name: "Trần Thị B", birth: "15/03/2007", role: "Thủ quỹ" },
];

document.addEventListener("DOMContentLoaded", function () {
  let table = document.querySelector(".table tbody");

  members.forEach((member) => {
    let row = `
      <tr>
        <td>${member.stt}</td>
        <td>${member.name}</td>
        <td>${member.birth}</td>
        <td>${member.role}</td>
        <td><a href="#">Xem chi tiết</a></td>
      </tr>
    `;
    table.innerHTML += row;
  });
});
```

**Bước 2: Cập nhật HTML để dùng JavaScript**
```html
<table class="table">
  <thead>
    <tr>
      <th>STT</th>
      <th>Họ và tên</th>
      <th>Ngày sinh</th>
      <th>Chức vụ</th>
      <th>Hành động</th>
    </tr>
  </thead>
  <tbody>
    <!-- Dữ liệu sẽ được thêm tự động bằng JavaScript -->
  </tbody>
</table>
<script src="data.js"></script>
```

**Lợi ích của cách này:**

✅ Không cần sửa HTML mỗi khi thêm thành viên mới.

✅ Dữ liệu dễ quản lý, có thể lấy từ API hoặc file JSON.

### Kết luận:

Chúng đã xây dựng một trang danh sách lớp cơ bản rất tốt. Với các tối ưu trên, trang sẽ chuyên nghiệp hơn, dễ mở rộng và tương thích với chuẩn HTML5. 😃

***

## **test.css**

Cuối cùng trong cái dự án này là file `test.css`, file này các bạn có thể lấy hoặc không, tuy vậy mình khuyên các bạn nên lấy vì 

- Cơ bản mik lười sửa lại code ở trên kkk
- Đằng nào cuối kì các bạn cũng học CSS nên mình giới thiệu trước (xem thêm qua web ở mục blog nhé)
- Tạo thêm điểm nhấn cho web để các bạn trình bày sản phẩm cho cô, tăng cơ hội điểm cao ( hoặc không )

---

### 1. Định dạng chung cho thẻ <a> (liên kết)

```css
a {
  text-decoration: none;
  color: blue; /* Màu chữ mặc định của liên kết */
  font-size: 15px;
  font-family: "Times New Roman", serif;
  transition: color 0.3s ease; /* Hiệu ứng chuyển đổi màu chữ mượt mà */
}
```
- `text-decoration: none`; → Xóa gạch chân mặc định của liên kết.
- `color: blue`; → Màu chữ của liên kết mặc định là xanh dương.
- `font-size`: 15px; → Cỡ chữ của liên kết là 15 pixel.
- `font-family`: "Times New Roman", serif; → Sử dụng font "Times New Roman" hoặc font serif nếu không có.
- `transition: color 0.3s ease`; → Khi màu chữ thay đổi, nó sẽ chuyển đổi trong 0.3 giây với hiệu ứng mượt.

---

### 2. Hiệu ứng khi di chuột vào liên kết `(hover)`
```css
a:hover {
  color: orange; /* Khi di chuột vào, đổi màu thành cam */
}
```
- Khi di chuột vào một liên kết, màu của nó sẽ đổi thành màu cam (orange).
- Đây là cách tạo hiệu ứng trực quan giúp người dùng biết rằng liên kết có thể được nhấp vào.

---

### 3. Định dạng các tiêu đề (`title`, `title1`, `title2`)

```css
.title {
  font-family: "Times New Roman", serif;
  font-style: normal;
  color: orange;
  font-size: 50px;
}
```
- `.title` → Dùng cho tiêu đề chính, có:
  - Font "Times New Roman".
  - Màu chữ cam (orange).
  - Kích thước chữ 50px (rất lớn).

```css
.title1 {
  font-family: "Times New Roman", serif;
  font-style: normal;
  color: blue;
  font-size: 20px;
}
```
- `.title1` → Dùng cho tiêu đề phụ:
  - Font "Times New Roman".
  - Màu chữ xanh dương (blue).
  - Kích thước chữ 20px.

```css
.title2 {
  font-family: "Times New Roman", serif;
  font-style: normal;
  color: blue;
  font-size: 30px;
}
```
- `.title2` → Tiêu đề có kích thước 30px, màu xanh dương.

---

### 4. Định dạng bảng `(.table)`

```css
.table {
  border-collapse: collapse;
  border: 1px solid blue; /* Viền xanh nước biển */
}
```
- `border-collapse: collapse`; → Làm cho viền bảng gọn lại, không bị giãn ra.
- `border: 1px solid blue`; → Viền bảng có độ dày 1px, màu xanh nước biển (blue).

***4.1. Định dạng tiêu đề và nội dung bảng***

```css
.table th,
.table td {
  border: 1px solid blue; /* Viền xanh nước biển */
  padding: 8px;
  text-align: center;
}
```
- `border: 1px solid blue`; → Các ô tiêu đề `(<th>)` và ô dữ liệu `(<td>)` đều có viền xanh.
- `padding: 8px`; → Khoảng cách giữa nội dung và viền ô là **8px**.
- `text-align: center`; → Căn giữa nội dung trong ô.

---

### 5. Định dạng đặc biệt cho liên kết trong bảng

```css
table a:hover {
  color: orange;
}
```
- Khi di chuột vào liên kết bên trong bảng, màu chữ đổi thành cam.

```css
table a.active {
  color: red; /* Màu khi đang ở trang đó */
}
```

- Nếu liên kết đang được chọn (tức là trang hiện tại trùng với liên kết đó), nó sẽ có **màu đỏ (red)**.

---

### 6. Tổng kết

| **Thành phần** | 	**Chức năng** |
| :--- | :--- | 
| `a` | Xóa gạch chân, đổi màu liên kết, thêm hiệu ứng mượt khi đổi màu |
| a:hover | Khi di chuột vào, liên kết đổi sang màu cam |
| .title, .title1, .title2 | Định dạng các tiêu đề với màu sắc và kích thước khác nhau |
| .table | Định dạng bảng với viền xanh và gọn gàng hơn |
| .table th, .table td | 	Thêm viền, padding và căn giữa nội dung ô bảng |
| table a:hover | Khi di chuột vào liên kết trong bảng, đổi màu cam |
| table a.active | Khi liên kết trong bảng đang ở trang hiện tại, đổi màu đỏ |

***

**- The end -**
