# 빅데이터자연어처리 프로젝트
* 영어, 한국어 감정 분류 모델 개발
  - [English SA Competition - BDC101](https://www.kaggle.com/c/english-sa-competition-bdc101/)
  - [Korean SA Competition - BDC101](https://www.kaggle.com/c/korean-sa-competition-bdc101/)
* 머신러닝, 딥러닝, 앙상블 기법 활용하여 견고한 성능의 모형을 구축하는 것을 목표로 함
* 모델 관련 출처 등 별도 설명 없는 것은 직접 구현 대상

---

## 1. 영어(Friends)
* **데이터 출처** : http://doraemon.iis.sinica.edu.tw/emotionlines/
 
* **머신러닝 모델**
  - Logistic Regression
  - Random Forest
  - XGBoost
  - Light GBM 
 
* **딥러닝 모델**
  - ANN : [참고 소스 출처](https://devtimes.com/nlp-korea-movie-review)
  - CNN : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - LSTM : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - BERT : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - ELECTRA : [참고 소스 출처](https://github.com/jiwonny/nlp_emotion_classification/blob/master/friends_electra.ipynb)

머신러닝 모델 | 전처리 | 모델 상세
----- | ----- | -----
Logistic Regression | NLTK, TF-IDF, Regular Expression  | 별도 하이퍼파라미터 적용 없음
Random Forest | (상동) | (상동)
XGBoost | (상동) | (상동)
Light GBM | (상동) | (상동)

딥러닝 모델 | 전처리 | 모델 상세
----- | ----- | -----
ANN | NLTK, TF-IDF, Regular Expression | 각 64개 뉴런(노드) 보유한 2개 은닉층 적용
CNN | Tensorflow tokenizer, Regular Expression | 1차원 Conv1D 합성곱 레이어 3개 및 Max Pooling 적용
LSTM | (상동) | LSTM 레이어 2개 적용
BERT | 유니코드 '\x92' 제거 | Google 제공 bert-base-multilingual-cased 적용
ELECTRA | 유니코드 '\x92' 제거 | Google 제공 electra-small, electra-base, electra-large 적용
 
* **앙상블 모델**
  - Voting(다수결) 방식 적용(직접 구현) => https://github.com/ajaalsgus/nlp_2020_finalterm/blob/main/01_FRIENDS/12_FRIENDS_Ensemble_NN_ELECTRA_EmoLexSWD_7.ipynb

---

## 2. 한국어(NSMC)
* **데이터 출처** : https://github.com/e9t/nsmc.git
 
* **머신러닝 모델**
  - Logistic Regression
  - Random Forest
  - XGBoost
  - Light GBM
 
* **딥러닝 모델**
  - ANN : [참고 소스 출처](https://devtimes.com/nlp-korea-movie-review)
  - CNN : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - LSTM : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - BERT : [참고 소스 출처](https://github.com/deepseasw/bert-naver-movie-review)
  - KoBERT : [참고 소스 출처](https://github.com/SKTBrain/KoBERT#using-with-pytorch)
  - KoELECTRA : [참고 소스 출처](https://github.com/monologg/KoELECTRA)

머신러닝 모델 | 전처리 | 모델 상세
----- | ----- | -----
Logistic Regression | KoNLPy Okt(Twitter), TF-IDF, Regular Expression 적용 | 별도 하이퍼파라미터 적용 없음
Random Forest | (상동) | (상동)
XGBoost | (상동) | (상동)
Light GBM | (상동) | (상동)

딥러닝 모델 | 전처리 | 모델 상세
----- | ----- | -----
ANN | KoNLPy Okt(Twitter), Count Vectorization, Regular Expression | 각 64개 뉴런(노드) 보유한 2개 은닉층 적용
CNN | KoNLPy Okt(Twitter), Tensorflow tokenizer, Regular Expression | 1차원 Conv1D 합성곱 레이어 3개 및 Max Pooling 적용
LSTM | (상동) | LSTM 레이어 2개 적용
BERT | Google 제공 bert-base-multilingual-cased 적용 | Google 제공 bert-base-multilingual-cased 적용
KoBERT | SKT(T-Brain) 제공 kobert.utils 라이브러리 get_tokenizer 적용 | SKT(T-Brain) 제공 kobert.pytorch_kobert 라이브러리 get_pytorch_kobert_model 적용
KoELECTRA | KoELECTRA-v3 토크나이저 적용 | KoELECTRA-v3 모델 적용
 
* **앙상블 모델**
  - Voting(다수결) 방식 적용(직접 구현) => https://github.com/ajaalsgus/nlp_2020_finalterm/blob/main/02_NSMC/12_NSMC_Ensemble_NN_KoELECTRA_KoBERT.ipynb

---

## 기타
* 추가 데이터(한국어) : KNU 감성사전 ☞ https://github.com/park1200656/KnuSentiLex
* 추가 데이터(한국어) : 네이버 쇼핑 리뷰 ☞ https://github.com/bab2min/corpus/tree/master/sentiment
* 추가 데이터(한국어) : 한국어 혐오발언 ☞ https://github.com/kocohub/korean-hate-speech
* 추가 데이터(영어) : The Sentiment and Emotion Lexicons ☞ http://sentiment.nrc.ca/lexicons-for-research/

---

* 리스트1
  - 리스트2
    + 리스트3

1. 리스트1
2. 리스트2
3. 리스트3 

*텍스트*

**텍스트**

~~텍스트 취소선~~

(1) 인라인 링크  

[블로그 주소](https://lsh424.tistory.com/)

(2) 참조 링크  

[블로그 주소][blog]

[blog]: https://lsh424.tistory.com/
