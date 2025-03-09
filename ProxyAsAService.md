![image](https://github.com/user-attachments/assets/0bc6e2ba-ddc4-434c-9fc9-b2de6912bdb2)![image](https://github.com/user-attachments/assets/81db8560-2e86-4d8f-862e-d3bd4879f9f2)![image](https://github.com/user-attachments/assets/6976ba0b-1709-446d-895c-0a10453e9ba3)

Đây là giao diện khi vào web, status code là 403:

![image](https://github.com/user-attachments/assets/f4eaf162-90ec-4d13-9f29-4a9c50ffe42a)

Đại khái thì cái này dẫn đến reddit.com và muốn có flag thì phải vào environment:

![image](https://github.com/user-attachments/assets/03abd8a4-01f1-4461-a12d-b78071c94297)

Mà vào thẳng environment thì không có được, phải đi qua cái debug:

![image](https://github.com/user-attachments/assets/bd8161e9-67bf-4478-8ed2-90b858b15d98)

![image](https://github.com/user-attachments/assets/34df8fb4-788d-4cf4-99a7-2d7f74c44c32)

Để ý src code thì muốn vào được thì phải là từ localhost tới @is_from_localhost

![image](https://github.com/user-attachments/assets/7f08c74f-8e36-41bb-827b-c03af53a03e8)

Cái url là cái param mà tôi có thể nhập vào và bằng cách search google + chatpgt, tôi được cái [URL Obfuscation Through Schema Abuse](https://cloud.google.com/blog/topics/threat-intelligence/url-obfuscation-schema-abuse/):

![image](https://github.com/user-attachments/assets/d118d525-891c-47e5-a833-088dd39b7d74)

![image](https://github.com/user-attachments/assets/9926f01c-9c77-4d9d-b267-df408178d4f6)

Vậy là đã có ssrf, tôi nghĩ là sẽ tìm cách vào localhost, cơ mà trong code cũng đã hạn chế các đường dẫn tới localhost

![image](https://github.com/user-attachments/assets/95bb1cf7-c278-491f-9585-a12ff4b7a3d0)

Nhưng mà ở run.py thì có 0.0.0.0 và port 1337:

![image](https://github.com/user-attachments/assets/15afecff-9357-4b21-85b5-2bbfad779999)

`?url=@0.0.0.0:1337/debug/environment` là ra:

![image](https://github.com/user-attachments/assets/c86a8f08-c18a-4176-a2ab-835f78602763)

