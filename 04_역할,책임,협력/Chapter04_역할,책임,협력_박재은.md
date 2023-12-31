### 협력

- 협력은 다수의 요청과 응답으로 구성된다.
- 요청과 응답은 협력에 참여하는 객체가 수행할 책임을 정의한다.

### 책임

- 어떤 객체가 어떤 요청에 대해 응답이 가능하거나 행동할 의무가 있는 경우 해당 객체가 책임을 가진다고 한다.
- 이 때 객체의 책임은 외부에서 접근 가능한 공용 서비스의 관점에서 이야기한다. 즉 객체가 **무엇을 알고 있는가(knowing)**과 **무엇을 할 수 있는가(doing)**으로 구성된다.
  - knowing : 객체의 외부에 제공해 줄 수 있는 정보
  - doing : 외부에 제공해 줄 수 있는 서비스
- 따라서 책임은 객체의 공용 인터페이스 (public interface)를 구성한다.

#### 책임과 메시지

- 객체가 다른 객체에게 주어진 책임을 수행하도록 요청을 모내는 것을 **메시지 전송(message-send)**라고 한다.
- 책임이 협력이라는 문맥 속에서 요청을 수신하는 한 쪽의 객체 관점에서 무엇을 할 수 있는지 나열하는 것이라면 메시지는 **협력에 참여하는 두 객체 사이의 관계**를 강조한 것이다.

### 역할

- 어떤 객체가 수행하는 책임의 집합은 객체가 협력 안에서 수행하는 역할을 암시한다. 역할은 재사용이 가능하고 유연한 객체 지향 설계를 낳는 중요한 구성요소이다.
- 역할이 부여됨으로써 협력을 추상화하여 인지 과부하를 줄일 수 있다. (단순성)
  - 즉 협력 내에서 해당 역할을 가진 객체는 **각 역할이 수신할 수 있는 메시지를 동일한 방식으로 이해하고 처리할 수 있는 다른 객체로 대체**될 수 있다. (유연성, 재사용성)

### 객체의 모양을 결정하는 협력

- 객체지향의 핵심은 클래스를 어떻게 구현할 것인가가 아니라 **객체가 협력 안에서 어떤 책임과 역할을 수행할 것인가를 결정**하는 것이다.

#### 객체 설계 방법

1. 올바른 객체를 설계하기 위해서는 먼저 견고하고 깔끔한 **협력**을 설계해야 한다. 즉 **설계에 참여하는 객체들이 주고받을 요청과 응답의 **흐름을** 결정해야 한다.
2. 이렇게 결정된 요청과 응답의 흐름은 객체가 협력에 참여하기 위해 수행될 **책임**이 된다.
3. 객체에게 책임을 할당하고 나면 책임은 객체가 **외부에 제공하게 될 행동**이 된다.
4. 협력이라는 문맥에서 객체가 수행하게 될 적절한 책임, 즉 행동을 결정한 후에 그 행동을 수행하는 데 필요한 **데이터**를 고민해야 한다.
5. 데이터와 행동이 어느 정도 결정된 후 **클래스의 구현 방법**을 결정해야 한다.

### 객체지향 설계 기법

- 역할, 책임, 협력의 관점에서 애플리케이션을 설계하는 세가지 기법을 살펴보자.

#### 책임-주도 설계 (Responsibility-Driven Design)

 협력에 필요한 책임들을 식별하고 적합한 객체에 책임을 할당하는 방식으로 애플리케이션을 설계한다.

**시스템 설계 절차**
- 시스템이 사용자에게 제공해야 하는 기능인 시스템 책임을 파악한다.
- 시스템 책임을 더 작은 책임으로 분할한다.
- 분할된 책임을 수행할 수 있는 적절한 객체 또는 역할을 찾아 책임을 할당한다.
- 객체가 책임을 수행하는 중에 다른 객체의 도움이 필요한 경우 이를 책임질 적절한 객체 또는 역할을 찾는다.
- 해당 객체 또는 역할에게 책임을 할당함으로써 두 객체가 협력하게 된다.


#### 디자인 패턴 (Design Pattern)

 기존 환경 내에서 반복적으로 일어나는 문제들을 어떻게 풀어나갈 것인가에 대한 설계 템플릿의 모음이다.

| 생성 패턴          | 구조 패턴     | 행동 패턴         |
| :--------------: |  :-------: | :--:            |
| Singleton        |	Adapter   |	Command         |
| Abstract Factory | Composite  |	Interpreter     |
| Factory Method   |	Decorator |	Iterator        |
| Builder          |	Facade    |	Mediator        |
| Prototype        |	Flyweight |	Memento         |
|                  |	Proxy     |	Observer        |
|                  |            |	State           |
|                  |            |	Strategy        |
|                  |            |	Template Method |

#### 테스트-주도 개발 (Test-Driven Development)

테스트를 먼저 작성하고 테스트를 통과하는 구체적인 코드를 추가하면서 애플리케이션을 완성해가는 방식이다.

테스트-주도 개발은 테스트를 작성하는 것이 아니라 책임을 수행할 객체 또는 클라이언트가 기대하는 객체의 역할이 메시지를 수신할 때 어떤 결과를 반환하고 그 과정에서 어떤 객체와 협력할 것인지에 대한 기대를 코드의 형태로 작성하는 것이다.
