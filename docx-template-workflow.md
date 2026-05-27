# DOCX Template Workflow

고객사 템플릿을 사용해 Word 문서를 작성할 때 이 절차를 따른다.

## Template Slot

고정 파일명:

```text
assets/templates/current/rmp-template.docx
assets/templates/current/rmr-template.docx
assets/templates/current/fmea-template.docx
```

고객사가 바뀌면 파일명은 유지하고 `.docx` 내용만 교체한다.

## Placeholder Inspection

가능하면 다음 스크립트를 사용한다.

```bash
python scripts/inspect_placeholders.py assets/templates/current/rmr-template.docx --doc-type rmr
```

확인 대상:

- 본문 paragraph
- tables and table cells
- headers
- footers
- footnotes/endnotes가 있는 경우 해당 XML

## Filling Rules

- 템플릿 파일을 직접 덮어쓰지 말고 출력 파일로 복사해 작업한다.
- 단일 값 placeholder는 동일 paragraph/run 스타일을 가능한 유지한다.
- section placeholder는 여러 paragraph로 치환한다.
- table placeholder는 placeholder paragraph를 실제 Word table로 대체한다.
- 고객사 template의 기존 heading, margins, header/footer, logo, approval block을 보존한다.
- 표가 너무 넓으면 landscape section 또는 작은 font를 검토하되, 고객사 양식을 임의로 크게 바꾸지 않는다.

## QA Rules

완료 전에 확인한다.

- 남아 있는 `{{...}}` placeholder 없음
- 문서번호, 제품명, 개정번호, intended use 일치
- RMP criteria와 FMEA/RMR 판단 일치
- 표 행이 잘리지 않음
- header/footer와 CI가 유지됨
- 페이지 번호, 목차, cross-reference가 있는 경우 업데이트 또는 고정 텍스트 처리

DOCX 산출 시 Documents skill의 render-and-verify workflow를 사용한다. 렌더링을 통해 페이지별 PNG를 확인하고, 표 깨짐, 겹침, header/footer 오류, placeholder 잔존을 점검한다.
