![image](https://github.com/user-attachments/assets/472bda53-c364-4c8e-bfee-95d9390d7ecb)

Đây là giao diện của web, tôi không có tài khoản nên vào phần register:

![image](https://github.com/user-attachments/assets/60e31a9a-6063-4769-b8ee-6c33dabdefcb)

![image](https://github.com/user-attachments/assets/5e6789d1-f21a-428b-82a6-d81f43c402b5)

Sau khi đăng kí xong thì được cho cái jwt token, tôi hashcat thử với rockyou nhưng không ra key và tôi cũng nghịch thử 1 số thứ với jwt nhưng không được:

![image](https://github.com/user-attachments/assets/4fdbfab7-6331-4818-a1aa-0493185c67ef)

FUZZ cũng không có mấy khả quan, đọc src code thì có administrator là ra flag:

![image](https://github.com/user-attachments/assets/52b1bbcb-249c-404a-8f69-235861559c22)

![image](https://github.com/user-attachments/assets/057e10f5-1b66-4374-a568-4a55b0041118)

Còn đây là phần xử lý username và password từ json:

![image](https://github.com/user-attachments/assets/6a146b86-a766-417b-b473-6601951959c8)

Cái phần này nó bị sai ở chỗ là thiếu dấu ngoặc, đáng ra phải là `!(count($json_data) == 2)` thì nó mới hoạt động đúng, lỗi sai này dẫn đến việc tôi chỉ nhập mỗi administrator là có jwt token của admin:

![image](https://github.com/user-attachments/assets/0167b638-360f-4c87-ae57-9f336ba057ac)

![image](https://github.com/user-attachments/assets/81baa8f6-7e3b-4c64-90ed-9236c107dd0d)




