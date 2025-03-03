![image](https://github.com/user-attachments/assets/b29d3a08-6fb9-4052-8c8d-3b020617bd5f)

Giao diện đây:

![image](https://github.com/user-attachments/assets/62e98d95-616f-430f-b99c-06eed641ab4b)

Khi tôi ấn cái nút kia thì có tham số format xuất hiện với giá trị là r:

![image](https://github.com/user-attachments/assets/ab6d9d76-acf3-4a1b-b825-cd2bfcb953db)

Đọc src code thì thấy có TimeController là chả làm gì thì nó sẽ mặc định là r

![image](https://github.com/user-attachments/assets/b11e3c38-64d9-4466-baf5-f6e3ba1998a2)

Còn cái này thì tạo thời gian random, và để ý cái __construct, trong PHP là một phương thức khởi tạo (constructor) được tự động gọi khi một đối tượng của lớp được tạo. Nó thường được dùng để thiết lập giá trị ban đầu cho các thuộc tính của đối tượng hoặc thực hiện các thao tác khởi tạo khác

![image](https://github.com/user-attachments/assets/1efc213b-7a29-4d6a-a9d8-fc71c6da27f9)

Tiếp là nó xuất hiện ở /views/index.php 

![image](https://github.com/user-attachments/assets/3f948cd0-a001-4917-8583-c1618740cb28)

Vấn đề chính là ở chỗ getTime có cái eval, eval() cực kỳ nguy hiểm nếu dữ liệu đầu vào có thể bị kiểm soát bởi người dùng, vì nó cho phép thực thi mã PHP tùy ý:

![image](https://github.com/user-attachments/assets/eccc7033-a30c-4b1f-9f35-b88870082658)

Để minh họa cho cái này thì tôi dùng `format=${phpinfo()}`, để ý payload nếu có dấu đặc biệt thì không được do cái addslashes nó lọc hết:

![image](https://github.com/user-attachments/assets/0b20d867-6935-4971-bb21-32e5eb5de92e)

![image](https://github.com/user-attachments/assets/4fba9ea4-265d-4b6f-8229-ea6d56a488bc)

![image](https://github.com/user-attachments/assets/18190961-a392-49b2-ba72-8a17a6014a81)

Để không bị filter thì tách làm 2 cái param: 

![image](https://github.com/user-attachments/assets/316267f9-59bf-4e34-acb0-762601d1acfa)

![image](https://github.com/user-attachments/assets/0dec3a09-c5d3-4b41-85e0-73a6a02efa24)




