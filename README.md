<h1> Movie For You </h1>
<hr> 
<h2> AI Movie Recommendation Project </h2>
:: 사용자의 단어 입력에 따른 영화를 추천해주는 인공지능 추천 시스템입니다. ::
:: 소셜 리뷰 데이터를 기반으로 입력값과의 코사인유사도를 측정하여 영화를 추천합니다. ::
:: 복수개의 단어 입력 가능 (예: 박진감+유쾌한 / 가족+힐링 ) / 추천받은 영화에 대한 감성분석 제공 / 리뷰 데이터 기반 평가지수 제공 ::



# #참고 문헌# #
- Spring Boot의 구조 및 이해 ::  
- https://tutledeveoper.wordpress.com/2018/07/22/spring-boot-%EA%B8%B0%EB%B3%B8-%EA%B5%AC%EC%A1%B0-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0/

<hr>


# 사용 방법 #  
1. 먼저 우측 위의 녹색 Clone or Download를 눌러 자신의 PC로 (Clone or ZIP)내려받는다.  
2. VS CODE로 열어준다.  
3. 프로젝트 탐색기 좌측 아래에 **_pom.xml_** 이 있다. 이것을 우클릭해서 위쪽에 Update.. 를 클릭해준다. 최초 1회만 한다..!   
4. 업데이트를 빠르게 마치고 testServerApplication.java를 우클릭해서 아래에 Run을 돌려준다. 그리고 약 20초 대기(최초 초기화 실시)  
5. 서버 페이지가 뜨는 것을 확인하며 작업한다.  
6. 작성을 마친 파트별로 깃허브에 **파트별 브랜치로 커밋**한다.   


<hr>

# 백앤드 파트 #  
1. 백앤드 파트는 JSP 파일을 작성하게 됩니다.  
2. 폴더 경로는 src/main/webapp/WEB-INF/views 이고 여기에 JSP페이지를 작성해서 담아줍니다.  
3. src/main/java/com.classproject.testServer/MainController.java로 이동  
   [public class MainController] 클래스 내에 메소드를 추가해줍니다. (제일 중요합니다!)  
   
 <pre><code>
**_EX) 만약에 내가 작성해서 추가하고자 하는 JSP 파일의 이름이 [Apple.jsp] 라고 하고, /Apple로 URI를 맵핑하고 싶다면.._**   
      
    @RequestMapping(value="/[Apple]")    --> 맵핑되고자 하는 URI   
        public String [Apple]() {      --> 맵핑 간 호출되는 메소드 이름  
           return "[Apple]";          --> 내가 작성한 JSP파일의 이름  
    }  </code></pre>
    
4. 코드 내에서 연결하고자하는 JSP파일간 연결해준다.  
  - form action으로 이동 / input type="button" ..(중략).. onclick=["location.href='backend'"]/> 활용! 
  <pre><code>
**_EX.1) index.jsp -> Apple.jsp로 이동하는데 Form을 활용해서 페이지 이동 ::  
                     ==> '<form action = Apple.jsp..' 중략  
                        
**_EX.2) index.jps -> Apple.jsp로 이동하는데 Button을 활용해서 페이지 이동 ::  
                     ==> Input type=Button.. 중략 .. onclick="location.href='Apple'"  
                        </code></pre>
                    
<hr>

# 프론트 파트 #  
1. CSS : CSS작성 후 파일은 src/main/resource/static/css에 넣어주시면 됩니다.  
2. JavaScript : JS 작성 후 파일은 src/main/resource/static/js에 넣어주시면 됩니다.  
3. Image : 첨부하는 img 파일은 src/main/resource/static/images에 넣어주시면 됩니다.  
  --> _이미지 첨부 후 경로 명시 놓치지 말기!_   
4. 각 css, js파일은 JSP파일에서 연결 필수! 
  **_EX ) Apple.jsp에서 Apple.css, Apple.js를 사용할 경우 JSP에서 명시해줘야 합니다.
  
  
<hr>

# 데이터 관리 #  
1. MS - SQL SERVER(Azure)와 MyBatis를 이용합니다.  
2. Controller(interface) -> Service(interface) -> DAO -> Mapper - > Model -> DAO 순서로 동작합니다.  
3. 전체적인 과정은 구현해 놓았고 데이터에 접근해야하는 로직에서 Model을 구현하고 DAO를 호출해서 쓰시면 됩니다.  
추가 설명 :: DTO = Model(변수 집합), DAO (SQL Statement 호출 메소드), Mapper(SQL Query Storage) 

<hr>

# 데이터 분석 #  
1. 데이터 분석팀은 먼저 분석게시물을 게시할 수 있는 보드를 만들어 주셔야합니다.  
2. 그 후 각자가 진행한 결과물을 올리겠습니다.  
<hr>

# 서버 #  
1. 각 팀별로 올리는 커밋에 대해 확인하고 리퀘스트 받아 머징토록 합니다.
2. Git Hub / VS code 기반으로 작업합니다.  
<hr>
