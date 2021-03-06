---
title: "Python 문법 정리_updating"
date: 2020-10-03 14:26:28 -1400
categories: python
---
# Python 기본 문법

Python의 기본 문법을 정리해 보겠습니다.

>## 슬라이싱


```python
jumin = "990120-1234567"

print("성별 : " + jumin[7]) # 1
print("연 : " + jumin[0:2]) # 99
print("월 : " + jumin[2:4]) # 01
print("일 : " + jumin[4:6])

print("생년월일 : " + jumin[:6]) # 990120
print("뒤 7자리 : " + jumin[7:]) # 1234567
print("뒤 7자리 (뒤에서부터): " + jumin[-8:]) #-1234567
```
***

>## 문자열 처리 함수

```python
python = "Python is Amazing"

print(python.lower()) # python is amazing
print(python.upper()) # PYTHON IS AMAZING
print(python[0].isupper()) # True
print(len(python)) # 17
print(python.replace("Python", "Java")) # Java is Amazing

index = python.index("n")
print(index) # 5

# 두번째 n 나오는 index
index = python.index("n", index + 1)
print(index) # 15

# -1 , index는 값 없으면 에러 발생.
print(python.find("Java"))

# 문자열에 n이 몇개 있는지 count.
print(python.count("n")) # 2
```
***

>## 문자열 포멧

```python
# 정수형 처리
print("나는 %d살입니다." %20)
# 문자열 처리
print("나는 %s을 좋아해요" %"파이썬")
# char 처리
print("Apple은 %c로 시작해요" % "A")
# 괄호로 2개 이상의 문자열 처리
print("나는 %s색과 %s색을 좋아해요" %("파란", "빨간"))

print("나는 {}살 입니다." .format(20))
print("나는 {}색과 {}색을 좋아해요" .format("파란", "빨간")) # 나는 파란색과 빨간색을 좋아해요
print("나는 {1}색과 {0}색을 좋아해요" .format("파란", "빨간")) # 나는 빨간색과 파란색을 좋아해요

print("나는 {age}살이며, {color}색을 좋아해요" .format(age = 20, color="빨간")) # 나는 20살이며, 빨간색을 좋아해요

#문자열 앞에 f를 넣으면, 변수로 선언한 문자열을 중간에 넣을 수 있다.
age = 20
color = "빨간"
print(f"나는 {age}살이며, {color}색을 좋아해요.")
```
***

>## 탈출 문자

```python
print("백문이 불여일견\n백견이 불여일타") # 백문이 불여일견
                                  # 백견이 불여일타
# 문자열 중간에 \로 "" 문자열 넣기.
print("저는 \"나도코딩\"입니다.") # 저는 "나도코딩"입니다.

# \\ 는 문자열 내에서 \로 변환 된다.
print("C:\\Library\\Frameworks") # C:\Library\Frameworks

# \r은 커서를 맨 앞으로 이동 시킨다.
print("Red Apple\rPine") # PineApple

# \b은 백스프페이스와 동일한 동작을 한다.
print("Redd\bApple") # RedApple

# \t 탭
print("Red\tApple")
```
***

>## 리스트 (list)

```python
subway = ["유재석", "조세호", "박명수"]
print(subway)

# 리스트 마지막에 item 추가
subway.append("하하") # ['유재석', '조세호', '박명수', '하하']
print(subway)

# 리스트 중간에 item 추가
subway.insert(1, "정형돈") # ['유재석', '정형돈', '조세호', '박명수', '하하']
print(subway)

# 리스트의 마자막 item 값 얻기.
print(subway.pop()) # 하하

# 정렬
num_list = [5,2,4,3,1]
num_list.sort()
print(num_list) # [1, 2, 3, 4, 5]

# 정렬(반대)
num_list.reverse()
print(num_list) # [5, 4, 3, 2, 1]

# 삭제
num_list.clear()
print(num_list) # []

# 리스트 확장 (다른 형이 한 리스트에 담김)
mix_list = ["조세호", 20, True]
num_list.extend(mix_list)
print(num_list)
```
***

>## 사전 (dictionary)

```python
cabinet = {3:"유재석", 100:"김태호"}
print(cabinet[3]) # 유재석
print(cabinet[100]) # 김태호

# Dictionary에서 []이용 하여, 없는 key 값으로 가져오면 프로그램 종료 됨.
# get을 이용 하면, 종료 되지 않고, None 반환 받음.
print(cabinet.get(5)) # None
print(cabinet.get(5), "대체 문자") # 대체 문자

print(3 in cabinet) # True
print(5 in cabinet) # False

# 사전에 item 추가
cabinet[10] = "조세호"
print(cabinet) # {3: '유재석', 100: '김태호', 10: '조세호'}

# 사전에 값은 key로 item 추가하면, 값 변경 된다.
cabinet[3] = "김종국"
print(cabinet) # {3: '김종국', 100: '김태호', 10: '조세호'}

# 사전에서 item 제거
del cabinet[3]
print(cabinet) # {100: '김태호', 10: '조세호'}

# 사전에서 key 값들만 출력
print(cabinet.keys()) # dict_keys([100, 10])

# 사전에서 value 값들만 출력
print(cabinet.values())

# 사전에서 key, value 쌍으로 출력
print(cabinet.items()) # dict_items([(100, '김태호'), (10, '조세호')])

# 사전 item 삭제
cabinet.clear()
print(cabinet) # {}
```
***

>## 튜플 (tuple)

* 리스트와 다르게 내용을 변경 및 추가 할 수 없다.
* 속도가 리스트 보다 빠르다.
* 변경 되지 않는 목록에 사용 한다.

```
menu = ("돈까스", "치즈까스")
print(menu[0]) # 돈까스
print(menu[1]) # 치즈까스

(name, age, hobby) = ("김종국", 20, "코딩")
print(name, age, hobby)
```
***

>## 세트 (set)

* 중복이 되지 않음.
* 순서가 없음.

```python
my_set = {1,2,3,3,3}
print(my_set) # {1, 2, 3}

java = {"유재석", "김태호", "양세형"}
python = set(["유재석", "박명수"])

# java 와 python의 교집합
print(java & python) # {'유재석'}
print(java.intersection(python)) # {'유재석'}

# java 와 python의 합집합
print(java | python) # {'유재석', '김태호', '박명수', '양세형'}
print(java.union(python)) # {'유재석', '김태호', '박명수', '양세형'}

# java 와 python의 차집합
print(java - python) # {'양세형', '김태호'}
print(java.difference(python)) # {'양세형', '김태호'}

# 세트에 item 추가
python.add("김태호")
print(python) # {'김태호', '박명수', '유재석'}

# 세트에 item 제거
java.remove("김태호")
print(java) # {'유재석', '양세형'}
```
***

>## 자료구조의 변경

```python
# set 생성
menu = {"커피", "우유", "주스"}
print(menu, type(menu)) # {'커피', '주스', '우유'} <class 'set'>

# list로 변경
menu = list(menu)
print(menu, type(menu)) # ['커피', '우유', '주스'] <class 'list'>

# tuple로 변경
menu = tuple(menu)
print(menu, type(menu)) # ('주스', '우유', '커피') <class 'tuple'>
```
***

>## if

```python
# input 메서드로 문자열 입력 받을 수 있음.

temp = int(input("기온은 어때요?"))
if 30 <= temp:
    print("너무 더워요. 나가지 마세요.")
elif 10 <= temp and temp < 30:
    print("괜찮은 날씨에요.")
elif 0 <= temp and temp <10:
    print("외투를 챙기세요.")
else:
    print("너무 추워요. 나가지 마세요.")
```
***

>## for

```python
# range를 이용한 for문 출력
for waiting_no in range(1, 3):
    print("대기번호 : {0}" .format(waiting_no)) # 대기번호 : 1
                                              # 대기번호 : 2

# list 를 이용한 for 문 출력
startbucks = ["아이언맨", "토르"]
for custom in startbucks:
    print("{0}, 커피가 준비 됨." .format(custom)) # 아이언맨, 커피가 준비 됨.
                                               # 토르, 커피가 준비 됨.
```
***

>## while

```python
customer = "토르"
index = 2
while index >= 1:
    print("{0}, 커피 준비 까지, {1} 분 남음" .format(customer, index))
    index -= 1
    if index == 0:
        print("커피 나옴.")
```
***

>## continue & break

조건에 해당 되면, 아래 행을 실행 시키지 않는다.

```python
absent = [2, 3]
no_book = [4]
for student in range(1, 5):
    if student in absent:
        continue
    elif student in no_book:
        print("수업 끝! {}는 교무실로 따라와" .format(student)) # 수업 끝! 4는 교무실로 따라와
        break
    print("{}, 책을 읽어봐" .format(student)) # 1, 책을 읽어봐
```
***

>## 한줄 for 문

```python
students = [1,2,3,4,5]
print(students) # [1, 2, 3, 4, 5]
students = [i+100 for i in students]
print(students) # [101, 102, 103, 104, 105]
```
***

>## 함수

def keyword로 함수 생성 한다.
```python
def open_account():
    print("새로운 계좌가 생성 되었습니다.")

open_account()
```
***
>## 전달값과 반환값

```python
def deposit(balance, money):
    print("입금이 완료. 잔액은 {} 원입니다." .format(balance + money))
    return balance + money

def withdraw(blance, money):
    if balance > money: # 잔액이 출금보다 많으면
        print("출금이 완료. 잔액은 {} 원입니다.". format(balance - money))
        return balance - money
    else:
        print(print("출금이 완료 되지 않음. 잔액은 {} 원입니다.". format(balance)))
        return balance

def withdraw_night(balance, money):
    commission = 100 # 수수료 100원
    return commission, balance - money - commission # 튜플 형식 return 값

balance = 0 # 잔액
balance = deposit(balance, 1000) # 입금이 완료. 잔액은 1000 원입니다.
balance = withdraw(balance, 500) # 출금이 완료. 잔액은 500 원입니다.

commission, balance = withdraw_night(balance, 300)
print("수수료 {0} 원이며, 잔액은 {1} 원입니다." .format(commission, balance)) # 수수료 100 원이며, 잔액은 100 원입니다.
```
***

>## 기본값

파라미터(parameter) 값에 =로 값을 정의하면, 기본값이 되며, 오버로딩 처리가 자동으로 된다.
```python
def profile(name, age=17, main_lang="파이썬"):
    print("이름: {0} 나이: {1} 주 언어: {2}" .format(name, age, main_lang))

profile("유재석", 20, "파이썬") # 이름: 유재석 나이: 20 주 언어: 파이썬이름: 유재석 나이: 20 주 언어: 파이썬
profile("김태호") # 이름: 김태호 나이: 17 주 언어: 파이썬
```
***

>## 키워드값

아규먼트(argument) 값에 =로 값을 정의하면, 오버로딩 규칙에 맞지 않아도, key 값으로 매칭 가능하다.
```python
def profile(name, age, main_lang):
    print(name, age, main_lang)

profile(name="유재석", main_lang="파이썬", age=20) # 유재석 20 파이썬
profile(main_lang="자바", age=25, name="김태호") # 김태호 25 자바
```
***

>## 가변인자

파라미터 특정 값에 *을 앞에 붙이면, 가변적으로 오버로딩 된다.
```python
def profile(name, age, *language):
    print("이름:{0} 나이:{1}" .format(name, age), end=" ")
    for lang in language:
        print(lang, end=" ")
    print()

profile("유재석", 20, "python", "java", "C") # 유재석 20 파이썬
profile("김태호", 25, "android")
```
***

>## 지역변수와 전역변수

```python
gun = 10

def checkpoint(soldiers): # 경계근무
    global gun # 전역 공간에 있는 gun 사용
    gun = gun - soldiers
    print("[함수 내 남은 총] : {0}" .format(gun)) # 8

# 전역 변수를 지역 변수화 하여 사용하는 것이 변수 관리 측면에서 더 좋다.
def checkpoint_ret(gun, soldiers):
    gun = gun - soldiers
    return gun

print("전체 총 : {0}" .format(gun)) # 10
checkpoint(2) # 2명 경계 근무 나감
print("남은 총 : {0}" .format(gun)) # 8
```

***

>## 표준 입출력

```python
#sep keyword 사용하면 ,를 대체하여 값을 변환 한다.
#end keyword 사용하면, 개행(개행을 해당 값으로 변경)하지 않는다.
print("Python", "Java", sep=",", end="?") # Python,Java?무엇이 더 재밌나요?
print("무엇이 더 재밌나요?")

# 문자열 정렬
scores = {"수학":0, "영어":50, "코딩":100}
for subject, score in scores.items():
    # rjust 키워드는, 우측정렬 및 확보 공간(4)을 의미한다.
    print(subject, str(score).rjust(4), sep=":")
    # 수학:   0
    # 영어:  50
    # 코딩: 100

# zfill keyword 사용하면, 빈 공간을 0으로 체운다.
for num in range(1, 2):
    print("대기번호 : " + str(num).zfill(3)) # 대기번호 : 001

# input은 숫자를 입력 받아도 type은 str이 된다.
answer = input("입력 하세요 : ") # 숫자 입력
print("입력 값은 " + answer + "입니다.") # <class 'str'>

```
***

>## 다양한 출력 포멧

```python

```

***
# 예시

```python

```

# source
https://www.youtube.com/watch?v=kWiCuklohdY&t=153s
