# global

- 파이썬은 global variable을 함수 내에서 읽는 것만 가능하고 수정하는 것은 기본적으로 불가능하다. 이를 가능하게 하는 것이 `global` 키워드이다. 

예제1
```
stamp = 0

def add():
    stamp += 1
    print(stamp)

add()
add()
```

결과1
```
Traceback (most recent call last):
  File "test.py", line 7, in <module>
    add()
  File "test.py", line 4, in add
    stamp += 1
UnboundLocalError: local variable 'stamp' referenced before assignment
```

예제2
```
stamp = 0

def add():
    global stamp
    stamp += 1
    print(stamp)

add()
add()
```

결과2
```
1
2
```

- global 키워드가 없는데 값을 변경하려고 할 경우 아래와 같이 의도치 않은 상황이 벌어질 수 있다. 아래 코드에서 global variable x와 local variable x는 별개의 변수이다.

예제3
```
x = 10

def func():
    x = 20
    print(x)

func()
print(x)
```

결과3
```
20
10
```
