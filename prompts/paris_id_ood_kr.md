# Paris 주제: ID / OOD 프롬프트 세트

이 파일의 기준 문서는 영어이며, 영어 원문은 [paris_id_ood.md](paris_id_ood.md)에서 볼 수 있다.

이 문서는 대규모 언어 모델의 추론 단계에서 지시 이행과 실패 양상을 분석하기 위해 설계한 in-distribution(ID) 및 out-of-distribution(OOD) 프롬프트 쌍을 정리한다.

## 프롬프트 설계 원칙
- ID 프롬프트는 표준 benchmark에 가까운 단순한 문구를 사용한다.
- OOD 프롬프트는 형식 제약, 관점 전환, 금지 단어처럼 실제 사용자 질의에서 자주 보이는 제약을 도입한다.
- 모든 프롬프트 쌍은 동일한 도메인 안에 두어 출력 차이를 제약 자체로 해석하기 쉽게 했다.

---

## Prompt Set 1
**ID**
Describe the city of Paris in two sentences.

**OOD**
Describe the city of Paris in two sentences without mentioning any famous landmarks.

---

## Prompt Set 2
**ID**
Summarize Paris as a tourist destination.

**OOD**
Summarize Paris as a tourist destination for someone who dislikes crowded places.

---

## Prompt Set 3
**ID**
What is Paris known for?

**OOD**
What is Paris known for? Answer using exactly three bullet points, each under ten words.

---

## Prompt Set 4
**ID**
Explain why Paris is considered culturally important.

**OOD**
Explain why Paris is considered culturally important from the perspective of a first-time visitor.

---

## Prompt Set 5
**ID**
Describe Paris as a travel destination.

**OOD**
Describe Paris as a travel destination without using the words "France", "city", or "capital."

---

## Prompt Set 6
**ID**
Describe what daily life in Paris might be like.

**OOD**
Describe what daily life in Paris might be like for someone moving there temporarily for work.
