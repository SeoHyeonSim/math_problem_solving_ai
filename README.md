# 수학 문제 풀이 AI 모델 

## 프로젝트 개요

해당 프로젝트는 수학문제를 투입 시, 문제의 자세한 풀이 과정과 답을 제공하여, 문제를 이해하고 정확한 풀이를 공부할 수 있게끔 하여 학생의 수학 학습을 보조하는 것을 목표로 합니다. 수학 문제, 문제 풀이, 정답으로 구성된 데이터셋을 학습시키고, 모델이 정답과 함께 자세한 풀이를 제공하도록 프롬프트를 투입하여, 사용자가 이해하기 쉬운 방식으로 답변을 반환하도록 설계하였습니다. 

---

## 🎯 목표

- 수학 문제를 학습하여 정확히 정답을 예측하는 AI 모델 구축.
- 사용자가 이해할 수 있도록 자세한 풀이를 제공하도록 프롬프트 구성 
- 학습 효율성을 개선하기 위해 **PEFT 기법 적용**.
- 학습 과정 모니터링 및 실험 기록을 위해 **Weights & Biases (wandb)** 사용.

---

## 📊 데이터셋 구성

https\://www\.kaggle.com/datasets/awsaf49/math-qsa-dataset

     
     problem                   수학 문제
     
     level                     문제 난이도
     
     type                      문제 유형

     solution                  문제의 풀이

     answer                    문제의 정답

---

## 📈 모델 구조 및 학습 방법

### 1. 사용된 모델: **Transformer 기반 모델 (GPT-2, BERT 등)**

- `transformers` 라이브러리의 `AutoModelForCausalLM`, `AutoTokenizer` 를 사용하여 모델을 정의합니다.
- 모델은 문장을 학습하여 문제와 답변 사이의 관계를 학습합니다.

### 2. 파인튜닝 기법: **PEFT (Parameter-Efficient Fine-Tuning)**

- 경량화된 모델 학습을 위해 **LoRA (Low-Rank Adaptation)** 방식을 사용합니다.
- 일부 파라미터만 학습시키기 때문에 학습 속도가 빠르고 메모리 사용이 적습니다.

### 3. 학습 과정 모니터링: **Weights & Biases (wandb)**

- 학습 과정에서 발생하는 손실 값, 정확도 등을 기록하고 시각화합니다.

---

## 🔍 모델 학습 및 평가

### 1. 학습 과정

- 모델은 학습 데이터를 기반으로 학습되며, PEFT 기법을 사용하여 효율적으로 학습합니다.
- 다양한 하이퍼파라미터 설정을 통해 최적의 모델을 탐색합니다.

### 2. 평가 방법

- 평가 지표: **정확도 (Accuracy)** 또는 **F1-score**
- 학습 및 평가 결과는 Wandb를 통해 시각화합니다.

---

## 📌 사용 방법

1. 리포지토리 클론하기:

```bash
$ git clone https://github.com/your-repo/math-ai-model.git
```

2. 필요한 라이브러리 설치:

```bash
$ pip install -r requirements.txt
```

3. 모델 학습:

```bash
$ python train.py
```

4. 예측 수행 및 결과 저장:

```bash
$ python predict.py
```

---

## 🚀 향후 개선 사항

- **모델 개선:** 더 큰 모델 (예: GPT-3) 사용하여 학습 성능 향상.
- **데이터 증강:** 데이터셋의 크기를 늘려 모델의 일반화 능력 향상.
- **다양한 모델 비교:** 다른 Transformer 모델과의 성능 비교 실험.

---

## 📜 라이선스

이 프로젝트는 MIT 라이선스에 따라 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 확인하세요.

---

## 🙏 감사의 말

- 이 프로젝트는 Kaggle의 Math QSA Dataset을 활용하여 개발되었습니다.
- 모델 학습을 위해 `transformers`, `PEFT`, `Wandb` 등의 라이브러리를 사용하였습니다.

