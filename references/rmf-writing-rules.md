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

권장 컬럼:

- ID
- Process/Function/Use Step
- Hazard
- Sequence of Events or Failure Mode
- Hazardous Situation
- Harm
- Initial Severity
- Initial Probability
- Initial Risk Level
- Risk Acceptability
- Risk Control Measure
- Verification Evidence
- Residual Severity
- Residual Probability
- Residual Risk Level
- Residual Risk Acceptability
- Benefit-Risk Rationale, if needed
- Residual Risk Disclosure, if needed
- Related Documents

작성 주의:

- Failure mode 중심 FMEA를 쓰더라도 ISO 14971의 hazard-harm chain이 드러나야 한다.
- Severity는 harm의 임상적/안전성 영향에 맞춘다.
- Probability 감소는 risk control의 작동 원리와 evidence가 있어야 한다.
- Labeling/IFU warning을 risk control로 쓸 때는 사용자가 실제로 위험을 회피할 수 있는지 고려한다.
- IFU의 operating step별로 foreseeable misuse, use error, warning 미준수 상황을 도출한다.
- IFU warning을 risk control로 사용하는 경우 `Information for safety`로 분류하고, 필요한 경우 design/protective measure가 우선 검토되었는지 표시한다.

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
