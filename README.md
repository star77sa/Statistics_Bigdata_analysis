# Stat_Bigdata_analysis_Competition_2022
[전북대학교 통계학과 빅데이터 분석 경진대회(2022 win)](https://www.kaggle.com/c/statjbnu1), 최우수상

## 1. 혼잡도를 예측하는 모델 구현

### 변수선택

- 전체 변수 : 조사일자(평일인지 주말인지), 호선, 역 번호, 역병, 구분(상선인지 하선이지), 시간별 혼잡도

- 선택 변수 : 조사일자, 호선, 역명 + 역 주변에 버스터미널이 있는지 여부

- 예측 : 하루 평균 혼잡도

*기계학습을 이용한 서울 지하철 승하차 인원 예측* 논문에 따르면 역 주변에 버스터미널이 있는지 여부가 혼잡도에 영향을 미친다는 내용을 발견하여 이에 해당하는 변수를 만들어서 사용하였습니다.

### 모델

- 선형회귀, MSE : 72.105

- 랜덤포레스트, MSE : 68.459

- 랜덤포레스트의 MSE가 더 낮아 랜덤포레스트 모델을 채택

![image](https://user-images.githubusercontent.com/73769046/156136334-20e0a96b-9f90-40b1-94a1-733a98baab8c.png)

x축 : 예측한 값 , y축 : 정답 값

시간과 데이터 수집의 한계로 부족한 모습을 보이지만 유의한 변수들이 조금 더 추가된다면 더 좋은 성능을 보일 것으로 예상

## 2. 혼잡도와 미세먼지 사이의 관계 분석

### (1) 역 내부, 외부 미세먼지 비교

![image](https://user-images.githubusercontent.com/73769046/156136705-3dcac9c5-93de-426c-b66b-119cb1a075a8.png)

- 외부에 비해 내부 미세먼지가 2배 가량 높은 것을 확인 가능

- 미세먼지 특성상, 높은 기온에서 지표면가 멀어지기 때문에, 기온이 높아지는 아침에 수치가 낮아짐
  
  하지만 지하철 내부 미세먼지 그래프를 보니, 동일 시간대에 오히려 더 높아지는 것을 확인
  이는 지하철 내부의 어떤 원인으로 인해 미세먼지 수치가 올라간다는 것을 예상 가능
 
- 또한 내부 미세먼지는 출퇴근 시간대에 높은 수치를 보임
