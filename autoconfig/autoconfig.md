# 자동 구성 기반 애플리케이션

> @AutoConfiguration

## 메타 애노테이션

> 애노테이션 위의 애노테이션

@Component 자체 애노테이션과, @Controller와 @Service와 같은 @Component가 붙어있는 새로운 애노테이션은 

스프링 컨테이너의 관점으로는 크게 차이가 없으나 추가적인 정보를 제공해준다.

ex) @Controller의 경우 DispatcherServlet이 웹 컨트롤러로 판단하고 매핑 정보를 찾아볼 수 있다.

애노테이션을 생성해서 @Component를 붙이면서 기능을 확장 해나갈 수 있다.

## 메타 애노테이션의 확장성

모든 애노테이션이 메타 애노테이션이 되는 것은 아니며, 애노테이션을 생성할 때에는

- **@Target**: 애노테이션이 붙을 수 있는 대상을 지정해준다.
- **@Retention**: 애노테이션의 라이프 사이클을 지정해준다.

두 애노테이션이 반드시 필요하다.

### @Target

@Test 애노테이션을 예를 들면,

@Target의 속성이 ElementType.ANNOTATION_TYPE, ElementType.METHOD임을 알 수 있다.

이는 메서드를 타깃으로 할 수 있고, 애노테이션을 타깃으로 할 수 있음을 의미한다.

### @Retention

마찬가지로, @Test의 경우 속성이 RetentionPolicy.RUNTIME인데, 이는 소스코드가 컴파일되고, 클래스로더에 의해 클래스 파일이 실행되는 런타임 시점까지 유지가 된다는 뜻이다.

## 합성 애노테이션

메타 애노테이션의 활용 방법 중 하나로, 두개 이상의 애노테이션을 가지고 있는 메타 애노테이션이라는 뜻이다.

예를 들어 @ResponseBody와 @Controller가 합쳐져서 만들어진 **@RestController**가 있다.

## ImportSelector

AutoConfiguration을 @Import 없이 동적으로 하고 싶을 경우, ImportSelector를 구현해서 사용해야한다.

ImportSelector는 애노테이션 메타데이터를 전달받아 Import할 클래스를 String으로 리턴해준다.

## @Configuration과 proxyBeanMethods

@Configuration의 속성으로는 proxyBeanMethods가 디폴트로 true이다.

이는 스프링 컨테이너가 시작할때 프록시 클래스를 생성후 @Configuration 어노테이션이 붙은 빈 오브젝트로 사용한다.

이를 이용해서 스프링 컨테이너는 하나의 빈을 두개 이상의 빈에서 의존하고 있을 때, 하나의 빈의 인스턴스를 싱글턴으로 관리하도록 한다.











