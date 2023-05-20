# Gateway Handler 요청과 경로에 대한 매칭 처리

- Gateway Web Handler 
  - Before 필터
  - After 필터
- Route 
  - 고유한 ID, 목적지 URL, Predicate, Filter로 구성되는 요소
  - 조건에 만족하면 설정된 경로로 라우팅
- Predicate
  - 요청이 조건에 충족하는지 테스트
- Filter
  - 하위 마이크로 서비스로 요청과 응답을 보낼 때 변경하는 기능
