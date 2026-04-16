**Controlled Component**는 리액트 상태(`state`)를 통해 입력 값을 제어하는 컴포넌트를 말합니다.
이 방식에서는 입력 요소의 값(`value`)을 리액트 상태와 동기화하고, 사용자가 입력을 변경할 때마다 `onChange` 이벤트 핸들러를 통해 상태를 업데이트합니다. Controlled Component는 값이 리액트의 `state`로 관리되므로, 입력 시마다 값을 검증하거나, 값을 자유롭게 변경할 수 있으며, 복잡한 폼 로직을 처리하는 데 유용합니다.

**Uncontrolled Component**는 입력 값을 리액트의 상태로 관리하지 않고, DOM을 통해 입력 값을 제어하는 방식입니다. 즉, 입력 요소의 값은 DOM에서 직접 관리되며, 리액트는 이를 제어하지 않습니다. 이 방식에서는 `useRef`를 사용해 생성된 참조 객체인 `ref`를 사용하여 DOM 요소에 직접 접근하여 값을 읽거나 조작합니다. Uncontrolled Component는 리액트 상태 관리에 따른 성능 비용이 없으므로 상대적으로 간단한 폼에서 주로 사용됩니다.

## Controlled Component와 Uncontrolled Component는 각각 어떤 상황에서 사용되나요? 🤔

단순한 입력 필드가 포함된 폼에서는 입력 요소의 값을 리액트 상태로 관리할 필요성이 적으므로, Uncontrolled Component를 사용하는 것이 더 간단하고 성능이 좋습니다. 사용자가 제출 버튼을 클릭했을 때만 입력 값을 가져와도 충분한 경우를 예시로 들 수 있습니다.

반면, 값을 입력할 때마다 유효성 검증을 실시간으로 해주어야 하는 경우에는 Controlled Component를 사용해야 합니다.

## 📚 추가 학습 자료를 공유합니다.
- [[10분 테코톡] 세인의 제어 컴포넌트와 비제어 컴포넌트](https://www.youtube.com/watch?v=PBgQKK6nelo&t=253s)
