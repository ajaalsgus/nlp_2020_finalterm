# 빅데이터자연어처리 프로젝트
* 영어, 한국어 감정 분류 모델 개발
  - [English SA Competition - BDC101](https://www.kaggle.com/c/english-sa-competition-bdc101/)
  - [Korean SA Competition - BDC101](https://www.kaggle.com/c/korean-sa-competition-bdc101/)
* 머신러닝, 딥러닝, 앙상블 기법 활용하여 견고한 성능의 모형을 구축하는 것을 목표로 함
* 모델 관련 출처 등 별도 설명 없는 것은 직접 구현 대상

---

## 1. 영어(Friends)
* **머신러닝 모델**
  - Logistic Regression
  - Random Forest
  - XGBoost
  - Light GBM 

머신러닝 모델 | 전처리 | 모델 상세
----- | ----- | -----
Logistic Regression | NLTK, TF-IDF, Regular Expression | 기본 하이퍼파라미터 적용
Random Forest | (상동) | 기본 하이퍼파라미터 적용
XGBoost | (상동) | 기본 하이퍼파라미터 적용
Light GBM | (상동) | 기본 하이퍼파라미터 적용

* **딥러닝 모델**
  - ANN : [참고 소스 출처](https://devtimes.com/nlp-korea-movie-review)
  - CNN : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - LSTM : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - BERT : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - ELECTRA : [참고 소스 출처](https://github.com/jiwonny/nlp_emotion_classification/blob/master/friends_electra.ipynb)

딥러닝 모델 | 전처리 | 모델 상세
----- | ----- | -----
ANN | NLTK, TF-IDF, Regular Expression | 각 64개 뉴런(노드) 보유한 2개 은닉층 적용
CNN | Tensorflow tokenizer, Regular Expression | 1차원 Conv1D 합성곱 레이어 3개 및 Max Pooling 적용
LSTM | (상동) | LSTM 레이어 2개 적용
BERT | 유니코드 '\x92' 제거 | Google 제공 bert-base-multilingual-cased 적용
ELECTRA | 유니코드 '\x92' 제거 | Google 제공 electra-small, electra-base, electra-large 적용

* **앙상블 모델**
  - Voting(다수결) 방식 적용(직접 구현)

---

## 2. 한국어(NSMC)
* **머신러닝 모델**
  - Logistic Regression : KoNLPy Okt(Twitter), TF-IDF, Regular Expression 적용
  - Random Forest : KoNLPy Okt(Twitter), TF-IDF, Regular Expression 적용
  - XGBoost : KoNLPy Okt(Twitter), TF-IDF, Regular Expression 적용
  - Light GBM : KoNLPy Okt(Twitter), TF-IDF, Regular Expression 적용

* **딥러닝 모델**
  - ANN : 카운트 기반 벡터화 적용 ([참고 소스 출처](https://devtimes.com/nlp-korea-movie-review))
  - CNN : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - LSTM : 텐서플로2와 머신러닝으로 시작하는 자연어 처리(전창욱 외, 위키북스, 2020) 참고
  - BERT : Google 제공 bert-base-multilingual-cased 모델(Pyrotch) 적용 ([참고 소스 출처](https://github.com/deepseasw/bert-naver-movie-review))
  - KoBERT : SKT(T-Brain) 제공 모델(Pytorch) 적용 ([참고 소스 출처](https://github.com/SKTBrain/KoBERT#using-with-pytorch))
  - KoELECTRA : KoELECTRA-v3 모델(Pytorch) 적용 ([참고 소스 출처](https://github.com/monologg/KoELECTRA))

* **앙상블 모델**
  - Voting(다수결) 방식 적용(직접 구현)

---

## 3. 인용
> 인용1

> 인용2
>> 인용안의 인용

---

## 4. 기타
* 리스트1
  - 리스트2
    + 리스트3

1. 리스트1
2. 리스트2
3. 리스트3 

*텍스트*

**텍스트**

(1) 인라인 링크  

[블로그 주소](https://lsh424.tistory.com/)

(2) 참조 링크  

[블로그 주소][blog]

[blog]: https://lsh424.tistory.com/


# 9. 이미지 추가하기
![이탈리아 포지타노](https://user-images.githubusercontent.com/31477658/85016059-f962aa80-b1a3-11ea-8c91-dacba2666b78.jpeg)

### 이미지 사이즈 조절
<img src="https://user-images.githubusercontent.com/31477658/85016059-f962aa80-b1a3-11ea-8c91-dacba2666b78.jpeg"  width="700" height="370">

# 10. 코드블럭 추가하기

```swift
public struct CGSize {
  public var width: CGFloat
  public var heigth: CGFloat
  ...
}
```

# etc

**텍스트 굵게**  
~~텍스트 취소선~~


# MARKDOWN
MARKDOWN 정리, 실습 for README.md

# 1. 제목(글머리) 작성
# H1 제목  
## H2 부제목
### H3 소제목
#### H4 제목4
##### H5 제목5
###### H6 제목6


# 2. 번호 없는 리스트 작성
* 리스트1
  - 리스트2
    + 리스트3
    
# 3. 번호 있는 리스트 작성
1. 리스트1
2. 리스트2
3. 리스트3 

# 4. 이텔릭체(기울어진 글씨) 작성
*텍스트*

# 5. 굵은 글씨 작성
**텍스트**

# 6. 인용
> 인용1

> 인용2
>> 인용안의 인용

# 7. 수평선 넣기

---
  
# 8. 링크 달기
(1) 인라인 링크  

[블로그 주소](https://lsh424.tistory.com/)

(2) 참조 링크  

[블로그 주소][blog]

[blog]: https://lsh424.tistory.com/

# 9. 이미지 추가하기
![이탈리아 포지타노](https://user-images.githubusercontent.com/31477658/85016059-f962aa80-b1a3-11ea-8c91-dacba2666b78.jpeg)

### 이미지 사이즈 조절
<img src="https://user-images.githubusercontent.com/31477658/85016059-f962aa80-b1a3-11ea-8c91-dacba2666b78.jpeg"  width="700" height="370">

# 10. 코드블럭 추가하기

```swift
public struct CGSize {
  public var width: CGFloat
  public var heigth: CGFloat
  ...
}
```

# etc

**텍스트 굵게**  
~~텍스트 취소선~~
