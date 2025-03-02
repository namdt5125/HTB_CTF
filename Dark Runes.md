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

Sau 1 lúc đọc src code và test thì tôi nhận ra 1 cái khá đặc biệt:

![image](https://github.com/user-attachments/assets/f1a0484f-c943-49a2-8773-aa923218e5e3)

![image](https://github.com/user-attachments/assets/e90c7b23-9666-4289-88bf-78d115a9944a)

![image](https://github.com/user-attachments/assets/6672317e-8c2d-4d5a-a3d5-0136d274f58e)

Cụ thể là nếu username mà không tồn tại thì trang sẽ chuyển hướng đến 1 nơi khác, còn tồn tại thì sẽ hiện ngay invalid ở trong web, nó làm tôi nghĩ đến việc brute force username và password:






