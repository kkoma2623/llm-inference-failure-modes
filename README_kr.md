# 분포 변화 하에서의 대규모 언어 모델 추론 실패 양상 및 불확실성 분석

이 저장소의 기준 문서는 영어이며, 한국어 보조 문서는 `_kr.md` suffix를 사용한다. 영어 기준 문서는 [README.md](README.md)에서 볼 수 있다.

## 개요
이 저장소는 분포 변화(distribution shift) 하에서 ChatGPT의 추론 행동이 어떻게 달라지는지를 살펴보는 소규모 연구를 정리한다. 현재 실험은 Paris 주제의 프롬프트 쌍 6개를 사용하며, 각 세트마다 in-distribution(ID) 프롬프트와 out-of-distribution(OOD) 프롬프트를 1개씩 두고 조건별로 5회 반복 실행했다.

## 연구 질문
- 분포 변화 하에서 실패 양상은 어떻게 달라지는가?
- 반복 실행에서 결정론적 행동과 확률적 행동은 어떻게 드러나는가?
- 출력 변동성과 같은 가벼운 불확실성 지표로 불안정하거나 과신적인 생성을 포착할 수 있는가?

## 저장소 안내
- [`prompts/paris_id_ood.md`](prompts/paris_id_ood.md): 현재 연구에 사용한 기준 프롬프트 쌍
- [`prompts/paris_id_ood_kr.md`](prompts/paris_id_ood_kr.md): 프롬프트 세트 한글판
- [`experiments/README.md`](experiments/README.md): 실험 로그 구조와 평가 규칙
- [`analysis/failure_taxonomy.md`](analysis/failure_taxonomy.md): 기본 실패 양상 라벨
- [`analysis/quantitative_overview.md`](analysis/quantitative_overview.md): 전체 60회 실행에 대한 정량 요약
- [`analysis/summary_overall.md`](analysis/summary_overall.md): 프롬프트 세트 전반의 정성 요약

## 현재 상태
- [x] 프로젝트 범위 정의
- [x] ID / OOD 프롬프트 셋 구성
- [x] 샘플링 기반 추론 실험
- [x] 실패 양상 분류체계 정교화
- [x] 정량적 및 정성적 분석

## 핵심 관찰
- 관점 전환과 사용자 맥락 제약은 주제 자체보다 서술 프레이밍을 더 크게 바꿨다.
- 엄격한 형식 제약은 가장 큰 결정성 증가를 보였다. P3 OOD에서는 텍스트 기준 동일 출력 군집이 `3/5`까지 나타났다.
- 전체 데이터에서 `needs-user-choice`는 단 1회 발생했고, P1 OOD에서만 관찰됐다.
- P2 관광 요약 프롬프트는 요청되지 않은 이미지 블록을 반복 삽입했고, 텍스트 전용 평가 기준에서는 이를 `partial correctness`로 라벨링했다.

## 권장 읽기 순서
1. [`prompts/paris_id_ood.md`](prompts/paris_id_ood.md)에서 프롬프트 쌍을 확인한다.
2. [`experiments/`](experiments/README.md) 아래의 원시 로그를 본다.
3. [`analysis/quantitative_overview.md`](analysis/quantitative_overview.md)에서 전체 집계를 확인한다.
4. [`analysis/summary_overall.md`](analysis/summary_overall.md)에서 행동 패턴 해석을 마무리한다.
