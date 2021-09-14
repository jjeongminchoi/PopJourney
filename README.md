# 📌 PopJourney
![popjourneylogo](https://user-images.githubusercontent.com/76789355/133204745-19f39261-55de-4d45-8a8c-2456019fac6d.png)
>**여행일지 기록 및 경험이나 일상 등을 공유할 수 있는 SNS 형태의 커뮤니티 서비스**  
>PopJourney 저장소 [바로가기](https://github.com/nashs789/PopJourney)

</br>

**:book: Contents**
1. [제작 기간 및 참여 인원](#1-제작-기간-및-참여-인원)
2. [사용 기술](#2-사용-기술)
3. [제안배경 및 프로젝트 소개](#3-제안배경-및-프로젝트-소개)
4. [기능 기획](#4-기능-기획)
5. [디자인 기획](#5-디자인-기획)
6. [DB 설계](#6-db-설계)
7. [개발](#7-개발)
8. [테스트](#8-테스트)

</br>

## 1. 제작 기간 및 참여 인원
- 2021.06.24 ~ 2021.08.01 (39일간)  
- 팀 프로젝트 (3명)

</br>

## 2. 사용 기술
#### `Front-End`
  - HTML
  - CSS
  - Javascript
  - jQuery

#### `Back-End`
  - Java 8
  - Spring 4.3.4
  - Maven
  - MyBatis 3.2.7
  - Oracle 11g

#### `Tool`
  - Eclipse
  - SQL Developer
  - Trello
  - Oven
  - draw.io

</br>

## 3. 제안배경 및 프로젝트 소개

- #### 제안 배경

코로나 19로 인해 우리 일상의 커다란 활력소였던 여행에도 많은 제약이 생기게 되었다.  
포스트 코로나 시대에 사용자 간 여행기를 공유하고 여행작가의 글을 통해 방구석에서도  
여행을 즐길 수 있는 소통의 창구가 필요하다고 생각되어 제안을 하게 되었다.

- #### 프로젝트 소개

여행일지 기록 및 경험이나 일상 등을 공유할 수 있는 SNS 형태의 커뮤니티 서비스이다.  
자기만의 여행 경험을 공유하여 보는 이가 색다른 경험을 할 수 있기를 바라는 마음에 프로젝트를 진행하게 되었다.  

</br>

## 4. 기능 기획
**제안 내용을 기반으로 SNS 형태의 서비스를 고려하여 기획**

![기능 정의서](https://user-images.githubusercontent.com/76789355/133205925-b499ff39-8a9b-40c5-b299-ff8783600fee.jpg)

</br>

## 5. 디자인 기획
**기능 정의서를 기반으로 사용자 친화적 UX 구현**

![](https://user-images.githubusercontent.com/76789355/133206511-f450f830-d123-45c4-a919-d1ff23819aff.jpg)
![](https://user-images.githubusercontent.com/76789355/133206524-9e95c629-a05e-4970-882a-137fb8b26ece.jpg)

ovenapp.io 프로그램 사용

</br>


## 6. DB 설계

- #### 메타 관리

**메타데이터를 관리하여 개발 시 공통 사전으로 활용 및 공통 코드 사용 통한 데이터 사이즈 축소**

![메타데이터](https://user-images.githubusercontent.com/76789355/133207511-1d7f7017-e189-49d1-a89e-93f16eebb39e.jpg)

- #### ERD 설계

**메타데이터를 기준으로 DB 모델링**

![erd](https://user-images.githubusercontent.com/76789355/133207783-14c2a119-fa44-40f0-97ad-9308aa858369.jpg)

draw.io 프로그램 사용

- #### 테이블 정의서

**모델링을 기준으로 테이블 정의서 작성**

![테이블정의서1](https://user-images.githubusercontent.com/76789355/133208384-dbd983c1-af71-4a10-aea7-c15aea10a7c0.jpg)  
![테이블정의서2](https://user-images.githubusercontent.com/76789355/133208398-6e772a2a-7827-4867-b333-51beb0345f39.jpg)  

</br>

## 7. 개발
>💡 ▶를 클릭하시면 세부 내용을 확인할 수 있습니다.

<details>
<summary><b>el 태그 및 jstl을 활용한 정적 web 구현</b></summary>
<div markdown="1">
  </br>
  
  - Controller → jsp 이동 시 view resolver가 view 경로 추가 및 화면 구현
  
  ![](https://user-images.githubusercontent.com/76789355/133209331-fc0fa7eb-7b42-452b-9eb4-4492c4735732.jpg)  
  🔍 Controller [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/web/Controller/JmPopJourneyController.java#L1200)  
  🔍 JSP [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/webapp/WEB-INF/views/CJM/journal.jsp#L2728)
  
</div>
</details>

<details>
<summary><b>post 전송 방식의 Ajax를 활용한 동적 web 구현</b></summary>
<div markdown="1">
  </br>
  
  - 로딩된 페이지 상에서 동적으로 웹을 구현함으로써 화면의 리로드 없이 사용할 수 있도록 구현
  
  ![](https://user-images.githubusercontent.com/76789355/133211536-29600c3d-dc10-4691-ba85-0e1b437bfaf1.jpg)  
  🔍 Controller [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/web/Controller/JmPopJourneyController.java#L85)  
  🔍 JSP [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/webapp/WEB-INF/views/CJM/clientCenterQuestion.jsp#L1070)
  
</div>
</details>

<details>
<summary><b>Maven을 이용한 Spring 라이브러리 관리</b></summary>
<div markdown="1">
  </br>
  
  🔍 Porn.xml [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/pom.xml#L18)  
  
</div>
</details>

<details>
<summary><b>Annotation-driven 설정을 통한 Annotation 기능 사용</b></summary>
<div markdown="1">
  </br>
  
  - 주석에 의미를 부여하고 재사용성 증가
  
  ```xml:servlet-context.xml
  
  <!-- Enables the Spring MVC @Controller programming model -->  
  <annotation-driven />
  ```
  
</div>
</details>

<details>
<summary><b>@Autowired를 이용한 객체 주입 및 DI (의존성 주입) 확보</b></summary>
<div markdown="1">
  </br>
  
  - 객체에 의존성을 주입시켜 error 방지 및 효율적인 유지보수 가능
  
  ```java:JmPopJourneyController.java
  
  @Controller
  public class JmPopJourneyController {
	@Autowired
	public IJmPopjourneyService iJmPopjourneyService;

	@Autowired
	public IPagingService iPagingService;

  ...

  @Service
  public class JmPopjourneyService implements IJmPopjourneyService {
	@Autowired IJmPopjourneyDao iJmPopjourneyDao;

  ...

  @Repository
  public class JmPopjourneyDao implements IJmPopjourneyDao {
	@Autowired SqlSession sqlSession;

  ...
  ```
  
</div>
</details>

<details>
<summary><b>Bean을 활용한 Paging 처리</b></summary>
<div markdown="1">
  </br>
  
  ![](https://user-images.githubusercontent.com/76789355/133216343-504e603d-2e53-49ad-89e1-36614aede955.jpg)  
  🔍 Controller [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/web/Controller/JmPopJourneyController.java#L407)  
  🔍 PagingBean [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/common/bean/PagingBean.java#L3)  
   🔍 PagingService [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/common/service/PagingService.java#L8)
  
</div>
</details>

<details>
<summary><b>HttpSession을 활용한 로그인 구현</b></summary>
<div markdown="1">
  </br>
  
  - Tomcat 서버를 활용하여 로그인 정보를 Session에 보관하여 사용
   
  🔍 Controller [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/web/Controller/PopJourneyController.java#L497)
  
</div>
</details>

<details>
<summary><b>AES 알고리즘 방식을 이용한 암호화 구현</b></summary>
<div markdown="1">
  </br>
  
  - param에 들어 있는 비밀번호 키를 AES 알고리즘 방식으로 암호화 후 재정의
  
  🔍 Controller [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/web/Controller/PopJourneyController.java#L214)  
  🔍 Utils [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/util/Utils.java#L18)
  
</div>
</details>

<details>
<summary><b>AOP - Aspect를 활용 및 구현</b></summary>
<div markdown="1">
  </br>
  
  - 공통적인 기능을 수행하는 메소드에 부가기능 추가  
    - 로그인이 필요한 기능에 비 로그인으로 접속 시 서비스를 이용할 수 없도록 구현
  
  🔍 CommonAOP [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/java/com/gdj35/popjourney/common/controller/CommonAOP.java#L14)  
 
</div>
</details>

<details>
<summary><b>Ansi SQL 사용으로 쿼리의 가독성 확보</b></summary>
<div markdown="1">
  </br>
  
  - 테이블간 관계가 FROM에서 명시 및 WHERE에서 조건 확인  
  
  🔍 SQL [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/resources/mapper/JmPJ_SQL.xml#L4)  
 
</div>
</details>

<details>
<summary><b>MyBatis에서 Dynamic SQL 사용으로 쿼리의 재사용 및 쿼리 최소화</b></summary>
<div markdown="1">
  </br>
  
  - 조건문을 사용해 중복되는 쿼리를 최소화 
  
  🔍 SQL [코드확인](https://github.com/nashs789/PopJourney/blob/3f5fcde32233c027187baeef4b47b75ea3eda2ba/Popjourney/src/main/resources/mapper/JmPJ_SQL.xml#L83)  
 
</div>
</details>

<details>
<summary><b>Git을 통한 협업</b></summary>
<div markdown="1">
  </br>
  
  - Git을 활용하여 팀 작업을 진행 및 파트별 개발을 통한 개발 일정 단축
  
  ![](https://user-images.githubusercontent.com/76789355/133221080-12ca90b1-7d2e-423c-8823-8926c18ead98.jpg)  
  
</div>
</details>

</br>

## 8. 테스트

- #### 테스트케이스

각 페이지별 테스트 케이스 설계 및 시나리오 작성 후 테스트 케이스 기반의 통합 테스트 수행

![테스트보고서](https://user-images.githubusercontent.com/76789355/133222823-c912fd90-be1e-4036-a545-b51fe8758add.jpg)

</br>
  
[뒤로가기](https://github.com/jjeongminchoi/Portfolio) | [맨위로](https://github.com/jjeongminchoi/PopJourney)
