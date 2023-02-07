# Spring-Project-어울림

스프링 프레임워크 + JSP 모임 커뮤니티 사이트


## 🖥️ 프로젝트 소개
누구나 쉽게 자신의 지역과 관심사에 맞는 모임을 찾을 수 있도록 서비스를 제공하여 
서로가 배우고 시너지를 낼 수 있도록 하는 것이 목적인 웹 서비스 입니다.
<br>

## 🕰️ 개발 기간
* 22.08.24일 - 22.09.28일

### 🧑‍🤝‍🧑 맴버구성
 - 팀장  : 김형섭 - 유저 정보 페이지, 유저 정보 수정기능, 정모CRUD, DB설계 => [작업한 리포지터리 LINK](https://github.com/HyeongSeop-Kim/final-project)
 - 팀원1 : 강승호 - 로그인, 회원가입, ID찾기, PW찾기
 - 팀원2 : 이도엽 - 메인 페이지, 에러페이지, 모임개설기능, 검색 및 카테고리 필터 기능
 - 팀원3 : 최주영 - 모임 페이지, 모임 가입/탈퇴&찜 기능, 게시글&댓글 CRUD

### ⚙️ 개발 환경
- `Java 11`
- `JDK 11.0.14`
- **IDE** : Eclipse
- **Framework** : Spring 5.3.22
- **Database** : Oracle DB (18c)
- **ORM** : Mybatis

## 📌 Detail_Info

### 😵 주요 구현 기능
<details>
  <summary><h4>기능설명</h4></summary>

<!-- summary 아래 한칸 공백 두고 내용 삽입 -->
<details>
    <summary><h4>1. 검색기능 구현</h4></summary>
 
- 카테고리 검색, 카테고리+모임명 이 검색될 수 있도록 하는게 구현 목표입니다.<br>
  <h5>Controller</h5>  
 
  - Controller에서는 사용자 요청을 받고, Service, Mapper를 통해 사용자가 요청한 정보를 불러 옵니다.<br>
  - @RequestParam 어노테이션을 이용하여 URL의 요청 매개변수에 들어있는 기본타입 인자를 메서드로 받습니다.<br>
  - 모임 리스트를 불러오는 기능이기에 페이징처리도 함께 해줍니다.<br>
     <img src="https://user-images.githubusercontent.com/100770645/212907670-fa2e3c91-0a0e-425b-a700-28917fd9979e.PNG">
  
  <h5>Service</h5>
 
  - 사용자가 요청한 검색정보와 페이지정보를 Map에 담아 Mapper로 전달합니다.<br>
     <img src="https://user-images.githubusercontent.com/100770645/212885427-874cf1a6-02b6-4a94-9269-15791730917a.PNG">
 
  <h5>Mapper</h5>
 
  - 조건에 따른 검색기능 구현을 위해 기존 검색 쿼리를 동적 쿼리로 변환 하였습니다.  
     <img src="https://user-images.githubusercontent.com/100770645/212850520-8382511c-91d5-4ec1-b009-d9877d98bd72.PNG">       
 
  - 사용자가 검색조건을 사용하지 않았을 때는 전체 모임 리스트를 불러오고<br> 
  - 카테고리를 선택하거나, 따로 검색을 하거나 둘다 입력하거나 하면 그 조건에 맞춰 모임 리스트를 불러옵니다.<br>
</details>
<details>
    <summary><h4>2. 모임개설 기능 구현</h4></summary> 

- 개인당 가입가능 모임 수를 5개로 제한하기로 설정
  <h5>Controller</h5>
 
  - 화면단에서 사용자에게 지역, 모임제목, 모임정보, 관심사, 정원수 등의 정보를 받아옵니다.<br>
  - 로그인된 계정에 가입되어있는 모임의 수가 5개를 넘지 않는다는 조건에 충족할시 DB에 저장 합니다.
     <img src="https://user-images.githubusercontent.com/100770645/212967066-aefdbb3f-7fa0-4646-8c2e-ca2d8ce6954e.PNG">
 
  <h5>JS</h5>
 
  - 개설 시에 조건에 부합하는 사용자 요청 정보를 formData에 담아 Controller로 넘겨줍니다.<br>
     <img src="https://user-images.githubusercontent.com/100770645/213141347-85ff61b2-261a-4c8d-99d4-5f00f75b7ecc.PNG">
 
  <h5>Mapper</h5>
 
  - 조건에 부합하는  정보를 DB에 저장합니다.  
     <img src="https://user-images.githubusercontent.com/100770645/213175872-e29b8fde-9cf4-40bc-9553-014a44ec929f.PNG">       
</details>
<details>
    <summary><h4>3. JSP 공통 에러 페이지 구현</h4></summary> 
 
  - 공통 에러 페이지를 설정해 두지 않으면 웹 컨테이너가 제공하는 기본 에러 페이지가 출력되는데<br>
  - 해당 페이지 내용에 어떤 오류인지에 대한 정보가 출력되기 때문에 보안상 문제가 있으며<br>
  - 또 미관상 보기에 좋지 않으니 사용자 편의를 증진 시키기 위해 구현 합니다.<br>
      <img src="https://user-images.githubusercontent.com/100770645/213181824-19865af6-25a6-4fa8-9f28-7bb03cfe24e3.PNG"><br>
  - Web.xml에 error-page태그를 활용하여 간단하게 JSP페이지와 연동할 수 있었습니다.<br>
 
      <img src="https://user-images.githubusercontent.com/100770645/213184377-75f82821-8377-4916-bc67-415fd624faa4.PNG"><br>
  - 페이지 오류 발생시 연결해둔 공통 JSP페이지로 자동 넘어가 사용자 편의성을 올릴 수 있었습니다.
 </details>
 </details>
 
### 😤 회고

  ### [파이널 프로젝트 회고 <= TistoryBlog](https://dohyoup.tistory.com/entry/%ED%8C%8C%EC%9D%B4%EB%84%90-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%ED%9A%8C%EA%B3%A0) 
## 📜 Portfolio

### 📒 [노션 포트폴리오](https://www.notion.so/87662a3c2aef4ac7a1a38a7af370cd5f?p=53c2b32d45204bb890521e7106585cc1&pm=c)

