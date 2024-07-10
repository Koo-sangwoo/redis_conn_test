<h2>Redis 간단 연동 및 테스트</h2>

<h3>1. 프로젝트 생성 및 라이브러리 추가</h3>

우선 build.gradle에 <b>spring-data-redis</b>를 추가한다.

![image](https://github.com/Koo-sangwoo/redis_conn_test/assets/109846153/fa777639-c1df-43d5-8809-48597fc18b69)

<h3>2. 연동할 Redis 서버 호스트와 포트 입력해두기</h3>
서버 역시 이미지를 만들어 올리면 이미지 생성시 환경변수로 세팅할 수도 있지만, 서버는 IDE에서 호스팅을 할 예정이므로 application.properties(or yaml)에 정의한다.

또한 접근할 비밀번호 역시 정의해두겠다.

<img width="266" alt="image" src="https://github.com/Koo-sangwoo/redis_conn_test/assets/109846153/73a7676b-99ff-4a86-b589-934a364632cb">

<h3>3. Redis 서버 도커에 띄우기</h3>

위 과정을 완료했다면 이제 테스트시 Redis에 연결하지 못하는 상황을 예방하기 위해 로컬 Docker에 Redis이미지를 띄워두겠다.

참고로 아래 사진의 명령어를 입력하지만, 포트가 위의 application.properties와 다르면 해당 포트에 맞추어 이미지를 실행해야한다.
<img width="335" alt="image" src="https://github.com/Koo-sangwoo/redis_conn_test/assets/109846153/0ab37f27-f366-4cf2-9191-904f7c1517bc">

<h3>4. Redis Bean Config 클래스 생성</h3>
다른 RDB의 JPA나 MyBatis를 사용할 때처럼 Redis도 기능에 필요한 Bean을 정의해주어야한다.
