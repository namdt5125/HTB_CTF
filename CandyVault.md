![image](https://github.com/user-attachments/assets/c5375241-dfba-4610-b49b-65c632c44749)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/591121cd-a082-4b94-b2a0-65737f8ef957)

Đây là req khi login:

![image](https://github.com/user-attachments/assets/c3a2cc65-8820-467a-9f22-af9a90001a5e)

Đọc src code thì thấy nó dùng mongodb có chỗ nó tạo 1 cái user random

![image](https://github.com/user-attachments/assets/4f00f01d-5088-4768-874c-e2db1064c22e)

Flag thì nằm ở đây:

![image](https://github.com/user-attachments/assets/734dd5f0-173f-4311-a3a6-b555f9354c05)

![image](https://github.com/user-attachments/assets/09551afb-0d85-4aee-aa19-a858908e40d3)

Đọc trong code có chỗ chấp nhận dạng json, tôi chuyển req sang json:

![image](https://github.com/user-attachments/assets/e7fa9f8a-0775-4cb0-b8e0-b83f3898267c)

![image](https://github.com/user-attachments/assets/ad304f32-2774-45ac-be97-522df82e673e)

Do user được tạo random nên không thể biết được email và password để nhập và mongodb cũng không có filter gì hết nên tôi dùng `{"$ne":""}` chèn vào email và password:

![image](https://github.com/user-attachments/assets/b7b9fa25-ab8c-47eb-a78c-a698d7b96d5c)



