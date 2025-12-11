# 중급 프로젝트 개인 보고서

## 프로젝트 개요 및 담당 작업

덕후감은 OCR 기반으로 ISBN을 인식 후 도서 정보를 등록하고 공유하는 도서 정보 데이터베이스 시스템이다.

이 프로젝트의 주요 모듈은 사용자, 도서, 리뷰, 댓글, 대시보드, 알림으로 나뉘어져 있다.

본인은 도서 모듈과 관련 API를 담당하였다.

## 기술 스택

- 언어: Java 17
- 프레임워크: Spring Boot 3
- 빌드 도구: Gradle
- 데이터베이스: H2 Database (개발 및 테스트), PostgreSQL (운영)
- ORM: Spring Data JPA, Querydsl
- 버전 관리: Git, GitHub
- 협업 도구: Discord
- API 문서화: Swagger
- 테스트: JUnit 5, Mockito
- Null Safety: Jspecify, Spring Validation
- 배치: Spring Batch
- 외부 API: 네이버 도서 API, OCR SPACE

Null Safety를 위해 본인은 Jspecify를 도입하는 것에 대해 의견을 내었다.

자바와 스프링에서 컴파일 단계에서 Null Safety를 보장하는 어노테이션은 파편화 되어 있어 일관된 코딩 스타일을 유지하기 어렵다.

Jspecify는 파편화 문제를 해결하기 위해 자바 커뮤니티가 참여하여 비공식적으로 제안한 표준이다.

이미 Spring Framework 6에서 Jspecify를 지원하고 있고, 
공개 예정된 Spring Boot 4에서는 공식적으로 NotNull 어노테이션을 Jspecify로 통일할 예정이다.

## 요구사항

이 모듈의 요구사항은 다음과 같다.

- 도서 정보 등록/수정/삭제
- OCR SPACE를 사용한 ISBN 추출
- 네이버 API를 통한 도서 정보 fetch
- 도서 정보 커서 기반 페이지네이션
- 인기 도서 리스팅

이러한 점을 어필하여 다른 팀원들을 설득했고, 프로젝트에 Jspecify를 도입할 수 있었다.

  
