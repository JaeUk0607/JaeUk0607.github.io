---
title: java-oop-ref
author: JaeUk
layout: post
category: java
---

 # OOP
> 객체 지향언어 (OOP) 3대 특징 : 상속, 다형성, 캡슐화(은닉화)

1. 상속<br>
java : Child extends Base<br>
C#   : Child : Base

2. 상속 특징<br>
2.1 다중상속은 불가<br>
2.2 단일상속 지원 (여러개의 클래스 상속 받고 싶다면: 계층적 상속)<br>
2.3 다중상속 지원 (유일하게 Interface 만)

3. 의미<br>
진정한 의미: [재사용성]<br>
단점: 초기 설계비용

> 기준점<br>
> 상속관계 (is ~a: 상속) 은 ~이다 (부모쪽을 뒤로)<br>
> 포함관계 (has ~a: 포함) 은 ~가지고 있다
 
<br>

# [overloading과 override의 차이]<br>
##### overloading: 함수의 이름으로 여러가지 기능을 하는 것<br>
##### override: 상속에서의 재정의<br>
<br>

# [다형성(상속관계에서)]
##### 다형성: 여러가지 성질(형태)를 가질 수 있는 능력
##### C#: 다형성 안에 overloading, override 포함
##### java: [상속관계]에서 하나의 [참조변수]가 여러개의 [타입]을 가질 수 있다
##### 참조변수는 부모타입을 이야기 한다
##### 조상클래스 타입의 참조변수로 여러개의 자식클래스 객체를 참조 가능
<br>

# [추상클래스]
##### 미완성 설계도
##### 미완성 클래스: 완성된 코드 + 미완성 코드
##### -미완성 코드: 미완성 함수(함수가 { 실행블럭 }이 없다) ex) public void print();
##### -완성과 미완성 차이 (new를 통해 객체 생성(완성), 생성하지 못하면(미완성))

##### 1. 추상클래스 스스로 객체 생성 불가 (new 사용 불가)
##### 2. 추상클래스는 결국 완성된 클래스를 만들어서 사용 -> [상속]을 통해서 미완성 자원(추상함수) 완성해라(구현) -> 재정의 통해...(override)

##### Why? 추상클래스 >> 설계자가 바라보는 진정의 의미: 강제적 구현을 목적으로 한다

<br>

# [Interface]
##### 범용적 의미
##### 1. 약속, 표준, 규격 등을 만드는 행위
##### ex) 나사, 신발(사이즈) ...
##### ex) ISO 표준을 지키는 회사라면...
##### 소프트웨어 개발
##### 인터페이스가 최상위 단계
##### 설계 표준, 약속을 정의하는 행위

##### 2. 실제 구현부가 없다: 실행블럭이 없다: 이동에 관련된 기능<br>
##### >> void move(int x, int y);<br>
##### >> 추상 메서드
##### 3. 표준화된 설계를 보장 (완벽한 강제성)
##### 4. 공통설계

<br>

# [추상 클래스와 인터페이스]
##### 1. 인터페이스는 다중 상속이 가능 (구현)
##### 2. 추상클래스 단일상속 원칙
##### 3. 추상클래스 (완성된 코드 + 미완성된 코드)
##### 4. 인터페이스는 상수를 제외한 나머지는 미완성 코드 (추상자원)

##### *인터페이스 간에는 상속가능
~~~java
interface Ia extends Ib, Ic, Id {}
~~~

##### *하나의 클래스가 여러개의 인터페이스는 구현 가능
~~~java
class Test extends Object implements Ia, Ib, Ic
class Test implements Ia, Ib, Ic
~~~

##### 추상 클래스와 인터페이스 공통점
##### 1. 스스로 객체 생성이 불가능 (new연산자 사용불가)
##### 2. 상속, 구현을 통해서만 사용가능 (메모리에 적재 가능)
##### 3. 재정의 통해서 강제 구현이 목적
####  개발자 입장 
##### 1. 인터페이스를 [다형성] 입장에서 접근 (인터페이스도 부모타입이다)
##### 2. 서로 연관성이 없는 클래스에 대해서 하나로 묶는 기능을 제공 (부모가 동일)
##### 3. 인터페이스는 (~able): 날수있는, 수리할수 있는 (설계)
##### 4. 객체간의 연결 고리 (객체간의 소통의 역할)

<br>

# [상속과 포함]
##### 1. 상속: A extends B
##### 2. 포함: member field 형태: A 클래스 안에 B라는 클래스가 들어오는 것 
~~~java
(member field) class A { B b; } : //관계
class B {}
class A {
	int i;
	B b; //참조변수
}
~~~
##### 3. 포함: 함수(method parameter): 의존관계
~~~java
class B {}
class A {
	int i;
	
	void print(B b) { //method parameter
	
	}
	void print() {
		B b = new B();
	}
~~~