**클로저**는 함수가 선언될 때의 스코프를 기억하여, 함수가 생성된 이후에도 그 스코프에 접근할 수 있는 기능을 말합니다. 비유하자면, 함수가 자신이 생성된 환경을 '기억'하는 것이라고 할 수 있습니다. 클로저는 자바스크립트의 **함수가 일급 객체라는 특성**과 **렉시컬 스코프**의 조합으로 만들어집니다. 

예시와 함께 클로저의 동작을 설명드리면 좋을 것 같습니다.   

**클로저 예시 코드**
```javascript
function outerFunction(outerVariable) {
  return function innerFunction(innerVariable) {
    console.log('Outer Variable: ' + outerVariable);
    console.log('Inner Variable: ' + innerVariable);
  };
}

const newFunction = outerFunction('outside');
newFunction('inside');
```
여기서 `innerFunction`은 `outerFunction`의 내부에 정의되어 있습니다. `innerFunction`은 자신이 생성된 스코프, 즉 `outerFunction`의 스코프를 기억하고, `outerFunction`의 호출이 완료된 이후에도 그 스코프에 접근할 수 있습니다. 그리고 이에 따라 `innerFunction`은 `outerVariable`에도 접근할 수 있습니다. 이것이 클로저가 동작하는 방식입니다.

## 클로저는 언제 활용하나요?
클로저는 변수와 함수의 접근 범위를 제어하고 특정 데이터와 상태를 유지하기 위해 자주 활용됩니다. 크게 세 가지 대표적인 사용 사례로 나누어 설명드릴 수 있습니다.  

**첫째, 데이터 은닉에 활용됩니다.** 클로저는 외부에서 접근할 수 없는 비공개 변수와 함수를 만들 수 있습니다. 이를 통해 데이터를 은닉하여 외부 접근을 막고, 데이터 무결성을 유지할 수 있습니다. 예를 들어, 특정 함수 내부에서만 접근 가능한 변수를 생성하고, 이를 조작할 수 있는 함수만 외부로 노출하여 안전하게 데이터를 관리할 수 있습니다.   

**둘째, 비동기 작업에 활용됩니다.** 클로저는 비동기 작업에서 이전의 실행 컨텍스트를 유지해야 할 때 유용합니다. 콜백 함수가 비동기적으로 실행될 때 클로저를 사용하면 함수 실행 시점의 변수를 참조할 수 있습니다. 
```js
function createLogger(name) {
  return function() {
    console.log(`Logger: ${name}`);
  };
}

const logger = createLogger('MyApp');
setTimeout(logger, 1000); // 1초 후에 'Logger: MyApp' 출력
```
위의 예시에서 클로저가 `name` 변수(`'MyApp'`)를 저장하여 1초 후에도 해당 값이 유지되어 출력됩니다. 

**셋째, 모듈 패턴을 구현하는 데 활용됩니다.** 모듈 패턴은 특정 기능을 캡슐화하고, 외부에 공개하고자 하는 부분만 선택적으로 노출하여 코드의 응집력을 높이고, 유지보수성을 향상시키는 패턴입니다. 클로저를 활용하면 필요한 함수와 데이터만 외부로 노출함으로써 모듈 패턴을 쉽게 구현할 수 있습니다.

## 📚 추가 학습 자료를 공유합니다.
- [[얄팍한 코딩사전] 클로저(Closure) - 죽은 함수의 망령](https://www.youtube.com/watch?v=WbVVKY9CDP0)