# 객체 지향 프로그래밍
> 2018.01.10 업데이트

## 객체 지향 프로그래밍이란
절차 지향 프로그래밍의 문제점을 해결하고자 반복적인 일들을 처리하는 subProgram(함수)을 만들어, 같은 성격의 함수를 추상적으로 묶어 객체로 만든것이 객체 지향형 프로그래밍이다.

## 객체 지향 프로그래밍 정리

### 객체 지향 프로그램의 구성 요소
1. __클래스(Class) :__ 같은 종류의 집단에 속하는 **속성(변수)**과 **행위(메소드)**를 묶어 추상적으로 정의한 것으로 객체 지향 프로그램의 기본적인 사용자 정의 데이터형(user define data type)이라고 할 수 있다. 클래스는 프로그래머가 아니지만 해결해야 할 문제가 속하는 영역에 종사하는 사람이라면 사용할 수 있고, 다른 클래스 또는 외부 요소와 독립적으로 디자인하여야 한다.
  > 프로그램 단계에서 아직 실행 되지 않은 추상적 틀로 생각한다. 객체를 만들기 전 객체에 대한 추상적인 정의를 통해 객체가 만들어 질때 공통 분모를 가지고 만들 수 있게하여 프로그래밍의 생산성을 늘리는데 목적을 두고 있다 생각한다.
  > 게임을 예로 다양한 캐릭터를 만들기 위해서 클래스,능력치,성별,종족 값 등의 속성과 '아이템을 사용한다', '몬스터를 공격한다' 등과 같은 행위가 필요한데 이들을 개별적으로 만들기에는 개발 생산성이 저하됨과 공통적인 부분의 오류를 야기할 수 있기 때문에 이들에게 있는 캐릭터란 추상적 공통점을 가지고 이를 묶어 클래스를 만들어 실행하여 다양한 캐릭터 객체를 만드는 것으로 이해한다.

2. __객체(Object) :__ 클래스의 인스턴스(실제로 메모리상에 할당된 것)이다. 즉 클래스라는 일종의 설계도를 기반으로 실제로 생성된 그 실체가 바로 객체이다. 객체는 자신 고유의 속성(attribute)을 가지며 클래스에서 정의한 행위(behavior)를 수행할 수 있다.
  > 이렇게 만들어진 캐릭터들은 엘프, 휴먼, 드워프 같이 종족이 다르지만 종족값이라는 추상적 공통점을 바탕으로 캐릭터 고유의 속성을 가지며, 마찬가지로 클래스에서 정의한 '아이템 사용한다', '몬스터를 공격한다'와 같은 행위를 각자 수행할 수 있다고 이해한다.

3. __메서드(Method)와 메시지(Message)__ : 클래스로부터 생성된 객체를 사용하는 방법으로서 객체에 명령을 내리는 행위라고 할 수 있다. 메서드는 한 객체의 서브루틴(subroutine) 형태로 객체의 속성을 조작하는 데 사용된다. 메시지는 객체간의 통신이 이루어지는 방법이며 이 메시지를 통해 메소드가 호출되어 사용된다.
  > 위에서 만들어진 캐릭터에게 행위를 하기 위해서는 객체에 명령을 내려줘야 하는데 여기서 말한 명령이 메시지이고 그것을 받아 수행하는 방법이 메소드라 이해한다.

### 객체 지향의 특징
1. **추상화(Abstraction)**
  객체에서 공통된 속성과 행위를 추출하는 것을 추상화(Abstraction)라고 한다.
  > 위에서 말한 것과 같이 캐릭터란 공통점을 바탕으로 캐릭터의 속성과 행위를 추상적으로 묶는 것으로 이해한다.

2. **캡슐화(Encapsulation)**
  객체의 상세한 내용을 객체 외부에 철저히 숨기고 단순히 메시지만으로 객체와의 상호작용을 하게 하는 것을 캡슐화(encapsulation)라고 한다. 정보 은닉(information hiding)이라는 표현으로 설명하기도 하는데 추상화와 동일한 개념이다. 캡슐화는 추상화와 거의 같은 개념이지만 추상화를 지원하며 보다 구체적이고 제한적이라고 할 수 있다.
  > 추상적 공통점을 바탕으로 만들어진 캐릭터 클래스를 임의로 수정할 수 없도록 보호하고자 메세지를 통한 메서드 실행 방법을 캡슐화로 이해한다.

3. **은닉화(Hiding)**
  은닉이란 내부 데이터, 내부 연산을 외부에서 접근하지 못하도록 은닉(hiding) 혹은 격리(isolation)시키는 것이다.
  > 캡슐화와 비슷한 개념에서 생각할 수 있지만 내부 데이터를 보호하는 점에서 데이터 보호의 중요성을 강조한다고 이해한다.

4. **상속성(Inheritance)**
  상속은 클래스의 속성과 행위를 하위 클래스에 물려주거나, 상위 클래스에서 물려받는 것을 지칭한다.
  > 추상화가 속성과 행위를 묶는 것에서 시작했다면, 상속성을 속성과 행위를 어떻게 사용할 것인가에서 시작한 것으로 이해한다. 우리가 이미 정의해 놓은 캐릭터의 속성과 행위를 정의하는 것이 추상화라면, 상속성은 새로 만들어야 되는 캐릭터를 캐릭터라는 추상적 공통점을 바탕으로 속성과 행위를 캐릭터라는 클래스에서 가지고 오는 것이라 이해한다.

5. **다형성(Polymorphism)**
  다형성은 객체지향의 개념에서 가장 중요한 특징이라고 말할 수 있다. 다형성이란 사전적 의미로 '다양한 형태로 나타날 수 있는 능력'을 뜻한다.
  > 서로다른 캐릭터들이 같은 행위를 다양한 방법으로 수행할 수 있도록 만든 것이라 이해한다. 서로 다른 능력치를 가지고 있는 캐릭터가 다양한 방법으로 공격을 하게 되지만 공격이라는 같은 행위를 통해 명령하는 것으로 이해한다.

## 참고문서
* [[게임 개발자 블로그]](http://tenlie10.tistory.com/1)