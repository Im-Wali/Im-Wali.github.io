---
title:  "[ML] : 05. 앙상블 학습(Ensemble Learning)"
search: false
categories:
  - AI
  - ML
tags:
  - AI
  - ML
  - Machine Learning
  - 앙상블 학습
  - 앙상블
  - Ensemble Learning
  - Ensemble

---
<br/>

## 01. 앙상블 학습
### 1) 앙상블 학습(Ensemble Learning)
  * 앙상블이라는 단어는 프랑스어로 사전적인 의미는 "함께, 동시에, 협력하여" 이다. 보통은 합창단, 무용단, 합주단의 의미로 사용한다. 머신 러닝에서는 약한 분류기(모델)를 여러개로 학습하는 방법의 학습을 앙상블 학습이라고 칭한다.
  <br/>

  * 약한 여러개의 모델을 결합하여 학습하면, 예측들이 결합하여 보다 정확한 예측을 도출할 수 있다. 개별 모델이 가지고 있던 단점을 상쇄할 수 있기 때문에 현재 Kaggle의 상위권에 앙상블 학습을 사용하는 경우가 많다.
  <br/>
  
## 02. 앙상블 방법
### 1) 보팅 (Voting)
  * 여러개의 모델이 투표로 통해서 최종 예측 결과를 결정한다. 투표 방식에 따라서 하드 보팅과 소프트 보팅으로 나눤다. 하드 보팅은 다수의 모델이 예측한 결과를 최종 결과를 선정하는 방식이고 소프트 보팅은 각 모델이 예측한 확률의 평균을 구하고 해당 값을 최종 결과로 선정한다.
  <br/>

  ![image-center](/assets/images/2024-08-12-ML_Ensemble_Learning_01.jpg){: .align-center width="100%" height="100%"}
  <div style="text-align: right"> [참고: https://untitledtblog.tistory.com/156] </div>
  <br/>

  ![image-center](/assets/images/2024-08-12-ML_Ensemble_Learning_02.jpg){: .align-center width="100%" height="100%"}
  <div style="text-align: right"> [참고: https://itwiki.kr] </div>
  <br/>

### 2) 배깅(Bagging)
  * 데이터 샘플링을 통해서 모델을 학습 시키고 결과를 집계하는 방법이다. 학습 중 데이터의 중복을 허용하며, 각 모델은 전체 데이터의 일부로 학습을 진행한다. 같은 구조의 모델이 서로 다른 데이터로 학습한다. 평가를 위해서 어떠한 모델에서도 사용하지 않는 데이터를 사용한다. 이를 Out-of-Bag(OOB)라고 한다.
  <br/>

  ![image-center](/assets/images/2024-08-12-ML_Ensemble_Learning_03.jpg){: .align-center width="100%" height="100%"}
  <div style="text-align: right"> [참고: https://itwiki.kr] </div>
  <br/>

### 3) 페이스팅(Pasting)
  * 배깅과 동일한 방식이지만 배깅과 다르게 모델에서 사용하는 데이터의 중복을 허용하지 않는다.
  <br/>

### 4) 부스팅 (Boosting)
  * 여러개의 모델을 순차적으로 학습을 진행하는 방법이다. 앞순서가 끝나야 다음 순서가 학습이 가능하기 때문에 배깅보다 느리다는 단점이 있지만, 앞서 학습 모델에서 틀린 예측을 다음 순서의 모델에서 보완할 수 있다는 장점이 있다. 또한 앞서 학습 모데의 가중치를 부여하기 때문에 겹겹히 겹쳐서 학습하기 때문에 정확도가 높다.
  <br/>
  ![image-center](/assets/images/2024-08-12-ML_Ensemble_Learning_04.jpg){: .align-center width="100%" height="100%"}
  <div style="text-align: right"> [참고: https://esj205.oopy.io/] </div>
  <br/>

  * **에이다 부스트(Adaboost)**
    - 이진 모델의 틀린 데이터의 학습 효과를 높이기 위해서 다음 모델에 가중치(Weight)를 부여하는 방식이다.
  ![image-center](/assets/images/2024-08-12-ML_Ensemble_Learning_05.jpg){: .align-center width="100%" height="100%"}
  <div style="text-align: right"> [참고: https://www.analyticsvidhya.com/blog/2022/01/introduction-to-adaboost-for-absolute-beginners/] </div>
  <br/>

  * **그래디언트 부스트(Gradient boost)**
    - 그래디언트 부스트는 잔차(Residual)를 학습한다. 경사 하강법과 비슷한 방식으로 이전 모델의 잔차를 가중치로 활용하여 학습한다.
  ![image-center](/assets/images/2024-08-12-ML_Ensemble_Learning_06.jpg){: .align-center width="100%" height="100%"}
  <div style="text-align: right"> [참고: https://www.geeksforgeeks.org/ml-gradient-boosting/] </div>
  <br/>

### 5) 스태킹 (Stacking)
  * 앙상블 마지막에는 각 모델의 결과를 취합하는 단계가 있는데 이 단계에서 함수를 사용하는 방식으로, 스태킹은 각 모델의 출력을 입력으로 하여 Target을 출력하는 방법이다.
  <br/>
  ![image-center](/assets/images/2024-08-12-ML_Ensemble_Learning_07.jpg){: .align-center width="100%" height="100%"}
  <div style="text-align: right"> [참고: https://www.scaler.com/topics/machine-learning/stacking-in-machine-learning/] </div>
  <br/>
  
## 05. 끝마치며
  * 이번 포스팅에서는 앙상블 학습에 대해서 알아 보았다. 유명한 딥러닝 모델들도 결국에는 앙상블 방법과 같이 여러개의 모델 혹은 계층을 쌓아서 사용한다. 이와 같이 어떠한 문제를 해결하기 위해서는 각 모델들의 특징을 알고 잘 활용하는것이 중요하다는 생각이 들었다.
