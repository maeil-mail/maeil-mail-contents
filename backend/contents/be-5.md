## @ResponseBody(or ResponseEntity\<T\>)가 있을 때와 없을 때 차이점

`@ResponseBody` 혹은 `ResponseEntity<T>` 반환을 사용한다면, 스프링은 컨트롤러에서 반환된 값을 HTTP 응답 본문에 직접 씁니다.
이때 자바 객체를 자동으로 JSON이나 XML 등의 타입으로 직렬화합니다. 만약, 없는 경우에는 스프링은 반환값을 뷰 이름으로 해석합니다.
뷰 이름으로 해석한 이후에, 뷰 리졸버를 사용해 뷰를 찾고 응답합니다.(뷰에 전달할 모델이 있다면, 이를 뷰에 전달하고 응답합니다.)

## @ResponseBody와 ResponseEntity\<T\> 반환 중 어떤 방식이 더욱 좋나요? 😀

`@ResponseBody`를 사용하는 경우, 코드를 간결하게 유지할 수 있습니다. 하지만, 상태코드와 헤더를 유연하게 변경하기는 어렵습니다. 반면, `ResponseEntity<T>` 반환의 경우 상태코드와 헤더를 유연하게 변경할 수 있으나 작성할 코드량이 증가한다는 단점이 있습니다. 팀 상황에 맞게 적절한 방법을 사용하는 것이 중요하다고 생각합니다.

## 추가 학습 자료를 공유합니다.

- [[10분 테코톡] 제제의 ResponseBody vs ResponseEntity](https://youtu.be/fCgU_VFv33M?feature=shared)
