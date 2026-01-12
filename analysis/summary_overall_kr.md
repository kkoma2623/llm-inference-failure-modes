# 전체 요약 (Paris ID vs OOD 추론 행동)

이 파일의 기준 문서는 영어이며, 영어 원문은 [summary_overall.md](summary_overall.md)에서 볼 수 있다. 전체 정량 표는 [quantitative_overview.md](quantitative_overview.md)에 정리되어 있다.

## 설정
- 도메인: Paris
- 범위: 프롬프트 세트 6개 x 조건 2개 x 반복 5회 = 총 60회 실행
- 절차: 각 조건마다 fresh chat에서 동일한 질의를 5회 반복하고 출력을 그대로 기록
- 평가: 텍스트 전용 평가이며 이미지 링크와 미디어는 제외
- 라벨: 기본 라벨 정의는 `analysis/failure_taxonomy.md` 참조

## 프롬프트 세트
- P1: two-sentences vs no-landmarks
- P2: tourist summary vs dislikes-crowds
- P3: known-for vs strict format (3 bullets, 각 10단어 미만)
- P4: cultural importance vs first-time-visitor perspective
- P5: travel destination vs forbidden words ("France", "city", "capital")
- P6: daily life vs temporary work relocation

## 세트 전반의 관찰
1. **사용자 맥락과 관점 제약은 주제보다 프레이밍을 더 많이 바꿨다.**
P4와 P6의 OOD 프롬프트는 각각 체험 중심, 실용 중심의 톤으로 이동했지만 핵심 주제 축은 ID와 거의 같았다.

2. **엄격한 형식 제약은 결정성을 높였지만 내용을 압축했다.**
P3 OOD는 저장소 전체에서 가장 강한 반복성을 보였고, 텍스트 기준 동일 출력 군집이 `3/5`까지 나타났다. 대신 내용은 매우 좁은 전형적 속성 집합으로 수렴했다.

3. **얕은 어휘 제약은 치환으로 처리됐다.**
P5 OOD는 금지 단어를 "destination", "place", "neighborhoods" 같은 대체 표현으로 바꾸면서도 전체 내용 구조는 거의 유지했다.

4. **사용자 선택 요청 행동은 드물지만 실제로 관찰됐다.**
전체 데이터에서 `needs-user-choice`는 단 1회였고, P1 OOD에서 모델이 두 후보 응답을 제시한 뒤 최종 선택을 사용자에게 넘겼다.

5. **검색형 포맷팅 습관이 일관된 partial-correctness 패턴을 만들었다.**
P2의 ID와 OOD 조건은 모두 5회 전부에서 이미지 블록을 앞에 붙였다. 저장소의 텍스트 전용 평가 규칙에서는 이 반복적 과포맷팅을 `partial correctness`로 라벨링했다.

## 정량 스냅샷
- 전체 `60`회 중 `49`회가 `ok`였다.
- `10/60`회는 `partial correctness`였고, 모두 P2에서 나왔다.
- `1/60`회는 `needs-user-choice`였고, P1 OOD에서만 나타났다.
- 가장 큰 동일 출력 군집은 `3/5`였고, P3 OOD에서 관찰됐다.

## 시사점
- 많은 현실적 OOD 제약은 전반적으로 잘 처리되지만, 제약 종류에 따라 trade-off가 다르다.
- 형식 제약은 준수율과 결정성을 올리는 대신 내용 풍부함을 낮춘다.
- 관점 제약은 주제 이탈 없이 tailoring을 강화한다.
- 어휘 제약은 내용 계획보다 표현만 바꾸기 때문에 상대적으로 쉽다.
- 답변 본문이 유용해도 과도한 포맷팅은 평가 프로토콜을 깨뜨릴 수 있다.

## 한계
- 단일 도메인(Paris) 중심
- 조건별 5회 반복의 소규모 설계
- 대규모 벤치마크가 아니라 정성 라벨과 가벼운 정량 요약 중심

## 확장 가능성
- P3 같은 신호가 강한 OOD 프롬프트를 다른 모델로 재현하기
- 두 번째 도메인을 추가해 패턴 일반화 여부 보기
- lexical overlap이나 self-consistency 같은 간단한 불확실성 지표 도입하기
