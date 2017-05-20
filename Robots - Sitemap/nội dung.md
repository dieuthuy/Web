
# ROBOTS AND SITEMAP

1.[Cài đặt WordPress lên hosting](#1)

2.[Tìm hiểu về Robots.txt](#2)

3.[Tìm hiểu về sitemap.xml](#3)

4.[Thực hành demo về robots.txt và sitemap.xml lên site wordpress vừa cài đặt](#4)

<a name="1"></a>
## 1. Cài đặt WordPress lên hosting

WordPress là cài đặt website trực tiếp mà không cần sử dụng localhost để chuyển host lên.

**--> Có " GOOGLE"**

<a name="2"></a>
## 2. Tìm hiểu về robots:

- robots là những `con bọ tìm kiếm ` có tác dụng ` tìm kiếm ` thông tin trên website, Kiểm tra chất lượng đánh giá website theo các truy vấn tìm kiếm cụ thể.

- file `robots.txt` để hướng dẫn công cụ tìm kiếm tự động đến những trang mà bạn muốn nó tìm kiếm và sau đó thì index trang đó.

- Hầu hết các trang web đều cũng có những thư mục và file không cần đến robots, tức là không muốn bị các công cụ tìm kiếm ghé thăm.

- file `robots.txt` được tạo bởi công cụ đơn giản như Notepad++, ..

- File này `đặt trong thư mục gốc chứa mã nguồn website của mình.`

**Các lệnh cơ bản của robots.txt : **

    + User - agent: user-agent của robots cần chặn, hoặc cấp quyền sử dụng cho tất cả robots.
    
    + Disallow : không cho phép crawler truy cập 1 nội dung file.
    
    + allow thì ngược lại disallow
    
    + Sitemap:thông báo cho máy tìm kiếm biết `XML` của trang web.
    
<a name="3"></a>
## 3.Tìm hiểu về sitemap.xml   

- XML sitemap là `bản đồ thu nhỏ` của website, nó liệt kê tất cả các liên kết trong website.

- Mục đích là lấy `sitemap` gửi lên `google webmaster tools `. Các bot tìm kiếm sẽ lần theo địa chỉ trong sitemap này đưa nó vào hệ thống dữ liệu của google.

- Giúp cho các robot của các máy chủ như google, yahoo,..dễ dàng thu nhập dữ liệu trang web bởi nó đã tạo ra 1 lộ trình sẵn( bản đồ), Các robots tìm kiếm chỉ việc đi theo lộ trình đó.

-  Đối với các website mới thì sitemap giúp cho các công cụ tìm kiếm dò thấy trang mình nhanh hơn, giảm thời gian đáng kể để thiết lập chỉ mục.

- Nhưng đối với những trang web có nội dung chất lượng kém thì mặc dù có trong sitemap nhưng vẫn có thể bị google loại bỏ không cho index.
