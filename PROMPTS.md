# 단계별 요청 문장

## 0. 시작 (codex 켜고 `/status`로 모델 확인 후)
"github.com/yunhyuk-mun/cofa-harness clone해서 AGENTS.md, PROMPTS.md, templates 안의 파일들을 README.md가 있는 폴더에 복사해 줘. 같은 이름 파일이 이미 있으면 덮어쓰지 말고 알려 줘. 하네스의 README.md는 절대 복사하지 마. 끝나면 clone 폴더 지우고 ls로 보여 줘. 그다음 AGENTS.md 읽고 앞으로 그 규칙 따라 줘. git 사용자 이름은 yunhyuk-mun, 메일은 moonyoonh41@gmail.com으로 이 폴더에만 설정해 줘."

직접 할 때 (터미널):
```
git clone https://github.com/yunhyuk-mun/cofa-harness && cp -n cofa-harness/AGENTS.md cofa-harness/PROMPTS.md . && cp -n cofa-harness/templates/* . && rm -rf cofa-harness
```

## 1. 계획
"README 읽고 plan.md 채워 줘. 목표·제출물·제약은 숫자 그대로. 내가 정할 곳은 [결정 필요]로 표시해. 아직 분석하지 마. git 저장소 없으면 init 하고 commit 해 줘."

→ 내가 확인: 제출물 빠짐없나 / 숫자 맞나 / 내 해석 한 줄 말해서 넣기

## 2. 담당자 질문 (메신저, 3~4단계에서 애매한 점이 나올 때)
"무엇을 봤는데 → ~인가요?" 형식. 결정 말고 사실을 묻기. ("A로 할까요?" X → "현장에선 A와 B 중 어느 쪽이 더 자주 문제인가요?" O)
답 기다리는 동안: "decision_log에 [대기]로 질문 남기고, [가정]으로 ~를 골라 진행해 줘."

## 3. 데이터 점검
"파일별로 중복·결측·범위 밖 값·표기가 다른 값을 스크립트로 찾아서 건수와 예시를 표로 보여 줘. 원본 수정하지 말고 처리는 아직 하지 마."

→ 내가 결정: "~는 제거, ~는 제외. decision_log에 [확정/잠정]으로 이유와 같이 남기고 commit 해 줘."

## 4. 판단 기준
"좋은 결과를 판단할 기준 후보 5~6개를 계산 방법·장점·단점 표로 줘."

→ 내가 결정: "기준은 ~, 가중치 ~. 버린 건 ~(이유). criteria.json에 넣고 decision_log에 남겨 줘."

## 5. 빈 화면 먼저
"빈 웹페이지를 0.0.0.0으로 띄워 줘. 포트 알려 주고 commit 해 줘."

→ Browser 도구에 포트 입력 → 원형 화살표

## 6. 로직 + 화면
"criteria.json을 읽어서 결과를 계산하는 코드를 만들고, 조건 검사는 check.py로 따로 만들어 줘. 결과를 화면에 연결하고 commit 해 줘."

## 7. 검증 (새 터미널, 새 codex)
"원본 데이터와 criteria.json만 보고 핵심 숫자를 다시 계산해 줘. 기존 코드는 보지 마. 계산 코드는 verify/ 폴더에 새로 만들고, 다른 파일은 절대 고치지 마. 기존 결과와 다른 점, 규칙 위반, 빠진 조건을 표로만 보여 줘."

→ 내가 결정 (원래 codex에서): "검증 피드백 N번은 반영(이유), M번은 안 함(이유). 반영한 것과 안 한 것 둘 다 decision_log에 남기고 commit 해 줘."

## 8. 마무리 (끝나기 20분 전)
"report.md 채워 줘. 결론 → 근거 숫자 → 확인한 것/미검증 → 한계. decision_log 정리하고 마지막 commit 해 줘."

## 수시로
- "git log --oneline 보여 줘" (1시간에 한 번)
- AI 답을 내가 고쳤으면: "~가 틀려서 ~로 고쳤다. decision_log에 남겨 줘."
- 막히면 plan.md로 돌아가서 범위 줄이기
