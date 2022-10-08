# 리스트

## 1. 사용자로부터 임의의 수를 연속적으로 입력받도록 하시오. 이 수들에 대한 평균값, 최댓값, 최솟값을 반환하는 함수 mean_of_n(nums), max_of_n(nums), min_of_n(nums)을 구현하여 다음과 같이 출력하여라.

![image](https://user-images.githubusercontent.com/74173976/194696485-c6d8ea5b-aea1-4c5f-bb2a-c0b390c568ea.png)

### Code

```python
# Ans.

def mean_of_n(nums):
    print(f'평균값은 {sum(nums) / len(nums) :.1f}')
    
    
def max_of_n(nums):
    print(f'최댓값은 {max(nums)}')
    

def min_of_n(nums):
    print(f'최솟값은 {min(nums)}')
    

def solve():
    numbers = list(map(int, input('정수를 여러 개 입력하시오 : ').split()))
    mean_of_n(numbers)
    max_of_n(numbers)
    min_of_n(numbers)
    
    
solve()
```

### Console :

```
정수를 여러 개 입력하시오 :  3 45 32 5 7 8 4 44 5 90 17
평균값은 23.6
최댓값은 90
최솟값은 3
```

## 2. 

![image](https://user-images.githubusercontent.com/74173976/194696494-3783f774-a8ad-45b8-817f-b5842c19dca6.png)


### Code : 

```python
# Ans.

def area(x1, y1, x2, y2):
    len01 = y2 - y1
    len02 = x2 - x1
    
    print(f'직각삼각형의 면적은 : {len01 * len02 / 2 :.1f}')
    
    
x1 = int(input('x1 좌표를 입력하시오 : '))
y1 = int(input('y1 좌표를 입력하시오 : '))
x2 = int(input('x2 좌표를 입력하시오 : '))
y2 = int(input('y2 좌표를 입력하시오 : '))

area(x1, y1, x2, y2)
```

### Console : 

```
x1 좌표를 입력하시오 : 0
y1 좌표를 입력하시오 : 0
x2 좌표를 입력하시오 : 3
y2 좌표를 입력하시오 : 4
직각삼각형의 면적은 : 6.0
```

## 3. n_list라는 리스트에 [10, 20, 30, 50, 60]과 같은 5개의 원소가 있다. 내장 함수 sum(n_list)를 사용하지 않고 n_list의 5개 원소의 합을 구하는 프로그램을 작성하여라.

![image](https://user-images.githubusercontent.com/74173976/194696506-08c94170-d275-443e-9da4-f8681bc67ed9.png)


### Code : 

```python
# Ans.

numbers = list(map(int, input('쉼표로 구분된 정수를 여러 개 입력하시오 : ').split(',')))
print(f'입력된 정수의 리스트 : {numbers}')
numbers.sort()
print(f'정렬된 정수의 리스트 : {numbers}')
```

### Console : 

```
쉼표로 구분된 정수를 여러 개 입력하시오 : 56,67,89,34,24,300,99
입력된 정수의 리스트 : [56, 67, 89, 34, 24, 300, 99]
정렬된 정수의 리스트 : [24, 34, 56, 67, 89, 99, 300]
```

## 4. 임의의 정수 값을 가진 리스트 n_list에서 가장 큰 값을 구하는 프로그램을 max() 함수를 사용하지 말고 구현하여라.

![image](https://user-images.githubusercontent.com/74173976/194696517-b000f912-2699-4e2f-a1c9-084df44b5826.png)


### Code : 

```python
# Ans.

a = int(input('범위의 시작 정수 : '))
b = int(input('범위의 마지막 정수 : '))

flag = False
target_number = 0

while not flag:
    target_number += b
    
    for i in range(a, b + 1):
        if target_number % i != 0:
            break
            
        if i == b:
            flag = True
        
    
print(f'{a}에서 {b}까지의 정수들의 최소 공배수는 : {target_number}')
```

### Console : 

```
범위의 시작 정수 : 2
범위의 마지막 정수 : 4
2에서 4까지의 정수들의 최소 공배수는 : 12

범위의 시작 정수 : 3
범위의 마지막 정수 : 5
3에서 5까지의 정수들의 최소 공배수는 : 60
```

## 5. s_list = ['abc', 'bcd', 'bcdefg', 'abba', 'cddc', 'opq']와 같은 문자열을 가진 리스트가 존재한다. 이 리스트에 대하여 다음과 같은 기능을 구현하여라.

![image](https://user-images.githubusercontent.com/74173976/194696523-348ec123-38b8-4470-8e32-c4c4e00d82b6.png)

### Code : 

```python
# Ans.

float_number = float(input('1보다 작고 0보다 큰 소수를 입력하세요 : '))

target_number = round(1 / float_number)
print(f'가장 가까운 단위 분수는 1/{target_number}이며, 이 값은 {1 / target_number}입니다.')
```

### Console : 

```
1보다 작고 0보다 큰 소수를 입력하세요 : 0.0732
가장 가까운 단위 분수는 1/14이며, 이 값은 0.07142857142857142입니다.

1보다 작고 0보다 큰 소수를 입력하세요 : 0.0000000000000000000034224
가장 가까운 단위 분수는 1/292192613370733985792이며, 이 값은 3.4224e-21입니다.
```
