![image](https://github.com/user-attachments/assets/94f13611-7116-4309-b63d-b6df25bf30ac)

Chức năng có vẻ là nhập vào và nó in ra phông chữ khác 

![image](https://github.com/user-attachments/assets/a5c6ec0a-490a-4729-8bc4-77cfbf54c5af)

Và có dính xss ở đây

![image](https://github.com/user-attachments/assets/582d8f51-9780-4ef1-84f5-ca2f2162d547)

Cơ mà dính xss thì tôi cũng chưa biết phải làm gì tiếp, nghịch tiếp thì tôi thấy cái `${1+1}` được thực thi, nó dính SSTI (Server Side Template Injection)

![image](https://github.com/user-attachments/assets/c4e29367-5f2b-45a3-ac90-911a4cf31480)

Tôi dùng payload `${self.module.cache.util.os.popen('cat /flag.txt').read()}` để mở flag.txt  

![image](https://github.com/user-attachments/assets/ed8906e5-9c90-4c3f-a930-f0754d80e655)

