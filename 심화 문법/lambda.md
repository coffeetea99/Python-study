# lambda

- `lambda`는 간단한 함수를 쉽게 선언하는 방법이다.

- `lambda 매개변수: 리턴값` 형태로 작성한다.

예제 1
```
mod = lambda x, y: x % y
print(mod(97, 7))
```

결과 1
```
6
```

- `lambda`는 주로 함수의 매개변수로 함수를 전달할 때 사용한다. 대표적으로 `map()`과 `filter()` 함수가 있다.
  - `map()`은 `list`의 element들을 매개변수 함수에 넣고 return된 값으로 새로운 `generator`를 반환한다.

    예제 2
    ```
    input_list = [3, 8, 7]

    square_map = map(lambda x : x * x, input_list)
    print(list(square_map))
    ```

    결과 2
    ```
    [9, 64, 49]
    ```

  - `filter()`는 `list`의 element들 중 매개변수 함수에 넣었을 때 return된 값이 True인 것만으로 이루어진 `generator`를 반환한다.

    예제 3
    ```
    input_list = [3, 8, 7]

    odd_filter = filter(lambda x : x % 2 == 1, input_list)
    print(list(odd_filter))
    ```

    결과 3
    ```
    [3, 7]
    ```
