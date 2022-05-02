# 03 사이킷런 기반 프레임 워크 익히기
1. 주요 모듈
    - 피처 처리: 
        - preprocessing
        - feature_selection
        - feature_extraction
        - decomposition
    - 데이터분리, 파라미터 튜닝, 검증
        - model_selection
    - 평가
        - metrics
    - ML 알고리즘
        - ensemble
        - linear_model
        - navie_bayes
        - neighbors
        - svm
        - tree
        - cluster
    - 유틸리티
        - pipeline
2. 머신러닝 프로세스
    - 피처 가공, 변경, 추출
    - ML 알고리즘 학습/예측 수행
    - 모델 평가
# 04 Model Selection 모듈 소개
1. train_test_split
2. 교차검증
    - KFold
    - Stratified K: 불균형한 클래스로 교차검증이 이루어질경우 균형있게 나누기위해 사용, 회귀모델에서는 안됨
    - cross_val_score, cross_validate: 교차검증에서의 추가 코드를 없애기위해 만듦 반복학습및 예측수행하는 코드를 한번에 해서 KFold만큼 실행함
3. GridSearchCV
    - 교차검증 + 하이퍼 파라미터 튜닝
    - N개의 폴딩세트에서 성능 수치를 평균화해서 그 순간 하이퍼파라미터 정확도를 나타낸것
# 05 데이터 전처리
1. 결손값 처리
2. 데이터 인코딩
    - 레이블 인코딩: 1,2,3,4
        - 선형회귀와같은 알고리즘에서는 적용하면안됨, 큰숫자도 데이터로 들어가기떄문
    - 원핫 인코딩: 열당 하나만 표시
3. 피처스케일링 정규화
    - 표준화: 평균 0, 분산 1인 가우시안 정규분포를 가진값으로 변환
        - SVM, Linear Regression, Logistic Regression등은 데이터가 가우신 분포를 가지고 있다 구현하였기때문에 사전 표준화는 중요함
    - 정규화: 0 ~ 1 사이의 값으로 변환
    - **가능하다면 전체 스케일링 변환을 적용한 후 테스트 데이터로 분리**
    - **위항목이 불가능하다면 fit이나 fit_transform을 적용하지 않고 학습데이터로 이미 fit된 Scaler객체를 이용해 transform 변환**
