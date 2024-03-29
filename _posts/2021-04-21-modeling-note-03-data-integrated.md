---
title:  "관계형 데이터 모델링 노트 : 03 데이터 통합과 서브 타입"
search: false
categories:
  - DataModeling
tags:
  - Data
  - Data Modeling
  - Modeling
  - 관계형 데이터 모델링 노트
  - 데이터 모델링
  - 데이터 통합
  - 서브타입
  - 모델링
---
<br/>
# Chapter 3 : 데이터 통합과 서브 타입

## 서론
  * "관계형 데이터 모델링 노트" 책을 통해 진행한 이론 스터디 세번째 시간이다.
  <br/>
  이번 시간에는 데이터 통합과 서브 타입에 대해서 얘기할려고 한다. 미리 데이터 통합을 얘기 하자면, 성격이 비슷한 데이터를 일반화하여 하나의 엔티티로 만드는것을 말한다.<br/>
  서브 타입은 엔티티를 조금 더 상세화 시킨 것으로, 공통적인 부분을 수퍼 타입으로 상세적인 부분을 서브 타입으로 설계하여 조금더 비지니스, 혹은 데이터를 정확하게 표현하고자 하는 방법이다.<br/>

## 데이터 통합에 대한 서설

  * 정규화는 이론적이지만 데이터 통합은 딱히 이론적이라고 볼 수 없다. 오히려 직관이나 통찰력을 기반하여 수행되기 때문에 모델러 개개인의 능력 차이가 큰 영역이다.
  <br/>

  * 보통 통합하려는 데이터는 핵심적으로 사용되는 데이터일 가능성이 크다. 통합에 대한 이슈가 발생할 수 있는 데이터는 더욱 핵심 데이터이다. 핵심적이지 않은 데이터는 무관심해서 통합과 관련된 이슈가 발생하지 않는다.
  <br/>

  * 데이터 통합은 정규화를 기반으로 이뤄져야 한다. 정규화가 되지 않은 통합은 의미가 없다.
  <br/>

## 일반화와 상세화

  * **일반화**
    - 모델링에서 일반화한다는 것은 데이터 통합을 의미한다. 유사한 것을 묶는 것을 일반화라고 한다.
    <br/>

    - 일반화는 상세한(개별적인) 것에서 출발해서 일반적(포괄적)인 것을 만드는 과정이다. 상향식 방법과 유사하다.
    <br/>

  * **상세화 / 특수화**
    - 상세화는 하향식 방법으로, 차이를 도출하는 것이 주요 행위이다.
    <br/>

## 데이터 통합과 엔티티 통합
  * 데이터 통합이란 유사한 성격의 데이터를 합치는 것을 말한다. 데이터라는 의미에는 아직 엔티티가 되기 이전 상태인 집합이라는 개념이 포함되어 있다.
  <br/>

  * 엔티티 통합은 주로 리버스 모델링에서, 이미 엔티티가 설계된 상태에서 두 엔티티를 통합하는 것을 의미한다.
  <br/>

## 통힙 시 유의사항
  * **통합을 위한 통합은 지양되어야 한다.**
  <br/>

  * **성능**
    - 통합해야 성능이 좋아지는 요건이 많아 통합을 우선으로 고려한다. 통합을 원칙으로 하면서 성능이 나빠질 수 있다는 점을 염두에 둔다.
    <br/>

  * **정체성 희석**
    - 지나치게 일반화하면 데이터의 정체성이 희석된다.
    <br/>

  * **무결성 저하**
    - 데이터를 통합하면 데이터 무결성이 저하될 수 있다. 통합해서 같이 사용함으로써 제약 조건을 생성하지 못하거나, 도메인을 정확히 설정하지 못할 수 있다.
    <br/>

  * **마이그레이션 가능 여부**
    - 기존에 사용했던 엔티티를 통합할 때는 데이터 마이그레이션을 고려해야 한다.
    - 특히 시스템 오픈 시 마이그레이션 시간이 중요하다.
    <br/>

## 어떤 경우에 통합을 고려하는가?
  * **데이터 성격이 유사할 때**
    - 가장 원론적인 원칙은 데이터의 성격(본질)이 유사할 때 통합할 수 있다. 데이터의 성격이 개념(본질)적으로 유사하면 통합할 수 있다. 주로 핵심적인 실체를 관리하는 데이터 중에서 데이터의 본질이 유사한 경우가 많다.
    <br/>

  * **엔티티의 기초 속성이 유사할 때**
    - 엔티티에서 관리하는 데이터의 본질은 속성으로 나타난다. 따라서 속성이 유사하면 본질이 유사할 가능성이 높다. 더욱이 기초 속성이 유사하면 통합을 고려할 수 있다.
    <br/>

  * **역할을 관리할 때**
    - 역할을 관리하는 엔티티는 대체로 통합하는 것이 좋다.
    <br/>

  * **대칭적인 업무일때**
    - 대칭적인 업무를 관리하는 데이터도 통합을 고려할 수 있다.
    <br/>

  * **계층 관계가 존재할 때**
    - 계층 관계도 통합을 고려해야 할 주요 대상이다.
    <br/>

  * **공통 속성이 존재할 때**
    - 공통 속성이 별도의 데이터 성격을 지닌다면 그 속성만을 분리해서 통합을 고려 할만 하다.
    <br/>

  * **집계 엔티티의 집계 대상이 같을 때**
    - 통합해야 좋은 대표적인 엔티티는 집계 엔티티이다. 집계 엔티티를 설계할 때, 집계하려는 대상이 같다면 통합을 검토해야 한다.
    - 집계 엔티티는 집계하려는 대상(데이터 성격)과 집계하려는 내용(집계 속성), 집계하려는 기준을 고려하여 통합을 검토해야 한다. 사실 이 세가지 요소가 집계 데이터에 대한 요건이다.
    <br/>

  * **비정규화를 수행할 때**
    - 비정규화를 하면서 엔티티가 통합될 수 있다.
    <br/>

  * **일대일 관계일 때**
    - 일대일 관계가 발생하는 엔티티는 통합할 수 있다. 물론 이는 엔티티 합체이다.
    <br/>

  * **업무가 변경될 가능성이 많을 때**
    - 업무가 바뀔 가능성이 많을 수록 데이터를 일반화해야 한다. 데이터를 일반화 시킬수록 업무변경에 유연한 모델이 된다.
    <br/>

## 통합을 고려하지 않아도 되는 경우
  * 엔티티가 같이 조회되지 않는다면 통합을 고려하지 않을 수 있다.
  <br/>

  * 유사 종류의 엔티티가 향후에도 늘어나지 않는 경우.
  <br/>

  * 유사한 하위 엔티티가 없을때.
  <br/>

## 데이터 통합이 어려운 이유
  * 1) 통합의 단점 때문에
  <br/>

  * 2) 조직이 원인이 되어서 데이터가 통합되지 않는 경우가 빈번.
  <br/>

## 데이터 통합과 정규화
  * 데이터 통합은 정규화를 기반으로 이루어진다.
  <br/>

  * 정규화는 명확한 이론이 있지만, 데이터 통합은 특별한 이론이 없다. 데이터를 통합하는 방법은 개인마다 다를 수 있어, 데이터 통합은 모델러의 역량에 따라 차이가 크게 발생하는 부분 중 하나다.
  <br/>

  * 데이터 통합은 동질성은 가지는 데이터를 합치는 것이다. 그런데 동질성을 가진 데이터라는 판단을 하려면 데이터의 성격을 규정할 수 있어야 한다.
  <br/>

  * 데이터 통합은 엔티티 정의에 종속된 개념이다. 엔티티를 어떻게 정의하느냐에 따라 데이터 통합의 기준이 달라질 수 있다. 엔티티 정의는 정규화에 의해서 명확해진다. 따라서 데이터 통합은 정규화에 종속되어 있다.
  <br/>

  * 데이터를 통합한다는 것은 데이터를 일반화하는 것이다. 이때 데이터 뿐만 아니라 업무도 일반화하여 설계한다.
  <br/>

## 통합과 합체
  * 통합은 집합을 합치는 것을 의미한다. 두 개 이상의 집합을 합쳐서 하나의 집합을 만드는 것을 통합이라고 한다. 집합의 원소는 결국 엔티티의 인스턴스를 의미한다.
  <br/>

  * 합체는 일대일 관게의 엔티티를 합치는 것을 말한다. 즉 속성을 합치는 것이기 때문에 인스턴스의 개수는 늘어나지 않는다.
  <br/>

## 서브 타입에 대한 서설
  * 슈퍼 타입과 서브 타입 관계는 체계를 의미하는 상하 관계가 아니라 포함 관계이다. 슈퍼 타입과 서브 타입을 하나의 인스턴스로 인식해야 한다.
  <br/>

  * **서브 타입 종류**
    - 베타(Exclusive) 서브 타입 VS 중복(Inclusive) 서브 타입
    - 완전(Complete) 서브 타입 VS 불완전(Incomplete) 서브 타입

## 서브타입과 부분 집합
  * 서브 타입과 부분 집합이라는 용어 자체는 다소 다르다. 서브 타입은 엔티티다. 서브 타입은 슈퍼 타입 엔티티와 일대일 관계에 있는 엔티티를 의미한다. 반면에 부분 집합은 엔티티의 전체 집합 중에서 일부 집합을 의미한다. 부분 집합은 개념적인 범주를 나타내는 용어지만, 서브 타입은 실체적인 엔티티를 나타내는 용어다.
  <br/>

## 서브타입 도출 방법
  * 서브 타입을 도출하는 방법은 크게 두가지다. 두 개 이상의 유사한 엔티티에서 공통 속성을 도출하는 방법과 복잡한 하나의 엔티티에서 유사한 속성끼리 분류하는 방법이 있다. 전자는 엔티티를 통합하는 행위이고, 후자는 엔티티를 상세화 또는 논리화하는 행위이다.
  <br/>

  * 유사한 성격의 엔티티를 모아서 슈퍼 타입을 생성하는 방법이 일반화이며, 복잡한 엔티티를 분해해서 서브타입을 생성하는 방법이 상세화다. 서브 타입 모델은 이 두 가지 방법에 따라서 설계된다.
  <br/>

## 왜 서브 타입을 사용하는가?
  * 데이터가 어떤 종류(집합)로 이루어졌는지를 한눈에 보여주기 위함이 서브 타입의 가장 중요한 사용법이다.
  <br/>

## 서브 타입과 코드
  * 서브 타입과 코드는 다른 것인데도 유사하게 사용되는 경우가 있다. 하지만 유사해 보일 뿐 서브 타입과 코드는 다르므로 구분해서 사용해야 한다.
  <br/>

## 중복 서브 타입에 대한 설계
  * 베타 서브타입과 달리 중복 서브 타입은 주의해서 설계해야 한다. 중복 서브 타입은 서브 타입끼리 겹쳐지는 부분이 존재하는데 이 겹쳐지는 부분을 데이터로 어떻게 관리하느냐에 따라 모델링에 영향을 미친다.
  <br/>

  * 중복 서브 타입 모델에서 데이터 관리 방법
    - 슈퍼 타입 인스턴스와 서브 타입 인스턴스가 일대일 대응
    - 슈퍼 타입 인스턴스와 서브 타입 인스턴스가 일대다 대응(문제가 발생할 가능성 있음.)
    <br/>

## 서브타입과 슈퍼 타입의 관계
  ![image-center](/assets/images/2021-04-21_subtype-case.png){: .align-center}
  <br/>

## 슈퍼/서브 타입 논리 모델의 물리 모델 변환
  * 서브타입 별로 엔티티 분할
  * 슈퍼 타입 엔티티 하나로 통합
  * 슈퍼 타입 엔티티와 개별 서브 타입 엔티티로 분할

  ![image-center](/assets/images/2021-04-21_physical-model.jpg){: .align-center}
  <br/>

## 서브 타입 모델의 물리 모델 변환 - 서브 타입별로 엔티티 분할
  * **장점**
    - 엔티티의 속성이 근본적으로 구분되므로 엔티티를 명확하게 관리할 수 있다.
    - 대부분의 조회 조건이 개별 서브 타입을 사용할 때 효율적
    - 각 엔티티에 해당하는 업무에 대해 상호 영향을 미치지 않고 처리할 수 있다.
    - 각 엔티티의 크기가 줄어든다.
    - 슈퍼 타입과 서브 타입 엔티티의 조인이 필요 없으므로 성능면에서 유리하다.
    - 널 값을 갖는 속성이 줄어든다.
    <br/>

  * **단점**
    - 정규직 사원과 계약직 사원을 동시에 조회하는 요건이 있을 때 UNION이 발생하여 Query가 복잡하고 성능 측면에서 불리하다.
    - 사원 유형 코드 속성과 같이 서브 타입으 구분하는 속성을 사용하면 처리하기 불편하다.
    - 시퀀스나 채번 관리 엔티티를 사용해 주 식별자 값을 생성하기 복잡하다.
    - 업무가 개별적으로 처리되더라도 데이터는 통합된 모습이 아니므로 DW 등의 요건에 의해 조회가 복잡해질 수 있다.
    - 공통 속성이 개별 엔티티에 반복됨으로써 넓은 의미의 1정규형이 아니다.
    <br/>

## 서브 타입 모델의 물리 변환 - 슈퍼 타입 엔티티로 통합
  * **장점**
    - 슈퍼 타입과 서브 타입 엔티티의 조인이 발생하지 않아 조회 쿼리가 단순해지며 성능이 좋아질 때가 많다.
    - 엔티티 수가 감소해 관리가 용이해 진다.
    - 복잡한 관계가 없어져 모델이 단순해지기 때문에 ERD를 관리하기 수월하다.
    - 전체 서브 타입을 검색할 때 유니온이 발생하지 않아 성능 측면에서 효율적이다.
    <br/>

  * **단점**
    - 엔티티의 속성 개수가 많아져 크기가 증가한다.
    - NULL 값이 존재하는 속성이 많아진다.
    - 업무 규칙을 모델에 표현하기 어렵다.
    - 공통 속성만을 조회하는 요건이 빈번하거나 조회 범위가 넓으면 IO가 많아져 성능이 나빠진다.
    - 엔티티의 정체성이 희석될 수 있다.
    <br/>

## 서브 타입 모델의 물리 모델 변환 - 슈퍼/서브 타입 개별 생성
  * **선택 기준**
    - 공통 속성을 주로 사용할 때
    - 고유 속성이 많을 때
    - 속성이 빈번하게 추가될 때
    - 트랜잭션을 분리할 때
    - 통합하면 속성 개수가 많아질 때
    <br/>

  * **장점**
    - 슈퍼 타입인 사원 엔티티는 한 블록에 많은 인스턴스가 저장되므로 핵심 조회 요건의 성능이 좋아질 때가 많다.
    - 논리 모델과 유사한 구조이기 때문에 모델에 업무 규칙이 표현되므로 모델의 가독성이 높아진다.
    - 추가 업무로 생기는 어플리케이션의 변경 영향을 줄일 수 있다.
    - 집게나 DW 요건을 만족할 가능성이 커진다.
    - 데이터 저장 공간을 가장 효율적으로 사용한다.
    <br/>

  * **단점**
    - 조회 요건에 따라 조인이나 조인 후의 유니온 쿼리 등이 발생해 성능 효율이 떨어질 수 있다.
    - 여러 엔티티로 나눠어 엔티티 개수가 늘어나며 관리가 어려워진다.
    - 베타-중복, 완전-불완전 서브 타입의 종류에 따라 인스턴스를 발생 시킬 때 혼선이 발생할 수 있다.
    <br/>
