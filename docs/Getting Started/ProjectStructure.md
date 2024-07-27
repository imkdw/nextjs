# 최상위 폴더

- 최상위 폴더에는 어플리케이션의 코드와 정적 에셋들이 존재함
- `app` : App Router 폴더
- `pages` : Pages Router 폴더
- `public` : 정적 에셋들
- `src` : 어플리케이션 코드들 모음, 선택적으로 사용가능함

<br/>

# 최상위 파일들

- 최상위 파일들은 어플리케이션 설정 파일들임
- 의존성관리, 미들웨어, 모니터링툴, 환경변수 등이 있음
- `next.config.ts` : Next.js 설정파일
- `package.json` : 프로젝트의 의존성 및 스크립트 관리
- ` instrumentation.ts` : 모니터링 등 정의파일
- `middleware.ts` : Request 미들웨어
- `.env` : 환경 변수들
- `.env.local` : 로컬 환경의 환경변수
- `.env.production` : 프로덕션 환경의 환경변수
- `.env.development` : 개발 환경의 환경변수
- `eslintrc.json` : ESLint 설정
- `.gitignore` : Git 업로드에서 제외할 파일들
- `next-env.d.ts` : Next.js의 타입스크립트 타입 정의파일
- `tsconfig.json` : 타입스크립트 설정
- `jsconfig.json` : 자바스크립트 설정

<br/>

# App Router 컨벤션

- App Router에서 라우터, 메타데이터 등을 사용할때 따라야하는 컨벤션들
- `layout` : 레이아웃
- `page` : 페이지
- `loading` : 로딩중 UI
- `not-found` : 리소스를 찾을 수 없을때 UI
- `error` : 기타 에러 UI
- `global-error` : 글로벌 에러 UI
- `route` : API 엔드포인트, tsx/jsx 사용불가
- `template` : 리렌더링 되는 레이아웃
- `default` : 병렬 라우팅에 대한 fallback 페이지

<br/>

# 중첩 라우터

- `folder` : 라우터
- `folder/folder` : 중첩 라우터

<br/>

# 동적 라우터

- `[folder]` : 동적 라우터
- `[...folder]` : 모든 라우터를 칭함
- `[[...folder]]` : 선택적인 모든 라우터를 칭함

<br/>

# 라우터 그룹과 비공개 폴더

- `(folder)` : 라우터에 영향을 주지 않고 파일을 그룹화 하기위해 사용
- `_folder` : 현재 폴더와 모든 하위 자식 폴더를 라우터에서 제외함

<br/>

# Parallel and Intercepted Routes

TODO: 아직 어디에 쓰는지 모르겠음

<br/>

# 메타데이터 파일 컨벤션

### 앱 아이콘들

- `favicon` : 파비콘 파일
  - ico
- `icon` : 앱 아이콘 파일들
  - ico, jpg, jpeg, png, svg
- `icon` : 동적으로 생성되는 아이콘들
  - js, ts, tsx
- `apple-icon` : 애플 앱 아이콘들
  - jpg, jpeg, png
- `apple-icon` : 동적으로 생성되는 애플 앱 아이콘들
  - js, ts, tsx

### 오픈그래프와 트위터 이미지들

- `opengrapgh-image` : 오픈그래프 이미지들
  - jpg, jpeg, png, gif
- `opengraph-image` : 동적으로 생성되는 오픈그래프 이미지들
  - js, ts, tsx
- `twiter-image` : 트위터 이미지들
  - jpg, jpeg, png, gif
- `twiter-image` : 동적으로 생성되는 트위터 이미지들
  - js, ts, tsx

### 검색 엔진 최적화(SEO) 관련

- `sitemap` : 사이트맵 파일
  - xml
- `sitemap` : 동적으로 생성되는 사이트맵 파일
  - js, ts
- `robots` : 로봇 파일
  - txt
- `robots` : 동적으로 생성되는 로봇 파일
  - js, ts
