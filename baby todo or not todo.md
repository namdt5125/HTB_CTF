![image](https://github.com/user-attachments/assets/0b7b06a4-1ab0-4a7f-9bc3-05f68e4b2a78)

Đây là giao diện của web:

![image](https://github.com/user-attachments/assets/98cd4f3f-23dd-40c3-be09-9facd2f18879)

Và đây là req của web trả lại sau khi add gì đó

![image](https://github.com/user-attachments/assets/29d0d0de-069b-4174-8b3f-f532ee947729)

Đọc src code thì flag ở đây:

![image](https://github.com/user-attachments/assets/cf54f3e2-b0f1-4576-8760-dbea2959bfbd)

Ở database thì các câu truy vấn đề dùng ? nên không thể sqli được:

![image](https://github.com/user-attachments/assets/a9f30430-ee57-4246-96f2-b218d609cc6b)

Khi ctrl u thì có có data-secret:

![image](https://github.com/user-attachments/assets/5b01d4b4-bc6b-4466-b8f8-66db50a7c597)

Trong cái ctrl u lại có thêm cái note này

![image](https://github.com/user-attachments/assets/bd0c3375-8c5d-4c28-9763-8cf1108cfa12)

Tôi chạy thử getstatus('all') trên console thì không được, chạy getTasks('user106D3edd') thì ra được mấy cái của tôi, còn khi chạy getTasks('all') thì ra nhiều thứ và bị refresh ngay sau đó do trong code nó làm thế:

![image](https://github.com/user-attachments/assets/ce15a097-6452-4298-b916-f0b6e7bbba7f)

Tôi bật intercept lên để xem

![image](https://github.com/user-attachments/assets/e9b92812-c002-44c1-9588-fc6ad67e2a65)







