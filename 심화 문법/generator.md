# generator

- `generator`는 `iterator`를 직접 만들 때 사용하는 코드이다.

- 함수 내부에 `return` 대신 `yield`를 사용하면 `generator` 함수가 된다.

- `generator` 함수를 호출하면 함수 내부의 코드들이 실행되는 것이 아니라 `generator` 객체를 return한다. 함수 내부의 코드를 실행하려면 `generator` 객체를 `next()`에 넣어 실행해야 하며, 이때 `yield`를 만나면 `yield` 키워드 뒤의 값을 반환하고 실행을 일시정지한다. 다음에 `next()`를 실행하면 일시정지한 지점에서부터 시작한다.

- `next()`를 실행했는ㄷ데 `yield`를 만나지 못하면 함수가 끝나고 `StopIteration` Exception이 발생한다.

예제
```
def gen_func():
    print("1번 실행되었습니다")
    yield "1차 반환"
    print("2번 실행되었습니다")
    yield "2차 반환"
    print("3번 실행되었습니다")
    yield "3차 반환"

gen_obj = gen_func()
print("시작")

ret = next(gen_obj)
print(ret)

ret = next(gen_obj)
print(ret)

ret = next(gen_obj)
print(ret)

next(gen_obj)
```

결과
```
시작
1번 실행되었습니다
1차 반환
2번 실행되었습니다
2차 반환
3번 실행되었습니다
3차 반환
Traceback (most recent call last):
  File "test.py", line 21, in <module>
    next(gen_obj)
StopIteration
```