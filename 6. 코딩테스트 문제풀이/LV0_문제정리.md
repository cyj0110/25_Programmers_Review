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
code = input()
last_four_words = code[-4:]

if last_four_words == "_eye":
    print("Ophthalmologyc")
elif last_four_words == "head":
    print("Neurosurgery")
elif last_four_words == "infl":
    print("Orthopedics")
elif last_four_words == "skin":
    print("Dermatology")
else:
    print("direct recommendation")
```
**주요 개념 및 로직**
1. 조건에 맞게 분기한다.

***

### 5번 / 심폐소생술
```Python
def solution(cpr):
    answer = []
    basic_order = ["check", "call", "pressure", "respiration", "repeat"]
    for action in cpr:
        for i in range(len(basic_order)):
            if action == basic_order[i]:
                answer.append(i+1)
    return answer
```
**주요 개념 및 로직**
1. cpr 리스트의 동작들을 action이라 하고,
2. basic_order를 하나씩 순회하기 위해 인덱스 i를 사용하여
3. basic_order의 해당 인덱스가 action과 같은 경우 i + 1(1번부터 세므로)을 answer에 붙인다.

***

### 6번 / 물 부족
```Python
def solution(storage, usage, change):
    total_usage = 0
    for i in range(len(change)):
        usage = usage * (1 + change[i] / 100)
        total_usage += usage
        if total_usage > storage:
            return i
    
    return -1
```
**주요 개념 및 로직**
1. 증감률을 제대로 usage에 저장하려면 usage = usage * (1 + change[i] / 100) 형태로 쓴다. (ex) 10 -> 1.1, -10 -> 0.9)

***

### 7번 / 
