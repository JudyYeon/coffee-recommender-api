# AI-inference-API

이 서버는 외부 요청을 받아서 모델에게 입력 전달하고, 모델의 출력을 받아 클라이언트에 결과를 JSON 등으로 응답합니다.


---

## 구성 요소 설명

- **Client / Frontend**  
  사용자 인터페이스를 담당하며, 웹 혹은 앱 형태로 제공됩니다.  
  사용자의 질문, 이미지 등 다양한 입력을 받아 서버로 전송합니다.

- **Java Backend**  
  Spring 또는 Express 기반의 서버로, 클라이언트로부터 받은 요청을 처리하고 AI API와 통신합니다.  
  비즈니스 로직 및 인증, 권한 관리 등을 담당합니다.

- **AI Inference API**  
  Python의 FastAPI로 구현된 AI 서비스 인터페이스입니다.  
  백엔드에서 요청받은 데이터를 AI 모델에 전달하고 결과를 응답합니다.

- **AI Model**  
  HuggingFace, PyTorch, TensorFlow 등으로 학습된 인공지능 모델입니다.  
  입력 데이터를 기반으로 예측, 요약, 분류 등의 결과를 생성합니다.

---

## 흐름 요약

1. 클라이언트가 질문이나 이미지를 Java Backend로 전송합니다.  
2. Java Backend는 REST API 호출을 통해 AI Inference API에 요청합니다.  
3. AI Inference API는 내부 AI 모델에 입력 데이터를 전달해 결과를 받습니다.  
4. 결과를 Java Backend로 반환하고, 다시 클라이언트에 전달됩니다.

---

## 기술 스택

| 역할            | 기술 스택                  |
|----------------|--------------------------|
| Frontend       | React, React Native 등     |
| Backend        | Spring Boot, Express.js    |
| AI Inference   | FastAPI (Python)           |
| AI Model       | HuggingFace, PyTorch, TensorFlow |

---

## 프로젝트 구조

```plaintext
coffee-recommender-api/
├── app.py                    # Flask 서버: POST /recommend
├── recommender.py            # 모델 로딩 및 추천 함수
├── train_model.py            # 모델 학습용 스크립트
├── model.pkl                 # 학습된 모델
├── sample_training_data.csv  # 학습용 데이터 예시
├── requirements.txt          # pip 설치 목록

