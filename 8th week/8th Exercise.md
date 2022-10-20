# 모듈과 활용

<a href="https://github.com/Moon-GD/SW_coding_Python_/blob/main/8th%20week/%EB%AC%B8%EA%B2%BD%EB%8D%95%208%EC%A3%BC%EC%B0%A8%20%EC%97%B0%EC%8A%B5%EB%AC%B8%EC%A0%9C%20%EA%B3%BC%EC%A0%9C.ipynb">전체 코드 주소</a>

## 1. 다음과 같은 내용을 포함하고 있는 greet.txt 파일을 파이썬의 write() 메소드를 이용하여 작성하시오. 이때 greet.txt 파일이 이미 존재할 경우를 가정하고 이 파일이 쓰기 금지 모드(읽기 모드)로 되어 있을 가능성이 있기 때문에 이를 위한 예외처리 기능을 구현하시오.
![image](https://user-images.githubusercontent.com/74173976/196883844-3b3b9cec-12bd-4f07-b184-ad1a2cc709c8.png)
![image](https://user-images.githubusercontent.com/74173976/196883859-1a0d2d9d-b613-484e-ad1b-f76694ff6b4b.png)
![image](https://user-images.githubusercontent.com/74173976/196883875-a677d663-75af-4659-bccd-b5e92aa5d5bc.png)

### Code

```python
# Ans.

try:
    greet_file = open('greet.txt', "w")
    greet_file.write("""Hi, everyone.
    welcome to Python.""")
    greet_file.close()
except:
    print('Error:: PermissionError[errno 13] Permission denined')
```

### Console :

```
Error:: PermissionError[errno 13] Permission denined
```

## 2. 다음과 같은 내용을 포함하고 있는 number1to10.txt 파일을 한 줄씩 읽어들이도록 하여라.
## (1) 이 파일을 읽어서 각 행의 정수에 곱하기 10을 수행한 후 다음과 같은 numberby10.txt라는 이름의 파일로 저장하여라.
![image](https://user-images.githubusercontent.com/74173976/196883946-0477e465-a9c6-4ad7-a91f-5d8ea0a0c67e.png)
![image](https://user-images.githubusercontent.com/74173976/196883954-781295b5-8f68-4977-802e-c5fd97524cff.png)

### Code :

```python
# Ans. (1)

numbers_file = open("number1to10.txt", "r")
contents = []

one_line = numbers_file.readline().rstrip()
while one_line != '':
    contents.append(one_line)
    one_line = numbers_file.readline().rstrip()
    
numbers_new_file = open('numberby10.txt', "w")
for line in contents:
    numbers_new_file.write(str(int(line) * 10) + '\n')
numbers_new_file.close()
```

## (2) 위 두 파일을 읽어서 다음과 같이 각 행의 값을 하나의 내용으로 묶어서 저장하는 프로그램을 작성하여라. 이 파일의 이름은 merge.txt이다.
![image](https://user-images.githubusercontent.com/74173976/196883996-a951b321-9349-414f-9069-466ffcb61925.png)


### Code : 

```python
# Ans. (2)

numbers_file = open("number1to10.txt", "r")
contents = []

one_line = numbers_file.readline().rstrip()
while one_line != '':
    contents.append(one_line)
    one_line = numbers_file.readline().rstrip()
    
count = 1
numbers_new_file = open('merge.txt', "w")
for line in contents:
    sentence = str(count) + " : " + str(int(line) * 10) + "\n"
    numbers_new_file.write(sentence)
    count += 1
    
numbers_new_file.close()
```

## 3. “Hello Python”이라는 문자열을 파일로 저장하기 위하여 my_hello.txt 라는 파일을 열고 쓰기를 시도하였다. 이때 이 파일이 이미 존재하고 있으며 문제 1번의 읽기 모드 설정 방법을 참고하여 이미 이 파일이 읽기 모드로 설정되어 있다고 가정한다.

### (1) 이 상황에서는 어떤 예외가 발생하는지, 실제로 파일을 만들어서 이러한 상황을 테스트하는 프로그램을 작성하여 예외를 출력하여라

### Code :

```python
# Ans : PermissionError: [Errno 13] Permission denied: 'my_hello.txt'

hello_file = open("my_hello.txt", "r+")
hello_file.readline()
hello_file.close()
```

### Console :

```
PermissionError                           Traceback (most recent call last)
<ipython-input-14-10abde429684> in <module>
      1 # Ans : PermissionError: [Errno 13] Permission denied: 'my_hello.txt'
      2 
----> 3 hello_file = open("my_hello.txt", "r+")
      4 hello_file.readline()
      5 hello_file.close()

PermissionError: [Errno 13] Permission denied: 'my_hello.txt'
```

### (2) 이 예외를 처리하는 try-exception 문을 구현하여라

### Code : 

```python
# Ans.

try:
    hello_file = open("my_hello.txt", "r+")
    hello_file.readline()
    hello_file.close()

except PermissionError:
    print('읽기만 가능한 파일입니다.')
```

### Console : 

```
읽기만 가능한 파일입니다.
```

## 4. 다음과 같은 내용을 포함하고 있는 hello.txt 파일을 텍스트 편집기를 이용하여 작성하시오
![image](https://user-images.githubusercontent.com/74173976/196884885-ad955b2e-bafb-4f62-94b1-714fd9141c1e.png)

## (1) 이제 이 파일을 open() 함수를 통해 읽어서 이 파일의 내용을 다음과 같이 화면에 출력하시오.
![image](https://user-images.githubusercontent.com/74173976/196884922-ad79176a-8e20-444f-a0db-92b7b96ec78a.png)

### Code : 

```python
# Ans.

filename = "hello.txt"
hello_file = open(filename, "r")

print(f'{filename} 파일 : ')

one_line = hello_file.readline().rstrip()
while one_line:
    print(one_line)
    
    one_line = hello_file.readline().rstrip()
    
hello_file.close()
```

### Console : 

```
hello.txt 파일 : 
Hello.
Hi, there.
```

## (2) 이 파일을 open() 함수를 통해 읽어서 원래 파일의 내용 아래쪽에 ‘Welcome to Python!’을 추가한 후 저장하시오. 그리고 다시 한번 파일을 읽어서 다음과 같이 화면에 출력하시오.
![image](https://user-images.githubusercontent.com/74173976/196885129-633d2ed0-bcb4-4f67-bc94-6db9c2a9050a.png)

### Code :

```python
# Ans.

# write 부분
filename = "hello.txt"
hello_file = open(filename, "a")
hello_file.write("\nWelcome to Python!")
hello_file.close()

# read 부분
hello_file = open(filename, "r")
print(f'{filename} 파일 : ')

one_line = hello_file.readline().rstrip()
while one_line:
    print(one_line)
    
    one_line = hello_file.readline().rstrip()
    
hello_file.close()
```

```
hello.txt 파일 : 
Hello.
Hi, there.
Welcome to Python!
```

## 5. 1에서 10사이의 랜덤한 숫자를 30개 가진 randint30.txt 라는 파일을 random 모듈을 사용하여 생성하시오. 이 때 생성한 숫자는 다음과 같이 공백으로 구분하여 나열하시오.
![image](https://user-images.githubusercontent.com/74173976/196885290-69e8fecb-79f9-42fc-96da-cf8ba7529b08.png)


### Code : 

```python
# Ans.

import random as rd

random_file = open("randint30.txt", "w")

for _ in range(30):
    random_file.write(str(rd.randint(1, 10)))
    random_file.write(' ')
    
random_file.close()
```

## (1) 위의 randint30.txt라는 파일을 읽어서 1에서 10까지 정수의 출현횟수를 다음과 같이 출력하여라.
![image](https://user-images.githubusercontent.com/74173976/196885456-dd6c5950-4403-4e4e-bd4b-1e21e1141925.png)

### Code : 

```python
# Ans.

random_file = open("randint30.txt", "r")

numbers_list = random_file.readline().split(" ")
count_list = [0 for _ in range(11)]

for number in numbers_list[:-1]:
    count_list[int(number)] += 1

for i in range(1, 11) :
    print(f'{i:2d} : {count_list[i]}개')

random_file.close()
```

### Console : 
```
 1 : 3개
 2 : 5개
 3 : 4개
 4 : 2개
 5 : 3개
 6 : 0개
 7 : 3개
 8 : 3개
 9 : 4개
10 : 3개
```
