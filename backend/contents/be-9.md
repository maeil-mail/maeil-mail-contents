`@ControllerAdvice`는 모든 컨트롤러에 대해 전역 기능을 제공하는 애너테이션입니다. 
`@ControllerAdvice`가 선언된 클래스에 `@ExceptionHandler`, `@InitBinder`, `@ModelAttribute`를 등록하면 예외 처리, 바인딩 등을 한 곳에서 처리할 수 있어, 코드의 중복을 줄이고 유지보수성을 높일 수 있습니다. 
`@ControllerAdvice`는 내부에 `@Component`가 포함되어 있어 컴포넌트 스캔 과정에서 빈으로 등록됩니다. `@RestControllerAdvice`는 내부에 `@ResponseBody`를 포함하여 `@ExceptionHandler`와 함께 사용될 때 예외 응답을 Json 형태로 내려준다는 특징이 있습니다.