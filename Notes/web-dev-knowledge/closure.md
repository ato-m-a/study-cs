# 클로저 (Closure)

클로저란, 함수가 속한 렉시컬 스코프(선언부, 정적 스코프) 밖에서 실행될 때도 그 스코프에 접근할 수 있게 하는 기능입니다.

```javascript
const outer = () => {
  const outerVariable = 2;

  const inner = () => {
    console.log(outerVariable);
  }

  return inner;
}

const func = outer();
func(); // 2
```

여기서 가비지 컬렉터가 `outer()` 의 참조를 없앨 것 같지만 내부 함수인 `inner()` 가 해당 스코프의 변수인 `outerVariable` 을 참조하고 있기 때문에
없애지 않습니다.

따라서, 스코프 외부에서 `inner()` 가 실행되어도 해당 스코프를 기억하기 때문에 `2` 를 출력하게 됩니다.

즉, 여기서 클로저는 `inner()` 가 되며 `func` 에 담겨 밖에서도 실행되고 렉시컬 스코프를 기억하게 됩니다.

<br>

## 예제

클로저를 활용해 본 예제로, 상태를 내부적으로 유지하면서 메소드 체이닝을 할 수 있는 함수를 구현해 보았습니다.

```javascript
// baseUrl을 인자로 받아, append 메소드를 통해 쿼리 파라미터를 추가하고 compose 메소드를 통해 완성된 url을 반환하는 함수 입니다.
const uriBuilder = (baseUrl) => {
  const link = baseUrl.includes('?') ? '&' : '?';

  const listed = [];
  const queryParams = new URLSearchParams();

  const methods = {
    append: (key, value) => {
      if (listed.includes(key)) return methods;

      listed.push(key);
      queryParams.append(key, value);
      return methods;
    },
    compose: () => {
      return baseUrl + link + queryParams.toString();
    }
  }

  return methods;
}

const uriInstance = uriBuilder('https://ato-m-a.me');

uriInstance.append('name', 'hong');

if (condition) {
  uriInstance.append('age', 29)
    .append('gender', 'male');
}

const url = uriInstance.compose(); // https://ato-m-a.me?name=hong&age=29&gender=mail
```

위의 기능을 함수로 구현하면서, 내부 상태를 유지하며 메소드 체이닝을 할 수 있게 하기 위해 클로저를 활용하였습니다.

`append` 메소드는 새로운 쿼리 파라미터를 추가한 후 자신이 속한 `methods` 객체를 반환함으로써 체이닝을 지속할 수 있게 합니다.

또한, `uriBuilder` 함수의 `link`, `listed`, `queryParams` 와 같은 내부 변수는 `append` 메소드가 속한 `methods` 객체의 렉시컬 스코프에
접근할 수 있기 때문에, `append` 메소드가 실행될 때마다 해당 변수들의 상태를 유지할 수 있습니다.

