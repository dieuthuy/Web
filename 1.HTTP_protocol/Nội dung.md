# Web

[1.Khái niệm về giao thức HTTP](#1):

[2. HTTP request ](#2):

[- HTTP Request method](#2.1)

[- URLs](#2.2)

[3. HTTP response](#3):

[-HTTP Status Codes](#3.1):

[-Gói tin HTTP](#3.2):

[4. Encrypted connection](#4)

[5. HTTP Caching](#5):

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

Cấu trúc HTTP response gần giống với HTTP request, chỉ *khác nhau* là thay vì **request - line**,
thì **HTTP response** có **status-line**.

- **Status line** có 3 phần : 
  
  + HTTP-Version: phiên bản HTTP cao nhất mà server hỗ trợ.
  
  + Status-Code: mã kết quả trả về . 
  
  + Reason-Phrase: mô tả về Status-Code

<a name="3.1"></a>
** - HTTP Status Codes:**

* Mốt số loại status- code thông dụng mà Server trả về cho client như sau: *

  + **1xx:  information message (thông tin)**: các status này chỉ mang tính tạm thời, client có thể không quan tâm.

    + 100(continue) : máy chủ trả về nói rằng nó đã nhận được 1 phần request và chờ đợi gửi thêm phần còn lại.
    
    + 101 (Switching protocol) : request đã hỏi server về việc thay đổi protocol và server đã chấp nhận.
    
  + **2xx : Successful**: khi đã xử lý thành công request của client, server trả về status này: 
  
    + 200: OK: request thành công.
    
    + 202 : Acceptes: Request đã được nhận, nhưng không có kết quả nào trả về, thông báo cho client tiếp tục chờ đợi.
    
    + 204: No Content: Request đã được xử lý nhưng không có thành phần nào được trả về.
    
    + 205: Reset: Giống như 204 nhưng mã này còn yêu cầu client reset lại document view.
    
    + 206 : Partial content: server chỉ gửi về một phần dữ liệu, phụ thuộc vào các giá trị range header của client đã gửi.
    
  + **3xx Redirection**: server thông báo cho client phải thực hiện thêm thao tác để hoàn tất request:
  
    + 301 moved permanently: tài nguyên đã được chuyển hoàn toàn tới địa chỉ location trong http response.
    
    + 303: see other: tài nguyên đã đc chuyển tạm thời tới địa chỉ location trong http response.
    
    + 304 not modified: tài nguyên không thay đổi từ lần cuối client request, nên client có thể sử dụng đã lưu trong cache.
    
  + **4xx client error:** Lỗi của client: 
  
    + 400 bad request: request không đúng dạng, cú pháp
    
    + 401 unauthorized: client chưa xác thực.
    
    + 403 forbidden: client không có quyền truy cập.
    
    + 404: not found: không tìm thấy tài nguyên.
    
    + 405 method not allowed: phương thức không đc server hỗ trợ.
    
    + 406 not acceptable: server chỉ có thể tạo phản hồi mà không được chấp nhận bới client.
    
    + 407 proxy authentication required: yêu cầu client xác thực sử dụng proxy, khi máy chủ trả về phản hồi này nó cùng chỉ ra proxy mà người yêu cầu phải sử dụng.
    
    + 408 request time out: hết time chờ, requets tốn thời gian dài hơn thời gian của server phản hồi.
    
    + 409 conflic: các server gặp phải conflic( xung đột) khi thực hiện request. các server phải bảo gồm thông tin
    confict trong các phản ứng. máy chủ có thể trả về mã này để đáp ứng với yêu cầu PUT xung đột với các yêu cầu trước đó với cột danh sách khác biệt giữa các yêu cầu.
  + **5xx server error**: lỗi của server:
  
    + 500: internal server error: có lỗi trong quá trình xử lý của server.
    
    + 501: not implemented: server không hỗ trợ chức năng client yêu cầu.
    
    + 503 : service unavaialbe: server bị quá tải, hoặc bị lỗi xử lý.
   
<a name="3.2"></a>
**-Gói tin HTTP:**

  + Trong wireshark ta có một số thông tin: 

![](https://camo.githubusercontent.com/4a00babac8f58ef87f0ea54afb6766a0d336289d/687474703a2f2f692e696d6775722e636f6d2f506e48517236392e706e67)(<img/>)
   
  + có nghĩa: 
  
    + ta đang sử dụng HTTP phiên bản 1/1
    
    + DNS PORT là http (80)
    
    + địa chỉ nguồn (source) : 192.168.1.103
    
    + địa chỉ ip đích (destination): 182.161.72.71
    
<a name="4"></a>
# 4. Encrypted connections: 

có 2 cách thường dùng để mã hóa kết nối HTTP : 

- HTTP secure ( HTTP + SSL)

- HTTP + transport layer securerity (TLS)

<a name="5"></a>
# 5. HTTP Caching: 

Thường dùng cho các hệ thống thông tin nơi hiệu suất được cải thiện bằng việc sử dụng bộ **nhớ đệm**.

Mục đích của bộ nhớ đệm là loại bỏ sự cần thiết phải gởi yêu cầu trong nhiều trường hợp, gửi phản hồi một cách đầy đủ trong nhiều trường hợp khác để tiết kiệm tài nguyên.

Caching sẽ vô ít nếu không cải hiện hiệu suất.
   
   
   
   
   
   
   
   
   
   
   
   
   



