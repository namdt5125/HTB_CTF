![image](https://github.com/user-attachments/assets/8adeb2b8-cb81-4316-b6ac-dc0131872ede)

Đây là giao diện của trang web:

![image](https://github.com/user-attachments/assets/0cca8cb4-59a6-4765-8ddd-03e288068bba)

Đây là sau khi upload ảnh:

![image](https://github.com/user-attachments/assets/716a83d6-05db-4607-a665-ecbdc0639294)

Tôi thử upload file .txt thì không được:

![image](https://github.com/user-attachments/assets/36d4d8d3-95de-412d-baff-ab3187d82948)

Đây là đoạn code upload file:

![image](https://github.com/user-attachments/assets/1071a587-c593-4f07-abb3-635f7447a651)

Cái này chỉ cho upload mấy file có extension là 'png', 'jpg', 'jpeg':

![image](https://github.com/user-attachments/assets/9c1e08a6-2de1-41dc-972e-ba91d26f6a5a)

Có save_tmp là tạo file tạm thời, trong petpet thì có mở file rồi xóa file đó luôn:

![image](https://github.com/user-attachments/assets/44144d52-c29f-4ac8-ae6e-1e4a54033c6f)

Nếu search mạng đoạn code này thì có quả [CVE-2018-16509](https://github.com/farisv/PIL-RCE-Ghostscript-CVE-2018-16509) nhìn giống với code này:

![image](https://github.com/user-attachments/assets/cd8d6fd4-837c-4d01-b6b6-88f0f15fb609)

Và cái github này cũng cung cấp PoC luôn:

![image](https://github.com/user-attachments/assets/47a5baea-c2e2-4af2-8816-65d612231d4f)

![image](https://github.com/user-attachments/assets/6bc50261-dc64-4116-8f18-e8cbc72c5292)

Dựa vào cái src code thì có đường dẫn `application/static/petpets/` là có thể truy cập công khai:

![image](https://github.com/user-attachments/assets/5270377a-f88e-4e92-bf09-908ed403ff25)

Tôi đổi sang lệnh khác để rce:

![image](https://github.com/user-attachments/assets/7f429953-7964-4b94-9690-8f9e9a5e1ce3)

![image](https://github.com/user-attachments/assets/abe27f94-1a56-41ba-98fa-57c97146645f)

