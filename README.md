# BigContest-2022

2022 빅콘테스트 데이터 분석 분야 퓨쳐스 리그 우수상
: 대출 지원 핀테크 기업 Finda의 앱 사용성 data와 사용자 data를 통한 대출 상품 별 신청 여부 예측 분석

### 발표 영상
<div>
<a href="https://youtu.be/XwjPwGqD09w?t=44" target="_blank">
  <img width="424" alt="핀테크 대출 상품 비교 발표 영상" src="https://github.com/user-attachments/assets/3715c2a0-7119-4e64-9239-e17bde04aaa3" />
</a>

# 📊 Loan Application Prediction (2-Stage Modeling)

## 🧩 Problem Overview

본 프로젝트는 총 1,048,576개의 (application_id, product_id) 쌍에 대한 대출 신청 여부를 예측하는 이진 분류 문제입니다.
그러나 단순한 classification 문제가 아닌, 다음과 같은 구조적 특징을 갖습니다:

- 하나의 User는 여러 개의 신청서를 생성
- 하나의 신청서는 여러 개의 대출 상품을 추천
- 각 상품에 대해 신청 여부를 개별적으로 예측해야 함

즉, 데이터는 다음과 같은 계층 구조를 가집니다:
- User → Application → Loan Products

각 상품의 선택은 독립적이지 않고, 동일 신청서 내 다른 상품들과의 **상대적 비교**에 의해 결정됩니다.

> 단일 모델로 해결하기 어려운 문제를 다음과 같이 분리:

### 🔹 Stage 1: "무의미한 신청서 제거"
- 어떤 신청서는 어떤 상품도 선택하지 않음
- 이런 샘플을 미리 제거 → UnderSampling

### 🔹 Stage 2: "상품 선택 여부 예측"
- 의미 있는 신청서만 대상으로 정밀 예측

## 🧪 Key Point
- 실제 앱 사용 경험을 기반으로 Feature 설계
- 데이터 구조를 "문제 정의" 단계에서 재해석
- 모델보다 데이터 설계가 성능을 좌우함을 경험

## ⚙️ Execution Environment

- Platform: Google Colab
- Python: 3.10 (Colab default at the time)

### GPU
- NVIDIA Tesla T4

### Libraries
- pandas
- numpy
- lightgbm
- scikit-learn
- imblearn (SMOTE)
- optuna
- pycaret
- torch (AutoEncoder)



## 대회 설명
<img width="1217" height="638" alt="image" src="https://github.com/user-attachments/assets/ffa5f633-d657-4403-bd1a-65d4a2f1adb2" />
<img width="1207" height="583" alt="image" src="https://github.com/user-attachments/assets/2cb55829-506a-478d-820a-a771c84c39be" />
<img width="1232" height="641" alt="image" src="https://github.com/user-attachments/assets/52d707e5-1434-4521-98e8-f906a675ea3c" />
<img width="1112" height="587" alt="image" src="https://github.com/user-attachments/assets/2ecf7512-d573-4fe6-a4bf-6832150ab638" />

## 문제 분석
<img width="1920" height="1080" alt="007" src="https://github.com/user-attachments/assets/bfd2b3b9-a64b-4ba3-8a0c-c256ced2bcec" />
<img width="1920" height="1080" alt="009" src="https://github.com/user-attachments/assets/9ab4dd9e-1306-4418-96cf-19c75ebd20a8" />
<img width="1920" height="1080" alt="010" src="https://github.com/user-attachments/assets/f54793dd-9201-478e-8464-52cb96b63d6d" />

## DATA 전처리
<img width="1920" height="1080" alt="033" src="https://github.com/user-attachments/assets/36431bf0-9eca-4222-a099-ebae2a021f1f" />
<img width="1920" height="1080" alt="034" src="https://github.com/user-attachments/assets/0bb489ef-e450-45cc-bae0-c1955d7b070f" />
<img width="1920" height="1080" alt="035" src="https://github.com/user-attachments/assets/31ad6316-ecba-49cd-8b3e-452c206ff0a4" />

## STAGE 1. 대출을 1개도 신청하지 않을 신청서 분류를 통한 Under Sampling
<img width="1920" height="1080" alt="데이터분석분야_퓨처스부문_FIELData_결과보고서_복사본-039" src="https://github.com/user-attachments/assets/5017fcb7-d420-46bd-98a8-df008d51c18f" />

## STAGE 2. Auto Encoder와 LGBM을 통한 대출 상품 별 대출 신청 여부 예측
<img width="1920" height="1080" alt="046" src="https://github.com/user-attachments/assets/11907945-0ad3-4c2a-969d-e93cdef6934b" />
<img width="1920" height="1080" alt="049" src="https://github.com/user-attachments/assets/44e0e9da-53bd-4663-962a-d5186092a08b" />
<img width="1920" height="1080" alt="052" src="https://github.com/user-attachments/assets/42e65655-3dd0-436b-a1bb-6eeea9fea3a9" />



