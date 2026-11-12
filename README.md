# MY DESK HEROES — 책상 위 작은 히어로

HTML, CSS, JavaScript로 제작한 피규어 컬렉션 관리 사이트입니다.

## 파일 구성

- `index.html`: 화면 구성, 등록 폼
- `style.css`: 디자인, 모바일 대응
- `app.js`: 예시 데이터, 검색, 분류, 등록, 수정, 삭제, 즐겨찾기, 백업
- `README.md`: 사용 및 업로드 안내

## 실행

압축을 풀고 index.html을 브라우저로 열면 화면을 확인할 수 있습니다.
등록·저장 기능은 HTTPS로 배포한 사이트 또는 로컬 서버에서 사용하는 것을 권장합니다.
Python이 설치되어 있다면 이 폴더에서 `python -m http.server 8000`을 실행하고
브라우저에서 http://localhost:8000 을 엽니다. 별도 패키지 설치나 빌드가 필요하지 않습니다.

## GitHub에 직접 업로드

1. GitHub에 로그인하고 새 저장소를 만듭니다. 예시 이름: `mydeskheroes`.
2. 새 저장소 화면의 `uploading an existing file`을 선택합니다.
   기존 파일이 있는 저장소에서는 `Add file` → `Upload files`를 선택합니다.
3. ZIP을 먼저 압축 해제한 뒤, 안에 있는 index.html, style.css, app.js, README.md 파일을 드래그합니다.
4. 저장 메시지를 입력하고 변경 사항을 커밋합니다. 새 저장소의 기본 브랜치는 main을 사용합니다.
5. 저장소 첫 화면에 index.html이 바로 보이는지 확인합니다.

**ZIP 파일 자체를 올리거나 상위 폴더로 한 겹 감싸지 마세요. 네 파일을 저장소 최상위에 올리면 됩니다.**

## Cloudflare Pages 연결

Cloudflare의 Workers & Pages에서 Pages 프로젝트를 생성하고 Git 저장소 가져오기를 선택합니다.
GitHub의 mydeskheroes 저장소를 연결하고 아래처럼 설정합니다.

| 항목 | 값 |
| --- | --- |
| Production branch | main |
| Framework preset | None |
| Build command | exit 0 |
| Build output directory | . |
| Root directory | 기본값 (저장소 최상위) |

배포가 완료되면 발급된 사이트 주소로 접속합니다.

## 사용 및 데이터 저장

- 처음 나오는 6개 피규어는 예시 데이터이며 실제 소장 목록이 아닙니다.
- 그림은 제품 사진이 아닌 예시 SVG 일러스트입니다. 사진을 직접 등록할 수 있습니다.
- 컬렉션은 브라우저 localStorage에 저장됩니다. 회원가입이나 서버 DB는 없습니다.
- 다른 기기나 다른 사이트 주소에서는 데이터가 공유되지 않습니다.
- 브라우저 데이터를 지우면 기록이 사라질 수 있으므로 백업 버튼으로 JSON 파일을 보관하세요.
- 기존 사이트에서 등록한 데이터는 백업 후 새 배포 사이트에서 불러올 수 있습니다.
- 예시 목록을 모두 바꾸려면 app.js의 seed 배열을 수정합니다.
- Google Fonts를 불러오며, 연결되지 않으면 기본 글꼴로 표시됩니다.

## 공식 참고 문서

- GitHub 파일 업로드: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- Cloudflare 정적 HTML 배포: https://developers.cloudflare.com/pages/framework-guides/deploy-anything/
