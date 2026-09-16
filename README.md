# QUESTION / FORM

**생각을, 이해되는 형태로.**

[공개 포트폴리오 바로 보기](https://question-to-form-tb-portfolio.elindaystar.chatgpt.site)

기획서의 정보 구조와 디자인 가이드를 바탕으로 만든 개인 디자이너 포트폴리오입니다. 로그인 없이 누구나 볼 수 있습니다.

## 페이지

- Home: Hero → About → Selected Work → Design Attitude → Contact
- Projects: ALL / UI·UX / BRANDING / GRAPHIC 즉시 필터
- Project: Overview → Question → Interpret → Form → Result → Next Project
- 반응형 전체 화면 메뉴, 키보드 탐색, 모션 감소 설정, 스크롤 강조, 프로젝트 hover, 드래그 갤러리

## 콘텐츠 상태

이름·이메일·실제 작업 자료는 등록 전입니다. 프로젝트 3개와 타이포그래피 비주얼은 **구성 예시**이며 실제 수행 이력이나 성과를 의미하지 않습니다. GitHub는 연결된 계정의 실제 프로필입니다.

## 콘텐츠 수정

`includes/project-data.php`에서 프로필과 프로젝트를 관리합니다. `includes/header.php`, `includes/footer.php`는 공통 레이아웃입니다. `index.php`, `projects.php`, `project.php`는 PHP 원본입니다. 스타일과 기능별 JavaScript는 `dist/css/editorial.css`, `dist/js/`에 있습니다.

## 실행

XAMPP의 Apache 문서 루트에 이 폴더를 복사한 뒤 `index.php`를 엽니다. 상세 페이지는 `project.php?id=project01` 형식입니다. PHP 8 이상을 권장합니다.

정적 배포용 페이지는 같은 PHP 템플릿에서 생성합니다.

```sh
node generate.mjs
node validate.mjs
node server.mjs
```

`generate.mjs`는 기본적으로 Windows XAMPP의 PHP를 사용합니다. 다른 환경에서는 `PHP_BINARY` 환경 변수에 PHP 실행 파일 경로를 지정합니다. 공개 호스팅에는 PHP 소스가 아닌 `dist/`의 정적 HTML·CSS·JavaScript만 배포합니다. 정적 상세 페이지는 JavaScript 없이도 읽을 수 있습니다.

브라우저에서 `http://127.0.0.1:4173`으로 확인할 수 있습니다. 서버에는 데이터베이스나 로그인 기능이 없습니다.


## GitHub 배포본

이 저장소의 루트 HTML은 CSS·JavaScript를 포함한 독립 실행형 정적 배포본입니다. PHP 원본과 콘텐츠 데이터는 [question-form-source.zip](question-form-source.zip)에 포함되어 있습니다. 원본에서 `node generate.mjs`로 다시 내보낼 수 있습니다.
