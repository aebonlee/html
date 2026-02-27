# Vibe Coding Glossary 개발일지

## 프로젝트 개요

| 항목 | 내용 |
|------|------|
| **프로젝트명** | Vibe Coding Glossary (UI/UX 용어집) |
| **개발일** | 2026년 2월 27일 |
| **저장소** | https://github.com/aebonlee/html |
| **배포 URL** | https://html.dreamitbiz.com |
| **기술 스택** | HTML5, Tailwind CSS (CDN), Vanilla JavaScript, SVG |
| **참고 사이트** | https://vibe-coding-glossary-8101927467.us-west1.run.app/ |

---

## 1. 프로젝트 목표

UI/UX 디자인에서 자주 사용되는 81개 용어를 **한국어/영어** 양국어로 제공하는 인터랙티브 웹 용어집을 구축한다. 각 용어에 대해 설명, 사용 시점, 실제 예시, SVG 시각화 예시를 포함하여 비전공자도 직관적으로 이해할 수 있도록 한다.

---

## 2. 개발 타임라인

### Phase 1 - 초기 설정 (04:29 ~ 07:12)

| 시간 | 커밋 | 내용 |
|------|------|------|
| 04:29 | `c5cb7fa` | Initial commit - 저장소 초기 생성 |
| 04:30 | `1ed5b7e` | CNAME 설정 (`html.dreamitbiz.com`) |
| 04:34 ~ 07:12 | `4c254d5` ~ `95c072a` | HTML 구조 수정 및 기본 코드 테스트 |

### Phase 2 - 본격 개발 (15:03)

| 시간 | 커밋 | 내용 |
|------|------|------|
| 15:03 | `8206ef5` | **Vibe Coding Glossary 사이트 전체 구축** |

**주요 작업 내용:**

- 참고 사이트 분석 및 전체 콘텐츠 추출 (71개 용어, 13개 카테고리)
- `glossaryData_decoded.js` 데이터 파일 구성 (한국어/영어 양국어)
- `index.html` 단일 파일로 전체 UI 구현
- 그리드 뷰 (메인 홈) + 상세 뷰 (사이드바 + 콘텐츠 패널) 2가지 뷰 구현
- 다크모드, 언어 전환, 검색, 반응형 레이아웃 기능 구현
- 81개 SVG 시각화 예시 포함 (애니메이션 포함)

### Phase 3 - 디자인 커스터마이징 (15:06)

| 시간 | 커밋 | 내용 |
|------|------|------|
| 15:06 | `71f6db3` | **다크블루 컬러 테마 적용 + 카드 1.5배 확대** |

**주요 변경 사항:**

- 메인 컬러: `#00704A` (스타벅스 그린) → `#1E3A5F` (다크블루)
- 라이트 배경: `#F0F7F5` → `#EBF0F7`
- 다크모드 액센트: `emerald-400` → `sky-400`
- 메인 그리드 카드 크기 1.5배 확대
  - 패딩: `p-4` → `p-6`
  - SVG 영역 높이: `80px` → `120px`
  - 폰트: `text-sm` → `text-base`
  - 그리드 열 수: 최대 6열 → 최대 4열

### Phase 4 - UI 보완 및 크레딧 수정 (15:10)

| 시간 | 커밋 | 내용 |
|------|------|------|
| 15:10 | `cbd39af` | **디자이너 크레딧 수정 + 폰트 가독성 개선** |

**주요 변경 사항:**

- 디자이너 크레딧: `Designed by Junseong Hong` → `Designed by Ph.D Aebon Lee`
- 사이드바 용어 목록 폰트 굵기 완화: `font-semibold` → `font-normal` (선택 시 `font-medium`)
- 카테고리 헤더 폰트 굵기 완화: `font-semibold` → `font-medium`
- 그리드 카드 제목 폰트 조정: `text-base font-semibold` → `text-sm font-medium`
- 전체적인 가독성 향상을 위한 폰트 웨이트 최적화

### Phase 5 - 상세 뷰 UI 개선 + 용어 추가 (2026-02-27)

**주요 변경 사항:**

#### 상세 뷰 레이아웃 전면 개편
- **기존**: 좌측 사이드바(카테고리 + 전체 71개 용어 나열) + 우측 콘텐츠 패널
- **변경**: 사이드바 제거 → 상단 내비게이션으로 통합
  - **상단 고정 헤더**: 홈 버튼, 제목, 언어/다크모드 토글
  - **카테고리 탭 바**: 가로 스크롤 가능한 칩(Chip) 형태 버튼, sticky 고정
  - **용어 드롭다운**: 선택된 카테고리의 용어를 `<select>` 드롭다운으로 표시
  - **콘텐츠 영역**: 전체 너비 활용으로 가독성 대폭 향상
- 모바일 오버레이/햄버거 메뉴 관련 코드 제거 (불필요)
- `isSidebarOpen` 상태 변수 제거
- 미사용 i18n 문자열 정리 (`selectTermDesc`, `openMenu`)

#### 용어 10개 추가 (71개 → 81개)

| 추가 용어 | 카테고리 |
|-----------|---------|
| 검색바 (Search Bar) | 입력·선택 컴포넌트 |
| 별점 (Star Rating) | 입력·선택 컴포넌트 |
| 빈 상태 (Empty State) | 피드백·상태 표시 |
| 알림 센터 (Notification Center) | 피드백·상태 표시 |
| 이미지 갤러리/라이트박스 (Image Gallery/Lightbox) | 레이아웃·표시 컴포넌트 |
| 공유 버튼 (Share Button) | 상호작용 패턴·상태 |
| 비밀번호 강도 표시기 (Password Strength Meter) | 폼 도움 요소 |
| 메가 메뉴 (Mega Menu) | 내비게이션 & 레이아웃 (심화) |
| 타임라인 (Timeline) | 데이터 표현 & 시각화 |
| 리치 텍스트 에디터 (Rich Text Editor) | 고급 입력 컴포넌트 |

### Phase 6 - 상세 뷰 좌측 아코디언 내비게이션 개편 (2026-02-27)

**주요 변경 사항:**

#### 상세 뷰 레이아웃: 좌측 아코디언 사이드바 + 콘텐츠 2-Panel
- **기존**: 좌/중/우 3-Panel 구조 (좌: 카테고리, 우: 용어 목록) → 시각적으로 복잡
- **변경**: 좌측 사이드바에 아코디언(드롭다운) 방식으로 카테고리 + 용어 통합
  - **좌측 사이드바** (`w-64`, sticky): 카테고리 아코디언 내비게이션
    - 그룹 헤더 자동 감지 ("UI 기본", "UI 심화", "UI 심화 확장")
    - 카테고리 클릭 시 해당 용어 목록 펼침 (chevron 회전 애니메이션)
    - 용어 목록: 왼쪽 보더 라인 + 들여쓰기로 시각적 계층 표현
    - 선택된 카테고리: `bg-starbucks-green text-white`
    - 선택된 용어: `bg-starbucks-green/10 text-starbucks-green font-semibold`
  - **중앙 콘텐츠** (`flex-1`, `max-w-4xl`): 선택된 용어의 상세 정보
    - 카테고리 라벨 표시 (상단 breadcrumb 스타일)
    - 콘텐츠 섹션 간격 `space-y-8`로 여유로운 가독성
- **우측 사이드바 제거**: 불필요한 시각적 복잡함 해소
- **모바일**(<md): 2개의 `<select>` 드롭다운 유지

#### 디자인 개선
- 카테고리명에서 접두사("UI 기본 - 1)") 제거하여 사이드바 가독성 향상
- 그룹 헤더 자동 라벨링 (uppercase, tracking-wider, 작은 폰트)
- 콘텐츠 헤더에 카테고리 라벨 + 용어명 분리 표시
- 섹션 간격 확대, 폰트 크기 미세 조정으로 가독성 강화

### Phase 7 - 콘텐츠 전문화 및 그룹 헤더 디자인 강화 (2026-02-27)

**주요 변경 사항:**

#### 1) "언제 사용하나요?" 라벨 통일
- **기존**: i18n 라벨 `"언제 써요?"` (구어체)
- **변경**: `"언제 사용하나요?"` (전문적 어조)로 통일
  - `index.html` i18n 설정, `DEVLOG.md` 문서 내 모든 참조 일괄 변경

#### 2) 81개 한국어 usage 필드 전문화
- 모든 용어의 `usage` 필드를 전문 UX 용어로 재작성
  - **WCAG 접근성 기준** 참조 (1.1.1, 2.1, 2.4.7, 3.3.2 등)
  - **구체적 수치 가이드라인**: 터치 타깃 44×44px, 색상 대비 4.5:1, 애니메이션 200~500ms 등
  - **패턴 비교**: 유사 컴포넌트 간 차이점 및 사용 맥락 명시
  - **접근성 구현**: ARIA 속성, 포커스 트랩, `prefers-reduced-motion` 등
  - **전문 UX 용어**: 스캐너빌리티(scannability), 디스커버러빌리티(discoverability), CLS, 어포던스(affordance) 등

#### 3) 그룹 헤더 디자인 강화
- **기존**: `text-[11px]` 회색 소문자 라벨 → 시각적으로 묻힘
- **변경**: 그라데이션 배경 + 좌측 포인트 보더로 돋보이는 디자인
  - `bg-gradient-to-r from-starbucks-green/10` 그라데이션 배경
  - `border-l-[3px] border-starbucks-green` 좌측 강조 라인
  - `text-[12px] font-bold text-starbucks-green` 브랜드 컬러 적용
  - 다크모드: `from-sky-400/10`, `border-sky-400`, `text-sky-400`
  - 그룹 간 간격 확대 (`mt-4`)로 시각적 분리 강화

### Phase 8 - 아코디언 토글 닫기 기능 추가 (2026-02-27)

**주요 변경 사항:**

#### 카테고리 아코디언 토글 개선
- **기존**: 열린 카테고리를 닫으려면 다른 카테고리를 클릭해야만 가능
- **변경**: 이미 열린 카테고리를 다시 클릭하면 접히도록 토글 동작 추가
  - 같은 카테고리 재클릭 시 `selectedCategoryIndex`, `selectedTermIndex`, `selectedTerm`을 `null`로 초기화
  - 다른 카테고리 클릭 시 기존 동작 유지 (해당 카테고리 열림 + 첫 번째 용어 자동 선택)
  - 사이드바 전체가 접힌 상태에서도 카테고리 목록 탐색 가능

### Phase 9 - 코드 예시 패널 추가 (2026-02-27)

**주요 변경 사항:**

#### 상세 뷰 우측 코드 패널 (3-Panel 레이아웃)
- **기존**: 좌측 아코디언 사이드바(w-64) + 중앙 콘텐츠(flex-1, max-w-4xl) → 우측 여백 과다
- **변경**: 우측에 코드 예시 패널(`w-[480px]`) 추가하여 3-Panel 구조 완성
  - **4개 탭**: HTML / CSS / JS / 결과(Result)
  - **HTML/CSS/JS 탭**: `<pre><code>` 블록으로 모노스페이스 코드 표시, 언어별 색상 구분
  - **결과 탭**: sandboxed `<iframe>` (srcdoc)으로 HTML+CSS+JS 결합 실시간 렌더링
  - sticky 배치 (`sticky top-14 h-[calc(100vh-3.5rem)]`)로 스크롤 시 고정
  - 용어 전환 시 코드 패널 콘텐츠도 함께 변경

#### 반응형 코드 패널
- **데스크톱 (lg+)**: 우측 고정 패널로 상시 표시
- **태블릿/모바일 (< lg)**: 콘텐츠 하단 접이식(collapsible) 버튼으로 토글
  - 토글 버튼에 코드 아이콘 + 상태 텍스트 표시

#### 81개 용어 코드 예시 데이터 추가
- 모든 용어에 `codeExample: { html, css, js }` 필드 추가 (한/영 공유)
- 각 코드 예시는 해당 UI 컴포넌트의 실제 구현 가능한 코드 제공
- 결과 탭에서 즉시 렌더링 확인 가능

#### 상태 변수 추가
- `activeCodeTab`: 현재 활성 코드 탭 (`'html'` | `'css'` | `'js'` | `'result'`)
- `mobileCodeOpen`: 모바일 코드 섹션 펼침 상태

#### i18n 문자열 추가
- `codeExample`, `codeResult`, `codeToggle`, `codeToggleHide`, `noCodeExample` (한/영)

### Phase 10 - 검색 기능 강화 및 UX 개선 (2026-02-27)

| 커밋 | 내용 |
|------|------|
| `f5e9daf` | 코드 예시 패널 너비 480px → 580px 확대 |
| `fffdad9` | 코드 예시 영역 세로 스크롤 제거 |
| `47a7bb1` | 코드 예시 결과 탭 가로 스크롤 제거 |
| `54b91f1` | 탭 바 코드 예시 결과 크기 확대 |
| `0f60dbe` | 상세 뷰에 검색 기능 추가 |
| `ff86ce9` | 모바일 상세 뷰에도 검색 기능 추가 |
| `b8f21e5` | 메가 메뉴 결과 탭 링크 클릭 시 페이지 이동 방지 |
| `dd247e1` | 검색창 한국어 IME 조합 깨짐 수정 |
| `100da30` | 상세 뷰 헤더 로고화 (홈 아이콘/텍스트 제거) |

**주요 변경 사항:**

#### 상세 뷰 검색 기능 추가
- **데스크톱 헤더**: 로고 우측에 검색 입력 필드 추가 (`detailSearch`)
- **모바일 상단**: 모바일 전용 검색 입력 필드 추가 (`mobileDetailSearch`)
- 그리드 뷰 / 상세 뷰 공통 `searchTerm` 상태 공유
- 검색 결과가 있으면 사이드바 용어 목록이 필터링됨

#### 한국어 IME 조합 깨짐 수정
- `compositionstart` / `compositionend` 이벤트로 한국어 입력 중 조합 상태 감지
- 조합 중일 때 `input` 이벤트 무시 → 완성된 글자만 반영
- 검색 후 `render()` 호출 시 커서 위치 복원 (`setSelectionRange`)

#### 코드 예시 패널 UX 개선
- 패널 너비 480px → 580px로 확대 (코드 가독성 향상)
- 세로/가로 스크롤 제거로 깔끔한 결과 표시
- 결과 탭 iframe 크기 확대

#### 헤더 로고화
- 홈 아이콘/텍스트 제거 → 로고 텍스트 "Vibe Coding Glossary"가 홈 버튼 역할
- 클릭 시 `goHome()` 호출로 메인 그리드 뷰 복귀

### Phase 11 - 메인 그리드 뷰 네비게이션 전면 개편 (2026-02-27)

| 커밋 | 내용 |
|------|------|
| `a9d9ed3` | 메인 그리드 뷰에 좌측 사이드바 네비게이션 추가 |
| `c16b3dc` | 그리드 뷰 상단 그룹 탭 메뉴 + 카테고리 섹션 레이아웃으로 변경 |
| `811c1b0` | 그리드 뷰 전면 개편 - 뷰포트 채우는 대형 카드 + 세그먼트 메뉴 |
| `b0c7df3` | 헤더에 그룹 메뉴 통합 + 풍선 드롭다운 + 적정 사이즈 카드 |

**주요 변경 사항:**

#### 3단 그룹 메뉴 + 풍선 드롭다운 (최종 형태)
- **데스크톱 헤더**: 로고 | [UI기본▾] [UI심화▾] [UI심화확장▾] | 검색/EN/🌙
- 그룹 탭 클릭 시 풍선(balloon) 스타일 드롭다운 표시
  - CSS 애니메이션 (`@keyframes balloon-in`): 위에서 아래로 페이드인
  - 삼각형 화살표(pseudo-element)로 풍선 도움말 느낌 구현
  - 그림자 + 둥근 모서리로 드롭다운 카드 스타일
- 드롭다운 아이템: 하위 카테고리명 + 용어 수 뱃지
- 외부 클릭 시 닫힘 (overlay `#dropdownOverlay` 방식)
- **모바일**: 그룹 탭 + 하위 카테고리 칩 2줄 구성

#### 카드 사이즈 자연 배열
- CSS Grid `auto-fill` + `minmax()` 조합으로 카드가 갯수에 따라 적정 크기로 배열
- 모바일: `minmax(155px, 200px)`, 데스크톱: `minmax(170px, 220px)`
- `justify-content: center`로 중앙 정렬
- 뷰포트를 억지로 채우지 않고 카드 갯수에 맞는 자연스러운 레이아웃

#### 상태 변수 추가
- `selectedGroup`: 현재 선택된 그룹 인덱스 (0: UI기본, 1: UI심화, 2: UI심화확장)
- `gridCategory`: 현재 선택된 하위 카테고리 인덱스 (`null` = 그룹의 첫 카테고리)
- `openDropdownGroup`: 열려 있는 드롭다운 그룹 인덱스 (`null` = 모두 닫힘)

### Phase 12 - 바이브 코딩 정보 페이지 추가 (2026-02-27)

| 커밋 | 내용 |
|------|------|
| `004a44c` | 바이브 코딩 정보 페이지 추가 (4-탭 콘텐츠 + 출처) |

**주요 변경 사항:**

#### "Vibe Coding?" 정보 페이지 신규 추가
- 헤더에 **보라색~핑크색 그라데이션 "Vibe Coding?" 버튼** 추가 (그리드 뷰, 상세 뷰 모두)
- 클릭 시 4-탭 정보 페이지로 전환

#### 4개 탭 콘텐츠 (한/영 이중 언어)

| 탭 | 내용 |
|----|------|
| **바이브 코딩이란?** | 정의, Andrej Karpathy 인용문, 핵심 특징 4가지, 문화적 인정 (Collins, Merriam-Webster, Gartner) |
| **작동 방식 이해** | 저수준 코드 루프(3단계) + 고수준 앱 라이프사이클(5단계), 실전 팁 |
| **기존 프로그래밍 비교** | 7개 항목 비교표 (코드 작성, 필요 역량, 개발 속도, 제어 수준, 접근성, 디버깅, 유지보수) + 장점/주의점 |
| **시작하기: 도구 선택** | 풀스택 플랫폼 (Lovable, Bolt, Replit), AI 에디터 (Cursor, Copilot, Claude Code), Google Cloud (AI Studio, Firebase Studio, Gemini Code Assist) + 선택 가이드 |

#### 출처
- Google Cloud — Vibe Coding Explained
- Wikipedia — Vibe coding
- IBM — What is Vibe Coding?

#### 상태 변수 추가
- `showVibeCodingInfo`: 바이브 코딩 정보 페이지 표시 여부
- `vibeCodingTab`: 현재 활성 탭 인덱스 (0~3)

#### 뷰 라우팅 업데이트
```javascript
function render() {
    if (showVibeCodingInfo) → renderVibeCodingView()
    else if (selectedTerm) → renderDetailView()
    else → renderGridView()
}
```

### Phase 13 - 통합 헤더 메뉴 구조 개편 (2026-02-27)

**주요 변경 사항:**

#### 공통 헤더 함수 (`renderHeader()`) 신규 생성
- **기존**: 3개 뷰(gridView, detailView, vibeCodingView)가 각각 별도의 헤더를 가지고 있어 메뉴 구조가 일관되지 않음
- **변경**: 모든 뷰에서 공유하는 단일 통합 헤더로 통합
- **데스크톱 메뉴 구조**: `로고 | Vibe Coding | Web Programming | UI 기본▾ | UI 심화▾ | UI 심화확장▾ | Q&A | 교육신청 | 🔍 | EN | 🌙`
  - **Vibe Coding**: 바이브 코딩 정보 페이지로 이동 (활성 시 보라~핑크 그라데이션 하이라이트)
  - **Web Programming / Q&A / 교육신청**: 메뉴 배치만 완료 (클릭 시 "준비 중입니다" 알림)
  - **UI 기본▾ / UI 심화▾ / UI 심화확장▾**: 기존 풍선 드롭다운 재사용, 하위 카테고리 클릭 시 그리드 뷰로 이동
  - **🔍 검색 토글**: `searchOpen` 상태로 인라인 검색 입력창 표시/숨김
  - **EN / 🌙**: 기존 동작 유지

#### 활성 상태 하이라이트
- Vibe Coding 뷰일 때: "Vibe Coding" 메뉴 강조
- Grid 뷰일 때: 현재 `selectedGroup`에 해당하는 그룹 탭 강조
- Detail 뷰일 때: `selectedCategoryIndex`로 그룹 역추적하여 해당 탭 강조

#### 모바일 햄버거 메뉴 (`renderMobileMenu()`) 신규 생성
- **md 이하** 화면에서 우측 슬라이드인 드로어 (`w-72`, `slide-in-right` 애니메이션)
- 메뉴 아이템: Vibe Coding / Web Programming / UI 기본 (아코디언) / UI 심화 (아코디언) / UI 심화확장 (아코디언) / Q&A / 교육신청
- HTML `<details>/<summary>` 태그로 아코디언 구현 (추가 상태 변수 불필요)
- 하단에 검색 입력창 배치
- 반투명 오버레이 (`bg-black/40`) 클릭 시 닫힘

#### `getGroups()` 헬퍼 함수 추출
- 기존 `renderGridView()` 내부의 그룹/카테고리 매핑 로직을 독립 함수로 추출
- `renderHeader()`, `renderMobileMenu()`, `renderGridView()`에서 공유 사용

#### 3개 뷰 함수 수정
- **renderGridView()**: 개별 헤더 제거 → `renderHeader()` + `renderMobileMenu()` 삽입, `desktopMenuHtml` 생성 로직 제거 (renderHeader로 이동)
- **renderDetailView()**: 개별 헤더 및 `vibeCodingBtn`, `mobileDetailSearch` 제거 → 통합 헤더 삽입
- **renderVibeCodingView()**: 개별 헤더 제거 → 통합 헤더 삽입 (탭바는 뷰별 콘텐츠로 유지)

#### `attachEvents()` 업데이트
- **제거**: `['gridSearch', 'detailSearch', 'mobileDetailSearch']` 검색 루프, `#vibeCodingBtn` 핸들러
- **추가**: `#searchToggle` (검색 토글), `#headerSearch` / `#mobileSearch` (IME 처리 유지), `#hamburgerBtn` / `#closeMobileMenu` / `#mobileMenuOverlay`, `#navVibeCoding` / `#mNavVibeCoding`, `#navWebProg` / `#navQA` / `#navEdu` 및 모바일 버전 (`alert(t('comingSoon'))`)
- **수정**: `.subcategory-chip` 핸들러에 크로스-뷰 네비게이션 추가 (showVibeCodingInfo/selectedTerm 리셋)
- `.header-group-tab` / `.group-tab-btn` 분리 (데스크톱: 드롭다운 토글만, 모바일: 그룹 전환)

#### 상태 변수 추가
- `searchOpen`: 검색 입력창 토글
- `mobileMenuOpen`: 모바일 햄버거 메뉴 토글

#### i18n 문자열 추가
- `comingSoon`: '준비 중입니다.' / 'Coming soon.'
- `applyEdu`: '교육신청' / 'Apply'

#### CSS 애니메이션 추가
- `@keyframes slide-in-right`: 모바일 메뉴 슬라이드인 애니메이션
- `.mobile-menu-panel`: `animation: slide-in-right 0.2s ease-out`

#### `goHome()` 수정
- `searchOpen = false`, `mobileMenuOpen = false` 리셋 추가

### Phase 14 - 헤더 레이아웃 품질 개선 (2026-02-27)

| 커밋 | 내용 |
|------|------|
| `28b5549` | 헤더 메뉴 레이아웃 개선 (중앙정렬, 스크롤바 숨김, 하위뷰 sticky) |

**주요 변경 사항:**

#### 헤더 콘텐츠 중앙정렬
- **기존**: 헤더 내부에 `max-width` 제약 없음 → 와이드 스크린(2560px+)에서 로고와 메뉴가 화면 양쪽 끝으로 분산
- **변경**: `max-w-7xl mx-auto` 래퍼 추가 → 콘텐츠 영역(max-w-6xl, max-w-4xl)과 시각적 정렬 일치

#### 데스크톱 nav 스크롤바 숨김
- **기존**: `overflow-x-auto scrollbar-thin` → 메뉴 항목이 많아 데스크톱에서도 가로 스크롤바 노출
- **변경**: `scrollbar-none` CSS 클래스 추가 (WebKit `-webkit-scrollbar: none` + Firefox `scrollbar-width: none`)
- 스크롤 기능은 유지하되 시각적 스크롤바만 숨김 (마우스 휠/터치 스크롤 가능)

#### 상세 뷰 하위 요소 sticky 고정
- **모바일 드롭다운**: `sticky top-14 z-10` 추가 → 스크롤 시 헤더 바로 아래 고정 (기존에는 스크롤 시 사라짐)
- **좌측 사이드바** (`w-64`): `z-10` 추가 → 헤더(z-20)와 안정적 레이어링
- **우측 코드 패널** (`w-[580px]`): `z-10` 추가 → 동일한 z-index 안정화

#### CSS 유틸리티 추가
```css
.scrollbar-none::-webkit-scrollbar { display: none; }
.scrollbar-none { -ms-overflow-style: none; scrollbar-width: none; }
```

### Phase 15 - 헤더 드롭다운 메뉴 클리핑 수정 (2026-02-27)

| 커밋 | 내용 |
|------|------|
| `af0c122` | 헤더 드롭다운 메뉴 z-index 클리핑 수정 |

**주요 변경 사항:**

#### 문제: 풍선 드롭다운이 보이지 않음
- **원인**: `<nav>` 요소에 `overflow-x-auto`가 설정되어 있으면 CSS 스펙상 내부의 `position: absolute` 자식은 부모의 overflow 영역 밖으로 나갈 수 없음
- 풍선 드롭다운(`balloon-dropdown`)이 `<nav>` 안에 `absolute top-full`로 배치되어 있었으나, `overflow-x-auto`가 이를 클리핑하여 화면에 표시되지 않았음
- 이는 `overflow` 속성이 `visible`이 아닌 모든 값(`auto`, `hidden`, `scroll`, `clip` 등)에서 발생하는 CSS 기본 동작

#### 해결: overflow-x/y 축 분리
- **기존**: `overflow-x-auto scrollbar-none` → 가로/세로 모두 overflow 컨테이너 생성 → 드롭다운 잘림
- **변경**: `overflow-x: clip; overflow-y: visible` (인라인 스타일)
  - **가로(X축)**: `clip`으로 넘치는 메뉴 항목은 잘라내되 스크롤바 없음
  - **세로(Y축)**: `visible`로 드롭다운이 `<nav>` 영역 아래로 정상 표시
- `overflow-x: clip`은 `overflow-x: hidden`과 유사하나 스크롤 컨테이너를 생성하지 않아 더 가벼움

#### 기술 배경
```
overflow-x-auto + overflow-y 미지정
  → 브라우저가 자동으로 overflow-y: auto 적용 (CSS 스펙)
  → absolute 자식이 가로·세로 모두 잘림

overflow-x: clip + overflow-y: visible
  → X축: 넘치는 항목 잘림 (스크롤바 없음)
  → Y축: 드롭다운 정상 표시 ✓
```

### Phase 16 - 하위 페이지 좌측 사이드바 네비게이션 (2026-02-27)

**주요 변경 사항:**

#### 레이아웃 구조 변경
- **기존**: 모든 뷰(그리드/상세/Vibe Coding)에서 동일한 수평 상단 헤더(`renderHeader()`) 사용
- **변경**: 그리드 뷰만 수평 헤더 유지, 하위 페이지(상세 뷰/Vibe Coding 뷰)는 **데스크톱에서 좌측 수직 사이드바**로 전환

#### 새로운 함수
1. **`renderSideNav(innerContentHtml)`** — 데스크톱 전용 좌측 사이드바 (`hidden md:flex`, `sticky top-0 h-screen`)
   - 상단: 로고 (클릭 시 홈)
   - 검색 입력창 (IME 한국어 조합 처리)
   - 메뉴: Vibe Coding / Web Programming
   - 내부 콘텐츠 영역 (뷰별 다른 콘텐츠 삽입)
     - **상세 뷰**: `buildSidebarHtml()` 아코디언 (카테고리 + 용어 목록)
     - **Vibe Coding 뷰**: 그룹 링크 (클릭 시 그리드 뷰 이동)
   - 하단 메뉴: Q&A / 교육신청
   - 최하단: 언어 전환(EN/KO) + 다크모드 토글(🌙/☀️)

2. **`renderMobileSubHeader()`** — 모바일 전용 슬림 헤더 (`md:hidden`, `sticky top-0 h-14`)
   - 로고 + EN + 🌙 + ☰ (햄버거 버튼)
   - 기존 `renderMobileMenu()` 드로어와 연동

#### 뷰별 변경
| 뷰 | 데스크톱 | 모바일 |
|------|----------|--------|
| **그리드 뷰** | 수평 헤더 (`renderHeader()`) — 변경 없음 | 수평 헤더 + 햄버거 — 변경 없음 |
| **상세 뷰** | ~~수평 헤더~~ → 좌측 사이드바 + 콘텐츠 + 코드 패널 | 슬림 헤더 + 햄버거 드로어 |
| **Vibe Coding 뷰** | ~~수평 헤더~~ → 좌측 사이드바 + 탭 콘텐츠 | 슬림 헤더 + 햄버거 드로어 |

#### 이벤트 핸들러 통합
- **클래스 기반 핸들러**: `.home-btn`, `.lang-btn`, `.theme-btn` 클래스로 통합 (복수 요소 동시 바인딩)
- **사이드바 전용 ID**: `#snavSearch`, `#snavVibeCoding`, `#snavWebProg`, `#snavQA`, `#snavEdu`
- **그룹 네비게이션**: `.group-nav-link` 클래스 (Vibe Coding 뷰 사이드바에서 그룹 클릭 → 그리드 뷰 이동)

#### sticky 오프셋 조정
- 사이드바: `sticky top-0 h-screen` (데스크톱에서 상단 헤더 없으므로 `top-0`)
- 코드 패널: `sticky top-0 h-screen` (기존 `top-14 h-[calc(100vh-3.5rem)]`에서 변경)
- Vibe Coding 탭바: `sticky top-14 md:top-0` (모바일: 슬림헤더 아래, 데스크톱: 최상단)

---

## 3. 파일 구조

```
D:\html\
├── index.html                 # 메인 HTML (UI 전체 구현)
├── glossaryData_decoded.js    # 81개 용어 데이터 (KO/EN)
├── CNAME                      # GitHub Pages 커스텀 도메인
├── DEVLOG.md                  # 개발일지 (본 문서)
└── .gitignore                 # Git 제외 설정
```

---

## 4. 기능 상세

### 4.1 네비게이션 구조

#### 그리드 뷰 (메인): 수평 헤더
- **공통 헤더** (`renderHeader()`): 메인 뷰에서 수평 통합 메뉴 표시
- **중앙정렬**: `max-w-7xl mx-auto` 래퍼로 와이드 스크린에서도 콘텐츠 정렬
- **데스크톱 메뉴**: `로고 | Vibe Coding | Web Programming | UI 기본▾ | UI 심화▾ | UI 심화확장▾ | Q&A | 교육신청 | 🔍 | EN | 🌙`
- **풍선 드롭다운**: 그룹 클릭 시 하위 카테고리 목록 표시 (balloon 애니메이션 + 삼각 화살표)
- **활성 상태 하이라이트**: 현재 그룹에 맞는 메뉴 항목 강조
- **모바일 햄버거 메뉴** (`renderMobileMenu()`): 우측 슬라이드인 드로어 (아코디언 하위 메뉴 + 검색)

#### 하위 페이지 (상세/Vibe Coding): 좌측 사이드바
- **좌측 사이드바** (`renderSideNav()`): 데스크톱에서 `w-64 sticky top-0 h-screen`
- **모바일 슬림 헤더** (`renderMobileSubHeader()`): 로고 + EN + 🌙 + ☰
- **클래스 기반 이벤트**: `.home-btn`, `.lang-btn`, `.theme-btn` — 여러 위치의 같은 기능 버튼 통합 바인딩

### 4.2 그리드 뷰 (메인 홈)

- **CSS Grid 카드 레이아웃**: `auto-fill` + `minmax()`로 갯수에 따른 자연 사이즈 배열
- 각 카드에 SVG 시각화 예시 + 용어 이름 표시
- 카드 클릭 시 상세 뷰로 전환
- 호버 시 카드 상승 애니메이션 (`hover:-translate-y-1`)
- **모바일**: 그룹 탭 + 하위 카테고리 칩 2줄 구성

### 4.3 상세 뷰 (사이드바 통합 네비게이션 + 콘텐츠)

**데스크톱 (md+):**
- **좌측 사이드바** (`renderSideNav()`, `w-64`, `sticky top-0 h-screen`): 통합 네비게이션
  - 로고 + 검색 + Vibe Coding / Web Programming 링크
  - 아코디언 카테고리 (그룹 헤더 → 카테고리 → 용어 목록)
  - Q&A / 교육신청 + EN/🌙 토글
- **중앙 콘텐츠** (`flex-1`): 선택된 용어의 4가지 정보 표시
  - 카테고리 라벨 + 용어명 헤더
  - 설명 / 언제 사용하나요? / 예시 / 시각화 예시 (SVG)
  - 모바일/태블릿: 하단 접이식 코드 예시 섹션
- **우측 코드 패널** (`w-[580px]`, `sticky top-0 h-screen`, lg+ 데스크톱): 4-Tab 코드 예시
  - HTML / CSS / JS 탭: 모노스페이스 코드 블록
  - 결과 탭: iframe으로 실시간 렌더링

**모바일 (<md):**
- 슬림 헤더 (`renderMobileSubHeader()`) + 햄버거 드로어
- 2개의 `<select>` 드롭다운 (카테고리 + 용어)
- 콘텐츠 영역 전체 너비 활용

### 4.4 바이브 코딩 정보 페이지

- 헤더/사이드바의 "Vibe Coding" 메뉴 클릭으로 진입
- **데스크톱**: 좌측 사이드바(그룹 링크 포함) + 탭 콘텐츠
- **모바일**: 슬림 헤더 + 탭바
- 4개 탭: 바이브 코딩이란? / 작동 방식 이해 / 기존 프로그래밍 비교 / 시작하기: 도구 선택
- 한국어/영어 이중 언어 전체 지원
- 출처(Sources) 섹션: Google Cloud, Wikipedia, IBM 링크
- 사이드바 그룹 링크(`.group-nav-link`) 클릭 시 해당 그룹의 그리드 뷰로 이동

### 4.5 다크모드

- 시스템 설정 자동 감지 (`prefers-color-scheme: dark`)
- 수동 토글 (해/달 아이콘)
- `<html>` 태그에 `dark` 클래스 토글 방식 (Tailwind `darkMode: 'class'`)

### 4.6 언어 전환 (KO/EN)

- 모든 UI 텍스트 + 용어 데이터 양국어 지원
- 상세 뷰에서 언어 전환 시 현재 선택된 용어 유지

### 4.7 검색

- 용어 이름 + 설명 기반 실시간 필터링 (case-insensitive)
- 그리드 뷰 / 상세 뷰 모두 지원
- 한국어 IME 조합 처리 (`compositionstart`/`compositionend`)

### 4.8 반응형 디자인

| 화면 크기 | 그리드 뷰 | 상세 뷰 | Vibe Coding 뷰 |
|-----------|----------|----------|----------------|
| ~640px (모바일) | 그룹 탭 + 칩 + 2열 카드 | 슬림 헤더 + 드롭다운 2개 + 콘텐츠 | 슬림 헤더 + 탭바 + 콘텐츠 |
| 640px~ (sm) | 그룹 탭 + 칩 + 3열 카드 | 슬림 헤더 + 드롭다운 2개 + 콘텐츠 | 슬림 헤더 + 탭바 + 콘텐츠 |
| 768px~ (md) | 헤더 풍선 드롭다운 + auto-fill 카드 | 좌측 사이드바(통합) + 콘텐츠 + 하단 코드 접이식 | 좌측 사이드바 + 탭바 + 콘텐츠 |
| 1024px~ (lg) | 헤더 풍선 드롭다운 + auto-fill 카드 | 좌측 사이드바(통합) + 콘텐츠 + 우측 코드 패널 | 좌측 사이드바 + 탭바 + 콘텐츠 |

---

## 5. 용어 카테고리 (13개, 총 81개 용어)

| # | 카테고리 | 용어 수 |
|---|---------|--------|
| 1 | UI 기본 - 1) 입력·선택 컴포넌트 | 10 |
| 2 | UI 기본 - 2) 내비게이션·구조 | 9 |
| 3 | UI 기본 - 3) 피드백·상태 표시 | 12 |
| 4 | UI 기본 - 4) 레이아웃·표시 컴포넌트 | 9 |
| 5 | UI 기본 - 5) 상호작용 패턴·상태 | 7 |
| 6 | UI 기본 - 6) 폼 도움 요소 | 7 |
| 7 | UI 심화 - 1) 내비게이션 & 레이아웃 | 4 |
| 8 | UI 심화 - 2) 상호작용 & 피드백 | 3 |
| 9 | UI 심화 - 3) 데이터 표현 & 시각화 | 3 |
| 10 | UI 심화 - 4) 고급 입력 컴포넌트 | 4 |
| 11 | UI 심화 확장 - 1) 모바일 최적화 UI | 4 |
| 12 | UI 심화 확장 - 2) 접근성 관련 UI | 4 |
| 13 | UI 심화 확장 - 3) 최신 UI 패턴 | 5 |

---

## 6. 기술 스택 및 설계 결정

### 사용 기술

| 기술 | 용도 | 선택 이유 |
|------|------|----------|
| **HTML5** | 페이지 구조 | 별도 빌드 없이 바로 배포 가능 |
| **Tailwind CSS (CDN)** | 스타일링 | 유틸리티 클래스 기반, 다크모드 지원 |
| **Vanilla JavaScript** | 인터랙션 | 프레임워크 의존성 없이 경량 구현 |
| **SVG** | 시각화 예시 (81개) | 벡터 기반으로 다크모드 대응, 애니메이션 내장 |
| **Google Sans Text** | 폰트 | 원본 사이트와 동일한 디자인 유지 |
| **Noto Sans KR** | 한글 폰트 | 한국어 가독성 확보 |

### 설계 결정

1. **단일 HTML 파일 + 데이터 분리**: `index.html`에 UI 로직, `glossaryData_decoded.js`에 데이터를 분리하여 유지보수성 확보
2. **프레임워크 미사용**: React 등 프레임워크 없이 Vanilla JS로 구현하여 빌드 과정 불필요, GitHub Pages에서 바로 배포 가능
3. **Tailwind CDN 사용**: 별도 빌드 파이프라인 없이 Tailwind의 유틸리티 클래스 활용
4. **SVG 인라인 렌더링**: 81개 시각화 예시를 SVG로 직접 렌더링하여 외부 이미지 의존성 제거

---

## 7. 배포

- **플랫폼**: GitHub Pages
- **도메인**: `html.dreamitbiz.com` (CNAME 설정)
- **배포 방식**: `main` 브랜치 루트 디렉토리에서 자동 배포
- **설정 경로**: GitHub > Settings > Pages > Source: Deploy from branch (main / root)

---

## 8. 알려진 이슈 및 제한 사항

| 항목 | 상태 | 설명 |
|------|------|------|
| Tailwind CDN | 주의 | 프로덕션 환경에서는 CDN 대신 빌드 방식 권장 (초기 로딩 시 스타일 깜빡임 가능) |
| Google Sans Text 폰트 | 제한적 | Google 전용 폰트로 라이선스 제한 가능, Noto Sans KR로 폴백 |
| SVG `currentColor` | 정상 | 다크모드 전환 시 SVG 색상이 CSS `color` 속성을 상속하여 자동 대응 |
| 대용량 데이터 파일 | 주의 | `glossaryData_decoded.js`가 약 141KB로, 초기 로딩에 영향 가능 (gzip 압축 시 약 30KB) |
| IE 미지원 | 의도적 | Tailwind CSS, CSS `backdrop-blur`, ES6+ 사용으로 IE 미지원 |

---

## 9. 변경 이력 (Changelog)

| 날짜 | 커밋 | 변경 내용 |
|------|------|----------|
| 2026-02-27 04:29 | `c5cb7fa` | 저장소 초기 생성 |
| 2026-02-27 04:30 | `1ed5b7e` | CNAME 설정 (`html.dreamitbiz.com`) |
| 2026-02-27 04:34 ~ 07:12 | `4c254d5` ~ `95c072a` | HTML 구조 수정 및 테스트 |
| 2026-02-27 15:03 | `8206ef5` | Vibe Coding Glossary 전체 사이트 구축 (71개 용어, 13개 카테고리) |
| 2026-02-27 15:06 | `71f6db3` | 다크블루 컬러 테마 적용, 메인 카드 1.5배 확대 |
| 2026-02-27 15:08 | `01d0fc8` | 개발일지(DEVLOG.md) 작성 |
| 2026-02-27 15:10 | `cbd39af` | 디자이너 크레딧 수정, 폰트 가독성 개선 |
| 2026-02-27 | - | 상세 뷰 UI 개편 (사이드바 → 카테고리 탭 + 드롭다운), 용어 10개 추가 (71→81개) |
| 2026-02-27 | - | 상세 뷰 좌측 아코디언 내비게이션 개편 (카테고리+용어 통합, 우측 사이드바 제거), 가독성/디자인 개선 |
| 2026-02-27 | `d57a6f0` | "언제 써요?" → "언제 사용하나요?" 라벨 변경, 81개 용어 usage 필드 전문화 |
| 2026-02-27 | - | 그룹 헤더(UI 기본/심화/심화 확장) 디자인 강화 (그라데이션 배경 + 좌측 포인트 보더) |
| 2026-02-27 | - | 아코디언 토글 닫기 기능 추가 (열린 카테고리 재클릭 시 접힘) |
| 2026-02-27 | - | 코드 예시 패널 추가 (우측 4-Tab: HTML/CSS/JS/결과), 81개 용어 codeExample 데이터 추가 |
| 2026-02-27 | `f5e9daf` ~ `100da30` | 코드 패널 UX 개선, 상세 뷰 검색 추가, 한국어 IME 수정, 헤더 로고화 |
| 2026-02-27 | `a9d9ed3` ~ `b0c7df3` | 메인 그리드 뷰 네비게이션 전면 개편 (3-그룹 풍선 드롭다운 + 자연 사이즈 카드) |
| 2026-02-27 | `004a44c` | 바이브 코딩 정보 페이지 추가 (4-탭 콘텐츠 + 출처, 한/영 이중 언어) |
| 2026-02-27 | - | 통합 헤더 메뉴 구조 개편 (공통 renderHeader + 모바일 햄버거 드로어 + 크로스-뷰 네비게이션) |
| 2026-02-27 | `28b5549` | 헤더 레이아웃 품질 개선 (중앙정렬 max-w-7xl, 스크롤바 숨김, 하위뷰 sticky z-10) |
| 2026-02-27 | `af0c122` | 헤더 드롭다운 클리핑 수정 (overflow-x:clip + overflow-y:visible 축 분리) |
| 2026-02-27 | - | 하위 페이지 좌측 사이드바 네비게이션 (renderSideNav + renderMobileSubHeader, 클래스 기반 이벤트 통합) |

---

## 10. 향후 개선 가능 사항

### 우선순위 높음
- [x] ~~카테고리별 필터 버튼 추가~~ → 상세 뷰 3-Panel 레이아웃으로 구현 완료 (좌측 카테고리 사이드바)
- [ ] 검색 시 매칭 텍스트 하이라이팅
- [ ] 데이터 파일 lazy loading 또는 코드 스플리팅

### 우선순위 중간
- [ ] 용어 북마크/즐겨찾기 기능 (LocalStorage 활용)
- [ ] 용어 간 관련 용어 연결 (Related Terms)
- [ ] 뒤로가기 브라우저 히스토리 지원 (`history.pushState`)
- [ ] URL 해시 기반 딥링크 (`#term=dropdown` 등)

### 우선순위 낮음
- [ ] PWA 지원 (Service Worker, 오프라인 모드)
- [ ] 용어 퀴즈 모드 (학습 도구)
- [ ] 인쇄용 스타일시트 (`@media print`)
- [ ] 접근성 강화 (ARIA 속성, 키보드 내비게이션 개선)
