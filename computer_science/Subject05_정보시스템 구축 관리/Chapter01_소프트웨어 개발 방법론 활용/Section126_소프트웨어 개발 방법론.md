## CS Study - Section126 소프트웨어 개발 방법론
### ✏️ Study
#### 💡 소프트웨어 개발 방법론의 개요
- 의미
  - 소프트웨어 개발, 유지보수 등에 필요한 여러 가지 일들의 수행 방법과 이러한 일들을 효율적으로 수행하려는 과정에서 필요한 각종 기법 및 도구를 체계적으로 정리해 표준화한 것.
- 목적
  - 소프트웨어의 생산성
  - 품질 향상
<br>

#### 💡 구조적 방법론
- 정형화된 분석 절차에 따라 사용자 요구사항을 파악하여 문서화하는 처리 중심의 방법론.
- **쉬운 이해 및 검증이 가능한 프로그램 코드를 생성**하는 것이 목적.
- 복잡한 문제를 다루기 위해, 분활과 정복(Divide and Conquer) 원리를 적용.
- 절차
  - `타당성 검토` ➡️ `계획` ➡️ `요구사항` ➡️ `설계` ➡️ `구현` ➡️ `시험` ➡️ `운용/유지보수`
<br>

#### 💡 정보공학 방법론
- 정보 시스템의 개발을 위해 계획, 분석, 설계, 구축에 정형화된 기법들을 상호 연관성 있게 통합 및 적용하는 자료 중심의 방법론.
- 정보 시스템 개발 주기를 이용해 대규모 정보 시스템을 구축하는데 적합.
- 데이터베이스 설계를 위한 데이터 모델링으로 `개체 관계도`를 사용.
- 절차
  - `정보 전략 계획 수립` ➡️ `업무 영역 분석` ➡️ `업무 시스템 설계` ➡️ `업무 시스템 구축`
<br>

#### 💡 객체지향 방법론
- 현실 세계의 개체를 기계의 부품처럼 하나의 객체로 만들어, 소프트웨어를 개발할 때 기계의 부품을 조립하듯이 객체들을 조립해서 필요한 소프트웨어를 구현하는 방법론.
- 구조적 기법의 문제점으로 인한 소프트웨어 위기의 해결책으로 채택됨.
- 설계 과정에서 주로 사용되는 모델링 언어에는 `패키지 다이어그램`, `배치 다이어그램`, `상태 전이도` 등이 존재.
- 절차
  - `요구 분석` ➡️ `설계` ➡️ `구현` ➡️ `테스트 및 검증` ➡️ `인도`
<br>

#### 💡 컴포넌트 기반 방법론
- 기존의 시스템이나 소프트웨어를 구성하는 컴포넌트를 조합해, 하나의 새로운 애플리케이션을 만드는 방법론.
- **컴포넌트의 재사용**을 통해 시간과 노력을 절감.
- 새로운 기능을 추가하는 것이 간단해, 확장성이 보장됨.
- 유지 보수 비용을 최소화, 생산성 및 품질 향상이 가능.
- 절차
  - `개발 준비` ➡️ `분석` ➡️ `설계` ➡️ `구현` ➡️ `테스트` ➡️ `전개` ➡️ `인도`
<br>

#### 💡 애자일 방법론
- '민첩한', '기민한'
- 고객의 요구사항 변화에 유연하게 대응할 수 있도록 일정한 주기를 반복하면서 개발 과정을 진행하는 방법론.
- 소규모 프로젝트, 고도로 숙달된 개발자, 급변하는 요구사항에 적합.
- `익스트림 프로그래밍(XP)`, `스크럼(Scrum)`, `칸반(Kanban)`, `크리스탈(Crystal)`
- 절차
  - `사용자 스토리` ➡️ **`계획` ➡️ `개발` ➡️ `승인 테스트`**
<br>

#### 💡 제품 계열 방법론
- 특정 제품에 적용하고 싶은 공통된 기능을 정의해 개발하는 방법론.
- 임베디드 소프트웨어를 만드는데 적합.
- 영역공학과 응용공학으로 구분.
  - 영역공학 : 영역 분석, 영역 설계, 핵심 자산을 구현.
  - 응용공학 : 제품 요구 분석, 제품 설계, 제품 구현.
- 영역공학과 응용공학의 연계를 위해 제품의 요구사항, 아키텍처, 조립 생산이 필요.