# exception handling

- 프로그래밍 언어의 오류에는 두 가지가 있다.
  - 프로그램 실행 전에 발생하는 오류: `syntax error`
  - 프로그램 실행 중에 발생하는 오류: `runtime error` == `exception`

- 파이썬에서 exception을 처리하는 try 구문은 다음 키워드들로 만들 수 있다.
  - `try`: 예외가 발생할 가능성이 있는 코드를 적는다.
  - `except`: 예외가 발생했을 때 실행할 코드를 적는다.
    - `except (Exception 객체)`라고 적으면 해당하는 종류의 Exception만 받아서 처리한다.
    - `except (Exception 객체) as (객체명)`이라고 적으면 해당 종류의 Exception을 원하는 객체명으로 받아 사용할 수 있다.
    - `except Exception`이라고 적으면 모든 Exception을 받는다. 따라서 이 구문은 마지막에 적어 두는 것이 좋다.
  - `else`: 예외가 발생하지 않았을 때 실행할 코드를 적는다.
  - `finally`:예외 발생 여부와 상관없이 무조건 실행할 코드를 적는다. javascript와 같이 finally에 있는 코드는 루프를 탈출해도, 함수 return을 완료해도 실행된다.

- try 구문은 아래 두 규칙을 지켜야 한다.
  - `try`는 `except` 또는 `finally`가 따라와야 한다.
  - `else`가 있으려면 `except`가 앞에 있어야 한다.

```
try:
    pass
except ValueError as v:
    print("ValueError occurred: ", v)
except IndexError as i:
    print("IndexError occurred: ", i)
except Exception as e:
    print("Some error occurred: ", e)
else:
    print("Task complete")
finally:
    print("End of program")
```

- `raise`를 사용하면 에러를 발생시킬 수 있다. `raise (Exception 객체)` 형태로 사용하면 된다. 직접 예외 클래스를 만들어 사용해도 된다.