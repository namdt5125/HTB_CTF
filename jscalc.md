![image](https://github.com/user-attachments/assets/e8e40f48-bc34-4a95-a45c-316328587c75)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/1cd4290d-6904-42be-b6fb-5e10b57cdea3)

![image](https://github.com/user-attachments/assets/519da671-f891-4ecb-b1e3-c156879f6d71)

Và đây là req của nó:

![image](https://github.com/user-attachments/assets/46af064f-9743-48af-85c0-d533bdfb80c0)

Trong src code có dùng eval():

![image](https://github.com/user-attachments/assets/fbec9df6-5b7d-4915-9186-90dc5ea94d40)

Tôi đi search google, sau 1 lúc thì kiếm được cái rce này [RCE](https://medium.com/@sebnemK/node-js-rce-and-a-simple-reverse-shell-ctf-1b2de51c1a44):

![image](https://github.com/user-attachments/assets/4d114cf1-7f0d-4637-8898-b33e489c187c)

![image](https://github.com/user-attachments/assets/769ae3ce-1b2a-43ed-abb0-e66c53321b85)

Và nó chạy được với payload `require('fs').readdirSync('/').toString()` để xem các file và thư mục có trong /

![image](https://github.com/user-attachments/assets/b1ba0717-ae46-4fd5-90b3-852678da24b8)

Dùng `require('fs').readFileSync('/flag.txt').toString()` để đọc /flag.txt

![image](https://github.com/user-attachments/assets/35aac8d0-8e4f-4ee4-9bab-be6b1d1ae8ed)
