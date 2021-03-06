# S3스토리지

S3는 다양한 스토리지 클래스를 제공 용도와 목적에 맞게 사용

## S3 스탠다드
- 99.99 가용성
- 최소 3개 이상의 가용영역에 분산 보관

## S3 Intelligent Tiering
 - 머신 러닝을 사용해 자동으로 클래스 변경
 - 퍼포먼스 손해/오버헤드 없이 요금 최적화
 
## S3 standard IA(Infrequency Accessed)
- 자주 사용되지 않는 데이터를 저렴한 가격에 보관
- 데이터를 불러울 때마다 비용 ㅣㅈ불
- 사용사례: 자주 사용하지 않는 파일 중 중요한 파일

## S3 One Zone IA
- 자주 사용되지 않는 데이터를 저렴하게 보관
- 데이터를 불러올 때마다 비용지불
- 3개의 AZ대신 하나의 AZ에만 저장하기 떄문에 더 저렴한 대신에 내구성이 낮음
- 자주 사용하지 않으며 쉽게 복구 가능한 파일

## S3 Glacier instant Retireval
- 아카이브 저장소
- 저렴한 가격
- 바로 액세스 가능
- 사용사례
- : 의료 이미지 혹은 뉴스 아카이브 등

## S3 Glacier Flexible Retireval
- 아카이브 저장소
- 저렴한 가격
- 바로 액세스 불가능
- 사용 사례 : 장애복구용 데이터, 백업 데이터

## S3 Glacier Deep Archive
- 가장 저렴한 각격
- 데이터를 가져오는데 12~48시간 소요
- 오래된 로그 저장

## S3 on OutPosts
- 온프레미스 환경에 S3제공
- 내구성 확보한 상태로 파일을 저장하도록 설계
- IAM, S3 SDK등 사용가능
