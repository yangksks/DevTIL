# JUnit5 기본
**Write** : 2023-02-14 20:33
**Tag** : #TDD #Junit
***
## Junit5 란?
- Junit이란 자바 프로그래밍 언어용 단위 테스트 프레임워크
- Spring Boot 2.2.0 이전에는 JUnit4가 기본으로 설정되었지만, SpringBoot 2.2.0 버전부터는 JUnit5가 기본으로 설정 
- JUnit의 경우 SpringBoot initializer에서 Spring-Web을 사용하면 자동으로 추가

> JUnit5 = JUnit Platform + Junit Jupiter + JUnit Vintage

**JUnit Platform** : 테스트를 발견하고 테스트 계획을 생성하는 Test Engine API를 가지고 있습니다 Platform은 TestEngin을 통해서 테스트를 발견하고 실행하고 결과를 보고

**JUnit Jupiter** : Test Engine의 실제 구현체는 별도 모듈이며, 모듈 중 하나가 jupiter-engine 이다. 이 모듈은 jupiter-api를 사용해서 작성한 테스트 코드를 발견하고 실행합니다. Jupiter API는 JUnit 5에 새롭게 추가된 테스트 코드용 API로서, 개발자는 Jupiter API를 사용해서 테스트 코드를 작성할 수 있습니다

**JUnit Vintage** : JUnit 4 버전으로 작성한 테스트 코드를 실행할 때에는 vintage-engine 모듈을 사용합니다

## JUnit5 어노테이션 (Annotation) 알아보기
![image](https://user-images.githubusercontent.com/56426044/218726724-54f29232-17ba-42a5-9912-31c84b209667.png)

## JUnit5 Assertions 알아보기
![image](https://user-images.githubusercontent.com/56426044/218731630-5ea3d5f4-6d85-4d66-b927-a65997e44323.png)
![image](https://user-images.githubusercontent.com/56426044/218731676-95f0bd63-d571-4e54-8e0f-0c39e883f2e8.png)
![image](https://user-images.githubusercontent.com/56426044/218731731-30a889cf-37db-4d33-bcc6-95d51838d0d7.png)

## Given-When-Then
> Given-When-Then는 테스트 코드를 작성하는 반 구조화(semi-structured) 된 방법이다.

**Given** : 테스트를 위해 준비하는 과정, 테스트에 사용되는 변수, 입력 값 등을 정의하거나, Mock 객체를 정의하는 구문도 Given에 포함한다
**When** : 실제로 액션을 하는 테스트를 실행하는 과정이다.
**Then** : 테스트를 검증하는 과정이다. 예상한 값, 실제 실행을 통해서 나온 값을 검증한다.