# 🧠 CNN을 이용한 이미지 분류 실습

> Food-101 데이터셋을 활용한 컨볼루션 신경망(CNN) 이미지 분류 실험

---

## 📋 실험 개요

| 항목 | 내용 |
|------|------|
| 데이터셋 | Food-101 (101개 클래스, 약 101,000장) |
| 프레임워크 | TensorFlow 2.19.0 / Keras |
| 실험 환경 | Google Colab (GPU) |
| 입력 크기 | 128×128 RGB |
| 배치 크기 | 64 |
| 옵티마이저 | Adam (lr=0.001) |
| 최대 에폭 | 50 (Early Stopping 적용) |

---

## 🏗️ 모델 구조

4개의 Conv+MaxPooling 블록으로 구성된 CNN

| 블록 | 레이어 | 필터 수 |
|------|--------|---------|
| Block 1 | Conv2D + MaxPooling2D | 32 |
| Block 2 | Conv2D + MaxPooling2D | 64 |
| Block 3 | Conv2D + MaxPooling2D | 128 |
| Block 4 | Conv2D + MaxPooling2D | 256 |
| - | Flatten + Dropout(0.5) + Dense(256) + Dropout(0.5) | - |
| 출력 | Dense(101) + Softmax | - |

- 총 파라미터: 4,608,933개 (17.58MB)
- 손실 함수: `sparse_categorical_crossentropy`

---

## 📊 실험 결과

| 지표 | 값 |
|------|-----|
| 최종 훈련 정확도 | 약 34% (Epoch 29) |
| 최종 검증 정확도 | 약 30% |
| 수렴 구간 | Epoch 25~29 |

- 101개 클래스 분류 문제에서 단순 CNN으로 약 30% 검증 정확도 달성
- 과적합 없이 안정적으로 수렴 (훈련/검증 정확도 차이 5%p 이내)

---

## 🛠️ 사용 기술

![TensorFlow](https://img.shields.io/badge/TensorFlow-2.19.0-FF6F00?logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-FF0000?logo=keras)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python)
![Google Colab](https://img.shields.io/badge/Google%20Colab-GPU-F9AB00?logo=googlecolab)

---

## 📄 실험 보고서

📑 [보고서 보기 (PDF)](./2237004_김송희_CNN과제.pdf)

---

> 본 실험은 AI 이해 수업 과제로 진행되었습니다.
