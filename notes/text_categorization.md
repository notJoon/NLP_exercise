# 📄 텍스트 분류(Text Categorization)
텍스트 분류는 자연어처리에서 실생황과 가장 밀접하고 중요한 분야 중 하나이다.
예시)
    1. 스팸 메일 분류 
    2. 영화평 긍정/부정 분류 
    3. 감정 분석 

## 텍스트 분류란?
문장 또는 문서를 입력으로 받아 사전에 정의된 클래스 중에 어디에 속하는지 분류하거나 군집화하는 과정.

* 분류(Classification)
    - 사전에 정의된 클래스 중 어디에 속하는지 판단
    - 지도학습
    - K-NN, SVM, Decision Tree, Logistic Regression ... 

* 군집화(Clustering)
    - 항목들 간의 유사 정도를 분석하여 분류
    - 비지도학습
    - K-means, K-medoids, DBSCAN, 병합적 군집, 분할적 군집 ... 

## 감정분석(Sentiment Analysis)이란?
문장 또는 지문과 같은 텍스트에 나타난 사람들의 태도, 의견, 성향과 같은 데이터를 분석하는 방법

주로 SNS 분석, 영화평 분석등에 사용된다. 또한 이러한 과정을 통해 여론을 파악하고 이에 따른 전략, 정책 등을 수립할 수 있다. 

### 감정분석의 어려움 
 - 사람의 주관을 파악
 - 중의적인 표현 
 - 주변 상황 정보, 문맥에 따른 정보도 파악해야 하는 것의 어려움 

 ## 텍스트 분류 과정 
  - 전처리: 오탈자 교정, 띄어쓰기, 불용어 제거 
  - 토큰화: 품사태깅, 개체명 인식, 구문 분석기, N-gram, regexp 
  - 특징 값 추출: TFIDF, Information Gain, Mutual Info., Chi square, GINI, Bag of Words 

    * Bag of Words: 단어들의 순서 고려없이 출현 빈도에만 집중하는 텍스트 데이터의 수치화 표현 방식이다.

  - 학습: SVM, Decision Tree, Naive bayes, ANN 

 ### 학습 과정 
  전처리 -> 토큰화 -> 특징 값 추출 -> 학습
  
 ### 분류 과정 
  전처리 -> 토큰화 -> 특징 값 추출 -> 분류 

 ### 전체 과정
  학습과정 -> 모델 -> 분류과정 

## 대표적인 알고리즘
### 분류
- Naive-Bayes
    특성들 사이의 독립을 가정하는 베이즈 정리를 적용한 학률 분류기 
    * 분류기의 종류: 다중분포 나이브 베이즈, 베르누이 나이브 베이즈, 가우시안 나이브 베이즈
    - 다중분포 NB: 주로 문서 분류 문제에 쓰임
    - 베르누이 NB: 예측변수가 boolean 변수 
    - 가우시안 NB: 예픅 변수가 연속 값을 취하고 불연속적이지 않은 경우, 가우스 분포에서 샘플링 된 것으로 가정 

- Support Vector Machine(SVM)
    주어진 데이터 집합을 바탕으로 새로운 데이터가 어느 카테고리에 속할지 판단하는 비확률적 이진 선형 분류 모델을 만듦. 

- KNN
    분류 및 회귀 예측 문제 모두 사용 가능. 하지만 주로 산업의 분류 예측에서 사용      
        * 자연학습 알고리즘-KNN: 특수 학습 단계 없음. 지연학습 알고리즘 
        * 비모수적 학습 알고리즘-KNN: 기본 데이터에 대해 아무 것도 가정하지 않음. 확률 분포의 개념을 사용하지 않은 비모수적 학습 알고리즘.

- 결정트리(Decision Tree) 
    의사결정 규칙과 그 결과들을 트리구조로 찾는 것

- Stochastic Gradient Descent (SGD)
    데이터에 대한 매개변수를 평가하고 값을 조정하면서 손실함수를 최소화 하는 방법 

- Random Forest
    여러 개의 결정 트리들을 임의로 학습하는 앙상블(Ensemble) 학습방법

### 군집화 
- K-means
    주어진 데이터를 k개의 클러스터로 묶는 알고리즘
    각 클러스터와 거리 차이의 분산을 최소화 하는 방식으로 동작 
    * 분할법: 주어진 데이터를 여러개의 파티션으로 나누는 방법 