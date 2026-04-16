## Filter

`Filter`는 요청 및 응답의 전처리와 후처리를 수행하고 서블릿 컨테이너에 의해 실행되는 Java 클래스입니다. 주로 요청 로깅, 인증, 인코딩 설정, CORS 처리, 캐싱, 압축 등의 공통 기능을 구현하는 데 사용됩니다.

### 특징

1. `Filter`는 서블릿 컨테이너(예: Tomcat) 수준에서 동작합니다. 모든 요청이 서블릿으로 전달되기 전에 `Filter`를 거칩니다.
2. 생명 주기: Filter는 `doFilter` 메서드를 통해 요청 및 응답을 처리합니다. FilterChain을 통해 다음 필터 또는 최종 서블릿으로 요청을 전달합니다.
3. 순서: `web.xml`이나 `@WebFilter` 애노테이션을 통해 설정할 수 있으며, 필터의 순서는 설정 파일에서 정의합니다.

## Interceptor

Interceptor는 특정 핸들러 메서드 실행 전후에 공통 기능을 구현합니다. 주로 요청 로깅, 인증, 권한 검사, 세션 검사, 성능 모니터링 등을 수행하는 데 사용됩니다.

### 특징

1. Interceptor는 Spring MVC의 핸들러 수준에서 동작합니다. Dispatcher Servlet이 컨트롤러를 호출하기 전에 Interceptor를 거칩니다.
2. 생명 주기
    - `preHandle` 메서드: 컨트롤러의 메서드가 호출되기 전에 실행됩니다.
    - `postHandle` 메서드: 컨트롤러의 메서드가 실행된 후, 뷰가 렌더링되기 전에 실행됩니다.
    - `afterCompletion` 메서드: 뷰가 렌더링된 후 실행됩니다.
3. 순서: `WebMvcConfigurer`를 구현한 클래스에서 `addInterceptors` 메서드를 사용하여 설정합니다. 인터셉터의 순서는 등록 순서에 따릅니다.

## (Servlet) Filter vs (Handler) Interceptor

Characteristics | (Servlet) Filter | (Handler) Interceptor
-- | -- | --
Definition | HTTP 요청이나 응답이 수신될 때마다 서블릿 컨테이너는 Java 클래스 Filter를 실행합니다. | 인터셉터는 Spring Context에 대한 액세스를 통한 사용자 정의 사후 처리와 핸들러 실행을 금지할 가능성이 있는 사용자 정의 사전 처리만 허용합니다.
Interface | jakarta.servlet.Filter | HandlerInterceptor
실행 순서 | 서블릿 이전/이후, 서블릿 필터 | 컨트롤러 이전이나 이후에는 스프링 인터셉터가 필터 이후까지 작동하지 않습니다.
Level of operation | 서블릿 수준에서 작동 | 컨트롤러 수준에서 작동
Method | Interceptor의 postHandle에 비해 Filter의 doFilter 기술은 훨씬 더 유연합니다. 요청이나 응답을 수정하거나, FilterChain인으로 전달하거나, 요청 처리를 중지할 수도 있습니다. | 실제 대상 "핸들러"에 액세스할 수 있으므로 HandlerInterceptor는 필터보다 더 정확한 제어를 제공합니다. 핸들러 메소드의 annotation status도 확인할 수 있습니다.

