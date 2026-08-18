# 찬양 가사 정리 (Worship Lyric Formatter)

프로프리젠터(ProPresenter) 입력에 최적화된 찬양 가사 정리 웹앱입니다.
가사를 섹션(송폼)별로 분류하고, 2줄 단위 슬라이드로 정리해 다양한 형식으로 내보낼 수 있습니다.

## 주요 기능

- **섹션 구분** — `<A>`, `<B>`, `<후렴>`, `<간주>` 처럼 `< >` 로 감싼 태그를 섹션으로 인식
- **송폼 정렬** — `A-A-B-C` 형식으로 입력하면 그 순서대로 가사를 펼쳐 정리
- **복사** — 맑은 고딕 11pt 서식으로 복사 (Word에 붙여넣기 최적화), 메모장·ProPresenter에는 순수 텍스트로 붙음
- **파일 출력**
  - **TXT** — 텍스트 파일 (오프라인 가능)
  - **Word** — 맑은 고딕 11pt 문서 (오프라인 가능)
  - **PPTX** — 두 가지 버전
    - 투명배경 (녹색 #00FF00 크로마키) — PGM 화면 위에 가사만 올릴 때
    - 검정배경 · 흰 글씨 가운데 정렬
- **가사 라이브러리** — 브라우저에 곡을 저장/검색/불러오기, JSON 내보내기·가져오기로 백업

## 배포 방법 (GitHub → Vercel)

### 1. GitHub에 업로드

```bash
# 이 폴더에서
git init
git add .
git commit -m "찬양 가사 정리 웹앱"
git branch -M main
git remote add origin https://github.com/<사용자명>/<저장소명>.git
git push -u origin main
```

또는 GitHub 웹사이트에서 새 저장소를 만들고 이 폴더의 파일들을 그대로 업로드해도 됩니다.

### 2. Vercel로 배포

1. [vercel.com](https://vercel.com) 접속 후 GitHub 계정으로 로그인
2. **Add New → Project** 클릭
3. 방금 올린 저장소를 **Import**
4. 프레임워크 설정은 자동으로 **Other**(정적 사이트)로 인식됩니다 — 그대로 **Deploy**
5. 잠시 후 `https://<프로젝트명>.vercel.app` 주소가 생성됩니다

별도 빌드 설정이 필요 없습니다. `index.html` 하나로 동작하는 정적 사이트입니다.

## 참고

- **PPTX 출력**은 외부 라이브러리(PptxGenJS)를 CDN에서 불러오므로 **인터넷 연결이 필요**합니다. TXT·Word 출력은 오프라인에서도 동작합니다.
- **가사 라이브러리**는 사용하는 브라우저에 저장(localStorage)됩니다. 다른 기기로 옮기려면 "라이브러리 내보내기"로 JSON을 저장한 뒤, 다른 기기에서 "가져오기" 하세요.
- 저작권이 있는 가사를 직접 배포하지 않도록 주의하세요. 이 앱은 가사를 내장하지 않으며, 사용자가 입력한 내용만 처리합니다.

## 파일 구성

```
├── index.html      # 앱 본체 (단일 파일)
├── vercel.json     # Vercel 배포 설정
├── .gitignore
└── README.md
```
