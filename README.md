#  Youtube View Predictor (ML & Rule-Based)

> **유튜브 제목 데이터를 기반으로 조회수를 예측하는 머신러닝 및 룰베이스 모델 구축 프로젝트입니다.**

---

##  프로젝트 소개

이 프로젝트는 유튜브 트렌딩 영상 데이터를 활용하여 **조회수가 오를만한 영상을 예측**하는 모델을 구축하는 데 목적이 있습니다.  
단순한 단어 기반 가중치 룰베이스 방식과, BERT 임베딩을 활용한 머신러닝 회귀 모델을 비교하여 성능을 분석했습니다.

###  주요 기능
- 유튜브 영상 제목 기반 전처리 및 피처 추출
- BERT 기반 텍스트 임베딩 생성
- 선형 회귀 / 랜덤 포레스트 모델 학습 및 성능 비교
- Rule-Based 단어 사전 기반 점수화 예측 모델 구현

---

##  기술 스택

| 분야        | 기술 |
|-------------|------|
| 언어        | Python |
| 데이터 처리 | pandas, numpy |
| 머신러닝    | scikit-learn, RandomForestRegressor, LinearRegression |
| 텍스트 임베딩 | Huggingface Transformers (`bert-base-uncased`) |
| 시각화      | matplotlib, seaborn |
| 데이터 출처 | [USvideos.csv - YouTube Trending Data (Kaggle)](https://www.kaggle.com/datasets/datasnaek/youtube-new) |

---

##  모델 성능 요약

| 모델 | RMSE | R² | Spearman |
|------|------|----|----------|
| Linear Regression | 1.43 | 0.31 | 0.53 |
| Random Forest | **0.53** | **0.88** | **0.87** |


---

##  주요 시사점

- 단순한 제목 정보만으로도 조회수 예측 가능성이 존재함
- Rule-Based 방식은 설명이 쉬우나 성능은 낮고, BERT + ML 기반 모델이 훨씬 높은 예측력을 가짐
- 향후 썸네일 이미지, 설명란, 카테고리 등 다양한 feature를 추가할 경우 성능 향상 가능성 있음

---

##  실행 방법 요약

1. Python 환경 및 필요 라이브러리 설치
2. `USvideos.csv` 파일 로드
3. 제목 텍스트 → BERT 임베딩
4. 회귀 모델 학습 및 평가 수행
5. 결과 시각화 및 비교

---

##  향후 개선 방향

- 썸네일 이미지 feature 추가
- 제목 내 키워드의 시계열적 변화 반영
- Shorts vs 일반 영상 등 유형별 분류 추가
