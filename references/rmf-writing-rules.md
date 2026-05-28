# RMF Writing Rules

이 reference는 ISO 14971:2019 기반 RMP, RMR, FMEA 작성 시 사용할 실무 규칙을 정리한다.

## Common Writing Rules

- IFU 또는 user manual을 핵심 입력문서로 사용한다.
- IFU에서 intended use, contraindications, warnings, precautions, use steps, maintenance, cleaning, troubleshooting, disposal 정보를 먼저 추출한다.
- IFU에서 추출한 정보는 hazard identification, reasonably foreseeable misuse, use-related risk, information for safety, residual risk disclosure 작성에 반영한다.
- 제품 정보와 intended use를 먼저 고정한 뒤 risk 문서를 작성한다.
- RMP의 기준과 FMEA/RMR의 판단 결과를 일치시킨다.
- Hazard, hazardous situation, harm, sequence of events를 구분한다.
- Risk control은 구현 및 검증 가능한 표현으로 작성한다.
- Residual risk는 개별 위험과 전체 잔여위험 두 수준에서 다룬다.
- Benefit-risk rationale은 제품의 intended benefit, clinical/performance evidence, residual risk를 연결한다.
- PMS/complaint/CAPA feedback이 RMF 업데이트로 이어지는 구조를 포함한다.

## RMP Content Rules

RMP에는 다음을 포함한다.

- Scope: 제품, 모델, lifecycle phase, 포함/제외 범위
- Responsibilities: risk management 책임과 승인 권한
- Risk acceptability criteria: severity, probability, risk matrix, acceptable/unacceptable 기준
- Risk analysis method: hazard identification source와 analysis method
- Risk control method: option analysis와 verification method
- Overall residual risk evaluation method
- Production and post-production information 수집 및 반영 방법
- Risk management review timing and output

작성 주의:

- Acceptability criteria는 사후 판단이 아니라 사전 기준처럼 작성한다.
- Probability scale은 가능하면 정량 또는 반정량 정의를 둔다.
- Information for safety는 risk control hierarchy에서 마지막 수단임을 반영한다.
- Hazard identification source에 IFU/user manual, labeling, warnings/precautions, contraindications, use steps를 포함한다.

## RMR Content Rules

RMR에는 다음을 포함한다.

- RMP가 실행되었는지 요약
- Risk analysis completeness 판단
- Risk control implementation 및 verification status
- Residual risk acceptability 판단
- Overall residual risk acceptability 결론
- Benefit-risk evaluation 필요 여부 및 결론
- Production/post-production information 검토 결과 또는 계획
- Open issue, deviation, unresolved risk
- Final conclusion

작성 주의:

- "All risks are acceptable" 같은 선언만 쓰지 않는다. 근거와 추적성을 함께 제시한다.
- Open issue가 있으면 최종 결론에 조건부 acceptability 또는 action plan을 반영한다.
- RMR의 scope와 RMP/FMEA의 제품 범위가 일치해야 한다.
- IFU에 공개된 residual risk, warnings, precautions가 FMEA 및 RMR의 residual risk disclosure와 일치하는지 결론에 반영한다.

## FMEA and Risk Analysis Rules

FMEA는 가능한 경우 `assets/`에 저장된 고객사 FMEA template `.xlsx`를 뼈대로 작성한다. 템플릿이 제공된 경우 컬럼명, 병합 셀, 드롭다운, 번호 체계, 시트 구조, 서식, 헤더 그룹을 임의로 바꾸지 않는다. 아래 권장 컬럼은 새 표를 만들 때의 기준이 아니라, 템플릿을 채울 때 누락 여부와 의미 매핑을 확인하기 위한 기준으로 사용한다.

템플릿 기반 작성 원칙:

- `assets/fmea-template.xlsx`가 있으면 새 workbook을 만들지 말고 해당 파일을 복사하여 output workbook의 기반으로 사용한다.
- 템플릿의 기존 헤더와 섹션 구조를 보존한다.
- 템플릿 컬럼명이 아래 권장 컬럼과 다르더라도 의미가 같으면 템플릿 컬럼명을 우선한다.
- 템플릿에 있는 필수 컬럼은 삭제하거나 숨기지 않는다.
- 템플릿에 없는 보조 정보는 임의 컬럼을 추가하기보다 `Related Documents`, `Remarks`, `Open Items` 또는 사용자 지정 보조 시트에 정리한다.
- Severity, Probability, Risk Level, Risk Evaluation 값은 RMP의 risk acceptability criteria와 일치시킨다.
- 템플릿에 드롭다운이나 고정 선택지가 있으면 그 값 범위 안에서 작성한다.
- 값이 확정되지 않은 항목은 빈칸으로 두지 말고 `TBD:` 또는 `[Assumption: ...]` 형식으로 표시한다.

권장 컬럼 의미 매핑:

- Risk No. 또는 ID
- Process/Function/Use Step
- Hazard Identification 또는 Hazard
- Examples
- Normal or Fault
- Foreseeable Sequence of Events or Failure Mode
- Hazardous Situation
- Harm
- Initial Severity
- Initial Probability
- Initial Risk Level
- Risk Evaluation 또는 Risk Acceptability
- Risk Control Option Analysis
- Risk Control Measure
- Implementation
- Verification Evidence
- Residual Severity
- Residual Probability
- Residual Risk Level
- Residual Risk Evaluation 또는 Residual Risk Acceptability
- Benefit-Risk Rationale, if needed
- Residual Risk Information or Disclosure, if needed
- Overall Residual Risk Evaluation
- Risks Arising from Risk Control Measures
- Completeness of Risk Control
- Related Documents

작성 주의:

- FMEA template이 제공된 경우, 이 reference의 컬럼 목록보다 template의 실제 컬럼 구조를 우선한다.
- Failure mode 중심 FMEA를 쓰더라도 ISO 14971의 hazard-harm chain이 드러나야 한다.
- Severity는 harm의 임상적/안전성 영향에 맞춘다.
- Probability 감소는 risk control의 작동 원리와 evidence가 있어야 한다.
- Labeling/IFU warning을 risk control로 쓸 때는 사용자가 실제로 위험을 회피할 수 있는지 고려한다.
- IFU의 operating step별로 foreseeable misuse, use error, warning 미준수 상황을 도출한다.
- IFU warning을 risk control로 사용하는 경우 `Information for safety`로 분류하고, 필요한 경우 design/protective measure가 우선 검토되었는지 표시한다.
- Risk control option analysis에는 inherently safe design, protective measure, information for safety가 검토되었는지 드러나야 한다.
- Implementation과 Verification은 구분한다. Implementation은 통제수단이 문서, 설계, 소프트웨어, 라벨링, 절차에 반영되었는지 기록하고, Verification은 그 반영을 확인한 evidence를 기록한다.
- Residual risk evaluation은 개별 risk 단위로 수행하고, 필요한 경우 overall residual risk evaluation과 연결한다.
- Risk control measure 자체에서 새롭게 발생하는 risk가 있으면 `Risks Arising from Risk Control Measures`에 기록한다.
- 마지막에는 risk control이 완결되었는지 `Completeness of Risk Control`에 결론을 남긴다.

## Assumption Handling

정보가 부족하면 다음처럼 표시한다.

```text
[Assumption: The device is intended for use by trained healthcare professionals in a clinical environment.]
```

확정할 수 없는 항목은 다음처럼 둔다.

```text
TBD: PMS data summary to be inserted after complaint trend review.
```

최종 사용자에게는 별도 `Open Items` 목록으로 정리한다.
