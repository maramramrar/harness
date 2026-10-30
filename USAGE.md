# 사용법

1. 작업 폴더 안에 clone: `git clone https://github.com/maramramrar/harness`
2. 규칙과 기록 파일 복사 (과제에 AGENTS.md가 있으면 MY_RULES.md 이름 그대로)
   - harness/MY_RULES.md → ./AGENTS.md
   - harness/templates/의 REQUIREMENTS.md, DECISIONS.md, VERIFY.md → ./ (같은 이름 파일이 이미 있으면 덮어쓰지 않음)
3. git에서 제외: .gitignore에 `harness/` 한 줄 추가
4. 첫 번째 지시: 
```
   harness 폴더를 이용해 작업 준비를 해줘:
   1) harness/MY_RULES.md를 작업 폴더 루트에 AGENTS.md로 복사 (루트에 AGENTS.md가 이미 있으면 MY_RULES.md 이름 그대로 복사)
   2) harness/templates의 REQUIREMENTS.md, DECISIONS.md, VERIFY.md를 루트로 복사 (같은 이름 파일이 있으면 덮어쓰지 마)
   3) .gitignore에 harness/ 추가
   끝나면 루트 파일 목록만 보여줘.
```
두 번째 지시:
```
   AGENTS.md를 읽고 규칙을 3줄로 요약해줘. harness 폴더는 내 작업 도구이니 분석 대상에서 제외해.
   그다음 README와 data 폴더를 분석해서 다음만 제시하고 구현은 대기해:
   1) README의 요구사항 목록
   2) 데이터 구조와 품질 점검 결과(결측, 중복, 형식, 이상치, 시간대)
   3) 모호하거나 빠진 점, 그리고 담당자에게 물을 질문(답에 따라 구현이 달라지는 것만)
```
5. 적대적 리뷰 결과는 참고용이다. 채택 여부는 직접 판단한다.
6. 기능 하나를 마칠 때 (AI가 잊기 쉬우니 직접 한 줄 지시)
   - 결정 후: "방금 결정한 X와 이유를 DECISIONS.md에 기록해."
   - 검증 후: "방금 검증 결과를 VERIFY.md에 기록해."
   - AI 오류를 잡았을 때: "네가 X를 틀렸고 내가 Y로 발견해서 Z로 고쳤어. DECISIONS.md의 AI 수정 기록에 적어."
7. 큰 기능 시작 전: "REQUIREMENTS.md와 VERIFY.md를 다시 읽고 남은 요구사항과 미검증 항목을 알려줘."
8. 140분쯤: 세 기록 파일의 빈 곳을 확인하고 제출 문서 작성을 지시.
9. 제출 직전: harness 폴더 삭제 (제출물에 섞이지 않게)
