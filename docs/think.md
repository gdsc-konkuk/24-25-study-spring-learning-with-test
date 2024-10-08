# 생각해 볼까요?

> 다음은 알아두면 재밌을, 어쩌면 몰라도 크게 상관없을 내용들이기도 합니다.
> 
> 관심이 있는 주제(최소 1개)에 대해서 더 알아보고 스터디원과 생각을 교류해 봅시다!

1. **DI**란 무엇인가요?
   - Compile-time Dependency와 Run-time Dependency의 차이를 아시나요?
   - DI의 단점은 무엇일까요?
   - IoC Container 없이 DI를 하려면 어떤 불편함이 있을까요?
   - SOILD 원칙 각각의 단점에 대해 생각해보신적이 있나요? 어떤 단점이 있을까요?
2. **TEST**란 무엇이고 왜 하는 걸까요?
   - Test Coverage에 대해 아시나요? 몇 %의 Coverage가 현실적으로 목표로 할 만 한가요?
   - TDD와 BDD의 차이에 대해 아시나요?
   - aaa와 gwt에 대해 아시나요?
   - Functionality Test에는 어떤 종류가 있을까요? E2E, integration, unit Test에 대해 들어보셨나요?
   - Performance Test에는 어떤 종류가 있을까요? Load, Stress, Endurance Test에 대해 들어보셨나요?
   - 호오옥시... Chaos Engineering에 대해 아시나요?

# 아래에 정리해 주세요!

> 정리 양식은 자유입니다! 몇 가지 주제에 대해서 알아오셨나요? ALL.

###  Compile-time Dependency와 Run-time Dependency의 차이를 아시나요?
- Compile-time : 응용프로그램이 컴파일 (자바코드가 바이트코드로 변환되는) 시간
- Run-time : 응용프로그램이 실행되는 시간, 실제 서비스되는 시간

결국 Compile-time Dependency와 Run-time Dependency 의 차이점은 언제 의존관계가 맺어지는지며, 컴파일타임에는 클래스(class) 간의 의존관계가 맺어지고 런타임에는 객체(Object) 간의 의존관계가 맺어진다.

p.s. 과거 김영한님의 스프링강의를 들을때 가장 좋은 오류는 컴파일타임에 발생하는 오류이며, 클래스간의 관계 안정성을 높이는 때에는 Compile-time Dependency를 좋아한다는 이야기를 들은 적 있네요.

### DI의 단점은 무엇일까요?
의존관계를 무작정 주입하게되면, 설정이 복잡해지며 잘못된 설정으로 인해 오류가 발생하였을 때 이에대한 조치가 매우 어려워 질 수 있다.

### IoC Container 없이 DI를 하려면 어떤 불편함이 있을까요?
IoC Container는 객체의 생명주기를 관리해주기 때문에, 개발자의 입장에서는 단순히 코드로 (Spring에서는 Annotation 등으로) 두개의 관계를 이어주기만 하면 됐었다. 그러나 직접 DI를 수행하고자 하면 객체의 생명주기를 관리하는 코드또한 필요해지므로 코드가 복잡해지고 많은 오류가 발생할 수 있다.

### SOILD 원칙 각각의 단점에 대해 생각해보신적이 있나요? 어떤 단점이 있을까요?
- SRP : 클래스가 많아진다. 실제로 프로젝트에서 엄격히 SRP를 준수하면 패키지안에 클래스가 10개씩 생기곤한다.
- OCP : 인터페이스 설계하는 것또한 개발자가 고민해야하는 문제다. UseCase가 변함에따라 인터페이스도 바뀐다. 
- LSP : 인터페이스 설계하는 것또한 개발자가 고민해야하는 문제다.
- ISP : 인터페이스 설계하는 것또한 개발자가 고민해야하는 문제다. 인터페이스가 너무 많아질 수 있다.
- DIP : 인터페이스 설계하는 것또한 개발자가 고민해야하는 문제다.

### Test Coverage에 대해 아시나요? 몇 %의 Coverage가 현실적으로 목표로 할 만 한가요?
테스트로 코드를 얼마나 검사했는지 그 %를 따지는 수치. 실제로 이 Coverage에 집착하게되면 프로덕션 코드 짜는 시간보다 몇배의 시간을 테스트코드 짜는데 사용한다는 이야기도 들었습니다. 약 60%~80%정도의 coverage가 현실적이라고 소웨공 교수님이 언급하신 걸 들었네요.

### TDD와 BDD의 차이에 대해 아시나요?
TDD는 Test Driven Development 이고 BDD는 Behavior Driven Development

TDD는 테스트 코드를 작성하고 그에 맞춰서 프로덕션 코드를 작성하는것이 특징이고, BDD는 사용자의 행동패턴을 Given-When-Then으로 분석하여 테스트케이스를 만들어 개발하는 것이 특징입니다.

### aaa와 gwt에 대해 아시나요?
처음듣는 용어라서 구글에 물어봤습니다.^^
- AAA (Assignment Act Assert) : TDD에서 테스트 케이스 작성하는 방법
- GWT (Given When Then) : BDD에서 테스트 케이스 작성하는 방법

### Functionality Test에는 어떤 종류가 있을까요? E2E, integration, unit Test에 대해 들어보셨나요?
Funcitionality Testing은 기능요구사항을 만족하는지 확인하는 테스트로서 그 기능의 단위별로 서로 다르게 접근한다고 알고있습니다.

E2E(End to End) > Integration(unit들의 집합) > Unit Test(쪼갤수있는 가장 작은 기능)


### Performance Test에는 어떤 종류가 있을까요? Load, Stress, Endurance Test에 대해 들어보셨나요?
- Load Test : 예측가능한 정상 범위의 트래픽을 잘 견디는 지 검사
- Stress Test : 정상을 넘어선 범위의 트래픽을 잘 견디는 지 검사 
- Endurance Test : 시스템이 장기간동안 부하를 견딜 수 있는지 검사


### Chaos Engineering에 대해 아시나요?