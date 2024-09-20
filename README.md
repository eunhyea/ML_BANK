# ML_BANK
<br>
ML 모델 최적화
데이터셋 출처 : https://www.kaggle.com/datasets/janiobachmann/bank-marketing-dataset?select=bank.csv  

<br><br>

## 1. pycaret으로 최적의 모델 선별
![image](https://github.com/user-attachments/assets/2ee884b1-385c-4ac3-b2da-2026dbb32dee)

<br><br>

## 2. optuna로 각 모델의 Best Params 확인

### 2-1. Gradient Boosting Classifier(GBC)
![image](https://github.com/user-attachments/assets/82e46f33-4133-40d2-9fe8-a7c664b00770)



   
### 2-2. Light Gradient Boosting Machine(LightGBM)
![image](https://github.com/user-attachments/assets/b2788791-39ec-480f-985c-edbc1db52f1f)




### 2-3. Random Forest Classifier(RF)
![image](https://github.com/user-attachments/assets/986bd278-b579-43bd-922c-425d1bca9e37)

<br><br>

## 3. feature selection 진행 후 다시 optuna

### 3-1. Gradient Boosting Classifier(GBC)
![image](https://github.com/user-attachments/assets/eedca1b9-734d-4902-9520-636196865eb5)


### 3-2. Light Gradient Boosting Machine(LightGBM)
![image](https://github.com/user-attachments/assets/70a1861d-0b76-4968-b055-dea2782dd41a)



### 3-3. Random Forest Classifier(RF)
![image](https://github.com/user-attachments/assets/675886f7-785c-476e-8d28-1f621f5a6e38)

<br><br>


## 4. 트러블슈팅 및 개선점
- 스케일링과 인코딩 : train과 test를 분리하고, 각각 수치형/범주형 데이터로 나눠 스케일링과 인코딩 진행 -> pycaret에서 만들어진 데이터 불러오기
- pycaret에서 xgboost와 catboost도 적용 모델로 포함시키는 과정
- optuna로 하이퍼파라미터 조정 : 기준점이 accuracy인데 optuna.create_study(direction='minimize')로방향 설정 오류 -> direction='maximize'로 수정하거나 -accuracy를 반환하도록 수정
- 최대 accuracy RF의 0.7429083308450284로 별로 큰 효과를 거두지 못함
- 전처리 과정에서 이상치 처리해보기
- catboost도 하이퍼파라미터 조정해보기
 
