코드레벨 관심사 분리
- 통신 스펙
- 비즈니스 로직
- Database 변경



Layered Architecture
Controller
1. rate limit
2. authentication
3. request validation
	1. url variables
	2. query parameters
	3. body data
4. application method call & error handling
5. response validation (serializer)
6. versioning

Application
1. domain entity 사용
2. domain method 사용

Domain
- 재사용할 수 있는 단위로 도메인 분석
- 예시) 보고서 승인
	- 보고서 도메인
	- 지출 도메인
	- 알림 도메인
	- 웹훅 도메인

Domain Entity
- 도메인 관련 정보를 한 번에 메모리에 올림
- 비즈니스 로직 실행 후에 나중에 한 번에 permanent하게 DB에 저장


Q ReportEntity의 메서드와 ReportDomain method의 차이
- 엔티티에서는 메모리에 올리는 정도의 액션
- 도메인에서는 DB 관련된 액션


ReportRepository
- 기본적으로 하나의 테이블에 하나의 레퍼지토리
- 비즈니스 로직과는 단절
- ORM 코드 사용
- ReportEntity에서 해당 모델에서 지출 관련 정보가 필요한 경우 Repository Layer에서 join 쿼리 등의 복잡한 로직을 실행



Domain Driven Design

