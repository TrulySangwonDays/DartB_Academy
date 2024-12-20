# Big Query 기초지식
데이터는 데이터베이스(DB)의 테이블에 저장됨.  
이 테이블에 저장된 데이터를 사용해서 분석함  

데이터가 저장 되는 장소 = MySQL, Oracle, PostgreSQL  
얘네의 특징은 거래를 하기 위해 사용되는 데이터베이스 (OLTP, Online Transaction Processing)  
이 친구들의 분석을 위해 만든 데이터베이스가 아니기 때문에 분석 시 쿼리 처리 속도가 느려질 수 있음  

SQL : 데이터베이스에서 데이터를 가지고 올 때 사용하는 언어.  

![alt text](SQL_imagefile/week1_테이블구조.png)
- Row -> 데이터 한 개, 가로로 한 줄  
- Column -> 데이터의 특정 속성값, 세로  

-> 엑셀, 스프레드시트와 유사함

다시 `OLTP` -> 데이터분석 속도, 기능이 부족함  
이러한 이슈를 해결하기 위해 `OLAP` 등장  
OLAP : Online Analytical Processing. 분석을 위한 기능 제공

### 따라서 Big Query란, Google Cloud의 OLAP + Data Warehouse를 의미.
"Google Cloud의 데이터 웨어하우스"
- 장점
    - SQL를 사용해 쉽게 데이터 추출 가능
    - 속도가 빠름(유료)
    - Firebase, Google Analytics4의 데이터를 쉽게 추출할 수 있음
    - 데이터 웨어하우스를 사용하기에 서버를 띄울 필요 없음
- 사용하는 이유
    - 적은 비용으로 운영하기 위해
    - 쏘카, 당근, 컬리, 마이리얼트립 등 많은 기업들에서 사용
- 비용 (US기준)
    - 쿼리비용 = 1TB당 $6 정도
    - 저장비용 = 1GB당 $0.02/월 정도  

# Big Query 환경설정
### 빅쿼리 환경구성요소
1. 프로젝트
    - 하나의 큰 건물.
    - 하나의 프로젝트에 여러 데이터셋 존재 가능
2. 데이터셋
    - 건물 속의 창고 공간.
    - 판매 데이터, 고객 데이터 등 별도 데이터를 저장할 수 있음
3. 테이블
    - 창고에 있는 선반.
    - 행과 열로 이뤄진 테이블에 데이터 저장

![alt text](SQL_imagefile/week1_BigQueryScreen.png)


# 데이터 탐색 - 조건, 추출, 요약
### 데이터를 활용하는 과정
- 어떤 일을 해야 한다  
&rarr; 원하는 것을 정한다  
&rarr; 데이터 탐색  
&rarr; 단일자료?or다량의 자료?(->연결)  
&rarr; `조건/추출/변환/요약`  
&rarr; 데이터 결과 검증 -> 피드백/활용


# 저장된 데이터 확인하기
- 쿼리 작성하기 전에 `데이터를 제대로 이해하기!`  
ERD (Entity Relationship Diagram)
![alt text](SQL_imagefile/week1_ERD.png)
- 내가 원하는 데이터가 어디에 어떻게 존재하는가를 이해하는 과정이 필요  
- 칼럼들이 가지는 의미, 숫자들이 가진 의미, 영어들이 가진 의미들 정확히 파악하고 정리하는 과정이 필요함
![alt text](SQL_imagefile/week1_dataExample.png)

#### 포켓몬 데이터와 이커머스
- 포켓몬 : 상품
- 트레이너 : 유저
- 트레이너가 잡은 포켓몬 : 주문
- 장바구니에 담은 물건
- 웹페이지 접근 수
- 웹피이지 버튼 클릭 수


