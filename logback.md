# LogBack

### Appender 
- ConsoleAppender: 콘솔에 log를 출력
- FileAppender: 파일 단위로 log를 저장
- RollingFileAppender: 설정옵션에 따라 log를 여러 파일로 나누어저장
- SMTPAppender: log를 메일로 전송 하여 기록
- DBAppender: log를 db로 저장

## logback-spring.xml
기본 스프링부트 로그설정
<img width="697" alt="image" src="https://user-images.githubusercontent.com/46700734/213848029-2740d980-528f-4caa-b640-3e12b84cb738.png">

해당 설정을 통해 스프링부트의 기본 로그 설정을 참조할 수 있음
logback 프로필 설정을 통해 각 프로필별 설정 구성 가능