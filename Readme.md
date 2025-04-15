Vite + SCSS 기반의 정적 사이트 프로젝트입니다.GitHub Pages 배포 및 전달용 빌드 분리되어 있습니다.

파일 구조

src/
├── pages/        # HTML 페이지들
├── components/   # header, footer 등 핸들바르 컨포넌트
├── js/           # main.js, page별 js, 컨포넌트, 공통 모듈
├── scss/         # main.scss, layout, utils, components 등
public/
└── assets/       # 정적 이미지, 폰트 등


# 의존성 설치
npm install

# 로컬 개발 서버 실행 (PC 기준)
npm run dev

# 외부 개발 API 테스트 (dev 서버와 연동 시)
npm run dev:remote

빌드

# GitHub Pages 배포용 (절반경로: /exc-firstmove/)
npm run build:pages

# 전달용 로커 빌드 (상대경로: ./)
npm run build:local

dist/ → GitHub Pages용

build/ → 디자이너 등에게 전달할 HTML+CSS+JS

배포

# GitHub Pages에 배포
npm run deploy
배포 주소: https://yourname.github.io/레포명 ex(exc-firstmove)/

.env.devlocal
로컬 개발용 (localhost API)

.env.dev
외부 개발 서버 연동용

.env.production
배포용 환경변수

예시 (.env.example)

VITE_API_URL=http://localhost:3000
VITE_IMAGE_PATH=/assets/images

이미지의 경우 bulid 상태에 따라 scss변수명 수정

기타

CSS는 main.scss로 통합 관리

필요 시 페이지별 JS는 개별 import (about.js 등)

SCSS는 @use / @forward 방식 사용