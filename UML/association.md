
# Association
두 "객체" 간의 link들의 공통 의미이다.
link는 두 객체 간의 관계의 예시이다.
link와 Association은 예시와 패턴의 관계이다.
Association은 클래스가 아니라 객체들의 관계임을 주의해야한다.
즉, 클래스들 간에는 여러 개의 Association이 존재할 수 있다.

## degree
Association에 참여하는 클래스의 개수이다.
unary, binary, ternary 그리고 그 이상의 degree가 있다.
클래스 다이어그램에서는 binary까지만 쓰는 걸로 권장된다.

## Multiplicity
Association 관계의 두 클래스를 전제로, 한 클래스의 객체가 연관 될 수 있는 다른 클래스의 객체의 수.

Unary Association의 경우, Association의 끝에 role을 지정해야한다.

## Role
Association의 끝 지점으로서 Association에 참여하는 클래스의 역할을 의미한다.

## Aggregation/Composition
특수한 형태의 Association이다. 포함관계일 때는 Aggregation, 구성관계일 때 composition이다.
포함관계일 경우, 하나의 객체가 상대 객체와 반드시 함계일 필요는 없으나 구성관계일 때는 반드시 함께여야한다.
어떤 관계일지 명확하지 않을 때는 Association으로 표기해도 무관하다.

