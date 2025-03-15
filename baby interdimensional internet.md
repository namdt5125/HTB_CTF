![image](https://github.com/user-attachments/assets/ddc7783d-e409-467c-9d06-892f02c70c4f)

Đây là giao diện của web, cái số kia thì mỗi lần gửi 1 req là 1 số khác nhau:

![image](https://github.com/user-attachments/assets/74cde968-d735-4663-9f5f-daa3faa504ad)

Vào ctrl u thì thấy có /debug:

![image](https://github.com/user-attachments/assets/8b366fe7-b786-44e7-bb47-a968973339d0)

Full src code đây:

![image](https://github.com/user-attachments/assets/1c22246a-5719-47ed-a1d6-0000cb558928)

Ở đây có cái exec() là nguy hiểm và nó nhận recipe:

![image](https://github.com/user-attachments/assets/62510953-794a-4255-a3e3-8f76f47f9cb6)

![image](https://github.com/user-attachments/assets/a283538c-9310-439b-b4a8-20bcd14747dc)

Và trong src code có trường hợp GET và POST, với GET thì nó random nên không làm gì được, còn POST thì nhận giá trị từ body:

![image](https://github.com/user-attachments/assets/0d0d7ff4-7ad7-417f-8556-ff0efa856184)

![image](https://github.com/user-attachments/assets/b62cea73-7c11-4fe8-8550-a8f00efc8029)

Tôi dùng `__import__('os').popen('ls').read()` và nó ra được:

![image](https://github.com/user-attachments/assets/f4f89c1b-c42c-437c-bd79-9dbbe922d7ce)

![image](https://github.com/user-attachments/assets/2cdbdd33-0548-4d4b-a4f3-4e23fbeefada)
