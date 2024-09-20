# ML_BANK

## 1. pycaret으로 최적의 모델 선별
![image](https://github.com/user-attachments/assets/2ee884b1-385c-4ac3-b2da-2026dbb32dee)


## 2. optuna로 각 모델의 Best Params 확인
### 2-1. Gradient Boosting Classifier(GBC)
![image](https://github.com/user-attachments/assets/82e46f33-4133-40d2-9fe8-a7c664b00770)



   
### 2-2. Light Gradient Boosting Machine(LightGBM)
![image](https://github.com/user-attachments/assets/e38fd851-9a93-4eaa-9a79-6cdf316203a4)






### 2-3. Random Forest Classifier(RF)
![image](https://github.com/user-attachments/assets/b37aacf1-280d-4308-b453-c279176c298b)




---
### 3. 트러블슈팅 및 개선점
- 스케일링과 인코딩 : train과 test를 분리하고, 각각 수치형/범주형 데이터로 나눠 스케일링과 인코딩 진행 -> pycaret에서 만들어진 데이터 불러오기
- pycaret에서 xgboost와 catboost도 적용 모델로 포함시키는 과정
- optuna로 하이퍼파라미터 조정 : 기준점이 accuracy인데 optuna.create_study(direction='minimize')로방향 설정 오류 -> direction='maximize'로 수정
- 최대 accuracy RF의 0.7429083308450284로 별로 큰 효과를 거두지 못함
- 전처리 과정에서 이상치 처리해보기
- catboost도 하이퍼파라미터 조정해보기
 
