# 5부 아키텍처

### 정리
##### 20장 업무 규칙
업무 규칙 : 사업적으로 수익을 얻거나 비용을 줄일 수 있는 규칙 또는 절차
엔티티 : 컴퓨터 시스템 내부의 객체, 핵심 업무 규칙을 구현한 함수들로 구성
유스케이스 : 자동화된 시스템이 사용되는 방법을 설명, 애플리케이션에 특화된 업무 규칙을 설명
요청 및 응답 모델이 독립적이지 않다면, 그 모델에 의존하는 유스케이스도 의존성에 간접적으로 결합되어 버림

##### 21장 소리치는 아키텍처
아키텍처의 테마 : 소프트웨어 아키텍처는 시스템의 유스케이스를 지원하는 구조
아키텍처의 목적 : 좋은 아키텍처는 유스케이스를 중심에 두기 때문에 프레임워크나 환경에 구애받지 않고
유스케이스를 지원하는 구조를 아무런 문제없이 기술할 수 있다.
프레임워크가 아키텍처의 중심을 차지하는 일을 막을 수 있는 전략을 개발해야 함
테스트 하기 쉬운 아키텍처는 프레임워크를 준비하지 않더라도 필요한 유스케이스 전부에 대해 단위 테스트를 준비할 수 있어야 함

##### 22장 클린 아키텍처
육각형 아키텍처, DCI, BEC의 공통점
	- 프레임워크 독립성
	- 테스트 용이성
	- UI 독립성
	- 데이터베이스 독립성
	- 모든 외부 에이전시에 대한 독립성
의존성 규칙 : 소스 코드 의존성은 반드시 안쪽으로, 고수준의 정책을 향해야 한다.
	- 엔티티 : 전사적인 핵심 업무 규칙을 캡슐화
	- 유스케이스 : 애플리케이션에 특화된 업무 규칙을 포함
	- 인터페이스 어댑터 : 엔티티와 유스케이스에게 가장 편리한 형식에서 프레임워크가 이용하기에 편리한 방식으로 변환
	- 프레임워크와 드라이버 : 모든 세부사항이 위치하는 곳

##### 23장 프레젠터와 험블 객체
프레젠터 : 험블 객체 패턴을 따른 형태로, 아키텍처 경계를 식별하고 보호하는데 도움이 된다
험블 객체 패턴 : 가장 기본적인 본질은 남기고, 테스트하기 어려운 행위를 모두 험블 객체로 옮긴다.
뷰 : 험블 객체, 이 객체에 포함된 코드는 간단하게 유지한다
프레젠터 : 테스트하기 쉬운 객체, 애플리케이션으로 데이터를 받아 화면에 표현할 수 있는 포맷으로 만드는 것
데이터 매퍼 : 함축된 행위를 가지지 않는 public 데이터 변수의 집합
서비스 리스너 : 외부로부터 데이터를 수신하는 서비스의 경우 데이터를 애플리케이션에서 사용할 수 있게 간단한 데이터 구조로 포맷을 변경

##### 24장 부분적 경계
부분적 경계를 생성하는 방법중 하나는 독립적으로 컴파일하고 배포할 수 있는 컴포넌트를 만들기 위한 작업은 모두 수행한 후,
단일 컴포넌트에 모아만 두는 것
일차원 경계 : 완벽한 형태의 아키텍처 경계는 쌍방향 Boundary 인터페이스를 사용
퍼사드 패턴 : 경계를 Facade 클래스로만 간단히 정의, 모든 서비스 클래스를 메서드 형태로 정의한 후
서비스 호출이 발생하면 해당 서비스 클래스로 호출을 전달

### 결론
업무 규칙은 소프트웨어 시스템이 존재하는 이유이면서 핵심적인 기능이다.
업무 규칙은 시스템에서 가장 독립적이며 가장 많이 재사용할 수 있는 코드여야 한다.
아키텍처는 시스템을 이야기해야 하며, 시스템에 적용한 프레임워크에 대해 이야기해서는 안된다.
소프트웨어 계층을 분리하고 의존성 규칙을 준수하면 그에따른 이점을 누릴 수 있다.
아키텍처 경계에서 험블 객체 패턴을 사용하면 전체 시스템의 테스트 용이성을 크게 높일 수 있다.
아키텍처 경계가 언제, 어디에 존재해야 할지, 경계를 완벽하게 구현할지, 부분적으로 구현할지를
결정하는 일 또한 아키텍트의 역할이다.

