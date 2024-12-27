DDD를 사용하는 데서 오는 비즈니스 가치
1. 조직이 그 도메인에 유용한 모델을 얻는다.
2. 정교하고 정확하게 비즈니스를 정의하고 이해한다.
3. 도메인 전문가가 소프트웨어 설계에 기한다.
4. 사용자 경험이 개선된다.
5. 순수한 모델 주변에 명확한 경계가 생긴다.
6. 엔터프라이즈 아키텍처의 구성이 좋아진다.
7. 애자일하고, 반복적이고, 지속적인 모델링 사용된다.
8. 전략적인 동시에 전술적인 새로운 도구가 적용된다

DDD 적용의 난관
- 유비쿼터스 언어를 만드는 데 드는 시간과 노력을 계산하는 것
- 도메인 전문가를 시작부터 참여시키고 프로젝트 내내 함께하는 것
- 도메인 내의 해결책에 관한 개발자의 사고방식을 바꾸는 것



DDD는 무겁지 않다.
1. 도메인 모델의 클라이언트가 새로운 도메인 객체를 사용하는 방법을 보여주는 테스트를 작성하라
2. 새로운 도메인 객체를 만들 때는 테스트를 컴파일 할 수 있을 정도로 충분한 코드를 함께 작성하라
3. 테스트가 클라이언트가 도메인 객체를 사용하는 방법을 제대로 나타내고, 도메인 객체가 올바른 행동적 메서드 시그니처를 갖게 될 때까지 리팩토링하라
4. 테스트가 성공할 때까지 각 도메인 객체의 행동을 구현하고, 부적절한 코드의 중복이 없어질 때까지 도메인 객체를 리팩토링하라.
5. 유비쿼터스 언어의 현재 의미에 맞는 도메인 객체를 사용해 테스트하는지 확인할 수 있도록, 도메인 전문가를 포함한 팀원에게 코드를 시연하라.


도메인
- 조직의 전체 도메인은 여러 개의 서브도메인으로 이뤄져 있다.
- DDD를 사용할 때 모델은 바운디드 컨텍스트 안에 만들어진다.
- 전체 비즈니스 도메인을 고유의 한 영역으로 적극적으로 분리하는 것이 성공적인 모델을 만드는 데 도움이 된다.

서브도메인과 바운디드 컨텍스트