# LV0 문제 정리

[Python] 

## PCCE 기출문제

### 1번 / 문자 출력
```Python
message = "Let's go!"

print("3\n2\n1")
print(message)
```
**주요 개념 및 로직**
1. \n은 개행 문자

***

### 2번 / 각도 합치기
```Python
angle1 = int(input())
angle2 = int(input())

sum_angle = (angle1 + angle2) % 360
print(sum_angle)
```
**주요 개념 및 로직**
1. angle1과 angle2를 더하여 360로 나눈 나머지를 출력

***

### 3번 / 수 나누기
```Python
number = int(input())

answer = 0

while number > 0:
    answer += number % 100
    number //= 100

print(answer)
```
**주요 개념 및 로직**
1. 숫자의 자릿수와 상관없이 2자리씩 끝까지 처리하기 위해 for문을 while문으로 변경

***

### 4번 / 병과분류
```Python
