# Experiments

이 디렉터리의 기준 문서는 영어이며, 한국어 보조 문서는 `_kr.md` suffix를 사용한다. 영어 기준 문서는 [README.md](README.md)에서 볼 수 있다.

## 목적
이 디렉터리는 분포 변화 하에서의 추론 행동을 살펴보기 위한 원시 실험 로그를 저장한다. 각 프롬프트 계열은 ID 조건 1개와 OOD 조건 1개로 구성되며, 두 조건 모두 fresh chat에서 5회 반복 실행했다.

## 구조
각 실험 하위 디렉터리는 보통 다음 파일을 포함한다.

- `config.md`: 실험 설정, 프롬프트 원문, 평가 규칙
- `outputs.md`: 채팅에서 그대로 복사한 원시 모델 출력
- `notes.md`: 빠른 관찰 메모와 run별 기본 실패 라벨

## 프롬프트 계열
- `p1_two-sentences`: 기본 설명 vs 랜드마크 금지 제약
- `p2_tourist-summary`: 관광 요약 vs 혼잡 회피 사용자 맥락
- `p3_known-for`: 자유 응답 vs 3개 bullet 형식 제약
- `p4_cultural-importance`: 기본 설명 vs 첫 방문자 관점 제약
- `p5_travel-destination`: 여행지 설명 vs 금지 단어 제약
- `p6_daily-life`: 일상 설명 vs 임시 업무 이주 맥락

## 네이밍 규칙
실험 폴더는 다음 형식을 따른다.

`<model>_<domain>_<id|ood>_<short_tag>`

예시:
- `chatgpt_paris_id_two-sentences`
- `chatgpt_paris_ood_no-landmarks`
- `chatgpt_paris_ood_format-3bullets-10words`

## 평가 규칙
- 이미지 링크나 미디어 첨부는 부수 요소로 간주하고 텍스트 전용 평가에서 제외한다.
- 실패 라벨은 [`analysis/failure_taxonomy.md`](../analysis/failure_taxonomy.md)를 따른다.
- 한 run에 여러 문제가 있어도 기본 라벨은 하나만 부여한다.
