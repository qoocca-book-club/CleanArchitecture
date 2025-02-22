### 데이터베이스 시스템은 왜 이렇게 널리 사용되는가?

회전식 자기 디스크 때문.

디스크에서 데이터는 원형 트랙에 저장된다. 트랙은 섹터로 분활되고 각 섹터는 사용하기 편한 크기의 바이트를 저장했는데, 대체로 4k였다. 각 플래터는 대략 수백 개의 트랙으로 구성되었고 디스트는 십여개의 플래터로 구성되었다. 디스크에서 특정 바이트를 읽으려면 먼저 헤드를 적절한 트랙으로 옮기고 디스크가 돌면서 헤드 위치에 적절한 섹터가 올 때까지 기다린 후, 해당 섹터에서 4k 모두를 RAM으로 읽어들여야 한다. 그런 후 해당 RAM 버퍼의 색인을 찾아서 필요한 바이트를 가져왔다.

### 프레임워크는 세부사항이다.

프레임워크는 아키텍처가 될 수 없다.

프레임워크는 그들과 결합되기를 바라지만 위험과 부담은 오롯이 내가 감내해야한다.

프레임워크와의 첫만남부터 바로 결혼하려 들지 마라.

### 컴포넌트

> 컴포넌트는 멋지고 깔끔한 인터페이스로 감싸진 연관된 기능들의 묶음으로, 애플리케이션과 같은 실행 환경 내부에 존재한다.
> 

### 조직화 VS 캡슐화

자바 애플리케이션에서 모든 타입을 public으로 지정한다면, 패키지는 단순히 조직화를 위한 매커니즘으로 전락하여 캡슐화를 위한 매커니즘이 될 수 없다. public 지시자를 과용하면 이 장의 앞에서 제시한 네 가지 아키택처 접근법은 본질적으로 완전히 같아진다. protected를 잘 쓰는 것이 중요.

> 최적의 설계를 꽤했더라도, 구현 전략에 얽힌 복잡함을 고려하지 않으면 설계가 순식간에 망가질 수도 있다는 사실을 강조하는 데 그 목적이 있다. 설계를 어떻게 해야만 원하는 코드 구조로 매핑할 수 있을지, 그 코드를 어떻게 조직화할지, 런타임과 컴파일타임에 어떤 결합분리 모드를 적용할 지를 고민하라.
> 

> 가능하다면 선택사항을 열어두되, 실용주의적으로 행하라. 그리고 팀의 규모, 기술 수준, 해결책의 복잡성을 일정과 예산이라는 제약과 동시에 고려하라. 또한 선택된 아키텍처 스타일을 강제하는 데 컴파일러의 도움을 받을 수 있을 지를 고민하며, 데이터 모델과 같은 다른 영역에 결합되지 않도록 주의하라. 구현 세부사항에는 항상 문제가 있는 법이다.

### 결론 및 느낀점
-----
프레임워크에 너무 의존하는 방식이나 public을 남용하는 것은 나도 생각해보지 못한 부분이다. 접근제어자를 통해 프로젝트를 설계할 수 있다는 것에 큰 감명을 받았다.
내가 모르고 있었던 부분이 너무 많고 생각해서 설계를 해야하는 부분이 너무 많은 것 같다.
나 또한 오토와이어링을 무분별하게 사용하고 있었던 때도 있었는데 생성자 주입으로 바꾸는 것이 훨씬 좋다고 들은 이후로는
생성자 주입으로 의존성을 주입하고 있었지만 그 이유에 대해서는 깊게 고민해 보지 않은 듯 하다. 이런 부분도 생각하게 하는 점에서
많은 영감을 준 책이었던 것 같다.
아직도 배울 게 너무 많다..
