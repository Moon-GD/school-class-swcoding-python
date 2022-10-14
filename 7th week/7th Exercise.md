# 모듈과 활용

## 1. 로미오와 줄리엣 두 사람이 주사위를 던져서 높은 숫자가 나오면 이기는 게임을 만들어보자. 로미오와 줄리엣의 주사위는 모두 다음과 같이 random 모듈의 randrange( )를 통해서 생성한 난수를 바탕으로 한다. 출력 결과는 다음과 같이 로미오가 이기거나, 줄리엣이 이기거나, 비기는 결과가 나와야 한다.

![image](https://user-images.githubusercontent.com/74173976/195782264-88a7a4b9-b884-441d-9ec3-83c4d2f25aac.png)

### Code

```python
# Ans.

import random
a_dice = random.randrange(1, 7)  # 로미오 주사위
b_dice = random.randrange(1, 7)  # 줄리엣 주사위

# 결과 출력
print(f'로미오의 주사위 숫자는 {a_dice} 입니다.')
print(f'줄리엣의 주사위 숫자는 {b_dice} 입니다.')

if a_dice > b_dice:
    print('로미오가 이겼습니다.')
elif a_dice < b_dice:
    print('줄리엣이 이겼습니다.')
else:
    print('로미오와 줄리엣이 비겼습니다.')
```

### Console :

```
로미오의 주사위 숫자는 1 입니다.
줄리엣의 주사위 숫자는 6 입니다.
줄리엣이 이겼습니다.
```

## 2. 랜덤 숫자 맞추기 게임 프로그램을 작성하라. 먼저 랜덤하게 1~20까지의 숫자 x를 하나 생성시키고 사용자는 숫자를 하나씩 입력하면서 생성된 숫자 x와 비교해 큰지 작은지를 보고 숫자를 맞춰가는 게임이다. 컴퓨터는 사용자가 입력한 숫자가 정답보다 큰지 작은지를 알려주어야 한다. 그리고 사용자가 시도를 할 때 마다 시도한 횟수가 n에 저장되도록 한다. 만일 입력한 숫자와 x가 일치하면 “정답입니다!”라는 메시지를 출력한다. 이때 3번 이하로 입력하여 숫자를 맞추면 “n번 만에 맞춘 당신은 천재!”, 3번 이상 6번 이하로 입력하여 숫자를 맞추면 “n번 만에 맞추셨네요. 잘 했어요^^”, 7번 이상으로 숫자를 입력하여 맞추면 “n번 만에 맞추다니 쩝쩝…”이라고 출력하라.

![image](https://user-images.githubusercontent.com/74173976/195782402-e3ad27d0-db8c-42f7-8cdf-5f1cbe43790f.png)

### Code : 

```python
# Ans.

import random as rd

target_number = rd.randrange(1, 21)  # 정답
n = 0  # 시행 횟수

while True:
    n += 1  # 시행 횟수 1 증가
    
    # 사용자 추측
    guess = int(input('1~20까지의 숫자를 입력하세요 : '))
    
    # 정답인 경우 반복문 탈출
    if guess == target_number:
        break
        
    # guess > 정답
    elif guess > target_number:
        print(f'{guess}보다 작습니다!')
        
    # guess < 정답
    else:
        print(f'{guess}보다 큽니다!')
        
# 시행 횟수가 7 이상인 경우
if n >= 7:
    print(f'{n}번 만에 맞추다니 쩝쩝...')
# 7번 내로 맞힌 경우
else:
    print(f'{n}번만에 맞추셨네요. 잘했어요 ^^')
```

### Console : 

```
1~20까지의 숫자를 입력하세요 : 10
10보다 작습니다!
1~20까지의 숫자를 입력하세요 : 5
5보다 큽니다!
1~20까지의 숫자를 입력하세요 : 7
7보다 큽니다!
1~20까지의 숫자를 입력하세요 : 8
4번만에 맞추셨네요. 잘했어요 ^^
```

## 6. 춘향이와 몽룡이는 2019년 2월 24일 발렌타인데이에 연애를 시작했다. 오늘은 두사람의 연애 시작일로부터 며칠이 경과하였는가? Datetime 모듈을 사용하고 오늘날짜 date.today()를 통해 받아와서 오늘날짜, 연애를 시작한 날짜와 경과한 날짜, 기념일을 다음과 같이 출력하여라.

![image](https://user-images.githubusercontent.com/74173976/195782545-b1332217-ad13-42b8-817e-15ec29cb8655.png)

### Code : 

```python
# Ans.

import datetime as dt

start_day = dt.datetime(2019, 2, 24)  # 연애 시작일
today = dt.datetime.today()  # 오늘 날짜

D_day = today - start_day  # 경과 날짜

# 연애 시작일을 D + 1 로 가정하기 때문에 D + x 기념일을 찾을 때는
# x - 1 을 대입해서 계산
day_100 = start_day + dt.timedelta(days = 99)
day_200 = start_day + dt.timedelta(days = 199)
day_500 = start_day + dt.timedelta(days = 499)
day_1000 = start_day + dt.timedelta(days = 999)

# 출력
print(f'오늘은 {today.year}년 {today.month}월 {today.day}일입니다')
print('춘향이와 몽룡이의 연애 시작일 : 2019년 2월 24일')
print(f'연애 시작일로부터 경과한 날짜 : {D_day.days}일')
print(f'100일 기념일 : {day_100.year}년 {day_100.month}월 {day_100.day}일')
print(f'200일 기념일 : {day_200.year}년 {day_200.month}월 {day_200.day}일')
print(f'500일 기념일 : {day_500.year}년 {day_500.month}월 {day_500.day}일')
print(f'1000일 기념일 : {day_1000.year}년 {day_1000.month}월 {day_1000.day}일')
```

### Console : 

```
오늘은 2022년 10월 14일입니다
춘향이와 몽룡이의 연애 시작일 : 2019년 2월 24일
연애 시작일로부터 경과한 날짜 : 1328일
100일 기념일 : 2019년 6월 3일
200일 기념일 : 2019년 9월 11일
500일 기념일 : 2020년 7월 7일
1000일 기념일 : 2021년 11월 19일
```

## 7. 1부터 1,000,000까지 정수의 합을 구하여 반환하는 함수 sum1to1000000()을 작성하고 함수를 100번 호출하여 함수 수행 시간을 다음과 같이 초단위로 구하여 출력하여라. (소수점 4자리까지 표현할 것.)

![image](https://user-images.githubusercontent.com/74173976/195782688-dc6047e1-f3a5-49ac-b7c9-c846c99b17b1.png)

### Code : 

```python
# Ans.

import time


def sum1to1000000():
    value = 0
    for i in range(1, 1000001):
        value += i


# 시작 시간 기록
start_time = time.time()

# 연산
for i in range(100):
    sum1to1000000()
    
# 종료 시간 기록
end_time = time.time()

print(f'1에서 1,000,000까지의 합을 100번 반복해서 구하는 시간: {(end_time - start_time):.4f}초')
```

### Console : 

```
1에서 1,000,000까지의 합을 100번 반복해서 구하는 시간: 7.3560초
```

## 9. 0부터 1,000,000까지의 임의의 정수를 10개 연속적으로 출력하는 의사난수 함수 myRand()를 생성하여라.

![image](https://user-images.githubusercontent.com/74173976/195782794-7780aefa-c8a6-44f8-9072-85f1461ac13b.png)

### Code : 

```python
# Ans.

import random as rd


def myRand():
    # 0 ~ 1,000,000 정수 리스트 생성
    numbers = [i for i in range(1000001)]
    
    # 10번 임의 정수 출력
    for _ in range(10):
        print(rd.choice(numbers))
        
        
# 함수 호출
myRand()
```

### Console : 

```
809841
455546
349677
943575
950542
152654
667952
457475
349957
602598
```
