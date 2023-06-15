# Paper
KCC 2023에 oral session에 accept 되었습니다. 출간되는 대로 paper link를 달아놓겠습니다 

# KOME(Korean Online Moral Emotion)
KOTE (Korean Online That-gul Emotions) 데이터셋을, Haidt의 도덕감정(Moral Emotion) 분류로 편집한 멀티라벨(Multi-Labels) 데이터셋입니다.
해당 데이터셋을 KcELECTRA 훈련한 모델도 함께 공개합니다.

### Dataset
- 도덕 감정 분류

| 감정 유형 | 세부 유형 | 감정 |
| --- | --- | --- |
| Moral Emotion | Other-Condemning | anger, contempt, disgust |
|  | Other-Praising | admiration, gratitude |
|  | Other-Suffering | compassion |
|  | Self-Conscious | shame, guilt, embarrassment |
| Nonmoral Emotion | Emotional,but Nonmoral Emotion | care, comport, pride, anxiety, boredom, exhaustion, fear, gessepany, despair, laziness, reluctant, sorrow, fed up |
|  | Neutral | arrogance, resolute, no-emotion,realization, surprise |

- 데이터 개수: 49,663

KOME.parquet 파일을 통해 데이터를 확인할 수 있습니다.

### Model 
도덕감정 분류 모델을 만들기 위해 KcELECTRA  사전학습 모델을 사용하여, 도덕감정 데이터셋을 학습하였습니다. 

각 사전학습 모델을 백본으로 한 멀티 라벨 분류 모델을 도덕감정 분류 데이터셋으로 학습시켜 미세 조정(fine-tuning)하였습니다. 각 모델 학습 시 learning-rate은 2e-5, epoch은 10으로 설정하였다. training / validation / test 데이터셋은 각각 40000 / 5000 / 4663개로 나누어 사용하였습니다.

성능은 F1-Score 기준 0.70을 기록했습니다.
[KOME_MODEL](https://huggingface.co/kjhkjh95/KOME) 해당 링크에서 ckpt 파일을 다운받으실 수 있습니다.

### Reference
[KOTE](https://github.com/username/my-repository)

[KcELECTRA](https://github.com/Beomi/KcELECTRA)
