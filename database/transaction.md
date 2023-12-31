# Transaction
## 서론
Transaction은 작업에 필요한 연산의 모음이다.
- 데이터베이스에서 논리적 작업 단위
- 장애 복구시의 기준 단위
- SQL문들의 모임

## 특성
Transaction은 데이터베이스의 무결성과 일관성을 보장하기 위해 ACID로 표현되는 4가지 특징을 가진다.
1. Atomicity(원자성)
2. Consistency(일관성)
3. Isolation(격리)
4. Durability(지속성)

### Atomicity(원자성)
> Transaction은 실행시 완료가 되어야한다. 완료되지 않으면 아예 실행되지 않은 상태로 복귀되어야한다.

전산 거래를 할 때 송금 중 오류가 발생해서 거래 자체가 중단이 되어 본래 상태로 돌아가는 경우가 원자성의 예이다.

### Consistency(일관성)
> Transaction이 진행 된 후에도 데이터베이스 '전체'는 일관성을 유지해야한다.

Transaction이 완료 된 후 개별 요소에 변화가 생길 수 있지만 데이터베이스 자체의 관점에서 봤을 때 결과가 모순적이지 않아야한다.
예를 들어, 1000원이 있는 계좌에서 0원이 있는 계좌에 5000원을 송금했을 때 송금 후에 각각의 계좌에는 5000원이 있지만 전체로 볼 때는 10000원은 그대로 유지된다.

### Isolation(격리)
> 하나의 Transaction이 진행되는 경우 다른 transaction은 쓰여지는 데이터에 접근을 허용해서는 안된다.

### Durability(지속성)
> 시스템에 장애가 생기더라도 트랜젝션 작업 결과는 그대로 있어야한다.

### 구현원리
- 회복 : 원자성, 지속성에 대응
- 병행제어 : 일관성, 격리에 대응


## 연산
1. commit
2. roll-back

## 상태
1. active(활동상태)
2. partially committed(부분완료상태)
3. committed(완료상태)
4. failed(실패상태)
5. aborted(철회상태)