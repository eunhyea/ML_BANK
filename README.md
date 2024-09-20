# ML 최적화 프로젝트
<br>  

> 우리fis 아카데미_ ai엔지니어링 <br> 팀원 :
> [@kimnagyeong99](https://github.com/kimnagyeong99) 
> [@juyeon0312](https://github.com/juyeon0312) 
> [@MINGYUNGEUN](https://github.com/MINGYUNGEUN)
<br>

> 데이터셋 출처 : <br>
> https://www.kaggle.com/datasets/janiobachmann/bank-marketing-dataset?select=bank.csv  
<br>

# 프로젝트 소개
- 은행 마케팅 데이터를 사용하여 종속변수 y(deposit)를 예측하는 머신러닝 모델 탐색  
- 하이퍼파라미터 튜닝을 통한 모델 최적화   
<br>

# 사용 모델
- Gradient Boosting 
- Light Gradient Boosting Machine
- Random Forest Classifier
<br>

# 진행과정
## 1. pycaret으로 최적의 모델 선별 - base model 지정
![image](https://github.com/user-attachments/assets/2ee884b1-385c-4ac3-b2da-2026dbb32dee)
<br><br>

## 2. optuna로 각 모델의 Best Params 확인

| 2-1. Gradient Boosting Classifier (GBC) | 2-2. Light Gradient Boosting Machine (LightGBM) | 2-3. Random Forest Classifier (RF) |
| --- | --- | --- |
| ![GBC](https://github.com/user-attachments/assets/82e46f33-4133-40d2-9fe8-a7c664b00770) | ![LightGBM](https://github.com/user-attachments/assets/b2788791-39ec-480f-985c-edbc1db52f1f) | ![RF](https://github.com/user-attachments/assets/986bd278-b579-43bd-922c-425d1bca9e37) |

<br><br>

## 3. feature selection 진행 후 다시 optuna 확인

| 3-1. Gradient Boosting Classifier(GBC) | 3-2. Light Gradient Boosting Machine(LightGBM) | 3-3. Random Forest Classifier(RF) |
| --- | --- | --- |
| ![image](https://github.com/user-attachments/assets/eedca1b9-734d-4902-9520-636196865eb5) | ![image](https://github.com/user-attachments/assets/70a1861d-0b76-4968-b055-dea2782dd41a) | ![image](https://github.com/user-attachments/assets/675886f7-785c-476e-8d28-1f621f5a6e38) |

<br><br>

## 4. 트러블슈팅
- train과 test셋 분리, 각각 수치형/범주형 데이터로 나눠 스케일링과 인코딩 진행<br>
  **-> pycaret에서 만들어진 데이터 불러오기**
- pycaret에서 xgboost와 catboost도 포함시켜서 모델링하기<br>
  **-> 추가로 모델 install 진행**
- optuna로 하이퍼파라미터 조정 방향 설정 오류<br>
  **-> direction='maximize'로 수정하거나, -accuracy를 반환하도록 수정**

<br>

## 5. 추가적인 디벨롭 필요
- 최대 accuracy가 RF의 0.7429083308450284로 별로 큰 효과를 거두지 못함
- 전처리 과정에서 이상치 처리해보기
- catboost도 하이퍼파라미터 조정해보기
<<<<<<< HEAD
- 앙상블 혹은 소프트 보팅 적용해보기 
=======
- 앙상블 혹은 소프트 보팅 적용해보기 
>>>>>>> d208c74d74039fb30a774bf078a76ef79873ad7c
