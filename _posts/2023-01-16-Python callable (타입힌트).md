# Python callable (타입힌트)

파이썬 3.9~3.11 로 넘어오면서 타입 힌트를 

내장 함수로 추가하면서  함수에 인자나 리턴 값에 타입을 지정하는것이  거의 반 필수적이다



그러다 callable 이라고 하는 이녀석을 만났다.

우리가 흔히 아는 타입이라하면 list, dict, json, str, int 이런 기본 자료형 또는 datetime 같은 오브잭트로부터 상속받은 타입들이 파이썬에는 존재하는데

```python
from typing import Callable
class GzipRoute(APIRoute):
    def get_route_handler(self) -> Callable:

```



```python
class CustomClass:
    def __init__(self, name):
        self.name = name

    def __call__(self):
        print("My name is", self.name)
```

이라는 

클래스가 있고 이 클래스에서 파이썬 던더메서드인 call을 사용하여 호출 할 수 있으면 callable 이라고 한다.

즉 말그대로 call이 가능한 타입힌트 였던것이다..



참고로 파이썬 버전마다 타입 지정에 들어가는 PEP가 추가 되고있으므로 잘 참고 바람!