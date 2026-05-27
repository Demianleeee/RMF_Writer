# Placeholder Vocabulary

템플릿의 placeholder는 대문자 snake case를 사용하고 중괄호 두 개로 감싼다.

```text
{{PRODUCT_NAME}}
{{RISK_ANALYSIS_TABLE}}
```

## General Document Placeholders

권장 공통 placeholder:

- `{{DOCUMENT_TITLE}}`
- `{{DOCUMENT_NUMBER}}`
- `{{REVISION}}`
- `{{EFFECTIVE_DATE}}`
- `{{AUTHOR}}`
- `{{REVIEWER}}`
- `{{APPROVER}}`
- `{{MANUFACTURER}}`
- `{{PRODUCT_NAME}}`
- `{{MODEL_NAME}}`
- `{{DEVICE_DESCRIPTION}}`
- `{{INTENDED_USE}}`
- `{{INDICATIONS_FOR_USE}}`
- `{{CONTRAINDICATIONS}}`
- `{{INTENDED_USER}}`
- `{{PATIENT_POPULATION}}`
- `{{USE_ENVIRONMENT}}`
- `{{TARGET_MARKET}}`
- `{{DEVICE_CLASS}}`
- `{{APPLICABLE_STANDARDS}}`
- `{{IFU_DOCUMENT_TITLE}}`
- `{{IFU_DOCUMENT_VERSION}}`
- `{{IFU_ANALYSIS_SUMMARY}}`
- `{{ABBREVIATIONS_TABLE}}`
- `{{REVISION_HISTORY_TABLE}}`
- `{{APPROVAL_TABLE}}`

## RMP Placeholders

필수 권장:

- `{{RMP_SCOPE}}`
- `{{RISK_MANAGEMENT_PROCESS}}`
- `{{RISK_MANAGEMENT_RESPONSIBILITIES}}`
- `{{RISK_ACCEPTABILITY_CRITERIA}}`
- `{{SEVERITY_SCALE_TABLE}}`
- `{{PROBABILITY_SCALE_TABLE}}`
- `{{RISK_MATRIX_TABLE}}`
- `{{RISK_CONTROL_METHOD}}`
- `{{RISK_CONTROL_VERIFICATION_METHOD}}`
- `{{OVERALL_RESIDUAL_RISK_METHOD}}`
- `{{PRODUCTION_POST_PRODUCTION_PLAN}}`
- `{{RISK_MANAGEMENT_REVIEW_PLAN}}`

선택:

- `{{DEVICE_LIFECYCLE_SCOPE}}`
- `{{REFERENCE_DOCUMENTS_TABLE}}`
- `{{RISK_BENEFIT_METHOD}}`
- `{{PMS_FEEDBACK_TRIGGER_TABLE}}`
- `{{IFU_DERIVED_RISK_SOURCE_SUMMARY}}`

## RMR Placeholders

필수 권장:

- `{{RMR_SCOPE}}`
- `{{RMP_IMPLEMENTATION_SUMMARY}}`
- `{{RISK_ANALYSIS_SUMMARY}}`
- `{{RISK_CONTROL_SUMMARY}}`
- `{{OVERALL_RESIDUAL_RISK_EVALUATION}}`
- `{{RISK_BENEFIT_EVALUATION}}`
- `{{PRODUCTION_POST_PRODUCTION_REVIEW}}`
- `{{OPEN_ISSUES_TABLE}}`
- `{{RISK_MANAGEMENT_CONCLUSION}}`

선택:

- `{{TRACEABILITY_SUMMARY_TABLE}}`
- `{{RESIDUAL_RISK_DISCLOSURE_SUMMARY}}`
- `{{IFU_RMF_CONSISTENCY_SUMMARY}}`
- `{{PMS_DATA_SUMMARY_TABLE}}`
- `{{DEVIATION_TABLE}}`

## FMEA and Risk Analysis Placeholders

필수 권장:

- `{{RISK_ANALYSIS_METHOD}}`
- `{{SAFETY_CHARACTERISTICS}}`
- `{{RISK_ANALYSIS_TABLE}}`
- `{{FMEA_TABLE}}`
- `{{RISK_CONTROL_TRACEABILITY_TABLE}}`
- `{{RESIDUAL_RISK_SUMMARY_TABLE}}`

선택:

- `{{HAZARD_LIST_TABLE}}`
- `{{FORESEEABLE_MISUSE_TABLE}}`
- `{{USE_RELATED_RISK_TABLE}}`
- `{{SOFTWARE_RISK_TABLE}}`
- `{{CYBERSECURITY_RISK_TABLE}}`
- `{{IFU_WARNING_RISK_LINKAGE_TABLE}}`
- `{{IFU_USE_STEP_RISK_TABLE}}`

## Placeholder Types

Single value:

- 짧은 텍스트로 치환한다.
- 예: `{{PRODUCT_NAME}}`, `{{REVISION}}`

Section:

- 여러 문단 또는 목록으로 치환한다.
- placeholder 이름은 `_SECTION` 접미사를 붙여도 된다.
- 예: `{{DEVICE_DESCRIPTION_SECTION}}`

Table:

- 실제 Word table로 치환한다.
- placeholder 이름은 `_TABLE` 접미사를 사용한다.
- 예: `{{FMEA_TABLE}}`

## Required Behavior

- 필수 placeholder가 템플릿에 없으면 작성 전에 사용자에게 보고한다.
- 선택 placeholder가 없으면 생략해도 된다.
- 입력자료가 부족하면 `TBD` 또는 `[Assumption: ...]`로 표시한다.
- 최종 문서에 `{{...}}`가 남아 있으면 완료로 보지 않는다.
