# 양희본 0집 웹사이트

https://heebonmd.web.app

- `index.html`: 공개 페이지 (0집 판매 · 100일 라이브 · 공연)
- `content.json`: 페이지 문구의 처음 값. 관리자에서 한 번이라도 저장하면 그 뒤로는 저장한 값을 써요.
- `images/`: 자켓 이미지 (`album0.jpg`)
- `firebase.json`: Firebase Hosting 설정

## 문구 고치기

메인 홈페이지 관리자 **https://heebonyang.web.app/admin** › **0집 페이지** 에서 구글 계정으로 로그인해 고쳐요.
저장하면 Firestore(`heebonyang` 프로젝트의 `settings/albumPage`)에 들어가고, 이 페이지를 새로고침하면 바로 반영돼요. 배포는 필요 없어요.
(`heebonmd.web.app/admin` 으로 들어가도 메인 홈페이지 관리자로 이동해요.)

주문은 같은 관리자의 **0집 주문**, 남은 수량은 **0집 CD** 에서 관리해요.

## 코드 배포

`main`에 푸시하면 GitHub Actions(`.github/workflows/deploy.yml`)가 Firebase Hosting(`heebonmd`)에 자동 배포해요.
필요한 비밀값: 저장소 Settings › Secrets › `FIREBASE_SERVICE_ACCOUNT`
