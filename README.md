# 2022-hackathon
### 팀명
- 나띵벗(Nothing But)
----------

### 제출 세션 및 주제
- 특별세션 - 일회용품, 재활용 쓰레기
----------

### 프로젝트 한 줄 설명
- 텀블러를 통해 탄소중립을 실천하는 카페들을 소개하는 프로젝트
----------
### 프로젝트에 대한 설명
- **슬로건** : Bring Your Own Tumble

- **문제점** : 잦은 일회용 플라스틱 컵, 빨대 사용등으로 인해 하루에 발생하는 약 53만톤의 폐기물, 환경오염 및 쓰레기 처리비용 증가

- **‘Tumble’ 프로젝트 소개** : 본인의 텀블러를 가지고 갈 경우 음료 할인을 받을 수 있는 카페들을 리스트업해서 사용자에게 제공해줍니다.
일상속에서 실천할 수 있는 가장 작은 행동으로써 탄소중립을 실천하고 일회용품 배출량, 사용량을 줄임으로써 지구의 온도를 낮추고 탄소중립 캠페인에 함께할 수 있습니다.

- **서비스 타겟층** : 평소 환경 및 탄소중립에 관심이 많거나 새로운 캠페인에 관심이 많은 사용자들이 주요 타겟층, 하지만 환경에 관심이 없더라도 텀블러를 통해 혜택을 받고싶은 일반 사용자들 또한 타겟층으로 선정하였습니다.

- **주요기능**
  1. Tumble 서비스의 로그인/회원가입 및 로그아웃
  2. Tumble 서비스를 소개할 수 있는 탄소중립 캠페인 및 이슈되고있는 환경관련 소식, 언론 보도자료 소개
  3. 텀블러 사용시에 혜택을 제공하는 카페들에 대한 정보를 목록(리스트) 형태와 지도로 제공
  4. Tumble 사용자들의 카페방문후기 및 자유롭게 의견을 나눌수 있는 Tumble 만의 커뮤니티

- **기대효과** : 재활용을 하는 것만이 환경을 지킬 수 있는 방법이 아닌, 자신의 텀블러를 사용함으로써 일회용품 사용량을 줄이게 된다면 폐기물의 수를 급격하게 줄일 수 있을 것입니다. 텀블러 사용 시 혜택을 주는 카페를 소개함으로써 홍보 효과와 더불어 더 많은 카페 점주들의 Tumble 서비스 등록을 기대하고 그로인한 탄소중립 캠페인에 조금 더 많은 인원이 참여하게 될 것이라고 기대됩니다.

- **차별성** : 기존에 제공되는 프렌차이즈별 텀블러 이용시에 할인금액 정보제공 뿐만아니라 **직접 조사한** 개인카페의 텀블러 혜택내용 정보 제공

----------
### 프로젝트에 활용된 기술(3가지 이내)
- Front-End : JavaScript, Thymeleaf, Bootstrap
- Back-End : Spring Boot, Jpa, MariaDB on Amazon RDS
- ETC : Kakao 지도 Web API

- **Spring Boot**
  1. Http Session세션을 사용해서 로그인에 성공하면 session 속성에 유저 정보를 저장할 수 있습니다.
  2. 웹 브라우저를 완전히 종료하기 전까지 session객체의 정보를 사용해 로그인상태를 계속해서 유지할 수 있습니다.
  3. session.invalidate() 메서드를 통해 로그아웃 처리를 할 수 있습니다.
  4. 회원 / 비회원 권한 구별 ---> **회원만 접근 가능한 기능** : 카페소개 및 커뮤니티 글작성, 수정(로그인 된 본인의 글만), 삭제(로그인 된 본인의 글만)
  5. 조회수 기능 ---> Entity 내의 조회수변수를 만들어 DB와 연동후 글 ID 와 맞는 글 조회시 Query 명령어를 통해 변수의 값이 1 증가하는 방식으로 구현하였습니다.

- **Jpa**
  1. 검색 기능 - JPA 기본제공 함수인 FindBy 함수를 사용해 FindBy(Title)Containing 함수를 통해 제목 검색 기능을 구현했습니다. 
  > **ex) “가나다” 에 가나다를 검색해야 나오는것이 아닌 중간글자인 “나”를 검색하게 되면 “나”가 포홤된 모든 글들의 검색결과가 나오게 됩니다.**
  4. 글 작성 기능 - JPA 기본제공 함수인 Save 함수를 사용하여 글 작성 기능을 구현하였습니다. 글을 작성하게 되면 Session으로부터 로그인 된 사용자 ID와, 타임리프 자바 8날짜인 LocalDateTime으로부터 글 작성일자를 포함하여 작성할 수 있습니다.
  5. 글 삭제 기능 - JPA 기본제공함수인 DeleteById 를 사용하여 글 삭제 기능을 구현하였습니다. 글 번호(Primary Key)에 따라 글이 삭제 되게 구현하였습니다.
  6. 글 수정 기능 - 수정 시 들어오는 값들을 기존 객체의 값에 새로 update 하도록 구현하였습니다. 글 작성 당시 Session 정보에서 사용자의 ID도 등록되어 저장되는데, 현재 사용자가 작성한 글의 ID와 사용자의 ID를 비교하여 같은경우에만 수정이 가능하게 구현하였습니다.

- **Kakao 지도 Web API**
  1. 



### 시연 영상
