---
name: iso-14971-risk-management-writer
description: ISO 14971:2019 기반 의료기기 Risk Management File 작성 전문 SKILL. Use when Codex is asked to create, draft, populate, or generate Word DOCX risk management documents from customer templates and IFU/user manual inputs, including Risk Management Plan, Risk Management Report, FMEA, Risk Analysis Table, hazard analysis, risk-control traceability, residual risk evaluation, and production/post-production risk sections. docx template, IFU 분석, placeholder, RMP, RMR, FMEA 작성, RA 문서 산출 업무에 사용한다.
---

# ISO 14971 Risk Management Writer

## 역할

의료기기 RA Consultant가 고객사 Word 템플릿을 사용해 ISO 14971:2019 기반 Risk Management Plan, Risk Management Report, FMEA/Risk Analysis Table을 작성하도록 지원한다.

이 SKILL은 문서 양식을 새로 디자인하지 않는다. User의 `.docx` 템플릿의 CI, 머리말, 꼬리말, 표지, 문서번호 영역, 승인란, 스타일을 유지하고, 표준 placeholder 위치에 User가 제공한 IFU의 관련 내용을 추출하여 규제 문서 내용을 채워 넣는다.

핵심 입력문서는 User가 제공한 IFU 또는 user manual이다. IFU에서 intended use, indications, contraindications, warnings, precautions, operating steps, users, use environment, residual risk disclosure를 추출하고, 이를 RMF의 hazard identification, risk control, residual risk disclosure, FMEA row 작성에 반영한다.

## Template Contract

User가 제공하는 템플릿은 다음 고정 파일명으로 둔다.

risk management plan, risk management report의 경우
```text
assets/templates/current/rmf-template.docx
```
FMEA의 경우, excel file에 작업한다.


템플릿에는 `{{PRODUCT_NAME}}`, `{{INTENDED_USE}}`, `{{RISK_ANALYSIS_TABLE}}` 같은 표준 placeholder를 넣어야 한다. placeholder 규칙은 `references/placeholder-vocabulary.md`를 따른다. 

## 실행 절차

1. 작성 대상 문서를 식별한다.
   - RMP: `rmf-template.docx`
   - RMR: `rmf-template.docx`
   - FMEA 또는 Risk Analysis Table: `fmea-template.xlsx`

2. 템플릿 존재 여부와 placeholder를 확인한다.
   - 가능한 경우 `scripts/inspect_placeholders.py`로 템플릿 placeholder를 추출한다.
   - 필수 placeholder가 없으면 작성 전에 누락 목록을 보고한다.
   - 고객사 양식의 header/footer/table cell 안 placeholder도 확인한다.

3. 제품 정보를 구조화한다.
   - 제품명, 모델, 제조자, intended use, indications, contraindications
   - 대상 환자, 사용자, 사용환경, accessories, variants
   - device class, target market, lifecycle stage
   - 관련 표준, IFU/labeling, biological(ISO 10993 series)/software(IEC 62304)/usability(IEC 62366-1)/clinical(MEDDEV Guidance)/PMS 자료

4. IFU를 우선 분석한다.
   - IFU가 제공되면 `references/ifu-analysis-rules.md`를 반드시 읽는다.
   - IFU의 warnings, precautions, contraindications, operating steps, maintenance, cleaning, troubleshooting, disposal 정보를 risk source로 사용한다.
   - IFU에서 확인한 residual risk disclosure와 FMEA risk control/disclosure가 일치하도록 작성한다.

5. 필요한 reference를 읽는다.
   - placeholder 작성 규칙: `references/placeholder-vocabulary.md`
   - RMP/RMR/FMEA 작성 기준: `references/rmf-writing-rules.md`
   - Word 템플릿 치환 절차: `references/docx-template-workflow.md`
   - 산출물 글꼴/분량 기준: `references/output-specification.md`

6. ISO 14971:2019 프로세스에 맞게 내용을 작성한다.
   - Risk management planning
   - Risk analysis
   - Risk evaluation
   - Risk control
   - Evaluation of overall residual risk
   - Risk management review
   - Production and post-production activities

7. Word 문서를 생성한다.
   - 템플릿을 복사해 출력 파일로 사용한다.
   - placeholder를 텍스트, 섹션, Word table로 치환한다.
   - 고객사 스타일, header/footer, page setup, CI, approval block을 가능한 유지한다.
   - 표 placeholder는 단순 텍스트가 아니라 실제 Word table로 작성한다.
   - 글꼴, 글자 크기, 목표 분량은 템플릿 스타일을 우선하되 `references/output-specification.md`의 기본값을 적용한다.

8. 검증한다.
   - 남아 있는 `{{...}}` placeholder가 없는지 확인한다.
   - 문서번호, 개정번호, 제품명, intended use, risk criteria가 일관되는지 확인한다.
   - IFU의 warning/precaution/contraindication과 RMF의 risk control/residual risk disclosure가 연결되는지 확인한다.
   - RMP는 약 20 pages, RMR은 약 40 pages, FMEA는 최소 30 Risk IDs를 목표로 하되, 템플릿과 제품 복잡도에 따른 차이를 설명한다.
   - Documents skill의 render-and-verify workflow를 사용해 DOCX를 PNG로 렌더링하고 레이아웃을 확인한다.
   - 렌더링이 불가능하면 구조 검증 결과와 한계를 명시한다.

## 출력 원칙

- 작성 언어는 사용자의 요청을 따른다. 한국어 문서에서도 regulatory term은 필요한 경우 영어를 병기한다.
- 정보가 부족하면 임의로 확정하지 말고 `Assumption` 또는 `TBD`로 표시한다.
- 제품별 근거가 필요한 항목은 일반론으로 채우지 말고 필요한 입력자료를 요청한다.
- ISO 14971 원문을 길게 인용하지 않는다. 요구사항은 요약하고 clause 수준으로 참조한다.
- IFU warning만으로 risk reduction을 과대 주장하지 않는다.
- FMEA만 작성하더라도 hazard, hazardous situation, harm, sequence of events 관점이 드러나게 한다.
- IFU의 사용방법, warning, contraindication은 RMF 작성의 1차 evidence source로 취급한다. 단, IFU만으로 제품 설계, verification, clinical benefit을 확정하지 않는다.

## Writer와 Reviewer의 경계

이 SKILL은 초안 작성과 템플릿 채우기에 집중한다. 기존 고객사 문서를 심사자 관점으로 검토하고 finding table을 작성하는 업무는 `iso-14971-risk-management-reviewer`를 사용한다.

작성 중 명백한 모순이나 누락을 발견하면 문서 안에는 `TBD` 또는 `Assumption`으로 표시하고, 사용자에게 별도 보완 목록을 제공한다.

## 사용자에게 물어볼 정보

입력 정보가 부족할 때는 가장 중요한 1-3개만 먼저 묻는다.

- 작성 대상: RMP, RMR, FMEA 중 무엇인지
- 제품명, intended use, device class, target market
- 고객사 IFU 또는 user manual이 제공되었는지
- 사용할 템플릿이 `assets/templates/current/`에 준비되어 있는지
- FMEA 입력자료가 있는지, 아니면 초기 hazard analysis부터 작성해야 하는지
- 산출물 언어, 문서번호/개정번호 규칙, 글꼴/글자 크기/분량 목표
