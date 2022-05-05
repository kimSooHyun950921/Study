# 03 평가
## 01 정확도 (Accuracy)
-  $$ acc= \frac{예측결과가 동일한 데이터 건수}{전체 데이터건수}$$
- 문제 데이터셋만 치우치게 학습을 해도 정확도가 높아짐 --> 실제 높다고 할 수 없음
## 02 오차행렬 (confusion matrix)
- 예측 오류가 얼마인지 도불어 어떤 유형의 예측 오류가 발생하고 있는지 함께 나타내는 지표
- confusin matrix 사분면
    - TN: 예측값을 Negative로 잘 예측함(True)
    - TP: 예측값을 Positive로 잘 예측함(True)
    - FP: 예측값을 Positive로 잘못 예측함 (False)
    - FN: 예측값을 Negative로 잘못 예측함 (False)
- $$acc=\frac{TN+TP}{TN+TP+FP+FN}$$
- 정밀도
    - 예측을 얼마나 정밀하게 잘했는가?
    - $$precision=\frac{TP}{TP+FP}$$
    - FP가 커지면 정밀도가 낮아짐 
    - 즉, Positive로 예측한것중 잘못예측한것이 커지면 정밀도가 낮아짐
- 재현율
    - 실제 Postive값을 얼마나 똑같이 예측했는가?
    - $$recall = \frac{TP}{TP+FN}$$
    - FN이 이 커지면 재현율이 낮아짐
    - 즉, 실제 positive값을 잘못예측한것이 커지면 재현율이 낮아짐
- 정밀도 재현율 trade off
    - 거의대부분 Positive로 예측하면 재현율이 커지고 정밀도가 낮아짐
    - 거의대부분 Negative로 예측하면 정밀도가 커지고 재현율이 낮아짐
    - 정밀도/재현율을 결정하는 threshold를 잘정해야함
## 03 F1 스코어
- 정의: 정밀도와 재현율을 결합한 지표
- $$ F1 = \frac{2}{\frac{1}{recall}+\frac{1}{precision}} = 2*\frac{precision*recall}{precision+recall}
## 05 ROC 커브와 AUC
- TPR
    - true positive rate
    - 실제 positive 값을 positive로 잘 예측한(true) 비율 = recall
- FPR
    - false positve rate
    - 실제 negative 값중 positive로 잘못 예측한 비율
- ROC curve
    - x축: FPR
    - y축: TPR
    - FPR이 0부터 100까지 움직일때 TPR의 결과
    - ROC 커브가 직선형태로 x=y형태가 될수록 성능이 안좋은것
- AUC curve
    - Area Under Curve
    - ROC 커브 하단의 면적
    - FPR이 작은상태에서 얼마나 TPR이 크게 되는지가 문제 
        - 임계값을 1로변경하면 모두 negative로 예측하므로 FPR이 0이됨
        - 임계값을 0으로변경하면 모두 positive로 예측하므로 FPR이 1이됨
    - 1에 가까워지면 좋은 분류
    - 0.5에 가까워지면 랜덤수준의 분류