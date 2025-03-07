![image](https://github.com/user-attachments/assets/ce52713d-173b-4f9b-9941-13c099c34e15)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/b4ca7230-a7bf-4dbf-8106-defb6aa91ef9)

![image](https://github.com/user-attachments/assets/c1770115-a102-4785-8439-d87ba681f702)

![image](https://github.com/user-attachments/assets/9e93152d-3b2b-4636-b0f6-564908c51724)

Khi login với admin:admin thì nó ra như này, ở src code thì cái password admin được random:

![image](https://github.com/user-attachments/assets/dd3f250c-ba6d-4982-8e37-b1b2335e5d9b)

![image](https://github.com/user-attachments/assets/778ff23a-19ff-45b1-a4f9-0d5a2972379d)

Và cũng không có đăng kí được:

![image](https://github.com/user-attachments/assets/7a9a13f8-4c22-4139-821d-ce7624e6c66c)

Lý do là do cái này, chốc nữa sẽ nhắc lại sau:

![image](https://github.com/user-attachments/assets/ee8c6428-ff56-4ee1-b764-0dc265e50031)

Quay lại đọc src code, cái db gồm có 3 cột là id, username và password 

![image](https://github.com/user-attachments/assets/fd9aa526-d497-4b66-a170-e0ce67c54570)

Thêm 1 cái đáng lưu ý ở đây là cái register lại không dùng Prepared Statements, còn isadmin có ? rồi thì có vẻ không sqli được, tôi nghĩ là có thể lợi dụng register để đổi lại mật khẩu cho admin:

![image](https://github.com/user-attachments/assets/21764551-a156-426a-81e9-0abec0c94283)

Vậy là register có thể sẽ dính sqli với payload `admin') ON CONFLICT(username) DO UPDATE SET password = 'admin';--` nhưng lại vướng cái 401 do nó đưa về 127.0.0.1. Tiếp tục đọc src code thì đây là nodejs bản 8.12.0 và có 1 cái [cve](https://snyk.io/test/docker/node%3A8.12.0-alpine#SNYK-UPSTREAM-NODE-73603):

![image](https://github.com/user-attachments/assets/7c7c615d-dd43-4128-ac87-f6facbcda8a1)

Cái lỗi này là khi gửi 1 request nhưng vào phía server thì bên server sẽ tách ra tùy theo input mà user gửi tới, từ đó có thể tạo một POST request mới kẹp vào để để gửi theo, tôi gửi 3 req, gồm có 2 cái là localhost/lmao và GET / ở thứ nhất và thứ 3 để là giả, còn cái POST ở giữa để update lại password:

![image](https://github.com/user-attachments/assets/5e7d35cb-8257-4f38-8b44-d0a1c6309fa1)

Có mấy cái như space = "\u0120" \r = "\u010D" \n = "\u010A" là biểu thị trong unicode. 
Trong HTTP, một số ký tự được coi là ký tự điều khiển (control characters) và không được phép xuất hiện trong các thành phần như tiêu đề (headers), đường dẫn (URL), hoặc nội dung yêu cầu/phản hồi. 
Tuy nhiên, các ký tự Unicode được đề cập không phải là ký tự điều khiển trong HTTP, nên có thể sử dụng mà không vi phạm quy tắc của giao thức













