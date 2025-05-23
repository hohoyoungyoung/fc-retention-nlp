# fc-retention-nlp
Detecting emotional signals in Korean call center conversations to support FC retention strategy

# fc-retention-nlp

📌 **보험 해지 콜센터 대화 기반 감성 분석 프로젝트**  
고객의 감정 흐름과 해지 시그널을 분석하여  
설계사(FC)의 **고객 유지 대응 전략** 수립에 기여하는 NLP 프로젝트입니다.

---

## 🔍 프로젝트 개요

![image](https://github.com/user-attachments/assets/83246f14-a83e-4912-879b-14b3ead1981c)

`fc-retention-nlp`는 실제 보험 해지 콜센터 대화 데이터를 기반으로  
고객 발화의 감정 흐름을 분석하고, 감정 반전 지점을 탐지하여  
설계사의 대응 전략 및 워딩 템플릿 개선에 활용하기 위한 프로젝트입니다.

---

## 🎯 목적

- 해지 고객의 감정 변화를 시계열로 추적
- 감정 상승/하락을 유발한 설계사 워딩 유형 분석
- 설계사(FC)의 **설득 전략**, **해지 방지 시나리오** 설계 지원
- 향후 AI 기반 응대 시나리오 자동화 가능성 탐색

---

## 🧩 데이터 개요

- **형태**: 보험 해지 콜센터 대화 (STT 변환 텍스트)
- **구성**: 고객 발화, 설계사 응답, 감정 점수, 감정 변화량, 워딩 유형 등
- **전처리 내용**:
  - 문장별 분리 및 역할 구분
  - 감성 분석 모델을 통한 감정 점수 부여
  - 발화 순서 기반 감정 변화 파악

## 📦 데이터 출처

본 프로젝트에 사용된 데이터는 [AI Hub](https://aihub.or.kr/)의  
**"보험 해지 상담 음성 데이터 (STT 텍스트 포함)"**를 기반으로 분석되었습니다.

⚠️ 데이터는 AI Hub 사이트에서 직접 다운로드하셔야 합니다.  
원본 데이터는 저작권 보호를 위해 GitHub에는 포함되어 있지 않습니다.

---



## 🧠 사용 모델

- 모델: [`nlp04/korean_sentiment_analysis_dataset3_best`](https://huggingface.co/nlp04/korean_sentiment_analysis_dataset3_best)  
- 기반: BERT (한국어 특화 사전학습 모델)  
- 목적: 문장 단위 감정 분류 (긍정 / 부정 확률 추정)

---

## ⚙️ 분석 방법

1. 감성 점수 부여  
   → BERT 기반 감정 분석 모델 적용 (0~1 확률값 출력)

2. 감정 반전 탐지  
   → 이전 발화 대비 감정 점수 상승/하락 여부 추적

3. 필터링 기준  
   → 감성 점수 `0.7 이상`만 반영 (모델 확신도 기준)

4. 설계사 워딩 유형 분류  
   → 공감형, 기계형, 설득형 등 6가지 유형 매핑

5. 감정 변화와 워딩의 상관관계 분석  
   → 감정 상승/하락 유발 워딩 유형 비율 비교

---

## 📈 주요 결과 예시



![image](https://github.com/user-attachments/assets/8f69907b-2791-4b9f-ba8b-9ef7d480a881)
- 감정 하락 비율이 높은 워딩 유형: `기계형 (42%)`
- 감정 상승 유도 워딩 유형: `조건강조형`, `반문형`
- 감정 반전 시점 예측 가능 → FC 대응 전략 설계 가능

---

## 📄 발표 자료

👉 [발표 자료 다운로드 (PDF)](https://github.com/hohoyoungyoung/fc-retention-nlp/blob/main/files/삼성생명-서호영-팀-최종.pdf)


