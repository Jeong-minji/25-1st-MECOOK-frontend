## Introduction
[이마트 PEACOCK 사이트](https://peacock.emart.com/peacockMain/main.do) 클론 프로젝트<br>
PEACOCK 브랜드 제품을 카테고리별로 소개하고 판매하고 주문하는 웹사이트
- 기간: 2021. 10. 04. ~ 2021. 10. 15.
- [Backend GitHub](https://github.com/wecode-bootcamp-korea/25-1st-MECOOK-backend)
- 초기 세팅부터 직접 구현하였으며, 프론트와 백을 연결해 모든 데이터는 통신으로 받아왔습니다.

## Members
- **Frontend**: 김용현, 정민지, 손호영, 서고운
- **Backend**: 김민찬, 김도훈


## Technology
- **Frontend**: `JSX` `React(CRA)` `Sass` (Library: `React-router-DOM`)
- **Backend**: `Python`, `Django Web Framework`, `AWS`, `MySQL`
- **Common**: 버전관리 `Git & GitHub`, 일정관리 `Trello`, 소통 `Slack`

## Main Function
- **메인**: 회원가입, 로그인/로그아웃
- **카테고리별 상품 리스트**: 제품 이름 및 이미지, 조리시간, 용량, 상품 좋아요 개수 및 해당 상품 좋아요 여부
- **상품 상세**: 상품 상세 설명 및 이미지, 상품 좋아요 개수 및 해당 상품 좋아요 여부, 관련 해쉬태그, 상품 관련 리뷰 추가, 상품 장바구니 추가
- **이달의 베스트 메뉴**: 전체 메뉴 중, 이달의 베스트 메뉴 소개
- **상품 검색**: 검색어에 따른 검색 결과 필터링
- **마이페이지**: 회원 정보(이름, 포인트, 등급), 장바구니 상품 삭제 및 선택한 상품 주문하기(상품 주문시 회원 포인트 차감)

## Part
- 김용현: Nav, Footer 및 메인 페이지, 상품 리뷰 추가 기능 구현
- 정민지: 카테고리별 상품 리스트, 마이페이지, 이달의 베스트 메뉴 구현
- 손호영: 상품 상세 설명 페이지 및 상품 검색 페이지 구현
- 서고운: 로그인, 회원가입 구현

## 담당 부분 상세 설명
**1. 카테고리별 상품 리스트**
+ 카테고리에 마우스를 hover 할 때마다 background image와 상품 리스트가 변경됨
+ 로그인한 사용자가 상품리스트를 볼 경우, DB에 저장된 해당 유저의 상품 좋아요 여부를 받아와 상품에 좋아요를 눌렀는지 아닌지 확인 가능
+ 좋아요를 토글 시킬때 통신 -> DB에 해당 상품이 좋아요 되어 있는 경우는 삭제, 좋아요가 없는 경우는 좋아요 추가
+ 로그인 하지 않은 사용자는 하트를 누르면 "로그인한 사용자만 이용할 수 있는 서비스입니다" 알림을 띄움

**2. 마이페이지**
+ PEACOCK 사이트에 마이페이지가 별도로 없어, 화면 사이드에서 사용자 정보와 장바구니 정보를 확인할 수 있도록 레이아웃과 기능 구현
+ 상품 상세 페이지에서 장바구니 추가 버튼 클릭시 DB에 해당 유저의 장바구니 목록에 POST 하면, MyPage에서 장바구니 목록을 다시 GET 함
+ 주문할 상품을 체크하면 총 주문 가격을 실시간으로 띄워주고, 아이콘을 누르면 장바구니 목록에서 삭제 가능
+ 주문하기 버튼을 누르면 체크한 상품들의 cartId를 API URL에 포함해서 보내주고, 서버에서 해당 가격만큼 차감된 포인트를 GET 함

**3. 이달의 베스트 메뉴**
+ 일정한 기준으로 정렬된 이달의 베스트 메뉴 목록을 서버에서 GET
+ 받아온 데이터를 순서대로 화면에 띄워줌

## Demo
![image](https://user-images.githubusercontent.com/20683436/137589523-7a689221-91e5-4143-a563-833477358051.png)
