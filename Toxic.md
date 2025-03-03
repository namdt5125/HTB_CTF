![image](https://github.com/user-attachments/assets/f63baf0a-62f5-4721-af39-246511ff872f)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/ffc9bf94-8373-473f-8a46-07276b9adb63)

Web không có tính năng nào cả, check req thì thấy PHPSESSID decode ra `O:9:"PageModel":1:{s:4:"file";s:15:"/www/index.html";}`

![image](https://github.com/user-attachments/assets/22e68219-ffe5-4574-8f81-0ae13f270265)

Nếu đọc src code thì thấy có include, việc này có thể dễ dẫn đến LFI:

![image](https://github.com/user-attachments/assets/2b98dfe7-3545-4726-924d-2f26f6db96a7)

Và cái này còn liên quan đến cookie nữa, trong trường hợp không có gì thì mặc định là /www/index.html, nếu sửa cookie thì chắc là dùng được LFI:

![image](https://github.com/user-attachments/assets/25733330-4f22-43ee-bae0-44687f202c7a)

![image](https://github.com/user-attachments/assets/a13e4458-a4ba-417b-a39f-bebb313ef365)

Trong cái `O:9:"PageModel":1:{s:4:"file";s:15:"/www/index.html";}` thì sau khi tôi sửa đường dẫn thành /etc/passwd và chả có gì xảy ra, để ý cái s:15, tôi thấy nó trùng với độ dài của đường dẫn, tôi chỉnh thành độ dài 11 của đường dẫn /etc/passwd và thử:

![image](https://github.com/user-attachments/assets/43831fbe-ec03-4da5-85b5-3875504fea48)

Tiếp tục đọc code thì thấy access log ở /var/log/nginx/access.log:

![image](https://github.com/user-attachments/assets/063ef191-856e-4227-86ff-dc58efd2aa75)

Tôi chèn quả `<?php phpinfo(); ?>` vào User-Agent để thử và được:

![image](https://github.com/user-attachments/assets/4eb889b2-8a75-46d8-927b-32706aa20f84)

![image](https://github.com/user-attachments/assets/06eb8706-3015-4e4e-830a-1151c0e44147)

Dùng `User-Agent: <?php system($_GET[test]); ?>` thì chạy được ls

![image](https://github.com/user-attachments/assets/1d8bd0b4-928b-42bb-a272-e6c24b30caaa)

![image](https://github.com/user-attachments/assets/061fc421-3c0f-4097-b478-6ff4ea165346)











