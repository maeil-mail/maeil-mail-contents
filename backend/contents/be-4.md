## @ExceptionHandler란?

`@ExceptionHandler` 애너테이션은 Spring MVC에서 컨트롤러(`@Controller`)나 전역 예외 처리를 위한 `@ControllerAdvice` 클래스의 메서드에서 발생하는 예외를 처리하는 데 사용되는데요. 이 애너테이션은 특정 예외를 처리하는 메서드를 지정하거나 메서드의 파라미터로 처리할 예외를 설정할 수 있습니다.

## 어떤 방식으로 동작하나요? 🤔
Spring MVC 애플리케이션에서 예외가 발생하면, DispatcherServlet이 적절한 HandlerExceptionResolver를 찾아 예외를 처리합니다. Spring에 기본적으로 등록된 HandlerExceptionResolver는 세 가지가 있으며, 각 리졸버는 우선순위에 따라 예외를 처리합니다. 그 중 ExceptionHandlerExceptionResolver가 가장 먼저 동작하며, 발생한 예외가 `@ExceptionHandler`에 등록되어 있는지 확인합니다. 만약 처리할 수 없는 예외라면 다음 리졸버로 넘어갑니다. ExceptionHandlerExceptionResolver의 특징은 예외가 WAS로 던져지지 않고 직접 처리된다는 것입니다.

이렇게 함으로써 예외가 발생했을 때 적절한 방법으로 처리되어 사용자에게 친화적인 에러 메시지를 제공하거나 로깅 등의 추가 작업을 수행할 수 있습니다.