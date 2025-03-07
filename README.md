# LG_Aimers_6th  
**LG Aimers 6기 온라인 해커톤**


## 🖥️ 프로젝트 소개

<div align="center">
  <img src="https://github.com/user-attachments/assets/537effae-1740-4f6a-89a8-2b216e35c22e" alt="프로젝트 이미지" width="60%">
</div>

<div align="center">
  <img src="https://github.com/user-attachments/files/19124176/LG.AI.pdf" alt="프로젝트 이미지" width="60%">
</div>

### 프로젝트 정보

- **주제:** 난임 환자 대상 임신 성공 여부 예측  
- **주최:** LG Aimers, 데이콘  
- **기간:** 2025.02.01 ~ 2025.02.27 09:59  
- **참가자 수:** 1570명

## 👥 팀원
Team: **"흐헤히"**(5명)
| 진영인 | 이재훈 | 임소영 | 김민서 | 양진주 |
|:------:|:------:|:------:|:------:|:------:|
| [GitHub](https://github.com/0in11) | [GitHub](https://github.com/) | [GitHub](https://github.com/maeng99) | [GitHub](https://github.com/) | [GitHub](https://github.com/) |

## 📊 데이콘 리더보드 성적

<div align="center">
  <img src="https://github.com/user-attachments/assets/c84b247a-c5ba-42ee-a1ee-e67ada919cf2" alt="프로젝트 이미지" width="60%">
</div>

<div align="center">
  총 794팀 중 53등 → 상위 약 6.67% 달성!
</div>

## 🗂️ 프로젝트 구조

```
  ├── data/
  │   ├── train.csv              # 학습용 데이터
  │   └── test.csv               # 테스트용 데이터
  ├── src/
  │   ├── preprocess.ipynb           # 데이터 전처리
  │   ├── tuning.ipynb               # 하이퍼파라미터 튜닝
  │   └── ensemble.ipynb             # 앙상블 모델
  ├── submissions/
  │   └── sample_submission.csv    # 제출 파일 양식
  ├── requirements.txt            # 필요 패키지 목록
  └── README.md                   # 프로젝트 설명 및 결과 요약
```

## ⚙️ 모델링

- **데이터 전처리:**  
  - 결측치 비율이 99% 이상인 컬럼은 제거하여 노이즈를 줄임
  - 남은 결측치는 0으로 채워 데이터의 일관성을 확보
  - 수치형 변수는 MinMaxScaler를 사용하여 정규화 처리
  - 범주형 변수는 LabelEncoder를 사용하여 수치형 데이터로 변환

- **모델:**  
  - 다양한 시드와 하이퍼파라미터 변화를 반영한 XGBoost 앙상블 모델을 구축
  - 여러 실험을 통해 모델의 안정성과 예측 성능을 극대화

- **하이퍼파라미터 튜닝:**  
  - Optuna를 활용하여 체계적이고 효율적인 튜닝을 진행  
  - 최적의 파라미터 조합을 도출하여 모델 성능을 한층 업그레이드

## 🚀 성능 평가 및 오버피팅 분석

### 오버피팅 분석
- **검증 점수 평균:** 0.7400
- **검증 점수 표준편차:** 0.0004 (위험도: 낮음)
- **학습-검증 점수 차이:** 0.0041 (위험도: 낮음)
- **극단적 예측 비율:** 17.72% (위험도: 낮음)
- **모델간 성능 범위:** 0.0014 (위험도: 낮음)
- **종합 오버피팅 위험도:** 0.00 (0~1)
- **가중치 기반 예측 사용:** 오버피팅 위험 매우 낮음

### 최종 모델 성능
- **Out-of-fold AUC:** 0.7220

## 🔧 개선점
- 모델 성능 향상을 위해 다양한 데이터 전처리 기법 혹은 피처 엔지니어링을 더욱 적극적으로 시도해볼 것
