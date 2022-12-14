## Semantic HTML
Semantic HTML introduces meaning to the code we write. Before Semantic HTML the elements didn’t have any meaning as to what it does or what content goes in it. An element such as `<div>` was used as a general-purpose element to create things from headers to footers to articles. With Semantic HTML we were introduced to elements that tell developers and browsers exactly what it does and what content should go in it.
```
<!--Non Semantic HTML-->
<div id="footer">
 <p>this is a footer</p>
</div>

<!--Semantic HTML-->
<footer>
 <p>this is a footer</p>
</footer>
```
## Element Placement
Semantic HTML introduces elements that can tell developers exactly what the element does or where it’s placed based on the name of that element. Some of these elements are `<header>`, `<nav>`, `<main>`, and `<footer>`.  `<header>` describes the content at the top of the page `<body>`. It may include a logo, navigational links or a search bar. `<nav>` encapsulates the page’s navigational links. It is often placed inside the `<header>` or `<footer>`. `<main>` encapsulates the main content of a page between the header/navigation and the footer areas. `<footer>` includes the page’s footer content at the bottom of the `<body>`.s
![Giao diện web](../theory/images/img_structure_analysic.gif)

Với những phân tích trên, ta thấy những phần như: header, global navigation, page body, content, sidebar, footer đều là những phần nội dung lớn, do đó ta sẽ sử dụng thẻ `<div></div>` cho những thành phần này:

```{html}
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8" />
<title>Tiêu đề trang web</title>
</head>

<body>
<div id="header">Viết nội dung phần header ở đây</div>

<div id="gNav">Viết nội dung phần global navigation ở đây</div>

<div id="pageBody">
<div id="content">Viết nội dung phần content ở đây</div>
<div id="sidebar">Viết nội dung phần sidebar ở đây</div>
</div>

<div id="footer">Viết nội dung phần footer ở đây</div>
</body>
</html>
```
### Phần đầu: header
![Phần đầu: header](./images/img_structure_header01.gif)

*  Phần bên trái: ta tạm gọi là hLeft (header left), phần này chứa logo và domain trang web .Logo sử dụng image nên ta dùng thẻ `<img />`, nhưng do logo là phần quan trọng nhất của trang, nên ta sử dụng thẻ `<h1>` bao ngoài thẻ` <img />`.
Domain ta thấy cần bao bên ngoài bằng thẻ `<p>` là được.
* Phần bên phải: ta tạm gọi là hRight (header right), phần này chứa 2 button và một danh sách chứa link
    * 2 button này có thể coi như một danh sách không có thứ tự do đó ta có thể sử dụng thẻ `<ul><li>`.
    * Danh sách chứa link cũng thuộc dạng danh sách không có thứ tự vì vậy ta cũng có thể sử dụng thẻ `<ul><li>`.
* Để tiện cho việc điều khiển các thẻ, ta sử dụng 2 thẻ <div> bao bên ngoài phần bên trái và bên phải, vậy phần header ta có thể code như sau:

```{html}
<div id="header">
<div class="hLeft">
<h1><img src="images/img_logo.gif" alt="" /></h1>
<p>www.hoctepa.edu.com</p>
<!-- / class hLeft --></div>

<div class="hRight">
<ul>
<li><a href="#"><img src="images/btn_name01.gif" alt="" /></a></li>
<li><a href="#"><img src="images/btn_name02.gif" alt="" /></a></li>
</ul>

<ul>
<li><a href="#">link 01</a></li>
<li><a href="#">link 02</a></li>
<li><a href="#">link 03</a></li>
<li><a href="#">link 04</a></li>
</ul>
<!-- / class hRight --></div>
<!-- / id header --></div>
```
Kết nối phần header này vào phần cấu trúc cơ bản ta có được cấu trúc sau:
```{html}
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8" />
<title>Tiêu đề trang web</title>
</head>

<body>
<div id="layout">
<div id="header">
<div class="hLeft">
<h1><img src="images/img_logo.gif" alt="" /></h1>
<p>www.hoctepa.edu.com</p>
<!-- / class hLeft --></div>

<div class="hRight">
<ul>
<li><a href="#"><img src="images/btn_name01.gif" alt="" /></a></li>
<li><a href="#"><img src="images/btn_name02.gif" alt="" /></a></li>
</ul>
<ul>
<li><a href="#">link 01</a></li>
<li><a href="#">link 02</a></li>
<li><a href="#">link 03</a></li>
<li><a href="#">link 04</a></li>
</ul>
<!-- / class hRight --></div>
<!-- / id header --></div>

<div id="gNav">
Viết nội dung phần global navigation ở đây
<!-- / id gNav --></div>

<div id="pageBody">
<div id="content">
Viết nội dung phần content ở đây
<!-- / id content --></div>

<div id="sidebar">
Viết nội dung phần sidebar ở đây
<!-- / id sidebar --></div>
<!-- / id pageBody --></div>

<div id="footer">
Viết nội dung phần footer ở đây
<!-- / id footer --></div>
<!-- / id layout --></div>
</body>
</html>
```
### Global navigation: Phần liên kết toàn cục global
<p align="center">
    <img src="./images/img_structure_gnav.gif" />
</p>

```{html}
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8" />
<title>Tiêu đề trang web</title>
</head>

<body>
<div id="layout">
<div id="header">
<div class="hLeft">
<h1><img src="images/img_logo.gif" alt="" /></h1>
<p>www.hoctepa.edu.com</p>
<!-- / class hLeft --></div>

<div class="hRight">
<ul>
<li><a href="#"><img src="images/btn_name01.gif" alt="" /></a></li>
<li><a href="#"><img src="images/btn_name02.gif" alt="" /></a></li>
</ul>
<ul>
<li><a href="#">link 01</a></li>
<li><a href="#">link 02</a></li>
<li><a href="#">link 03</a></li>
<li><a href="#">link 04</a></li>
</ul>
<!-- / class hRight --></div>
<!-- / id header --></div>

<div id="gNav">
<ul>
<li><a href="#">TRANG CHỦ</a></li>
<li><a href="#">GIỚI THIỆU</a></li>
<li><a href="#">SẢN PHẨM</a></li>
<li><a href="#">DỊCH VỤ</a></li>
<li><a href="#">LIÊN HỆ</a></li>
</ul>
<!-- / id gNav --></div>

<div id="pageBody">
<div id="content">
Viết nội dung phần content ở đây
<!-- / id content --></div>

<div id="sidebar">
Viết nội dung phần sidebar ở đây
<!-- / id sidebar --></div>
<!-- / id pageBody --></div>

<div id="footer">
Viết nội dung phần footer ở đây
<!-- / id footer --></div>
<!-- / id layout --></div>
</body>
</html>
```

### Phần nội dung chính : content
Nhìn vào cấu trúc phần content ở trên, ta thấy nội dung gồm 3 phần: phần "Sản phẩm mới", phần "Tin tức" và phần banner.
<p align="center">
    <img alt="Ảnh content" src="./images/img_structure_content.gif" />
</p>
Nhìn vào cấu trúc phần content ở trên, ta thấy nội dung gồm 3 phần: phần "Sản phẩm mới", phần "Tin tức" và phần banner.

#### Phần "Sản phẩm mới", ta phân tích:
<p align="center">
    <img alt="Ảnh content" src="./images/img_structure_content01.gif" />
</p>

* Phần tiêu đề "Sản phẩm mới" ta sử dụng `<h2>` (vì `<h1>` đã sử dụng cho logo trong phần header).
* Đối với hình lớn, ta sử dụng thẻ `<p>`.
* Phần nội dung bên phải, ta sử dụng thẻ `<div>` bao bên ngoài để tiện điều khiển, bên trong ta thấy nội dung có một tiêu đề ta sử dụng thẻ `<h3>` và đoạn text giới thiệu ta sử dụng thẻ `<p>`.
* Phần còn lại là danh sách hình nhỏ, ta sử dụng thẻ danh sách `<ul><li>`
* Để phân biệt phần sản phẩm mới và danh sách những sản phẩm khác, ta sử dụng thẻ `<div>` nhóm phần sản phẩm mới lại.
```{html}
<h2>Sản phẩm mới</h2>
<div class="newProduct">
<p><img src="images/img_products_new01.jpg" alt="" /></p>
<div>
<h3>Tên sản phẩm</h3>
<p>Text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm.</p>
</div>
<!-- / class newProduct --></div>

<ul>
<li><a href="#"><img src="images/img_products01.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products02.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products03.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products04.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products05.jpg" alt="" /></a></li>
</ul>
```
#### Phần "Tin tức", ta phân tích:
<p align="center">
    <img alt="Ảnh content" src="./images/img_structure_content02.gif" />
</p>

* Phần tiêu đề "Tin tức" vì cùng cấp với tiêu đề "Sản phẩm mới" nên ta tiếp tục sử dụng `<h2>`.
* Phần bên dưới có dạng danh sách có nội dung và các mục, do đó ta sử dụng bộ 3 thẻ `<dl>`, `<dt>`, `<dd>`.
#### Phần banner:
<p align="center">
    <img alt="Ảnh content" src="./images/img_structure_content03.gif" />
</p>

> Phần banner này ta thấy chỉ là một tấm hình, do đó chỉ cần sử dụng thẻ `<p>` chứa thẻ `<img />` là đủ, tất nhiên phải có thẻ `<a>` để tạo liên kết

Kết nối phần "Sản phẩm mới", phần "Tin tức" và phần"banner" vào phần cấu trúc cơ bản ta có được cấu trúc sau:

```{html}
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Tiêu đề trang web</title>
</head>

<body>
<div id="layout">
<div id="header">
<div class="hLeft">
<h1><img src="images/img_logo.gif" alt="" /></h1>
<p>www.hoctepa.edu.com</p>
<!-- / class hLeft --></div>

<div class="hRight">
<ul>
<li><a href="#"><img src="images/btn_name01.gif" alt="" /></a></li>
<li><a href="#"><img src="images/btn_name02.gif" alt="" /></a></li>
</ul>
<ul>
<li><a href="#">link 01</a></li>
<li><a href="#">link 02</a></li>
<li><a href="#">link 03</a></li>
<li><a href="#">link 04</a></li>
</ul>
<!-- / class hRight --></div>
<!-- / id header --></div>

<div id="gNav">
<ul>
<li><a href="#">TRANG CHỦ</a></li>
<li><a href="#">GIỚI THIỆU</a></li>
<li><a href="#">SẢN PHẨM</a></li>
<li><a href="#">DỊCH VỤ</a></li>
<li><a href="#">LIÊN HỆ</a></li>
</ul>
<!-- / id gNav --></div>

<div id="pageBody">
<div id="content">
<h2>Sản phẩm mới</h2>
<div class="newProduct">
<p><img src="images/img_products_new01.jpg" alt="" /></p>
<div>
<h3>Tên sản phẩm</h3>
<p>Text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm.</p>
</div>
<!-- / class newProduct --></div>

<ul>
<li><a href="#"><img src="images/img_products01.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products02.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products03.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products04.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products05.jpg" alt="" /></a></li>
</ul>

<h2>Tin tức</h2>
<dl class="news">
<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>

<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>

<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>
</dl>

<p><a href="#"><img src="images/bnr_name01.gif" alt="" /></a></p>
<!-- / id content --></div>

<div id="sidebar">
Viết nội dung phần sidebar ở đây
<!-- / id sidebar --></div>
<!-- / id pageBody --></div>

<div id="footer">
Viết nội dung phần footer ở đây
<!-- / id footer --></div>
<!-- / id layout --></div>
</body>
</html>
```
### Phần nội dung phụ: Sidebar
Nhìn vào phần sidebar ta thấy nội dung chia ra làm 2 phần: phần link liên quan chứa danh sách link, và phần link liên quan chứa banner link, ta phân tích 2 phần này như sau:
<p align="center">
    <img alt="Ảnh content" src="./images/img_structure_sidebar01.gif" />
</p>

Vì phần "content" và phần "sidebar" có nội dung riêng biệt, nên phần tiêu đề `<hx>` cũng sẽ độc lập nhau, không cần code thứ tự tiêu đề của phần sidebar theo phần content, do đó ta tiếp tục sử dụng `<h2>` cho phần sidebar này.
Hai phần "link liên quan" ta thấy có cấu trúc của một danh sách, do đó cả 2 ta sử dụng thẻ `<ul>` và `<li>` là đủ thể hiện.

```{html}
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8" />
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Tiêu đề trang web</title>
</head>

<body>
<div id="layout">
<div id="header">
<div class="hLeft">
<h1><img src="images/img_logo.gif" alt="" /></h1>
<p>www.hoctepa.edu.com</p>
<!-- / class hLeft --></div>

<div class="hRight">
<ul>
<li><a href="#"><img src="images/btn_name01.gif" alt="" /></a></li>
<li><a href="#"><img src="images/btn_name02.gif" alt="" /></a></li>
</ul>
<ul>
<li><a href="#">link 01</a></li>
<li><a href="#">link 02</a></li>
<li><a href="#">link 03</a></li>
<li><a href="#">link 04</a></li>
</ul>
<!-- / class hRight --></div>
<!-- / id header --></div>

<div id="gNav">
<ul>
<li><a href="#">TRANG CHỦ</a></li>
<li><a href="#">GIỚI THIỆU</a></li>
<li><a href="#">SẢN PHẨM</a></li>
<li><a href="#">DỊCH VỤ</a></li>
<li><a href="#">LIÊN HỆ</a></li>
</ul>
<!-- / id gNav --></div>

<div id="pageBody">
<div id="content">
<h2>Sản phẩm mới</h2>
<div class="newProduct">
<p><img src="images/img_products_new01.jpg" alt="" /></p>
<div>
<h3>Tên sản phẩm</h3>
<p>Text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm.</p>
</div>
<!-- / class newProduct --></div>

<ul>
<li><a href="#"><img src="images/img_products01.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products02.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products03.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products04.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products05.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products06.jpg" alt="" /></a></li>
</ul>

<h2>Tin tức</h2>
<dl class="news">
<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>

<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>

<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>
</dl>

<p><a href="#"><img src="images/bnr_name01.gif" alt="" /></a></p>
<!-- / id content --></div>

<div id="sidebar">
<h2>Link liên quan</h2>
<ul>
<li><a href="#">Link liên quan 01</a></li>
<li><a href="#">Link liên quan 02</a></li>
<li><a href="#">Link liên quan 03</a></li>
<li><a href="#">Link liên quan 04</a></li>
<li><a href="#">Link liên quan 05</a></li>
<li><a href="#">Link liên quan 06</a></li>
</ul>

<h2>Link liên quan</h2>
<ul>
<li><a href="#"><img src="images/bnr_name02.gif" alt="" /></a></li>
<li><a href="#"><img src="images/bnr_name03.gif" alt="" /></a></li>
<li><a href="#"><img src="images/bnr_name04.gif" alt="" /></a></li>
</ul> <!-- / id sidebar --></div>
<!-- / id pageBody --></div>

<div id="footer">
Viết nội dung phần footer ở đây
<!-- / id footer --></div>
<!-- / id layout --></div>
</body>
</html>
```

### Phần cuối trang web: Footer
---
<p align="center">
    <img alt="Ảnh content" src="./images/img_structure_footer01.gif" />
</p>

```{html}
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8" />
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Tiêu đề trang web</title>
</head>

<body>
<div id="layout">
<div id="header">
<div class="hLeft">
<h1><img src="images/img_logo.gif" alt="" /></h1>
<p>www.hoctepa.edu.com</p>
<!-- / class hLeft --></div>

<div class="hRight">
<ul>
<li><a href="#"><img src="images/btn_name01.gif" alt="" /></a></li>
<li><a href="#"><img src="images/btn_name02.gif" alt="" /></a></li>
</ul>
<ul>
<li><a href="#">link 01</a></li>
<li><a href="#">link 02</a></li>
<li><a href="#">link 03</a></li>
<li><a href="#">link 04</a></li>
</ul>
<!-- / class hRight --></div>
<!-- / id header --></div>

<div id="gNav">
<ul>
<li><a href="#">TRANG CHỦ</a></li>
<li><a href="#">GIỚI THIỆU</a></li>
<li><a href="#">SẢN PHẨM</a></li>
<li><a href="#">DỊCH VỤ</a></li>
<li><a href="#">LIÊN HỆ</a></li>
</ul>
<!-- / id gNav --></div>

<div id="pageBody">
<div id="content">
<h2>Sản phẩm mới</h2>
<div class="newProduct">
<p><img src="images/img_products_new01.jpg" alt="" /></p>
<div>
<h3>Tên sản phẩm</h3>
<p>Text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm text giới thiệu sản phẩm.</p>
</div>
<!-- / class newProduct --></div>

<ul>
<li><a href="#"><img src="images/img_products01.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products02.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products03.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products04.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products05.jpg" alt="" /></a></li>
<li><a href="#"><img src="images/img_products06.jpg" alt="" /></a></li>
</ul>

<h2>Tin tức</h2>
<dl class="news">
<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>

<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>

<dt>07/05/2012</dt>
<dd><a href="#">Tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới tin mới.</a></dd>
</dl>

<p><a href="#"><img src="images/bnr_name01.gif" alt="" /></a></p>
<!-- / id content --></div>

<div id="sidebar">
<h2>Link liên quan</h2>
<ul>
<li><a href="#">Link liên quan 01</a></li>
<li><a href="#">Link liên quan 02</a></li>
<li><a href="#">Link liên quan 03</a></li>
<li><a href="#">Link liên quan 04</a></li>
<li><a href="#">Link liên quan 05</a></li>
<li><a href="#">Link liên quan 06</a></li>
</ul>

<h2>Link liên quan</h2>
<ul>
<li><a href="#"><img src="images/bnr_name02.gif" alt="" /></a></li>
<li><a href="#"><img src="images/bnr_name03.gif" alt="" /></a></li>
<li><a href="#"><img src="images/bnr_name04.gif" alt="" /></a></li>
</ul> <!-- / id sidebar --></div>
<!-- / id pageBody --></div>

<div id="footer">
<div class="fLeft">
<p>TÊN CÔNG TY</p>
<p>Địa chỉ: 123 abc, phường X, quận Y, tp.Z<br />
Điện thoại: 012.3456789</p>
<p>Email: <a href="mailto:support@hoctepa.edu.com">support@hoctepa.edu.com</a></p>
<!-- / class fLeft --></div>

<div class="fRight">
<ul>
<li><a href="#">Link 01</a></li>
<li><a href="#">Link 02</a></li>
<li><a href="#">Link 03</a></li>
<li><a href="#">Link 04</a></li>
</ul>
<p>Copyright (c) 2012 Tên công ty</p>
<!-- / class fRight --></div>
<!-- / id footer --></div>
<!-- / id layout --></div>
</body>
</html>
```
## Embedding media
Semantic HTML introduces us to `<video>`, `<audio>` and `<embed>`. `<video>` allows us to add videos to our website. `<audio>` allows us to implement audio into our website. `<embed>` can be used to implement any type of media. These elements are universal in that they all use the src attribute to link the source of the content. `<video>` and `<audio>` requires a closing tag while `<embed>` is a self-closing tag.
```
<!--Video Tag-->
<video src="4kvideo.mp4">video not supported</video>

<!--Audio Tag-->
<audio src="koreanhiphop.mp3"></audio>

<!--Embed tag-->
<embed src="babyyoda.gif"/>
```
## `<figure>` and `<figcaption>`
The `<figure>` element is used to encapsulate media such as an image, diagram. or code snippet. The `<figcaption>` element is used to describe the media encapsulated within the `<figure>` element. Developers will normally use `<figcaption>` within the `<figure>` element to group the media and description. This way, if a developer decides to change the position of the media, the description will follow along with it.
```
<figure>
 <img src="qwerty.jpg">
 <figcaption>The image shows the layout of a qwerty keyboard.</figcaption>
</figure>
```
## <section> and <article>
`<section>` defines elements in a document, such as chapters, headings, or any other area of the document with the same theme. `<article>` holds content that makes sense on its own such as articles, blogs, and comments. Generally developers will use `<section>` to define a theme for the webpage and use `<article>` to write independent content for that theme. This does not mean that `<article>` has to be used with `<section>`.
```
<section>
  <!--defines theme-->
  <h2>Top Sports league in America</h2>
<!--writes independent content relating to that theme-->
  <article>
    <p>One of the top sports league is the nba.</p>
  </article>
</section>
```
## `<aside>` Aside Element
The `<aside>` element is used to mark additional information that can enhance another element but isn’t required in order to understand the main content. Usually, this information would be in a sidebar or a location where it doesn’t obstruct the main piece of content. An example of this would be an article that discusses how to take care of a dog and next to the article an ad would appear advertising a dog grooming product.
```
<article>
<!--Main Content-->
</article>
<aside>
<!--Additional information-->
</aside>
```
