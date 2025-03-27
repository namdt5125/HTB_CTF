![image](https://github.com/user-attachments/assets/c0d208cc-e1f5-4313-8072-c3c56dfb4d9c)

Đây là giao diện của web, do chưa có tài khoản và cũng không có sqli nên tôi đăng kí và đăng nhập:

![image](https://github.com/user-attachments/assets/976f3368-1691-4411-86c7-b08f18d0edc9)

Thì cái credit đang là 0, không chuyển tiền đi được:

![image](https://github.com/user-attachments/assets/82d3157a-ea0c-48e2-8730-1019aca8295d)

![image](https://github.com/user-attachments/assets/34ca7ad3-8f08-4554-aa89-fcf98981ddee)

Còn trường hợp chuyển 0 thì không có chấp nhận, số âm cũng không được:

![image](https://github.com/user-attachments/assets/0dcb4152-d786-4812-86a9-c5a0c48f127c)

![image](https://github.com/user-attachments/assets/e3051677-436b-4040-b946-a0131baab1e5)

Phân tích src code thì để lấy được flag thì phải chuyển 1337:

![image](https://github.com/user-attachments/assets/abf4dced-b353-447e-a5df-d0925289b3f1)

![image](https://github.com/user-attachments/assets/0731d23c-17a3-4794-ad83-bba167adc783)

Chèn 2 lần amount với 1 lần là 0 và 1 lần là 1337 thì ok:

![image](https://github.com/user-attachments/assets/2e5841c5-447d-43cb-bf4d-e3dc13ec3a28)

lý do là với amount = 0 thì nó qua được cái này:

![image](https://github.com/user-attachments/assets/4ab6a4db-ce34-4f87-9283-43d54108eb45)

Sau khi qua được thì nó lấy cái 1337 ở sau để qua được cái này và tiến đến ok

![image](https://github.com/user-attachments/assets/3bed74b8-a5e0-4319-91f8-a055c0a9ff3f)

Quay lại chrome thì nó ra được flag:

![image](https://github.com/user-attachments/assets/69284e36-066d-4c31-afe5-95f305bc836d)
