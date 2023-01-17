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
- **Framework** : Spring
- **Database** : Oracle DB (18c)
- **ORM** : Mybatis

## 📌 Detail_Info
### ⭐[노션링크](https://www.notion.so/87662a3c2aef4ac7a1a38a7af370cd5f?p=53c2b32d45204bb890521e7106585cc1&pm=c)

### 😵 주요 구현 기능
<details>
    <summary>자세히</summary>

<!-- summary 아래 한칸 공백 두고 내용 삽입 -->
<h4>1. 검색기능 구현</h4>
- 카테고리 검색, 카테고리+모임명 이 검색될 수 있도록 하는게 구현 목표입니다.<br>
  <h5>Controller</h5>  
 
   - Controller에서는 사용자 요청을 받고, Service로직과 Mapper를 통해 사용자가 요청한 정보를 불러 옵니다.<br>
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

<h4>2. 모임개설 기능 구현</h4>
 
<h4>3. 404에러 페이지 구현</h4> 
 
 </details>
### 😤 회고

