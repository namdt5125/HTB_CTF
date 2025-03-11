![image](https://github.com/user-attachments/assets/90037bd9-ff2b-4406-9bfb-6fecc6baca1d)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/b2bf5e97-3720-491d-8196-0af0fdfa69b3)

Và đây là kết quả khi tôi chọn bừa 1 cái:

![image](https://github.com/user-attachments/assets/2d343e32-f5d8-420f-b8f9-d98cfa32848a)

Còn đây là src code cái đoạn xử lý khi user ấn vào:

![image](https://github.com/user-attachments/assets/8cf0c3e3-20fe-4d75-b289-acba6ae45f10)

Để ý đến cái này:

![image](https://github.com/user-attachments/assets/a4cf7fbc-cf62-4677-b5aa-ce5903a1f904)

Tôi thêm thử cái `X-Forwarded-Host: dev.apacheblaze.local` cơ mà vẫn không có được:

![image](https://github.com/user-attachments/assets/b10d61de-1115-424d-9c3d-b1787e36dcde)

Đọc ở docker thì thấy đây là httpd-2.4.55, search google thì có rất nhiều thứ nói về cái này như [đây](https://httpd.apache.org/security/vulnerabilities_24.html) hoặc [đây](https://whitehat.vn/threads/xuat-hien-poc-cho-lo-hong-nghiem-trong-trong-may-chu-apache-http.17263/)

![image](https://github.com/user-attachments/assets/a0dec92e-6ed6-45ce-a16f-45cad66d506d)

Nếu tìm tiếp thì có 1 cái [PoC](https://github.com/dhmosfunk/CVE-2023-25690-POC) của lỗ hổng này (HTTP Request Smuggling), tôi dùng thử payload:

![image](https://github.com/user-attachments/assets/b3e7e00c-cf3c-4a48-8777-8c98617d9d3b)

Tôi sửa thành `GET /api/games/click_topia%20HTTP/1.1%0d%0aHost:%20dev.apacheblaze.local%0d%0a%0d%0aGET%20/api/games/click_topia` và gửi thì ra flag

![image](https://github.com/user-attachments/assets/4e85603c-e7a0-45ef-9bc4-f6345e9457ae)








