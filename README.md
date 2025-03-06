# SwearWords-Detection
욕설 단어 탐지

욕설 문장을 분류하고 욕설을 찾아주는 프로젝트입니다.
colab 에서 작성하였습니다.

## 데이터셋
 [ZIZUN/korean-malicious-comments-dataset](https://github.com/ZIZUN/korean-malicious-comments-dataset)
 한국어 악성댓글 데이터셋
  
## 모델
https://huggingface.co/beomi/kcbert-base kcbert 모델을 학습하였습니다.

자세한 정보는 [코드](https://github.com/doormoonn/SwearWords-Detection/blob/main/src/model_train.ipynb)를 참조하세요.
#### 학습된 모델은 [여기](https://huggingface.co/yoyomo/KcBERT-Base-finetuned-yok)에서 사용할 수 있습니다.

## 구현
욕설문장을 [SEP] 토큰으로 연결시키고
```python3
input="시발 배고파"
['[CLS]', '시발', '배고', '##파', '[SEP]', '시발', '배고', '##파', '[SEP]']

```

[CLS] token 과 [SEP] token 뒤에 위치한 단어의 attention 을 비교하여 0.02 이상인 값을 욕설단어로 분류.

## 실행 화면
<img width="300" alt="Image" src="https://github.com/user-attachments/assets/b3b49757-5571-47a0-b44f-d20f881d28fc"/><img width="300" alt="Image" src="https://github.com/user-attachments/assets/66ecd0f2-e656-43b8-9e1e-b7f7bca70612" />
