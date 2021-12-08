# 2021 홍익대학교 산업공학과 졸업 프로젝트
*[시스템분석]*
*[시스템설계(캡스톤디자인)]*

*연구기간 : 2021.03 ~ 2021.11*

*연구자 : 신재영, 한진규, 송하준*

*연구 주제 : 감성분석을 통한 배달 APP 리뷰 시스템 개선*

### 1. Background

- 배달 앱을 통한 음식 구매가 크게 증가하고 있고 이러한 배달 앱에서 리뷰가 이용자들의 구매선택에 큰 영향을 미침
- 현재 배달 앱 리뷰시스템은 영업점의 특성 및 장단점을 한 눈에 알기 어렵다고 판단 

### 2. Purpose

- 기존 배달 APP의 리뷰 시스템보다 직관적이고 영업점 선별의 편리성을 제공할 수 있는 새로운 리뷰 시스템 구축

### 3. Approach

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
- 임계값(threshold) 수정(0.5 -> 0.55)
- 교차검증(Cross Validation - Stratified K-Fold)

(5) 감성분류 및 키워드 분석(Sentiment Classification & Keyword Analysis)

- 모델을 통한 예측 감성 분류와 실제 감성 분류 비교
- 회귀계수(coef) 값을 이용해 긍정 키워드와 부정 키워드 top5 추출

[리뷰 검색 시스템]

리뷰 시스템에 감성분류와 키워드 분석을 통한 정보를 제공할 뿐만 아니라 배달 APP 사용자들이 원하는 리뷰를 쉽게 검색하여 찾아볼 수 있는 기능 구현

(1) 사용자 입력

![image](https://user-images.githubusercontent.com/87981867/139672339-f8c6be59-4345-4920-b5ab-b0e5b50a1c6b.png)

- input을 통해 사용자 입력을 받아 입력란에 원하는 단어를 입력

(2) 리뷰 출력

![image](https://user-images.githubusercontent.com/87981867/139672562-a52aa1ea-73ea-4ffc-8694-aa1f60a42b21.png)

- '계란찜' 이라는 단어를 검색하여 '계란찜'이 포함된 리뷰들을 모두 출력
- 음식의 카테고리, 영업점명, 사용자ID, 리뷰, 별점과 함께 출력

[리뷰 시스템 UX/UI 디자인 설계]

: 새로 개발한 기능들을 기반으로 새로운 리뷰 시스템 디자인 
![image](https://user-images.githubusercontent.com/87981867/145213902-34e9d767-e695-42fb-9691-3e1c10981628.png)


[설문조사]

: 2~30대 남/여 50명을 대상으로 배달 APP 리뷰 시스템의 개선 여부에 대한 설문조사 실시(2021.11.03 ~ 2021.11.10)
![image](https://user-images.githubusercontent.com/87981867/144854592-78c9e26a-1cc6-42a5-88c8-0b7ea5bfd6a6.png)

### 4. Result

- 예측 감성과 실제 감성 분류하여 모델이 분류한 감성분류를 비교한 결과 모델의 분류 정확도가 높음을 확인
- 다른 영업점 데이터를 통한 분석 모델 검증 완료
- 목표로 한 기능이 전부 포함된 프로토타입 제작 완료
- 20~30대 남녀 50명 대상 설문조사 결과 개선된 기능 및 요소에 대해 긍정적 반응 확인

### 5. Conclusion

[개선 결과]

(1) 기존보다 직관적으로 요약 정보를 나타내며 필요한 정보를 찾을 수 있게 하여 영업점 선별 용이성 제공

(2) 영업점의 유지해야할 서비스와 개선해야할 서비스 피드백 제공

(3) 배달 APP 신규 이용자의 유입 기대

[한계점]

(1) 리뷰 이벤트 실시로 인해 긍/부정 데이터 불균형 -> 기술적 해결보다는 리뷰 이벤트 정책의 개선 필요

(2) 설문 조사 결과 기존 리뷰 시스템에 대한 인식이 나쁘다고 보기 어려움 -> 기존 시스템에서 어떤 요소가 불편한지 구체적 조사 필요
