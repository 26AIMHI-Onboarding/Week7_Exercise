# Week 7 Onboarding 실습 가이드

7주차 신경망 학습 실습에 오신 것을 환영합니다!

이 실습은 신경망의 순전파부터 시작하여 역전파를 통한 효율적인 학습까지 단계적으로 진행됩니다.

## 📋 실습 순서

### 1단계: 2층 신경망 구조 이해 (ch04)
수치 미분을 사용하여 신경망의 학습 원리를 이해합니다.

```
ch04/
├── two_layer_net.py        # 2층 신경망 클래스 구현 
├── train_neuralnet.py      # 신경망 학습 메인 스크립트
├── visualize_weights.py    # 은닉층 가중치 시각화 
├── visualize_digits.py     # 숫자별 형상 시각화 
└── sample_weight.pkl       # 샘플 가중치 파일
```

**실습 순서:**
1. `two_layer_net.py` - 순전파, 손실 함수, 정확도 계산 구현
2. `train_neuralnet.py` - 미니배치 학습 및 파라미터 업데이트
3. `visualize_weights.py` - 은닉층 뉴런이 학습한 패턴 관찰
4. `visualize_digits.py` - 각 숫자(0~9)의 학습된 형상 확인

### 2단계: 역전파 이해 (ch05)
계층 기반 구조로 효율적인 역전파를 구현합니다.

```
ch05/
├── two_layer_net.py        # 역전파 기반 2층 신경망 (빈칸 없음 - 읽기)
└── visualize_filter.py     # 필터 시각화 
```

**실습 순서:**
1. `two_layer_net.py` - 역전파 구현 코드 읽고 이해하기
2. `visualize_filter.py` - 학습된 필터의 특징 관찰

### 3단계: 공통 모듈 활용 (common)
신경망 구현에 필요한 다양한 함수와 레이어를 제공합니다.

```
common/
├── functions.py      # 활성화 함수, 손실 함수 등
├── gradient.py       # 수치 미분 함수
├── layers.py         # Affine, ReLU, SoftmaxWithLoss 레이어
└── util.py          # 기타 유틸리티
```

**주요 함수:**
- `sigmoid()`, `softmax()` - 활성화 함수
- `cross_entropy_error()` - 손실 함수
- `numerical_gradient()` - 수치 미분
- 각종 레이어 클래스 (Affine, Relu, SoftmaxWithLoss 등)

**⚠️ 중요:** 이미 구현되어 있는 모듈을 import하여 사용합니다!

### 4단계: MNIST 손글씨 인식 (dataset)
실제 데이터로 신경망을 학습시킵니다.

```
dataset/
├── mnist.py          # MNIST 데이터 로더
└── mnist.pkl         # MNIST 데이터셋 파일
```

**데이터 정보:**
- 훈련 데이터: 60,000개
- 테스트 데이터: 10,000개
- 이미지 크기: 28 × 28 픽셀
- 클래스: 0~9 숫자

## 🚀 시작하기

### 환경 설정
```bash
# 필요한 패키지 설치
pip install -r requirements.txt
```

### 실습 진행
```bash
# 1단계: 2층 신경망 구현 (ch04)
cd ch04

# 1-1. two_layer_net.py 빈칸 채우기 (8개)
# 코드를 열어서 ### 빈칸 N ### 부분을 채우세요

# 1-2. train_neuralnet.py 빈칸 채우기 (5개)
# 코드를 열어서 빈칸을 채운 후 실행
python train_neuralnet.py
# → 학습 곡선 그래프 확인

# 1-3. visualize_weights.py 빈칸 채우기 (2개)
python visualize_weights.py
# → 은닉층 뉴런의 패턴 확인

# 1-4. visualize_digits.py 빈칸 채우기 (3개)
python visualize_digits.py
# → 숫자별 학습된 형상 확인

# 2단계: 역전파 이해 (ch05)
cd ../ch05

# 2-1. two_layer_net.py 읽고 이해하기
# 역전파가 어떻게 동작하는지 코드를 읽어보세요

# 2-2. visualize_filter.py 빈칸 채우기 (2개)
python visualize_filter.py
# → 필터 시각화 확인
```

## 📚 학습 목표

### ch04: 신경망 학습 (수치 미분)
- **순전파(Forward Propagation)** 구현
- **손실 함수(Loss Function)** 계산
- **수치 미분**을 통한 기울기 계산
- **SGD(확률적 경사하강법)** 구현
- 학습된 가중치의 의미 이해

### ch05: 역전파 (Backpropagation)
- **계층(Layer) 기반 구조** 이해
- **역전파 알고리즘** 원리 파악
- 수치 미분 대비 **속도 향상** 체감
- 효율적인 기울기 계산 방법 학습

### 전체: 신경망의 핵심 개념
- 2층 신경망 구조 (입력 → 은닉 → 출력)
- 활성화 함수의 역할 (Sigmoid, ReLU, Softmax)
- 미니배치 학습의 효율성
- 학습률과 하이퍼파라미터 조정

## 💡 Tips

1. **순서대로 진행하세요** - ch04 완료 후 ch05로 넘어가세요.
2. **빈칸의 힌트를 활용하세요** - 각 빈칸에 주석으로 힌트가 제공됩니다.
3. **학습 시간을 고려하세요** - train_neuralnet.py는 2~3분 정도 소요됩니다.
4. **시각화를 적극 활용하세요** - 가중치와 필터를 보면 이해가 쉽습니다.
5. **속도 차이를 체감하세요** - ch04와 ch05의 학습 속도를 비교해보세요.

## 📁 프로젝트 구조

```
Week7_Exercise/
├── ch04/              # 신경망 학습 (수치 미분)
│   ├── two_layer_net.py        # 8개 빈칸
│   ├── train_neuralnet.py      # 5개 빈칸
│   ├── visualize_weights.py    # 2개 빈칸
│   ├── visualize_digits.py     # 3개 빈칸
│   └── sample_weight.pkl
├── ch05/              # 역전파
│   ├── two_layer_net.py        # 읽기 전용
│   └── visualize_filter.py     # 2개 빈칸
├── common/            # 공통 모듈
│   ├── functions.py   # 활성화/손실 함수
│   ├── gradient.py    # 수치 미분
│   ├── layers.py      # 레이어 클래스
│   └── util.py
├── dataset/           # MNIST 데이터
│   ├── mnist.py
│   └── mnist.pkl
├── requirements.txt
└── README.md
```

## 📝 빈칸 정리

| 파일 | 빈칸 개수 | 주요 내용 |
|------|-----------|-----------|
| ch04/two_layer_net.py | 8개 | 순전파, 손실, 정확도, 학습 루프 |
| ch04/train_neuralnet.py | 5개 | 하이퍼파라미터, 미니배치, 학습 |
| ch04/visualize_weights.py | 2개 | 은닉층 가중치 시각화 |
| ch04/visualize_digits.py | 3개 | 숫자별 형상 시각화 |
| ch05/two_layer_net.py | 0개 | 역전파 구현 (읽기) |
| ch05/visualize_filter.py | 2개 | 필터 시각화 |

**총 빈칸: 20개**

## 🔍 주요 개념

### 2층 신경망 구조
```
입력층 (784) → 은닉층 (50) → 출력층 (10)
   28×28 픽셀    활성화 함수     0~9 숫자
```

### 활성화 함수
- **Sigmoid**: Ch04에서 사용 (0~1 사이 값)
- **ReLU**: Ch05에서 사용 (음수→0, 양수→그대로)
- **Softmax**: 출력층, 확률로 변환 (합=1)

### 손실 함수
- **Cross Entropy Error**: 예측과 정답의 차이 측정

### 최적화
- **SGD (확률적 경사하강법)**: `W = W - η × ∇W`

### 수치 미분 vs 역전파
- **수치 미분 (Ch04)**: 느리지만 정확 → 검증용
- **역전파 (Ch05)**: 빠르고 효율적 → 실전용

## ⚙️ 요구사항

- Python 3.7+
- NumPy
- Matplotlib

## 🎯 체크리스트

- [ ] ch04/two_layer_net.py 빈칸 8개 채우기
- [ ] ch04/train_neuralnet.py 빈칸 5개 채우기
- [ ] 신경망 학습 실행 및 그래프 확인
- [ ] ch04/visualize_weights.py 빈칸 2개 채우기
- [ ] 은닉층 가중치 패턴 관찰
- [ ] ch04/visualize_digits.py 빈칸 3개 채우기
- [ ] 숫자별 형상 확인
- [ ] ch05/two_layer_net.py 코드 읽고 이해하기
- [ ] ch05/visualize_filter.py 빈칸 2개 채우기
- [ ] 필터 시각화 확인
- [ ] ch04와 ch05 학습 속도 비교

---

**Happy Learning! 🚀**

질문이 있다면 언제든지 문의하세요!