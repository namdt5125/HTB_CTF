![image](https://github.com/user-attachments/assets/4f5af3fd-69d5-4f0b-93fc-684c5cf4c953)

Khi vào trang web thì có phần login và register, do không có tài khoản nên tôi register và vào trong:

![image](https://github.com/user-attachments/assets/0476dbc8-0af3-460b-a6cb-989569e5ee8d)

![image](https://github.com/user-attachments/assets/99a53d17-7e84-40ad-b22d-31d18d6dcf3a)

Tôi dùng ffuf để FUZZ các dir và vào thử, đến cái storage thì ra cái này

![image](https://github.com/user-attachments/assets/6df284bf-61fc-4f9b-b4f1-cfe839619025)

![image](https://github.com/user-attachments/assets/5d68fe30-db7d-48d1-a8f0-6f47d4eaa764)

Trong đây chứa các config, ở cuối có 1 cái backup và đây là sau khi giải nén nó ra:

![image](https://github.com/user-attachments/assets/6ac8416e-58ed-4127-b471-b74d54244738)

Đưa lên sqlite online thì ra được 3 users

![image](https://github.com/user-attachments/assets/8e6a64c9-19f7-4e35-8465-34c4e7274945)

Tôi dùng hashcat với rockyou.txt thì tìm được mật khẩu của 1 user có tên là jr:

![image](https://github.com/user-attachments/assets/4eca7fda-6c14-4c32-b8c4-16a1777fddcb)

Tôi login vào:

![image](https://github.com/user-attachments/assets/7dbd0f39-efda-4d32-89b9-aca0fa0f7ce4)

![image](https://github.com/user-attachments/assets/16a93602-4038-4414-ab87-41facc4be5d0)





