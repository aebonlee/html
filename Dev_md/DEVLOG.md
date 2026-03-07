# 개발일지 (Development Log)

---

## 2026-03-07 (금) — DreamIT Biz 디자인 통일 전면 리뉴얼

### 작업 개요
기존 Tailwind CDN + 인라인 스타일 기반 Vibe Coding Glossary SPA를 DreamIT Biz 템플릿 디자인 시스템으로 전면 리뉴얼.
로그인 없이 모든 콘텐츠 접근 가능하도록 구현.

### 변경 파일
| 파일 | 작업 | 비고 |
|------|------|------|
| `styles.css` | 신규 생성 | DreamIT 디자인 시스템 CSS (~850줄) |
| `index.html` | 전면 재작성 | SPA 구조 + 모든 렌더 함수 리뉴얼 (~1,401줄) |
| `Dev_md/DEVLOG.md` | 신규 생성 | 본 개발일지 |
| `glossaryData_decoded.js` | 변경 없음 | 81개 용어 데이터 유지 |

---

### 1. 디자인 시스템 구축 — `styles.css`

#### 1.1 CSS Variables 색상 체계
- 기존 하드코딩(`starbucks-green: #1E3A5F`) → CSS Custom Properties 전환
- `--primary: #0046C8`, `--primary-dark: #002E8A`, `--primary-light: #4A8FE7`
- `--primary-rgb: 0, 70, 200` — `rgba()` 투명도 활용

#### 1.2 5가지 컬러 테마
| 테마 | Primary | Dark | Light |
|------|---------|------|-------|
| Blue (기본) | `#0046C8` | `#002E8A` | `#4A8FE7` |
| Red | `#DC2626` | `#991B1B` | `#F87171` |
| Green | `#059669` | `#065F46` | `#34D399` |
| Purple | `#7C3AED` | `#5B21B6` | `#A78BFA` |
| Orange | `#EA580C` | `#9A3412` | `#FB923C` |

- `[data-color]` 속성으로 전환, 네비바 컬러 피커 UI 제공

#### 1.3 다크 모드 (3모드 지원)
- **auto**: 시간 기반 자동 전환 (20:00~06:00 다크)
- **light / dark**: 강제 모드
- `[data-theme="dark"]` + Tailwind `dark:` 병행
- 쿠키 저장 (1년 유효)

#### 1.4 글래스모피즘 네비바
- `position: fixed`, `backdrop-filter: blur(12px)`, `height: 72px`
- 스크롤 감지 → `.scrolled` 클래스 (그림자 + 불투명도 증가)

#### 1.5 다크 그라데이션 푸터
- `background: linear-gradient(180deg, #111827 0%, #0A0F1A 100%)`
- 3컬럼 그리드: 브랜드 정보 | 바로가기 | 연락처
- Family Site 드롭다운

#### 1.6 카드 디자인
- `border-radius: 16px`, `hover: translateY(-6px)` + 그림자 확대
- CSS 변수 기반 보더/배경/텍스트 색상

#### 1.7 반응형 브레이크포인트
| 브레이크포인트 | 변경사항 |
|--------------|---------|
| 1100px | 모바일 네비게이션 전환 (햄버거 메뉴) |
| 1024px | 코드 패널 숨김, 2컬럼 푸터 |
| 768px | 단일 컬럼, 사이드바 숨김 |
| 480px | 소형 모바일 최적화 |

#### 1.8 스크롤 애니메이션
- `.fade-up` 클래스: `opacity:0→1`, `translateY(24px)→0`
- `IntersectionObserver` 기반, `nth-child` 순차 딜레이 (0.05s)

---

### 2. index.html 전면 재작성

#### 2.1 `<head>` 변경
- `styles.css` 링크 추가
- Tailwind 색상을 CSS 변수에 매핑 (`primary: 'var(--primary)'`)
- 페이지 타이틀 변경: `DreamIT Glossary - Vibe Coding & UI/UX`

#### 2.2 상태 관리 확장
```javascript
// 신규 상태 변수
let themeMode = 'auto';        // auto | light | dark
let colorTheme = 'blue';       // blue | red | green | purple | orange
let currentPage = 'home';      // home | vibecoding | webprog | qa | edu
let searchModalOpen = false;
let colorPickerOpen = false;
let familySiteOpen = false;
```

#### 2.3 renderNavbar() — 글래스모피즘 네비바
- 브랜드 로고: `Dream` + `IT` (그라데이션) + `Glossary` 3파트 구성
- 네비 링크: hover 시 하단 underline 애니메이션 (`::after`)
- 액션 버튼: 검색 모달, 언어 전환, 테마 3모드 순환, 컬러 피커

#### 2.4 renderFooter() — 3컬럼 다크 푸터
- 브랜드 설명 + Family Site 드롭다운
- 바로가기 링크 (Vibe Coding, Web Programming, Q&A, 교육신청)
- 연락처 (이메일, 전화, 주소)
- 하단 저작권 + 디자이너 크레딧

#### 2.5 renderGridView() — 히어로 + 카드
- 그라데이션 히어로 섹션: 전체 용어 수, 카테고리 수, 코드 예시 수 통계
- 카드: CSS 변수 기반, `hover: translateY(-6px)`, fade-up 애니메이션
- 검색 하이라이팅 (`<mark>` 태그)

#### 2.6 renderDetailView() — 통일 디자인
- `.content-card` / `.section-title` / `.section-content` 패턴 적용
- 사이드바: `.sidebar-cat-btn`, `.sidebar-term-btn` 디자인 통일
- 코드 패널: `.code-panel`, `.code-tab` 디자인 통일

#### 2.7 검색 모달
- `Ctrl+K` 단축키로 열기 / `ESC`로 닫기
- 실시간 검색 결과 (최대 12건)
- 검색어 하이라이팅 (`<mark>`)

#### 2.8 URL 해시 라우팅
- `#page=vibecoding` / `#page=webprog` / `#page=qa` / `#page=edu`
- `#term=드롭다운` — 특정 용어 직접 이동
- `popstate` 이벤트로 브라우저 뒤로가기/앞으로가기 지원

---

### 3. 신규 페이지 구현

#### 3.1 renderWebProgView() — Web Programming 기초
- HTML / CSS / JavaScript 기초 설명 카드 (이모지 아이콘)
- 바이브 코딩과 웹 기술의 관계 설명 (인용 블록)
- 학습 리소스 링크: MDN Web Docs, web.dev, W3Schools

#### 3.2 renderQAView() — Q&A
- 6개 FAQ 아코디언 (한국어/영어 이중 언어)
- 주제: UI vs UX 차이, 바이브 코딩 정의, 컴포넌트 vs 엘리먼트, 반응형 디자인, 다크 모드 구현 등
- CSS `max-height` 트랜지션 + `overflow: hidden` 토글

#### 3.3 renderEduView() — 교육신청
- 3개 과정 카드: 입문(바이브 코딩 기초) / 중급(UI/UX with AI) / 고급(풀스택 AI 개발)
- 로그인 없이 정보만 표시 (신청 양식 대신 연락처 안내)
- 교육 문의 이메일/전화번호 제공

---

### 4. 유지된 기능
- `glossaryData_decoded.js` 데이터 파일 (변경 없음)
- 81개 UI/UX 용어 + 코드 예시 (HTML/CSS/JS + iframe 결과 미리보기)
- 한/영 이중 언어 지원
- 카테고리 그룹핑 (UI 기본 6개, UI 심화 4개, UI 심화 확장 2개)
- 사이드바 아코디언 네비게이션
- 코드 패널 탭 전환 + 라이브 결과

---

### 5. 기술 스택
| 기술 | 용도 |
|------|------|
| HTML5 | 문서 구조 |
| CSS3 (Custom Properties) | 디자인 시스템, 테마, 다크모드 |
| Tailwind CSS (CDN) | 유틸리티 보조 |
| Vanilla JavaScript (IIFE) | SPA 라우팅, 렌더링, 이벤트 |
| Google Fonts (Noto Sans KR) | 타이포그래피 (400/500/600/700) |
| IntersectionObserver API | 스크롤 애니메이션 |
| Cookie API | 사용자 설정 저장 (테마, 색상, 언어) |

### 6. 파일 구조
```
D:\html\
├── index.html                  # 메인 SPA
├── styles.css                  # DreamIT 디자인 시스템 CSS
├── glossaryData_decoded.js     # 용어 데이터 (한/영 81개)
├── Dev_md/
│   └── DEVLOG.md               # 개발일지 (본 문서)
├── DEVLOG.md                   # (이전 개발 로그)
├── README.md
├── CNAME
└── .gitignore
```

---

> **다음 작업 예정**: 브라우저 테스트 (Chrome, Firefox, Safari), 모바일 반응형 확인, 접근성(a11y) 점검
