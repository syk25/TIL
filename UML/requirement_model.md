# Requirement Model
객체를 클래스로, 관계를 Association으로 추상화한 모델이다.
클래스 다이어그램으로 표현한다.

## Class
Application domain의 객체를 추상화한 결과물이자 구현단계에서 객체를 생성할 팩토리이다.

### 특징
1. Relationship(관계)
2. Attribute(속성)
3. Operation(동작)
4. Semantics(의미)

### Attribute
특정 클래스에 소속 된 "객체"가 갖는 값의 메타데이터.
이름과 데이터타입을 가진다.

### Operation
특정 클래스에 소속 된 "객체"가 가지거나 적용되는 함수(function) 또는 변화(transformation).
Signature, Visibility를 특징으로 가진다.

Signature
- name
- parameter name
- result type

메서드(method)는 Operation의 예시(instance)이다.
Operation은 여러개의 메서드를 가질 수 있다.

## Association
### 관련개념
- link
- degree
- multiplicity
- role

[association](association.md) 참조
