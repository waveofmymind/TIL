## 일반적인 쿼리 작동 순서

1. 불필요한 조건 제거
2. 복잡한 연산 단순화
3. join 발생 시 read 순서 결정
4. 인덱스 결정
5. 임시테이블 필요 여부 결정

## SELECT 문 작동 순서

FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY -> LIMIT


## SELECT 

> 테이블에 저장된 데이터를 검색하는 명령어

SELECT 컬럼 FROM 테이블;

## WHERE

> 검색하고싶은 데이터의 조건을 설정할 수 있는 명령어

SELECT 컬럼 FROM 테이블 WHERE 조건;

## COUNT

> 검색한 결과의 데이터의 개수를 가져오는 명령어

COUNT(컬럼) FROM 테이블;

## LIMIT

> 검색할 테이터의 개수를 제한하는 명령어

SELECT * FROM 테이블 LIMIT 1,5;

-> 2번째 데이터부터 5개

## SUM,AVG,MAX,MIN

산술 명령어

## +ONe




