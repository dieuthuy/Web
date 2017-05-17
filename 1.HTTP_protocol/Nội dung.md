# Web

[1.Khái niệm về giao thức HTTP](#1):

[2. HTTP request ](#2):

[- HTTP Request method](#2.1)

[- URLs](#2.2)

[3. HTTP response](#3):

<a name="1"></a>
# 1. Khái niệm về giao thức Http:

Http là viết tắt của hyperText Transfer Protocol ( *giao thức truyền tải siêu văn bản*). 

Đây là giao thức ứng dụng trong bộ các giao thức TCP/IP ( gồm 1 nhóm các giao thức nền tảng cho *internet*)

![](http://cache.media.techz.vn/upload/2014/11/04/image-1415117606-http-1.jpg) (<img/>)

HTTP hoạt động trên mô hình `Client- Server`. Trong mô hình này, **người dùng** đóng vai trò làm máy **khách (client)**.
Sau 1 thao tác nào đó của người dùng, các máy khách sẽ gửi yêu cầu đến **máy chủ (server)** và chờ đợi câu trả lời từ những máy chủ này.
Để có thể nói chuyện với nhau, các máy chủ và máy khách phải thực hiện trao đổi thông qua các giao thức. Và giao thức được nhắc tới ở đây là **HTTP**.

<a name="2"></a>
# 2. HTTP Request.

Để bắt đầu trao đổi dữ liệu, phía **Client** khởi tạo một **HTTP session** bằng cách mở một kết nối **TCP** đến 
**HTTP server** sau đó gửi **Request** đến **server** này.

**Request** có thể được tạo bằng nhiều cách ( trực tiếp và gián tiếp)

- Trực tiếp : khi người dùng nhấn vào một liên kết trên trình duyệt

- Gián tiếp: Ví dụ như một video được đính kèm trong một website và việc request đến website này sẽ dẫn đến một request tới video ấy.

***Ví dụ HTTP request:***

![](https://www.stdio.vn/statics/external_data/files/pages/articles/2015/202/content/ss_1.png)(<img/>)

<a name="2.1"></a>

## a. HTTP Request method:

**Method** là phương thức mà **HTTP REQUEST** này sử dụng, thường là *POST*,*GET*, ngoài ra còn một số phương thức như: 
HEAD,PUT,DELETE,OPTION,CONNECT.

URL là địa chỉ định danh của tài nguyên.

- GET: câu truy vấn sẽ được đính kèm vào đường dẫn của HTTP request. 

*Ví dụ: /?username=”abc”&password=”def”*

  + Một số đặc điểm của phương thức **Get**: 
    
    + GET REQUEST có thể được cached, bookmark và lưu trong lịch sử trình duyệt.
    
    + GET REQUEST bị giới hạn về chiều dài, do chiều dìa của url là có hạn.
    
    + GET REQUEST không nên dùng với dữ liệu quan trọng, chỉ dùng để nhận dữ liệu.
    
- POST:  câu truy vấn sẽ được gửi trong phần message body của HTTP request ( được truyền ngầm)

  + Một số đặc điểm của **POST**: 
  
    + POST không thể cached, boolmark hay lưu trong lịch sử trình duyệt.
    
    + POST không bị giới hạn về độ dài.
    
- Một số phương thức khác: 

  + **HEAD**: Giống GET nhưng chỉ gửi về HTTP header.
  
  + **PUT**: Tải lên một mô tả về URL định trước.
  
  + **DELETE**: Xóa một tài nguyên định trước.
  
  + **OPTIONS**: Trả về phương thức HTTP server hỗ trợ.
  
  + **CONNECT**: Chuyển kết nối của HTTP request thành một kết nối HTTP tunnel.
  
<a name="2.2"></a>
## b. URLs: Viết tắt của Uniform Resourse Locators

![](https://camo.githubusercontent.com/44e8bf77ac17436a55af988f5531a41a449be353/687474703a2f2f657870726573736d6167617a696e652e6e65742f73697465732f64656661756c742f66696c65732f696d616765732f323031332f30372f30382f68747470312d75726c2d7374727563747572652e706e67)

- protocol: HTTP và HTTPS

- Host: Tên miền Server

- Port: mặc định là 80

- Resourse path: đường dẫn tới resource trên server.

- Query: Truy vấn.

<a name="3"></a>
# 3.HTTP response:








