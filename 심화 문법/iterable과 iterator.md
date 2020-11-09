# iterable과 iterator

- 내부에 있는 element들을 차례차례 꺼낼 수 있는 객체들을 `iterable`이라고 함   
`list`, `dictionary`, `tuple` 등이 `iterable`에 속함  

- `iterable`에서 값을 하나씩 꺼낼 수 있는 객체를 `iterator`라고 함

- `next()` 안에 `iterator`를 넣으면 다음 element로 한 칸 이동한 다음 해당 element를 반환함  
`for`문에 `iterable`을 넣으면 매 loop마다 `next()`를 호출하는 원리임  
더 이상 이동할 수 없음에도 `next()`를 호출하면 `StopIteration` exception이 발생함

예제
```
list_a = [1, 2, 3]
iter_a = iter(list_a)
print(iter_a)
print(next(iter_a))
print(next(iter_a))
print(next(iter_a))
print(next(iter_a))
```

결과
```
<list_iterator object at 0x0141A770>
1
2
3
4
Traceback (most recent call last):
  File "test.py", line 8, in <module>
    print(next(iter_a))
StopIteration
```