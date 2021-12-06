# 2021 홍익대학교 산업공학과 졸업 프로젝트
*[시스템분석]*
*[시스템설계(캡스톤디자인)]*

*연구기간 : 2021.03 ~ 2021.11*

*연구자 : 신재영, 한진규, 송하준*

*연구 주제 : 감성분석을 통한 배달 APP 리뷰 시스템 개선*

### Background

- 배달 앱을 통한 음식 구매가 크게 증가하고 있고 이러한 배달 앱에서 리뷰가 이용자들의 구매선택에 큰 영향을 미침
- 현재 배달 앱 리뷰시스템은 영업점의 특성 및 장단점을 한 눈에 알기 어렵다고 판단 

### Purpose

- 기존 배달 APP의 리뷰 시스템보다 직관적이고 영업점 선별의 편리성을 제공할 수 있는 새로운 리뷰 시스템 구축

### Approach

[데이터 분석 과정]

(1) 데이터 수집(Data Collection)

*웅이네오돌뼈닭발도*

*요기요 웹 사이트 : https://www.yogiyo.co.kr/mobile/#/*
![image](https://user-images.githubusercontent.com/87981867/144852595-a7e0d940-4647-4d8c-b6c9-6069be83d302.png)

(2) 데이터 전처리(Data Preprocessing)

- 결측치와 중복 제거
- 개행문자(\) 제거
- 특수 문자 및 이모티콘 제거
- 의미 없는 자음 & 모음 제거
- Hanspell 맞춤법 검사

(3) 자연어처리 및 텍스트분석(NLP & Text Analysis)

- 형태소 분석(KoNLPY - Okt)
- BOW(Bag of Words)
- TF-IDF

(4) 모델링(Modeling)

- Scikit Learn - Logistic Regression
- 임계값(threshold) 수정
- 교차검증(Cross Validation - Stratified K-Fold)

(5) 감성분류 및 키워드 분석(Sentiment Classification & Keyword Analysis)

- 모델을 통한 예측 감성 분류와 실제 감성 분류 비교
- 회귀계수(coef) 값을 이용해 긍정 키워드와 부정 키워드 top5 추출

[리뷰 검색 시스템]

리뷰 시스템에 감성분류와 키워드 분석을 통한 정보를 제공할 뿐만 아니라 배달 APP 사용자들이 원하는 리뷰를 쉽게 검색하여 찾아볼 수 있는 기능 구현

[설문조사]
