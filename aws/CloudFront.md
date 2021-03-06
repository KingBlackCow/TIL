# CloudFront
개발자 친화적 환경에서 짧은 지연 시간과 빠른 전송 속도로 데이터, 동영상, 애플리케이션 및 API를 전 세계 고객에게 안전하게 전송하는 고속 콘텐츠 전송 네트워크서비스

- AWS에서 제공하는 Content Delivery Network(CDN)
- 웹페이지, 이미지, 동영상 등의 컨텐츠를 본래 서버에서 받아와 캐싱
- 해당 컨텐츠에 대한 요청이 들어오면 캐싱해둔 컨텐츠를 제공
- 컨텐츠를 제공하는 서버와 실제 요청 지점간의 지리적 거리가 매우 먼 경우 요청 지점 근처의 CDN을 통해 빠르게 컨텐츠 제공 가능
- 엣지 로케이션 데이터를 캐싱
- 정적 컨텐츠, 동적 컨텐츠 모두 호스팅 가능

# 용어정리
원본(Origin): 실제 컨텐츠가 존재하는 서버(S3, EC2)
배포(Distribution): CloudFront의 CDN 구분 단위로 여러 엣지 로케이션으로 구성된 컨텐츠 제공 채널
동작(Behavior): 프로토콜, 캐싱 정책, 로그 등 어떻게 컨텐츠를 전달할지 설정
