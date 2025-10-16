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

### 7번 / 버스
```Python
def func1(num):
    if 0 > num:
        return 0
    else:
        return num

def func2(num):
    if num > 0:
        return 0
    else:
        return num

def func3(station):
    num = 0
    for people in station:
        if people == "Off":
            num += 1
    return num

def func4(station):
    num = 0
    for people in station:
        if people == "On":
            num += 1
    return num


def solution(seat, passengers):
    num_passenger = 0
    for station in passengers:
        num_passenger += func4(station)
        num_passenger -= func3(station)
    answer = func1(seat - num_passenger)
    return answer
```
**주요 개념 및 로직**
1. station이 On일 때는 승객이 탑승한 것이므로 num_passenger에 func4 함수를 호출한 결과를 더하여 저장한다.
2. station이 Off일 때는 승객이 하차한 것이므로 num_pasenger에 func3 함수를 호출한 결과를 빼 저장한다.
3. 남은 자리 수는 전체 자리(seat)에서 num_passenger를 뺀 값인데, 음수가 되는 것을 방지하기 위해 func1 함수로 값을 보내어 전달받은 값을 answer에 할당한다.

***

### 7번 / 닉네임 규칙
```Python
def solution(nickname):
    answer = ""
    for letter in nickname:
        if letter == "l":
            answer += "I"
        elif letter == "w":
            answer += "vv"
        elif letter == "W":
            answer += "VV"
        elif letter == "O":
            answer += "0"
        else:
            answer += letter
    while len(answer) < 4:
        answer += "o"
    if len(answer) > 8:
        answer = answer[:8]
    return answer
```
**주요 개념 및 로직**
1. 기존의 if len(answer) < 3을 while len(answer) < 4로 바꾼다.
2. answer의 길이가 4 미만인 동안은 계속 "o"를 붙일 수 있어야 한다.

***

### 1번 / 출력
```Python
string_msg = "Spring is beginning"
int_val = 3
string_val = "3"

print(string_msg)
print(int_val + 10)
print(string_val + "10")
```
**주요 개념 및 로직**
1. String은 큰따옴표로, 정수는 큰따옴표 없이 선언한다.

***

### 2번 / 피타고라스의 정리
```Python
a = int(input())
c = int(input())

b_square = c*c - a*a
print(b_square)
```
**주요 개념 및 로직**
1. a와 c를 받고, c의 제곱에서 a의 제곱을 뺀다.

***

### 3번 / 나이 계산
```Python
