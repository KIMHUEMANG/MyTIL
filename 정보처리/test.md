# 테스트

## 테스트란 ?
개발된 응용 애플리케이션이나 시스템의 사용자가 요구하는 기능과 성능, 사용성, 안전성 등을 확인하고 노출되지 않은 숨어있는 결함을 찾아내는 활동이다.

- 테스트 과정에서 필요한 역할은 소프트웨어 아키텍트와 테스트 매니저이다.
  - 소프트웨어 생명 주기는 요구사항, 분석, 디자인, 구현 또는 개발 순으로 진행되며, 프로젝트의 특성과 방법론에 따라 반복적으로 수행되기도 한다.
  - 테스트는 `단위 테스트`, `통합 테스트`, `시스템 테스트`, `인수 테스트`의 순으로 구성된다.

> ### 소프트웨어 아키텍쳐
> - 소프트웨어의 골격이 되는 기본 구조
> - 구성요소(Component)간의 유기적 관계를 표현하는 시스템 구조 또는 구조체

<br>

## 테스트의 7가지 원칙
1. 테스트는 계획 단계부터 한다.
   - 테스트 활동은 소프트웨어 개발 주기에서 가능한 초기부터 시작해야한다.

2. 테스트는 결함을 밝히는 활동이다
   - 테스트의 목적은 결함의 제거가 아닌, 결함의 발견이다.
   - 테스트는 결함이 있다는 것을 보여줄 수 있지만, 결함이 없다는 것을 `증명할 수는 없다.`

3. 완전한 테스트는 불가능하다.
   - 모든 것(입력값, 경로, 타이밍)에 대한 테스팅은 자원의 한계로 불가능하다.

4. 테스트는 상황에 따라 다르다.
   - 애플리케이션 테스트에서도 동일한 테스트에 대한 비정상적인 결함 검수가 이루어질 수 있으므로 이러한 현상을 방지하기 위해서는 다양한 방법으로 테스트하는 것이 필요하다.

5. 결함 집중을 고려한다.
   - 대부분 결함은 소수의 특정 모듈에 집중되어 발생하는 경향을 보인다.
   - 결함의 80%는 20% 코드에 집중되어 있다. 즉, 결함이 높은 곳에 자원이 집중되어 있다.`(파레토 법칙)`

6. 살충제 페러독스를 고려한다.
   - 동일한 테스트 케이스에 의한 반복적 테스트로 새로운 버그를 찾지 못하는 내성 현상을 의미한다.

7. 오류 부재의 궤변을 고려한다.
   - 개발한 제품이 사용자의 필요와 기대에 부응하지 못하고 쓸모가 없다면 결함을 찾는 활동은 의미가 없다.
   - 개발한 제품은 요구 사항과 일치하고 사용에 적합해야한다.


<br>

## 프로젝트 수행 단계에 따른 테스트 분류

### 1. 단위 테스트
- 작은 소프트웨어 단위(컴포넌트 또는 모듈)를 테스트하는 것으로, 일반적으로 개발자 자신에 의해 진행된다.
- 과거에는 시간 부족을 이유로 단위 테스트가 생략되었으나 최근에는 개발 도구의 발전으로 개발 과정중에 자동으로 진행된다.
- 단위 테스트는 아주 중요한 부분이므로 개발 도구에서 지원하지 않아도 반드시 수행해야 한다.
- 구조적 테스트, 기능성 테스트, 리소스 관련 테스트, 강건성 테스트 등 특정 비기능성 테스트 등이 포함되어 수행된다.
- 컴포넌트 명세, 소프트웨어 상세 설계, 데이터 모델 명세 등을 이용하여 테스트한다.

테스트 방법 | 설명 | 테스트 목적
---|---|---
구조기반 |  업무 단위별 제어 흐름과 조건 결정에 따른 결과를 테스트하는 데 목적이 있다. | 제어 흐름, 조건 결정
명세기반| 동등 분할과 경계값 분석을 위하여 사용자의 입력, 출력, 내부 이벤트 등을 확인하는 데 목적이 있다.| 동등 분할, 경계값 분석


> 화이트박스 테스트와 블랙박스 테스트
> - 화이트 박스 테스트 : 개발자 관점 구조와 동작 기반의 테스트   
> `종류`: 기초 경로 테스트, 제어 흐름 테스트, 조건 테스트, 루프 테스트, 데이터 흐름 테스트, 분기 테스트. (`구조 기반`이다)
> 
> - 블랙박스 테스트 : 사용자 관점, 명세 기반의 테스트
> `종류` : 균등 분할 , 한계값 테스트, 원인 효과 그래프 테스트, 비교 테스트 (`명세 기반` 이다)

<br>

### 통합 테스트
- 모듈 사이의 인터페이스, 통합된 컴포넌트 간의 상호작용을 테스트한다.
- 하나의 프로세스가 완성된 경우 부분적으로 통합 테스트를 수행하는 경우도 있다.
- 일반적으로 빅뱅 방식보다는 순차적 형태와 아키텍처에 대한 이해를 바탕으로 된다.
- 빅뱅, 상향식, 하양식, 샌드위치, Central, Collaboration, 레이어 통합 등의 테스트가 있다.

1. 빅뱅  
   - `수행 방법` : 모든 모듈을 동시 통합 후 수행  
   - `더미 모듈` : 없음  
   - `장점` : 단시간 테스트 가능 , 작은 시스템에 유리  
   - `단점` : 장에 위치 파악이 어려움, 모든 모듈 개발
 
<br>

2. 상향식
   - `수행 방법` : 최하위 모듈부터 점진적으로 상위 모듈과 함께 수행
   - `더미 모듈` : 드라이버 필요
   - `장점` : 장애 위치 파악이 쉬움 , 모듈 개발 시간 낭비가 없음
   - `단점` : 이른 프로토타입 어려움 , 중요 모듈이 마지막으로 테스트될 가능성이 높음

<br>

3. 하향식 
   - `수행 방법` : 최상위 모듈부터 하위 모듈들을 통합하며 수행
   - `더미 모듈` : 스텁 필요
   - `장점` : 장애 위치 파악 쉬움 , 이른 프로토타입 가능 , 중요 모듈의 선 테스트 가능, 결함 조기 발견 가능.
   - `단점` : 많은 스텁이 필요 , 하위 모듈들의 불충분한 테스트 수행

> 드라이버 : 상향식 테스트 방식의 존재하지 않는 상위 모듈 간의 인터페이스 역할
> 스텁 : 하향식 테스트 방식의 작성이 쉬운 시험용 모듈

<br>

### 시스템 테스트
- 통합된 단위 시스템의 기능이 시스템에서 정상적으로 수행되는지를 테스트하는 것으로, 성능 및 장애 테스트가 여기에 포함된다.
- 시스템 테스트는 개발 프로젝트 차원에서 정의된 전체 시스템의 동작과 관련된다.
- 환경 제한적 장애 관련 리스크를 최소화하기 위하여 실제의 최종 사용자 환경과 유사하게 시스템 성능, 관련된 고객의 기능/비기능적인 요구사항 등이 완벽하게 수행되는지를 테스트한다.
- 요구사항 명세서, 비지니스 절차, 유스케이스, 리스크 분석 결과 등을 이용한다.

> ### 유스케이스
> - 시스템의 동작을 사용자의 입장에서 표현한 시나리오
> - 시스템에 관련한 요구사항을 알아내는 과정

- 업무 기반의 기능적 요구사항과 시스템적인 비기능적 요구사항으로 나누어 진다.
  1. `기능적 요구사항` : 요구사항 명세서, 비즈니스 절차, 유스케이스 등 명세서 기반의 블랙박스 테스트
  2. `비기능적 요구사항` : 성능 테스트 , 회복 테스트, 보안 테스트, 내부 시스템의 메뉴 구조 웹 페이지의 네비게이션 등의 구조적 요소에 대한 화이트박스 테스트

<br>

### 인수 테스트
- 일반적으로 최종 사용자와 업무에 따른 이해관계자 등이 테스트를 수행함으로써 개발된 제품에 대해 운영 여부를 결정하는 테스트로, **실제 업무 적용 전**에 수행한다
- 시스템의 일부 또는 특정한 비기능적인 특성을 확인한다.

1. `사용자 인수 테스트` : 비즈니스 사용자가 시스템 사용의 적절성 여부 확인
2. `운영상의 인수 테스트` : 시스템 관리자가 시스템 인수 시 수행하는 테스트 활동으로 백업/복원 시스템, 재난 복구, 사용자 관리, 정기 점검등을 확인
3. `계약 인수 테스트` : 계약상의 인수/검수 조건을 준수하는지 확인
4. `규정 인수 테스트` : 정부 지침, 법규, 규정 등 규정에 맞게 개발하였는지 확인
5. `알파 테스트` : 개발하는 조직 내 잠재 고객에 의해 테스트 수행
6. `베타 테스트` : 실제 환경에서 고객에 의해 테스트 수행
