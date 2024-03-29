## CS Study - Section016 소프트웨어 아키텍처 
### ✏️ Study
#### 💡 소프트웨어 아키텍처의 설계
- 소프트웨어 아키텍처
  - 소프트웨어의 골격이 되는 기본 구조.
  - 소프트웨어를 구성하는 요소들 간의 관계를 표현하는 시스템의 구조 또는 구조체.
  - 소프트웨어 개발 시 적용되는 원칙과 지침.
  - 이해 관계자들의 의사소통 도구로 활용됨.
- 소프트웨어 아키텍처의 설계
  - 좋은 품질을 유지하면서 사용자의 비기능적 요구사항으로 나타난 제약을 반영하고, 기능적 요구사항을 구현하는 방법을 찾는 해결 과정.
  - 애플리케이션의 분할 방법과 분할된 모듈에 할당될 기능, 모듈 간의 인터페이스 등을 결정.
  - 기본 원리로 `모듈화`, `추상화`, `단계적 분해`, `정보 은닉`이 존재.

##### 🔖 상위 설계와 하위 설계
|           | 상위 설계 | 하위 설계 |
|------------------|-------|-------------------|
| **별칭** | 아키텍처 설계, 예비 설계 | 모듈 설계, 상세 설계 |
| **설계 대상** | 시스템의 전체적인 구조 | 시스템의 내부 구조 및 행위 |
| **세부 목록** | 구조, DB, 인터페이스 | 컴포넌트, 자료구조, 알고리즘 |
<br>

#### 💡 모듈화(Modularity)
- 의미
  - 시스템의 기능들을 `모듈` 단위로 나누는 것.
- 특징
  - 소프트웨어의 성능을 향상시키거나 시스템의 수정 및 재사용, 유지 관리 등이 용이.
  - 공통 모듈 구성을 통해 **프로젝트의 재사용성을 향상**시킴.
  - 모듈의 크기가 작을 경우 개수가 많아져 모듈 간의 통합 비용이 많이 들고, 모듈의 크기가 클 경우 개수가 적어 통합 비용은 적게 들지만 모듈 하나의 개발 비용이 많이 듬.
  - 기능의 분리가 가능하여 **인터페이스가 단순**해짐.
  - 프로그램의 효율적인 관리가 가능. 오류의 파급 효과를 최소화.
<br>

#### 💡 추상화(Abstraction)
- 의미
  - 문제의 전체적이고 포괄적인 개념을 설계한 후, 차례로 세분화하여 구체화시켜 나가는 것.
- 특징
  - 복잡한 문제를 다룰 때 가장 기본적으로 사용하는 방법.
  - 완전한 시스템을 구축하기 전에 그 시스템과 유사한 모델을 만들어 여러 가지 요인들의 테스트가 가능.
  - 최소의 비용으로 실제 상황에 대처 가능. 시스템의 구조 및 구성을 대략적으로 파악 가능.
 
##### 🔖 추상화의 유형
| 유형 | 특징 |
|---------|-------------------|
| 과정 추상화 | 자세한 수행 과정을 정의X. 전반적인 흐름 파악을 위한 설계. |
| 데이터(자료) 추상화 | 데이터의 세부적인 속성이나 용도를 정의X. 데이터 구조를 대표할 수 있는 표현으로 대체. |
| 제어 추상화 | 이벤트 발생의 정확한 절차나 방법을 정의X. 대표할 수 있는 표현으로 대체. |
<br>

#### 💡단계적 분해(Stepwise Refinement)
- 의미
  - 문제를 상위 중요 개념으로부터 하위 개념으로 구체화시키는 분할 기법.
- 특징
  - Niklaus Wirth에 의해 제안된 `하향식 설계 전략`.
  - 추상화의 반복에 의해 세분화됨.
<br>

#### 💡 정보 은닉(Information Hiding)
- 의미
  - 한 모듈 내부에 포함된 절차와 자료들의 정보가 감추어져 다른 모듈이 접근하거나 변경하지 못하도록 하는 기법.
- 특징
  - 어떤 모듈이 정보 은닉된 모듈과 커뮤니케이션할 필요가 있을 때는 필요한 정보만 인터페이스를 통해 주고 받음.
  - 모듈의 독립적 수행이 가능.
  - 수정, 시험, 유지보수가 용이.