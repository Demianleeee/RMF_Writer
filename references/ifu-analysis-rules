# IFU Analysis Rules

IFU 또는 user manual은 RMF Writer의 핵심 입력문서다. IFU 분석 없이 RMP/RMR/FMEA를 완성도 높게 작성했다고 판단하지 않는다.

## Extract First

IFU에서 다음 정보를 먼저 추출한다.

- Document title, document number, revision, date
- Product name, model, variants, accessories
- Intended use and indications for use
- Contraindications
- Intended users and patient population
- Use environment
- Preparation before use
- Step-by-step operating procedure
- Warnings, precautions, cautions
- Maintenance, cleaning, storage, transport, disposal
- Troubleshooting and alarm/error messages
- Residual risk disclosure
- Training requirements
- Symbols, labels, and safety notices

## Convert IFU Content into RMF Inputs

각 IFU 정보는 다음 RMF 항목으로 변환한다.

- Intended use -> RMP scope, risk analysis scope, RMR scope
- Contraindications -> hazardous situation avoidance, residual risk disclosure, IFU-RMF consistency check
- Warnings/precautions -> information for safety, residual risk disclosure, FMEA risk control or linked disclosure
- Operating steps -> use-related hazards, foreseeable misuse, use error, hazardous situation
- Maintenance/cleaning/storage -> lifecycle hazards and risk controls
- Troubleshooting/alarm messages -> failure detection, protective measure, user action risk
- Training requirements -> user profile, risk control dependency, usability linkage
- Residual risk disclosure -> RMR residual risk summary and IFU consistency conclusion

## IFU-to-FMEA Derivation

For each relevant IFU step or warning, consider creating one or more FMEA/Risk Analysis rows.

Recommended fields:

- IFU section or page
- Use step or label statement
- Hazard
- Sequence of events or foreseeable misuse
- Hazardous situation
- Harm
- Existing risk control
- Whether the control is design, protective measure, or information for safety
- Verification evidence needed
- Residual risk disclosure needed

## Warning and Precaution Handling

- Do not automatically treat every warning as effective risk reduction.
- If the warning only informs the user, classify it as information for safety.
- If risk reduction depends on user action, evaluate whether the intended user can understand and reliably perform the action.
- If a warning addresses severe harm, check whether design or protective measures should also be considered.
- Ensure each important IFU warning has a corresponding risk item or explicit rationale for exclusion.

## Consistency Rules

Check consistency between IFU and RMF:

- Intended use in IFU vs RMP/RMR/FMEA
- Contraindications in IFU vs risk analysis and residual risk evaluation
- Warnings and precautions in IFU vs risk controls and residual risk disclosure
- Use environment in IFU vs hazard analysis
- User group in IFU vs usability/use-related risk assumptions
- Maintenance and cleaning instructions vs lifecycle risk analysis

## Output Expectations

When IFU is used, provide a short IFU analysis summary outside or inside the generated document, depending on the user request.

Include:

- Key IFU-derived risk sources
- IFU sections that drove FMEA rows
- IFU warnings that require risk-control traceability
- IFU/RMF consistency concerns
- Open questions where IFU lacks detail
