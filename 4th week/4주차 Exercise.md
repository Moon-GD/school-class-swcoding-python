# 리스트

## 1. 다음과 같은 list1, list2가 있을 경우 이중 for 루프를 사용하여 list1과 list2의 각 원소를 곱한 후 원소의 곱셈을 결과와 함께 출력하시오.

![image](https://user-images.githubusercontent.com/74173976/191738021-e44f0a27-7b87-4104-9aa4-b94777e80e4a.png) <br>
![image](https://user-images.githubusercontent.com/74173976/191738033-dc6cd916-21b7-4aea-9dae-e72b5e85e2a6.png)

### Code

```python
list1 = [3, 5, 7]
list2 = [2, 3, 4, 5, 6]

for a in list1:
    for b in list2:
        print(f'{a} * {b} = {a * b}')
```

### Console :

```
3 * 2 = 6
3 * 3 = 9
3 * 4 = 12
3 * 5 = 15
3 * 6 = 18
5 * 2 = 10
5 * 3 = 15
5 * 4 = 20
5 * 5 = 25
5 * 6 = 30
7 * 2 = 14
7 * 3 = 21
7 * 4 = 28
7 * 5 = 35
7 * 6 = 42
```

## 2. a = [2, 3, 4, 5, 6]이 있을 경우, 이 리스트의 순서를 바꾸는 기능을 for -in 문과 pop() 메소드를 사용하여 구현하시오(reverse() 메소드를 사용하지 않고 리스트의 원소를 하나하나 순회하면서 pop() 메소드를 호출하시오).

![image](https://user-images.githubusercontent.com/74173976/191738202-44e87fd4-b742-4bdf-8521-bcb63dec28f9.png)

### Code : 

```python
a = [2, 3, 4, 5, 6]
print(f'a = {a}')
rev_a = []

for i in range(5):
    rev_a.append(a.pop())
    
print(f'rev_a = {rev_a}')
```

### Console : 

```
a = [2, 3, 4, 5, 6]
rev_a = [6, 5, 4, 3, 2]
```

## 3. n_list라는 리스트에 [10, 20, 30, 50, 60]과 같은 5개의 원소가 있다. 내장 함수 sum(n_list)를 사용하지 않고 n_list의 5개 원소의 합을 구하는 프로그램을 작성하여라.

![image](https://user-images.githubusercontent.com/74173976/191738389-9d81df43-fa34-48f8-8f77-1fc5613e89ff.png)

### Code : 

```python
n_list = [10, 20, 30, 50, 60]
ssum = 0

for n in n_list:
    ssum += n
    
print(f'리스트 원소들 : {n_list}')
print(f'리스트 원소들의 합 : {ssum}')
```

### Console : 

```
리스트 원소들 : [10, 20, 30, 50, 60]
리스트 원소들의 합 : 170
```

## 4. 임의의 정수 값을 가진 리스트 n_list에서 가장 큰 값을 구하는 프로그램을 max() 함수를 사용하지 말고 구현하여라.

![image](https://user-images.githubusercontent.com/74173976/191738467-bb217747-2487-4321-98da-4438b2552f58.png)

### Code : 

```python
n_list = [10, 20, 30, 50, 60]
big = n_list[0]

for n in n_list:
    if n > big:
        big = n
        
print(f'리스트 원소들 : {n_list}')
print(f'리스트 원소들 중 최댓값 : {big}')
```

### Console : 

```
리스트 원소들 : [10, 20, 30, 50, 60]
리스트 원소들 중 최댓값 : 60
```

## 5. s_list = ['abc', 'bcd', 'bcdefg', 'abba', 'cddc', 'opq']와 같은 문자열을 가진 리스트가 존재한다. 이 리스트에 대하여 다음과 같은 기능을 구현하여라.

### (1) min() 함수나 sort() 메소드를 사용하지 말고, s_list 내의 문자열 항목 중에서 가장 길이가 짧은 문자열과 가장 길이가 긴 문자열을 출력하여라(길이가 가장 짧거나 긴 문자열이 여러 개 있을 경우 아래 출력과 같이 제일 먼저 나타나는 문자열을 출력하여라).
![image](https://user-images.githubusercontent.com/74173976/191738629-384aa162-fbcc-4103-9125-846da6d48f76.png)

### Code : 

```python
s_list = ['abc', 'bcd', 'bcdefg', 'abba', 'cddc', 'opq']
long = short = s_list[0]

for s in s_list:
    if len(s) > len(long):
        long = s
    if len(s) < len(short):
        short = s
        
        
        
print(f'가장 길이가 짧은 문자열 : {short}')
print(f'가장 길이가 긴 문자열 : {long}')
```

### Console : 

```
가장 길이가 짧은 문자열 : abc
가장 길이가 긴 문자열 : bcdefg
```

## (2) (1)번 문제에서 ‘abc’, ‘bcd’, ‘opq’의 세 문자열의 길이가 3으로 모두 같다. 이와 같이 문자열의 길이가 같을 경우 다음과 같이 가장 길이가 짧은 문자열 3개를 모두 출력하는 프로그램을 작성하여라. sort(key = len) 함수를 사용하여 길이에 따라 정렬한 후 코드를 작성하여라.

![image](https://user-images.githubusercontent.com/74173976/191738769-890e49b7-2edb-4639-b8a8-07a22f657b9f.png)

### Code : 

```python
s_list = ['abc', 'bcd', 'bcdefg', 'abba', 'cddc', 'opq']
short = [s_list[0]]
short_len = len(s_list[0])

for s in s_list:
    if len(s) < short_len:
        short = [s]
        short_len = len(s)
        
    if len(s) == short_len:
        short.append(s)
        
        

print(f'가장 길이가 짧은 문자열 :', end=' ')        
for sh in set(short):
    print(f"'{sh}', ", end = ' ')
```

### Console : 

```
가장 길이가 짧은 문자열 : 'abc',  'opq',  'bcd', 
```


# 딕셔너리, 튜플, 집합

## 1. 튜플 데이터를 이용하면 임시변수를 사용하지 않고 두 변수의 값을 서로 교환(swap)할 수 있다. 이 교환 방법을 이용하여 다음과 같이 주어진 리스트에서 가장 큰 값 12를 제일 마지막으로 옮겨 놓는 프로그램을 작성해 보라.(제약조건: 리스트의 요소를 살펴보기 위해 사용하는 for 문의 인덱스 변수 i를 제외하고는, 주어진 리스트 이외에 다른 어떤 변수도 추가로 사용해서는 안 된다.)

![image](https://user-images.githubusercontent.com/74173976/191738908-8c198109-b60d-40ea-b7f4-2cc2de43f092.png)

### Code : 

```python
original = [5, 6, 3, 9, 2, 12, 3, 8, 7]
print(f'before : {list(original)}')

for i in original:
    if i == 12:
        del original[original.index(12)]
        
        original = tuple(original) + (12,)
        
print(f'after : {list(original)}')
```

### Console : 

```
before : [5, 6, 3, 9, 2, 12, 3, 8, 7]
after : [5, 6, 3, 9, 2, 3, 8, 7, 12]
```

## 2. 1번을 개선하여 처음에는 가장 큰 수를 제일 마지막으로 옮기고, 두번째 단계는 끝으로 옮겨진 요소를 제외한 리스트에서 가장 큰 수를 뒤에서 두 번째 위치로 옮기며, 세 번째 단계에서는 뒤의 두 요소를 제외한 나머지 리스트에서 가장 큰 수를 뒤에서 세 번째로 옮긴다. 이를 일반화 하면 k번째 단계에서는 뒤에서 k-1개 요소를 제외하고, 남은 리스트에서 가장 큰 요소를 뒤에서부터 k번째 위치에 옮겨 놓는 일을 처리할 리스트가 남지 않을 때까지 반복하면 큰 수부터 차례로 뒤에 쌓이게 된다. 이를 거품(bubble) 정렬이라고 한다. 이를 구현해보라.

![image](https://user-images.githubusercontent.com/74173976/191738993-72156f72-1930-491d-a4f2-442deb9ea161.png)

### Code : 

```python
original = [5, 6, 3, 9, 2, 12, 3, 8, 7]
print(f'주어진 리스트는 = {original}')

for i in range(0, len(original)):
    for j in range(i + 1, len(original)):
        if original[i] > original[j]:
            original[i], original[j] = original[j], original[i]
            
print(f'정렬된 결과는 = {original}')
```

### Console : 

```
주어진 리스트는 = [5, 6, 3, 9, 2, 12, 3, 8, 7]
정렬된 결과는 = [2, 3, 3, 5, 6, 7, 8, 9, 12]
```

## 3. 어떤 문자열을 뒤집었을 때에 원래의 문자열과 같은 것을 회문(palindrome)이라고 한다. 예를 들어 ‘mom’은 문자열을 뒤집어도 ‘mom’이 되므로 회문이다. 사용자로부터 임의의 문자열이나 문장을 입력받아서 이 문자열이 회문인지 아닌지 검사하는 코드를 작성하라. 입력으로는 다음과 같은 영문자를 입력으로 받으며, 대문자와 소문자, 공백, 마침표 등은 무시하도록 구현하라.

![image](https://user-images.githubusercontent.com/74173976/191739072-de0486fd-08b8-4195-b332-7de2d40b37be.png)
![image](https://user-images.githubusercontent.com/74173976/191739079-c7cdd022-137e-4b16-b6d1-441b5f98b3e7.png)
![image](https://user-images.githubusercontent.com/74173976/191739083-a2110b07-b799-4222-af1c-be9f452a76f7.png)

### Code : 

```python
string = input('문자열을 입력하시오 : ').lower()
string = string.replace(' ', '')
string = string.replace('.', '')

if string == string[::-1]:
    print('회문입니다.')
else:
    print('회문이 아닙니다.')
```

### Console : 

```
문자열을 입력하시오 : racecar
회문입니다.

문자열을 입력하시오 : abv
회문이 아닙니다.

문자열을 입력하시오 : A nut for a jar of tuna...
회문입니다.
```

## 6. 주어진 튜플은 10일 동안 일일 매장 매출을 기록한 것이다. 매출이 전날보다 감소한 날이 며칠인지 출력하는 코드를 작성하라.

![image](https://user-images.githubusercontent.com/74173976/191739216-32ecb28e-29f6-4559-9393-61406ca43787.png)

### Code : 

```python
sales = (100, 121, 120, 130, 140, 120, 122, 123, 190, 125)

old_sale = 0
count = 0

for sale in sales:
    if old_sale > sale:
        count += 1
        
    old_sale = sale
    
print(f'지난 {len(sales)}일 동안 전일대비 매출이 감소한 날은 {count}일입니다.')
```

### Console : 

```
지난 10일 동안 전일대비 매출이 감소한 날은 3일입니다.
```

## 7. 중복 요소를 가진 튜플 tup에서 중복 요소가 하나만 나타나도록 수정한 튜플을 생성하라

![image](https://user-images.githubusercontent.com/74173976/191739312-a83559b5-d12b-4c61-b5ea-dfdbd9100620.png)

### Code : 

```python
given_tuple = (1, 2, 5, 4, 3, 1, 1, 1, 3, 2, 1, 5, 7, 7)
print(f'주어진 튜플 : {given_tuple}')

given_tuple = tuple(set(given_tuple))
print(f'중복 제거 튜플 : {given_tuple}')
```

### Console : 

```
주어진 튜플 : (1, 2, 5, 4, 3, 1, 1, 1, 3, 2, 1, 5, 7, 7)
중복 제거 튜플 : (1, 2, 3, 4, 5, 7)
```
