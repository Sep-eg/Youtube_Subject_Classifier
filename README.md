# 유튜브 자막 데이터를 활용한 영상 주제 분류 프로젝트
딥러닝을 사용한 자연어 분석을 통해 유튜브 강의 영상의 주제를 분류한다.

진행 기간: 2021.06.29 ~ 2021.07.02

프로젝트 진행 배경
---

당근마켓, 네이버 지식in 등을 이용하면 자동으로 글의 카테고리, 주제를 추천해 주는 기능을 볼 수 있다.

만약, 강의 "영상"이라면 어떻게 카테고리 혹은 주제를 어떻게 설정할 수 있을까?

프로젝트 목적
---
유튜브에 업로드되어있는 수학 관련 강의 영상의 자막 데이터를 활용하여 딥러닝 모델을 학습시키고,

이를 통해 강의 영상의 주제를 올바르게 분류한다.

데이터셋
---
데이터는 Kaggle의 [Math Lectures](https://www.kaggle.com/extralime/math-lectures) 데이터를 사용하였다.

해당 데이터는 총 860개 영상의 자막 데이터로 이루어져 있으며

각 영상은 11종류의 수학, CS 분야의 세부 주제로 분류되어 있다.

결과 및 개선방향
---
데이터의 학습은 딥러닝 방법론 3가지, 머신러닝 1가지를 사용하여 진행하였다.

각각 LSTM, TF-IDF 행렬을 이용한 다층 신경망, BERT 모델을 이용한 fine-tuning, TF-IDF 행렬을 이용한 랜덤 포레스트 분류기 학습이다.

최종적으로 각 모델별 테스트 데이터에 대한 정확도는
* LSTM: 0.1541
* TF-IDF with Dense: 0.1376
* BERT fine-tuning: 0.1436
* TF-IDF with RFC: 0.1802

등으로 나타났다.

이는 데이터의 양이 부족한 것이 가장 근본적인 이유로 판단되어 이를 개선하기 위해선
1. 데이터셋을 추가적으로 수집, 라벨링을 진행한다.
2. 라벨을 더 큰 범주로 합하여 라벨의 숫자를 줄인다.

등의 개선방안이 유효할 것으로 생각한다.
