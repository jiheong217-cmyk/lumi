# LUMI

정적 채팅 웹사이트 (index.html 하나 + Firebase Realtime Database / Auth).

- 방문자 화면: `https://jiheong217-cmyk.github.io/lumi/`
- 운영자 화면: `https://jiheong217-cmyk.github.io/lumi/#operator`

## 설정
1. `index.html` 맨 위 `LUMI_CONFIG` 에 Firebase 웹 앱 설정값과 `OWNER_EMAIL` 입력
2. `database.rules.json` 의 운영자 이메일(5곳)을 `OWNER_EMAIL` 과 같게 맞춘 뒤 Firebase 콘솔 → Realtime Database → 규칙에 붙여넣기

운영자 이메일을 바꾸면 index.html 과 database.rules.json 두 곳을 모두 바꿔야 합니다.

## 데이터 구조
```
rooms/{익명uid_대화번호}/u/{pushId}: {t, ts}   방문자 메시지
rooms/{익명uid_대화번호}/a/{pushId}: {t, ts}   운영자 답장
rooms/{...}/typing    운영자 입력 중 (true / 없음)
rooms/{...}/updated   마지막 활동 시각
rooms/{...}/seen      운영자가 마지막으로 읽은 시각 (안 읽은 개수 계산용)
```
