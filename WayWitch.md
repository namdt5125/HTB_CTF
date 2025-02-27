![image](https://github.com/user-attachments/assets/55f1ebc6-5942-492b-9fee-185fa06aef92)

Giao diện:

![image](https://github.com/user-attachments/assets/980f94c6-1e6f-48bc-bc53-dba2a463878b)

Nhập vào thì có 1 cái jwt 

![image](https://github.com/user-attachments/assets/66e1fa4e-f9c8-44b1-890f-2afc94be2f73)

Sau 1 lúc đọc src code thì tôi thấy cái này:

![image](https://github.com/user-attachments/assets/b8855cac-787f-47df-9d9e-e2d0207066ae)

Để ý đến cái /tickets:

![image](https://github.com/user-attachments/assets/010e8307-fff1-437f-a3ad-d37c62bb72f8)

Tôi sửa username thành admin mà không được:

![image](https://github.com/user-attachments/assets/78b373ee-f71d-4bf8-ba2a-a12d6fd80e54)

Tôi quên mất là có cái key halloween-secret của jwt 

![image](https://github.com/user-attachments/assets/fe5b4789-bfb6-4e7f-ba36-44bcd2041995)

Sang phần jwt editor và tạo 1 cái key mới, encode base64 halloween-secret và đưa vào giá trị k

![image](https://github.com/user-attachments/assets/d3f5d6b0-76e5-422e-bbbc-7edfd892088a)

Đổi username thành admin và kí 

![image](https://github.com/user-attachments/assets/7bc9cd0a-85a1-49ae-8bdf-5e8f79d3cddf)









