# 사용법

0. 아무것도 바꾸기 전에 처음 상태 기록: `git log`로 이미 저장소인지 확인
   - 저장소가 아니면 `git init` → `git add .` → `git commit -m "task baseline"` (과제가 준 파일만 담긴 기준점)
   - 이미 저장소면 기존 첫 커밋이 기준점

1. 작업 폴더 안에 clone: `git clone https://github.com/maramramrar/harness`

2. 첫 번째 지시 (작업 준비)
```
harness 폴더를 이용해 작업 준비를 해줘:
1) harness/MY_RULES.md를 작업 폴더 루트에 AGENTS.md로 복사 (루트에 AGENTS.md가 이미 있으면 MY_RULES.md 이름 그대로 복사)
2) harness/templates의 REQUIREMENTS.md, DECISIONS.md, VERIFY.md를 루트로 복사 (같은 이름 파일이 있으면 덮어쓰지 마)
3) .gitignore에 harness/ 추가
끝나면 루트 파일 목록만 보여줘.
```

3. 두 번째 지시 (분석, 구현 대기)
```
AGENTS.md를 읽고 규칙을 3줄로 요약해줘. harness 폴더는 내 작업 도구이니 분석 대상에서 제외해.
그다음 README와 과제가 제공한 파일 전체(harness 제외)를 분석해서 다음만 제시하고 구현은 대기해:
1) README의 요구사항 목록
2) 데이터 구조와 품질 점검 결과(결측, 중복, 형식, 이상치, 시간대)
3) 모호하거나 빠진 점, 그리고 담당자에게 물을 질문(답에 따라 구현이 달라지는 것만)
```
과제 AGENTS.md가 따로 있었다면 "MY_RULES.md도 읽고, 충돌하면 과제 쪽이 우선"을 덧붙인다.

4. 준비가 끝나면 `git add .` → `git commit -m "setup: rules and records"`. push는 하지 않는다.

5. 담당자 답변을 받으면: "담당자 답변이야: (내용). REQUIREMENTS.md에 기록하고 요구사항 표를 갱신해. 그다음 REQUIREMENTS.md에 '## 구현 계획' 섹션을 만들어 단계마다 요구사항 ID, 완료 기준, 검증 방법을 적어. 아직 구현하지 마."
   계획을 보고 모든 필수 요구사항 ID가 어느 단계에 들어갔는지 확인한 뒤 승인한다.

6. 기능 하나를 마칠 때 (AI가 잊기 쉬우니 직접 한 줄 지시)
   - 결정 후: "방금 결정한 X와 이유를 DECISIONS.md에 기록해."
   - 검증 후: "방금 검증 결과를 VERIFY.md에 기록해."
   - AI 오류를 잡았을 때: "네가 X를 틀렸고 내가 Y로 발견해서 Z로 고쳤어. DECISIONS.md의 AI 수정 기록에 적어."

7. 큰 기능 시작 전, 또는 /compact 후: "REQUIREMENTS.md, DECISIONS.md, VERIFY.md를 다시 읽고 필수 요구사항, 완료된 기능, 미검증 항목, 다음 작업을 짧게 보고해."
   /compact 전에는 기록 파일 3개를 먼저 갱신시킨다.

8. 적대적 리뷰 (핵심 완성 후, 제출 전): 새 세션(새 터미널에서 codex, 또는 /new)에 harness/templates/REVIEW_PROMPT.md를 붙여넣는다. 처리 순서: [필수] 요구사항 위반·재현되는 오류는 수정 / [위험] 증거가 약한 잠재 위험은 확인 후 판단 / [선택] 취향·선택 기능은 시간이 없으면 보류.

9. 140분쯤: 구현을 멈추고 세 기록 파일의 빈 곳을 확인한 뒤 제출 문서 작성을 지시한다.
```
README에서 제출 문서의 파일명과 양식을 확인해. 지정된 양식이 있으면 그대로 따르고,
없으면 harness/templates/SUBMISSION.md의 목차 구조를 써.
내용은 REQUIREMENTS.md, DECISIONS.md, VERIFY.md를 근거로 하고, 확인되지 않은 건 미검증으로 적어.
```
   한계와 AI 활용 방식 부분은 직접 읽고 고친다.

9-1. 시간이 남으면 (제출 전 5분): 서술형 대비
```
지금까지의 작업 기록(대화, git 로그, 코드, 테스트, 기록 파일, 제출 문서)을 보고
평가자가 물을 만한 확인 질문 10개를 만들어. 질문만 쓰고 답은 쓰지 마. 파일로 저장하지 마.
```
   답은 머릿속으로 직접 해 본다. 시간이 없으면 DECISIONS.md를 다시 읽는 것으로 대신한다.

10. 제출 직전 (종료 10분 전 시작)
   - 과제가 지정한 제출 파일이 있고 저장됨 상태인지 확인
   - `git diff --stat <첫 커밋>`으로 처음부터 있던 파일이 바뀌지 않았는지 확인
   - harness 폴더와 생성물(__pycache__ 등) 삭제

참고: 작업 도중 규칙을 갱신할 때는 첫 번째 지시를 다시 돌리지 말고 AGENTS.md를 직접 덮어쓴 뒤 "AGENTS.md가 갱신됐어. 다시 읽어."라고 말한다.
