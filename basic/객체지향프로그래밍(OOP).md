## 객체 지향

**객체 지향이란?**

- 객체 중심으로 생각하며 객체간의 상호작용으로 코드를 동작시키는 것을 의미
- 객체의 핵심은 기능을 제공하는 것(오퍼레이션)

**오퍼레이션(operation)**

- 객체를 정의할 때 사용하는 것, 객체가 제공해야 할 기능
(객체 내부적으로 어떤 데이터를 갖고 있는 지로 정의하지 않음)

**시그니처(Signature)** : 오퍼레이션을 구성하는 세가지

- 기능 식별 이름
- 파라미터 및 파라미터 타입
- 기능 실행 결과 값 및 타입

**인터페이스 (Interface)** 

- 객체가 제공하는 모든 오퍼레이션의 집합
(JAVA에서의 인터페이스를 의미하는 것이 아닌, 객체를 사용하기 위한 명세를 의미)

**메시지 (Message)**

- 오퍼레이션 실행을 요청하는 것 (자바에서 메소드 실행과 같음)

**책임** 

- 객체마다 자신이 제공해야 하는 기능에 대한 책임이 잇다.
- 책임의 크기는 작을 수록 좋음SRP, 단일 책임의 원칙)
⇒ 즉, 객체가 제공하는 기능의 개수가 적을 수록 좋음

**의존성**

- 한 객체가 다른 객체를 이용하는 것
예) 객체 안에서 다른 객체 생성, 다른 객체의 메소드를 직접 호출
- 코드를 수정하게 되면 의존하고 있던 객체들에게도 영향
이때, 이 여파가 다시 자기 자신에게 오는 경우를 순환 의존
이 순환 의존을 해결하기 위해서 DIP를 이용합니다.(의존 역전 원칙)

### 객체 지향의 특징 4가지

1. **추상화**
    - 추상화는 복잡한 시스템을 공통적인 부분으로 나누어 복잡한 시스템을 단순화 하는 것.
    - OOP에서는 추상화를 사용하여 실제 개체 또는 개념을 나타내는 클래스를 만듦
    - 즉, **객체의 공통적인 속성과 기능을 추출하여 정의하는것입니다.**
    - 주로 추상 클래스와 인터페이스를 사용하여 구현
2. **캡슐화**
    - 객체가 내부적으로 기능을 어떻게 구현하는지 감추는 것
    - 객체 지향에서 캡슐화를 통해 종속성을 줄여 변화의 여파를 줄임
    - 종속성을 줄였기 때문에 내부 구현 변경이 유연하게 가능
    - 캡슐화 규칙 2가지
        - **Tell, Don’t Ask (TDA 규칙)**
            
            데이터를 물어보지 않고 기능을 실행.
            ( 데이터를 읽게 되면 데이터 중점의 코드가 만들어지는 원인이 되기 때문에 주의 )
            
            ```java
            public class User{
            	private String id;
            	public String getId(){
            		return this.id;
            	}
            }
            ```
            
            id를 private로 객체 내부에 숨기고 getId를 통해서 (getter)접근
            
        - **Law of Demeter (LoD 원칙, 데메테르 규칙)**
            
            디미터의 법칙, 최소한의 지식 원칙
            객체의 내부 구조를 외부로 드러내지 않는 것을 지키는 것
            함수를 통해서 자신의 정보를 공개 ⇒ 여러개의 dot 접근법 사용 지양
            객체의 자율성과 응집도를 높히고 결합도를 낮춤
            하지만 DTO, 메소드 체이닝을 사용하는 경우 디미터 법칙을 적용하지 않음
            (내부 정보를 공개하는 것이 목적인 클래스이기 때문)
            
3. **상속**
    - 기존 클래스를 사용해서 새로운 클래스를 만드는 것
    - 클래스의 속성과 메소드들을 추상화 시켜 상위 클래스(부모 클래스)로 만들어 둔 뒤 상속 받으면 손쉽게 재사용 할 수 있으며 쉽게 확장 가능
4. **다형성**
    - 어떤 객체의 속성이나 기능이 그 맥락에 따라 다른 역할을 수행할수 있는 객체 지향의 특성
    - 객체 지향 프로그래밍에서 다형성이란 한 타입의 참조변수를 통해 여러 타입의 객체를 참조할 수 있도록 만든 것을 의미. 좀 더 구체적으로, 상위 클래스 타입의 참조변수로 하위 클래스의 객체를 참조할 수 있도록 하는 것 ⇒ 동적 바인딩…?
    - 오버라이딩, 오버로딩이 이에 해당

### 객체지향의 장점

- 재사용성 증가
    
    추상화, 상속 등을 이용하여 재사용이 용이
    
- 생산성 증가
    
    재 사용성이 증가하여 자연스럽게 생산성 또한 증가
    
- 모델링의 자연스러움
    
    현실에서 구조를 그대로 코드로 옮기기 때문에 자연스럽게 모델링이 가능
    
- 유지보수
    
    캡슐화를 통해 코드간 결합도를 낮췄기 때문에 유지보수 수월
    

### 객체지향의 단점

- 상대적 성능 저하: 절차 지향 프로그래밍에 비해 속도가 저하 
(객체간 상호작용이 발생하기 때문)
- 설계 난이도 상승
- 상속의 남용 발생
    
    상위 클래스에 의존하게 되고 불필요한 확장이 발생
    (Is-A 관계가 아닌 경우에도 상속을 받는 경우…)
    
    ⇒ 객체 조립을 사용하여 해결: 속성에 다른 객체를 의존하는 방식
    

### 객체 지향적 설계 원칙

1. SRP(Single Responsibility Principle) : 단일 책임 원칙, 클래스는 단 하나의 책임을 가져야 하며 클래스를 변경하는 이유는 단 하나의 이유이어야 한다.
2. OCP(Open-Closed Principle) : 개방-폐쇄 원칙, 확장에는 열려 있어야 하고 변경에는 닫혀 있어야 한다.
3. LSP(Liskov Substitution Principle) : 리스코프 치환 원칙, 상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.
4. ISP(Interface Segregation Principle) : 인터페이스 분리 원칙, 인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리해야 한다.
5. DIP(Dependency Inversion Principle) : 의존 역전 원칙, 고수준 모듈은 저수준 모듈의 구현에 의존해서는 안된다.

### 객체 지향 설계 과정

1. 제공할 기능을 세분화하고 알맞는 객체에 할당
    1. 기능을 구현하는데 필요한 데이터를 객체의 추가.
    2. 객체에 데이터를 먼저 추가하고 그 데이터를 이용하는 기능 추가.
    3. 기능은 캡슐화의 원칙을 사용하여 구현
2. 객체간 상호작용(메시지를 주고받는 것) 방법 결정

### 참고 사이트

[# 객체 지향에 대한 이해 / 객체 지향적 설계](http://asfirstalways.tistory.com/177)

[객체 지향 프로그래밍의 4가지 특징ㅣ추상화, 상속, 다형성, 캡슐화 -](https://www.codestates.com/blog/content/객체-지향-프로그래밍-특징)

[[OOP] 디미터의 법칙(Law of Demeter)](https://mangkyu.tistory.com/147)
