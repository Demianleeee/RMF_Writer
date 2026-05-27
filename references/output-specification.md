# Output Specification

이 reference는 기본 글꼴, 글자 크기, 목표 분량, FMEA row 목표를 정의한다. 고객사 Word 템플릿 스타일이 명확하면 템플릿을 우선하되, 새로 삽입하는 문단과 표에는 이 기준을 적용한다.

## Default Formatting

- Body font: Arial
- Body font size: 10 pt
- Table font: Arial
- Table font size: 8.5-9 pt
- Heading style: preserve customer template heading styles
- Line spacing: preserve template default unless user specifies otherwise
- Page margins, header, footer, logo, approval block: preserve customer template

## Target Length

- RMP: target 18-22 pages, nominal 20 pages
- RMR: target 35-45 pages, nominal 40 pages
- FMEA/Risk Analysis: at least 30 Risk IDs for a complete first draft unless the device is extremely simple

## Length Control Rules

- Treat page count as a target range, not a guarantee.
- Do not add filler text only to reach page count.
- If the target cannot be met because product information or IFU detail is insufficient, use focused `TBD` and open items instead of speculative content.
- If the IFU is detailed, use it to enrich hazard identification, use-related risk, warning traceability, and residual risk disclosure.
- If the generated document is materially shorter than target, explain whether this is due to missing input, simple device scope, or sparse template structure.

## FMEA Risk ID Rules

- Create at least 30 Risk IDs when preparing a complete first-draft FMEA for a typical active or software-related medical device.
- For simple non-active devices, fewer rows may be justified, but provide the rationale.
- Risk IDs should cover:
  - Intended use
  - Reasonably foreseeable misuse
  - IFU operating steps
  - Warnings and precautions
  - Contraindications
  - Use environment
  - Accessories and variants
  - Maintenance, cleaning, storage, transport, disposal
  - Software, data, alarm, cybersecurity, or interoperability risks where applicable
  - Production and post-production feedback sources where available

## Override Rules

User prompt can override these defaults.

Examples:

```text
Use Calibri 11 pt for body text.
Limit RMP to 15 pages.
Generate at least 50 FMEA Risk IDs.
```

When user instructions conflict with the customer template, preserve the customer template unless the user explicitly says to override the template formatting.
