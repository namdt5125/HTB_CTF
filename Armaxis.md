![image](https://github.com/user-attachments/assets/6e8b107b-2c38-4dd5-bf2f-070fc0d7c529)

Bài này cung cấp 2 port, 1 cái là để login, 1 cái là mail 

![image](https://github.com/user-attachments/assets/04d7f93f-1a8a-4ff4-ae7a-d94fd95ab03e)

![image](https://github.com/user-attachments/assets/6eb9a2d6-3862-4f73-803d-08b668497363)

Tôi đang kí tạm tài khoản mới, login vào trong 

![image](https://github.com/user-attachments/assets/dfd68cb9-d989-4905-8496-4bcf3ade0e92)

![image](https://github.com/user-attachments/assets/5a9fe4e5-b33a-48aa-9421-f1af3797c17d)

Login vào rồi thì chả có gì cả, tôi đi mở src code đọc 

![image](https://github.com/user-attachments/assets/014030a1-e32a-4d4a-84b6-8d546e0861e4)

Tôi tìm được mail của admin là `admin@armaxis.htb`, kết hợp với đọc qua qua src code thì tôi thấy máy chủ có vẻ không check tính xác thực của token, cụ thể là nhận tất cả token còn hạn sử dụng:

![image](https://github.com/user-attachments/assets/b3a25b91-7a8e-45fc-b2d4-079e1c3eb28f)

Lợi dùng điều này tôi đổi pass của admin

![image](https://github.com/user-attachments/assets/bceec902-ba76-471a-9571-7ffead864478)

![image](https://github.com/user-attachments/assets/787f708e-7bc1-491f-a32c-972be1141f94)

Vào được thì giao diện có thêm cái dispatch 

![image](https://github.com/user-attachments/assets/90931a43-f44b-4096-946f-7fed7436605f)

![image](https://github.com/user-attachments/assets/deb004c5-4965-43e5-9c25-7162b351c503)

![image](https://github.com/user-attachments/assets/fb40e804-a56d-4a2a-8bf2-705592cb36d9)

Điền bừa thông tin ở dispatch thì home có hiện ra, tôi thử SQLi mà không có được, đi lanh quanh thì thấy trong markdown.js có quả curl -s khả nghi 

![image](https://github.com/user-attachments/assets/2cc92e97-5964-4896-8021-f217dffaa1d3)

Tôi thử đút payload `![image](file:///flag.txt)` để xem có /flag.txt không:

![image](https://github.com/user-attachments/assets/32e01251-d792-47a3-9351-77e116daa3f1)

Flag chính là cái base64 kia, còn mấy cái dòng linh tinh khác là do tôi treo sqlmap trong lúc đọc code... 

![image](https://github.com/user-attachments/assets/717caedc-8817-4791-a3ca-51b08a8e5fe3)
