# 양희본 0집 웹사이트

- `index.html`: 공개 페이지
- `admin.html`: 관리자 페이지 (`사이트주소/admin.html`)
- `content.json`: 페이지에 들어가는 모든 글과 링크. 관리자 페이지에서 고치면 이 파일이 바뀌어요.
- `images/`: 관리자 페이지에서 올린 자켓 이미지가 저장되는 곳

## 처음 한 번만 하는 설정

1. 이 파일들을 GitHub 저장소에 올리기
2. 저장소 Settings → Pages → Source를 `main` 브랜치, `/ (root)`로 설정
3. 1~2분 뒤 `https://<아이디>.github.io/<저장소>/` 에서 사이트 확인

## 관리자 토큰 만들기

1. GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token
2. Repository access: **이 저장소만** 선택
3. Permissions → Repository permissions → **Contents: Read and write**
4. 만든 토큰을 `admin.html`의 토큰 칸에 붙여넣기

토큰은 그 브라우저에만 저장돼요. 다른 기기나 공용 PC에서 쓴 뒤에는 "연결 해제"를 눌러 주세요.
관리자 페이지 주소는 누구나 열 수 있지만, 토큰이 없으면 아무것도 바꿀 수 없어요.
