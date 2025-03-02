![image](https://github.com/user-attachments/assets/94836c87-1a36-4615-ab36-9daade606117)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/3337d0ed-c371-48db-81d2-b74086664d07)

Req cuar login:

![image](https://github.com/user-attachments/assets/3ea6d6bf-4814-4cfc-9a59-3a09c2e47b05)

Sau khi nghịch thử thì tôi chuyển qua đăng kí 1 tài khoản mới, vào thấy giao diện tạo document, tôi tạo thử 1 cái:

![image](https://github.com/user-attachments/assets/a8b1c846-8742-495c-b4d1-5ddbbe765133)

Nó cho cái cookie là username, id và 1 cái mã hóa ở đằng sau, tôi nhìn cái `33cf6fd88f73ac2ce581be6cc9417f54e54ccd7dc6154313851bf6c9f41d3428` giống giống SHA2-256

![image](https://github.com/user-attachments/assets/09d01487-4892-4b1d-ad6c-4485694164ba)

Đọc src code thì SQLi là không dùng được, tôi đổi cái username trong cookie thành admin và hiện ra Unauthorized

![image](https://github.com/user-attachments/assets/de162c94-3f2a-43eb-9f8d-e67d734046cb)

![image](https://github.com/user-attachments/assets/216bbf6c-e19b-4e3c-ab7d-00b51c59b090)

Việc giả mạo cookie cũng khó vì nó hash random bằng sha256:

![image](https://github.com/user-attachments/assets/da4fced0-3430-4075-ab93-f09d0f2c8816)

Sau 1 lúc đọc cái src của document và test thì tôi nhận ra là khi ném cái base64 thông tin của uusername vào trong document, nó sẽ cho cái Signature chính là hash nằm trong cookie:

![image](https://github.com/user-attachments/assets/e217f137-166d-4b28-a074-ab525c77c1b1)
 
![image](https://github.com/user-attachments/assets/4fadc1d4-3da3-4c21-a4ac-a323766b316c)

Vậy là có thể mạo danh với mọi user tồn tại, vào cái chỗ để lấy flag:

![image](https://github.com/user-attachments/assets/8da7537f-87d2-41a1-953c-b3c04283ad48)

Lần này thì lại liên quan đến ACCESS_PASS:

![image](https://github.com/user-attachments/assets/3b560f9e-3e9f-4cf4-950d-baf3008d3ee6)

![image](https://github.com/user-attachments/assets/298ac945-70fc-4df4-8c49-e8a41f785e69)

![image](https://github.com/user-attachments/assets/e01220d4-a741-4521-bde5-4df24696504e)

Tôi đã cố thử brute nhưng không ra 

![image](https://github.com/user-attachments/assets/7dd79479-2967-4ae3-80be-324cf219995c)













