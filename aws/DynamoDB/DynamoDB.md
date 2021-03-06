# AWS에서 제공하는 NoSQL 데이터베이스

- Key-Value 데이터모델
- 데이터를 단순히 키-값으로 정의 
- 키를 고유한 식별자로 사용하는 키-값 쌍의 집합으로 데이터를 저장
- 키를 사용해서만 쿼리가능
- Serverless 서비스

# DynamoDB의 구성
- 테이블 뎅터의 집합
 - 항목: 고유하게 식별할 수 있는 속성들의 집합(Row)
 - 속성: 항목의 속성(Column)
 - 파티션키: 하나의 속성으로 구성되는 기본 키
   - DynamoDB의 데이터는 분산 저장될 때 파티션으로 나누어 저장되며 이 때 어떤 파티션으로 저장될 것인지를 결정하는 키
   - 파티션 키로만 구성된 테이블에서는 중복된 파티션키는 존재할 수 없음
 - 정렬키: 파티션 키와 같이 복합키로 구성되며 항목들이 어떻게 정렬될 지를 결정하는 키
