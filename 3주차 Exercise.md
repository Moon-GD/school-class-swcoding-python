## 1. 다음과 같이 사용자로부터 3개의 임의의 정수를 입력으로 받아서 가장 작은 수부터 큰 수까지 나열하는 프로그램을 if-else 문을 사용하여 작성하시오.

![image](https://user-images.githubusercontent.com/74173976/190890099-dd70d53e-70ba-4a5c-a845-b88e236a74d2.png)

### Code : 

```python
a, b, c = map(int, input('세 정수를 입력하시오 : ').split())

if a > b:
    if b > c:
        print(c, b, a)
    # c >= b
    else:
        if a > c:
            print(b, c, a)
        else:
            print(b, a, c)

# b >= a
else:
    if a > c:
        print(c, a, b)
    # c >= a
    else:
        if b > c:
            print(a, c, b)
        else:
            print(a, b, c)
```

### Console : 
```
세 정수를 입력하시오 : 9 12 4
4 9 12

세 정수를 입력하시오 : 99 12 4
4 12 99
```

## 2. 사용자로부터 x, y 좌표를 가진 한 점을 입력으로 받아서 이 점이 1, 2, 3, 4 분면의 어디에 속하는지를 알려주는 프로그램을 작성하시오.

![image](https://user-images.githubusercontent.com/74173976/190890112-2682d456-eb3a-4132-b6fa-7832c385af5f.png)

### Code : 
```python
x, y = map(int, input('점의 좌표 x, y를 입력하시오 : ').split())

if x > 0:
    if y > 0:
        print('1사분면에 있음')
    else:
        print('4사분면에 있음')
else:
    if y > 0:
        print('2사분면에 있음')
    else:
        print('3사분면에 있음')
```

### Console : 
```
점의 좌표 x, y를 입력하시오 : 2 4
1사분면에 있음

점의 좌표 x, y를 입력하시오 : -2 -4
3사분면에 있음
```

## 3. 사용자로부터 점수를 입력받은 다음 게임 사용자의 게임점수(game_score)가 1000점 이상이면 ‘고수입니다.’를 출력하고 1000점 미만이면 ‘입문자입니다.’를 출력하는 프로그램을 if-else문을 이용하여 작성하시오. 

![image](https://user-images.githubusercontent.com/74173976/190890124-348525c1-718d-46f8-9c5b-b71ea83e2268.png)
![image](https://user-images.githubusercontent.com/74173976/190890125-295b2ffc-ada6-4924-b988-9c630d6621ee.png)

### code : 
```python
game_score = int(input('게임점수를 입력하시오 : '))

if game_score >= 1000:
    print('고수입니다.')
else:
    print('입문자입니다.')
```

### Console :
```
게임점수를 입력하시오 : 4222
고수입니다.

게임점수를 입력하시오 : 4
입문자입니다.
```

## 4. 다음의 프로그램은 어떤 결과 값을 출력하는가? 출력결과를 미리 예측한 후 타이핑하여 그 결과가 맞는지 확인해 보도록 하자.

#### 1) 
![image](https://user-images.githubusercontent.com/74173976/190890141-44ddb207-fc38-44cc-8d5f-f815eeb46ba3.png)

#### Code :
```python
for i in range(3):
    print('Python ')
    print('is ')
    print('FUN!')
```

#### Console :
```
Python 
is 
FUN!
Python 
is 
FUN!
Python 
is 
FUN!
```

#### 2) 
![image](https://user-images.githubusercontent.com/74173976/190890154-9dce3cf3-056c-4335-9e17-abfb6655ba94.png)

#### Code : 
```python
for i in range(3):
    print('Python ')
    print('is ')
print('FUN! ')
```

#### Console :
```
Python 
is 
Python 
is 
Python 
is 
FUN!
```

## 5. 소수란 양의 자연수 중에서 1과 자기 자신이외의 약수를 가지지 않는 수를 말한다. 사용자로부터 양의 정수 n을 입력받은 후 이 숫자가 소수인지 아닌지를 판별하는 프로그램을 작성하시오. 이때 수행 속도를 개선하기 위하여 2로 나누어 본 후 나누어지지 않을 경우 3, 5, 7, … 과 같은 홀수로 나눗셈을 시도하도록 코딩하여라.
![image](https://user-images.githubusercontent.com/74173976/190890165-eb138493-d49b-43b9-8a1f-98f7f024d774.png)

### Code :
``` python
number = int(input('숫자를 입력하세요 : '))
flag = False

for i in range(2, number):
    if number % i == 0:
        print(f'{number}는 소수가 아닙니다.')
        flag = True
        
if flag == False:
    print(f'{number}는 소수입니다.')
```


### Console : 
```
숫자를 입력하세요 : 5
5는 소수입니다.

숫자를 입력하세요 : 9
9는 소수가 아닙니다.
```

## 6. 암스트롱 수란 세 자리의 정수 중에서 각 자리의 수를 세제곱한 수의 합과 자신이 같은 수를 말한다. 구체적인 예를 들면 153은 1 + 125 + 27 의 합으로 구성될 수 있는데 이러한 수가 암스트롱 수이다. 세 자리 정수들 중에서 모든 암스트롱 수를 구하여 다음과 같이 출력하여라.
![image](https://user-images.githubusercontent.com/74173976/190890175-34b8cb2b-9b8e-4372-a568-4f366506fa4a.png)

### Code :
```python
numbers = []

for i in range(100, 1000):
    a = i // 100
    b = i // 10 % 10
    c = i % 10
    
    if a ** 3 + b ** 3 + c ** 3 == i:
        numbers.append(i)
        
print('세 자리의 암스트롱 수 : ', end=' ')
for number in numbers:
    print(number, end = ' ')
```

### Console :
```
세 자리의 암스트롱 수 :  153 370 371 407 
```

## 7. 다음과 같이 사용자로부터 1에서 9사이의 숫자를 입력받아 입력받은 숫자의 절에 해당하는 구구단을 출력하는 프로그램을 for문과 while 문을 사용하여 작성하여라. 만일 1에서 9 이외의 숫자가 입력되면 ‘1에서 9까지의 수를 다시 입력하세요’라는 안내문을 출력하여라.
![image](https://user-images.githubusercontent.com/74173976/190890185-6f029cdb-5a60-4504-8dfb-83fab0611eba.png)

### Code : 
``` python
number = int(input('1에서 9까지의 수를 입력하세요 : '))

while True:
    if 1 <= number and number <= 9:
        for i in range(1, 10):
            print(f'{number} * {i} = {number * i}')
        break
    else:
        number = int(input('1에서 9까지의 수를 다시 입력 하세요 : '))
```

### Console : 
```
1에서 9까지의 수를 입력하세요 : 11
1에서 9까지의 수를 다시 입력 하세요 : 134
1에서 9까지의 수를 다시 입력 하세요 : 2
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18
```

## 8. 맛나 식당의 메뉴 주문 프로그램을 개발하고자 한다. 이를 위해 사용자에게 다음과 같은 메뉴를 보여주고 이중에서 메뉴에 대응되는 하나의 알파벳을 선택하도록 하자. 이때 메뉴에 없는 알파벳이 입력되면 ‘메뉴를 다시 입력하세요:  ’가 출력되도록 한 후 다시 입력을 받도록 하자.
![image](https://user-images.githubusercontent.com/74173976/190890195-86cffd1b-d070-4f7e-93af-b3de128ee0e2.png)

### Code : 
``` python
print('맛나 식당에 오신 것을 환영합니다. 메뉴는 다음과 같습니다.')
print('- 삼겹구이 (입력 s)')
print('- 오삼불고기 (입력 o)')
print('- 된장찌개 (입력 d)')

menu = input('메뉴를 선택하세요 (알파벳 s, o, d 입력) : ')

while True:
    if menu == 's':
        print('삼겹구이를 선택하였습니다.')
        break
        
    elif menu == 'o':
        print('오삼불고기를 입력하였습니다.')
        break
        
    elif menu == 'd':
        print('된장찌개를 입력하였습니다.')
        break
        
    else:
        menu = input('메뉴를 다시 입력하세요 : ')
```

### Console : 
```
맛나 식당에 오신 것을 환영합니다. 메뉴는 다음과 같습니다.
- 삼겹구이 (입력 s)
- 오삼불고기 (입력 o)
- 된장찌개 (입력 d)
메뉴를 선택하세요 (알파벳 s, o, d 입력) : qqqq
메뉴를 다시 입력하세요 : o
오삼불고기를 입력하였습니다.
```

## 9. 이중 for 문을 사용하여 숫자를 입력 받아 다음과 같은 삼각형을 출력하는 프로그램을 작성하시오. 이때 아래 결과와 같이 숫자 10이 입력되면 높이가 10이고 제일 마지막 줄의 별이 10개가 삼각형 형태로 나타나도록 하시오.
![image](https://user-images.githubusercontent.com/74173976/190890201-138df06f-c19c-4c1d-b38d-40e823409f37.png)

### Code : 
``` python
number = int(input('숫자를 입력하세요 : '))

for i in range(1, number + 1):
    for _ in range(number - i):
        print(' ', end= '')
    
    for _ in range(i):
        print('*', end= '')
    
    print()
```

### Console : 
```
숫자를 입력하세요 : 10
         *
        **
       ***
      ****
     *****
    ******
   *******
  ********
 *********
**********
```

## 10. 사용자로부터 숫자 1보다 크고 10보다 작은 값 n을 입력으로 받아서 다음과 같이 뱀의 몸통처럼 증가하는 이차원 배열을 출력하여라. (이 배열은 마치 뱀의 몸통처럼 ‘ㄹ’과 같은 패턴을 그리며 수가 1씩 증가하는 형태의 배열이다.) 
![image](https://user-images.githubusercontent.com/74173976/190890208-93fcee1a-f8e1-4056-9eab-f14e04dd8af1.png)
![image](https://user-images.githubusercontent.com/74173976/190890211-f45d2fb9-594d-4050-931c-36e5ca3bdcd2.png)

### Code : 
``` python
n = int(input('n을 입력하시오 : '))

for i in range(1, n + 1):
    if i % 2 == 1:
        for j in range(1, n + 1) :
            print((i - 1) * n + j, end=' ')
    else:
        for j in range(n, 0, -1):
            print((i - 1) * n + j, end=' ')
    print()
```

### Console : 
```
n을 입력하시오 : 5
1 2 3 4 5 
10 9 8 7 6 
11 12 13 14 15 
20 19 18 17 16 
21 22 23 24 25 

n을 입력하시오 : 7
1 2 3 4 5 6 7 
14 13 12 11 10 9 8 
15 16 17 18 19 20 21 
28 27 26 25 24 23 22 
29 30 31 32 33 34 35 
42 41 40 39 38 37 36 
43 44 45 46 47 48 49 
```
