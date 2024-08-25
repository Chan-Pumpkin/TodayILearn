# Entity
DB 테이블과 매핑되는 클래스로 테이블에 존재하는 컬럼들을 필드로 가지는 객체    
- 데이터베이스 영속성(persistent)의 목적으로 사용되는 객체
- 외부에서 Entity 클래스의 Data Field 에 접근하지 못하도록 제한해야함.

## Entity에서는 Setter를 지양한다.
### 사용 의도를 파악하기 어려움
set 메서드로 값을 생성하는 것인지, 수정하는 것인지 의도 파악이 어려움

## Annotation

### @GeneratedValue
식별자 값을 자동 생성 시켜줄 수 있다.

### @JoinTable
연관관계 설정
- 한쪽 Entity에서 정의했으면 안써도 됨.

| 옵션 | 설명 |
| --- | --- |
| name | 조인 테이블명 |
| joinColumns | 현재 엔티티를 참조하는 외래키 |
| inverseJoinColumns | 반대방향 엔티티를 참조하는 외래키 |
