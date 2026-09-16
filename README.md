# QUESTION / FORM — 윤아인

**생각을, 이해되는 형태로.**

[공개 포트폴리오](https://question-to-form-tb-portfolio.elindaystar.chatgpt.site)

## 구성

- HOME: Hero → About → Profile → Selected Work → Design Attitude → Contact
- PROFILE: 윤아인 / meihaodeguanxi@gmail.com / Figma, Photoshop, Illustrator, After Effects / 웹디자인기능사, 컴퓨터그래픽스기능사, 시각디자인산업기사
- UI/UX: Ligachembio, GST, MOODLE
- BRANDING: UNSEEN, 아리담
- GRAPHIC: 라운드랩 독도
- CONTACT: 이메일 링크

실제 첨부 작업물 6개를 사용합니다. 제공되지 않은 연도·취득일·참여율·성과는 추가하지 않았습니다. 프로젝트 설명은 제공 이미지의 시각적 내용을 바탕으로 작성했습니다.

## home 폴더

```
home/
├── index.php                 # Home 및 Profile 포함
├── projects.php              # 6개 프로젝트 / 카테고리 필터
├── project.php               # 재사용하는 상세 템플릿
├── includes/                 # 공통 헤더·푸터·프로필·프로젝트 데이터
├── dist/
│   ├── *.html                # 공개 배포용 정적 페이지
│   ├── assets/projects/      # 원본 비율과 해상도를 유지한 WebP 6개
│   ├── css/editorial.css
│   └── js/                   # 메뉴, 필터, 커서, 모션
├── generate.mjs              # PHP → 정적 HTML
├── export-github.mjs         # GitHub 업로드본 준비
├── validate.mjs              # 링크·이미지·콘텐츠 검증
├── server.mjs                # 정적 미리보기
└── .openai/hosting.json      # 기존 공개 사이트 연결
```

## 수정 및 실행

프로필·프로젝트는 `includes/project-data.php`에서 관리합니다. 썸네일은 원본 이미지를 변형하지 않고 CSS `object-fit`과 프로젝트별 `crop`, `ratio` 값으로 필요한 부분만 보여줍니다. 상세 페이지에는 잘리지 않은 전체 작업물이 표시됩니다.

XAMPP의 `htdocs` 안에 `home` 폴더를 복사하면 `http://localhost/home/index.php`에서 실행할 수 있습니다. 상세 URL은 `project.php?id=project01`부터 `project06`까지 지원합니다.

```sh
node generate.mjs
node validate.mjs
node server.mjs
```

미리보기: `http://127.0.0.1:4173`. PHP 경로는 `PHP_BINARY` 환경 변수로 설정할 수 있습니다. Windows 기본값은 `C:/xampp/php/php.exe`, 그 외에는 `php`입니다.

정적 호스팅에는 `dist/`만 배포합니다. 이름, 이메일과 자격증은 사용자가 공개하도록 제공한 정보입니다.


## GitHub 배포본

저장소 루트 HTML과 WebP 파일은 바로 호스팅할 수 있는 정적 사이트입니다. 정리된 `home` 폴더의 PHP 원본은 [question-form-source.zip](question-form-source.zip)에서 내려받을 수 있습니다.
