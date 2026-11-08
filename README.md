# 양희본 0집 웹사이트

- `index.html`: 공개 페이지
- `admin.html`: 관리자 페이지 (`사이트주소/admin.html`)
- `content.json`: 페이지에 들어가는 모든 글과 링크. 관리자 페이지에서 고치면 이 파일이 바뀌어요.
- `images/`: 관리자 페이지에서 올린 자켓 이미지가 저장되는 곳
- `firebase.json`: Firebase Hosting 설정

## 동작 방식

관리자 페이지에서 저장 → GitHub 저장소의 content.json이 바뀜 → GitHub Actions가 Firebase에 자동 배포 → 1~2분 뒤 사이트에 반영

## 처음 한 번만 하는 설정 (PC에서)

1. Firebase 콘솔(https://console.firebase.google.com)에서 프로젝트 만들기
2. Node.js(https://nodejs.org) 설치 후 터미널에서:

```
npm install -g firebase-tools
firebase login
git clone https://github.com/heebonyang/md
cd md
firebase use --add
firebase init hosting:github
```

- `firebase use --add`: 1번에서 만든 프로젝트 선택, 별칭은 `default`
- `firebase init hosting:github`: 저장소 `heebonyang/md` 입력
  - build script 실행? → No
  - merge 시 자동 배포? → Yes, 브랜치는 `main`
3. 생긴 파일을 GitHub에 올리기:

```
git add -A
git commit -m "Firebase 자동 배포 설정"
git push
```

4. 1~2분 뒤 `https://<프로젝트ID>.web.app` 에서 사이트 확인

## 관리자 토큰 만들기

1. GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token (https://github.com/settings/personal-access-tokens/new)
2. Repository access: **이 저장소만** 선택
3. Permissions → Repository permissions → **Contents: Read and write**
4. `admin.html`에서 아이디 `heebonyang`, 저장소 `md`, 브랜치 `main`, 토큰 입력

토큰은 그 브라우저에만 저장돼요. 다른 기기나 공용 PC에서 쓴 뒤에는 "연결 해제"를 눌러 주세요.
관리자 페이지 주소는 누구나 열 수 있지만, 토큰이 없으면 아무것도 바꿀 수 없어요.
