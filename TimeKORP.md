![image](https://github.com/user-attachments/assets/7c4dff30-ac03-4fb0-ba26-b13f4664f6f2)

Giao diện gồm 2 nút là xem thời gian và ngày tháng năm 

![image](https://github.com/user-attachments/assets/0ad6fe99-7de2-435f-a847-4ec2ae3891f1)

![image](https://github.com/user-attachments/assets/cf9c611a-71f1-414f-9ed1-cca0b351b03b)

Tôi đang nghi nó là chạy bằng command trong terminal

![image](https://github.com/user-attachments/assets/119d5264-ac7b-4bef-8514-31cdf4eb76e2)

Tôi thử thêm ;ls thì nó như này:

![image](https://github.com/user-attachments/assets/3780ddff-5d74-4fe5-bf5e-3058d1d0af21)

Tôi thử thêm `')"%0als` thì nó ra như này:

![image](https://github.com/user-attachments/assets/a0e7d1a1-79ae-4c10-8f02-c563e25913c5)

Có vẻ không giống command injection lắm, sau 1 lúc không làm gì, recon không ra cái gì, tôi xem wup trên mạng thì nó có chỗ tải src về, còn tôi thì không thấy tải ở đâu

![image](https://github.com/user-attachments/assets/d77239dd-ee64-4478-b3a7-a6f1644fcb0d)

![image](https://github.com/user-attachments/assets/44b10bf0-bb89-4c93-b708-8225d7bca217)

Thế nên xem tạm src trên mạng, nhìn vào thì có thể truyền cái payload `?format='%3b+ls+/+|+base64+||+'` 

![image](https://github.com/user-attachments/assets/3e3ee7ea-2887-41a6-9776-4c94c7bbb54c)

cat flag ra là xong

![image](https://github.com/user-attachments/assets/0d0a91c0-4077-447b-bdf5-4b11cf86300e)

