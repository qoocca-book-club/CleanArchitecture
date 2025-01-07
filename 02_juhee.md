# 2부 벽돌부터 시작하기: 프로그래밍 패러다임

아키텍처의 큰 관심사 : 함수, 컴포넌트 분리, 데이터 관리

<br>

## 구조적 프로그래밍

- 제어흐름의 직접적인 전환에 대한 규칙을 부과

현재의 우리는 모두 구조적 프로그래머이며, 제어흐름을 제약없이 직접 전환할 수 있는 선택권 자체를 언어에서 제공하지 않는다. 

→ 자바의 break, 예외가 비슷할 수는 있지만 제약 없던 과거와는 다르다. 

 c언어의 goto문도 함수 안으로 한정

구조적 프로그래밍이 오늘날까지 가치 있는 이유는 프로그래밍에서 반증 가능한 단위를 만들어 낼 수 있는 능력 때문. 

> 테스트는 버그가 있음을 보여줄 뿐, 버그가 없음을 보여줄 수는 없다.

<br>

## 객체지향 프로그래밍

제어 흐름의 간접적인 전환에 대한 규칙을 부과

- 캡슐화 : 데이터와 함수가 응집력있게 구성된 집단을 서로 구분 짓는 선을 그를  수 있다. 

- 상속 : 상속이란 단순히 어떤 변수와 함수를 하나의 유효 범위로 묶어서 재정의하는 일에 불과하다.

- 다형성 : OO란 다형성을 이용하여 전체 시스템의 모든 소스 코드 의존성에 대한 절대적인 제어 권한을 획득할 수 있는 능력이다. 모듈에 대한 독립성 보장

<br>

## 함수형 프로그래밍

할당문에 대해 규칙을 부과한다.

경합 조건, 교착 상태, 동시 업데이트 문제가 모두 가변 변수로 인해 발생하기 때문

현명한 아키텍트라면 가능한 한 많은 처리를 불변 컴포넌트로 옮겨야 하고, 가변 컴포넌트에서는 가능한 한 많은 코드를 빼내야 한다. 

- 소프트웨어 즉 컴퓨터 프로그램은 순차, 분기, 반복 참조로 구성된다. 그 이상도 이하도 아니다.

<br>

# 2부를 읽고 느낀점

모든 문제는 가변변수로부터 발생할 수 있다는 사실을 인지했다. 하지만 과연 불변성은 실현 가능한 것인가?

> 애플리케이션을 제대로 구조화 하려면 변수를 변경하는 컴포넌트와 변경하지 않는 컴포넌트를 분리해야한다.

점점 저장공간과 처리능력의 한계가 없어짐과 동시에 가변변수가 아니라 트랜잭션 자체를 저장하여 계속해서 그 트랜잭션들을 단순 더한다.
예를들어 매일 자정에 모든 트랜잭션을 정리하여 처리하고 다시 변수에 저장하는 방식 -> 이벤트소싱의 기본 발상 
결국 crud에서 cr의 기능만 사용, 저장공간과 처리능력이 충분하면 완전 불변성으로 작업할 수도 있음.

아무리 저장공간과 처리능력이 충분하다고 하더라도 계속해서 트랜잭션을 저장하며 불변으로 애플리케이션을 만드는 일은 불필요해 보인다.
여기서 적절한 조화가 이루어져야 할 것 같다.
불변컴포넌트와 가변컴포넌트로 분리해서 가변변수를 컨트롤하고 무분별한 가변변수나 값을 할당하지 않는 것이 그 시작일 것이다.
<br>