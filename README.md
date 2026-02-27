# Vibe Coding Glossary

UI/UX 디자인 용어를 시각적으로 탐색할 수 있는 인터랙티브 웹 용어집입니다.

## Demo

https://html.dreamitbiz.com

## Features

- **71개 UI/UX 용어** - 13개 카테고리로 분류
- **SVG 시각화 예시** - 각 용어마다 인터랙티브 SVG 일러스트 제공
- **한국어/영어 전환** - 모든 콘텐츠 양국어 지원
- **다크모드** - 시스템 설정 자동 감지 + 수동 토글
- **실시간 검색** - 용어 이름/설명 기반 필터링
- **반응형 레이아웃** - 모바일 ~ 데스크탑 최적화

## Categories

| # | 카테고리 | 용어 수 |
|---|---------|--------|
| 1 | 입력/선택 컴포넌트 | 8 |
| 2 | 내비게이션/구조 | 9 |
| 3 | 피드백/상태 표시 | 10 |
| 4 | 레이아웃/표시 컴포넌트 | 8 |
| 5 | 상호작용 패턴/상태 | 6 |
| 6 | 폼 도움 요소 | 6 |
| 7 | 심화 - 내비게이션/레이아웃 | 3 |
| 8 | 심화 - 상호작용/피드백 | 3 |
| 9 | 심화 - 데이터 표현/시각화 | 2 |
| 10 | 심화 - 고급 입력 컴포넌트 | 3 |
| 11 | 모바일 최적화 UI | 4 |
| 12 | 접근성 관련 UI | 4 |
| 13 | 최신 UI 패턴 | 5 |

## Tech Stack

| 기술 | 용도 |
|------|------|
| HTML5 | 페이지 구조 |
| Tailwind CSS (CDN) | 스타일링, 다크모드 |
| Vanilla JavaScript | 상태 관리, 렌더링 |
| SVG | 용어별 시각화 예시 |

## Project Structure

```
├── index.html                 # 메인 페이지 (UI 전체)
├── glossaryData_decoded.js    # 71개 용어 데이터 (KO/EN)
├── CNAME                      # GitHub Pages 도메인
├── DEVLOG.md                  # 개발일지
└── README.md                  # 프로젝트 소개 (본 문서)
```

## Getting Started

별도 빌드 과정 없이 바로 실행 가능합니다.

```bash
# 저장소 클론
git clone https://github.com/aebonlee/html.git
cd html

# 브라우저에서 열기
open index.html
```

## Deployment

GitHub Pages를 통해 자동 배포됩니다.

- **Branch**: `main`
- **Source**: `/` (root)
- **Domain**: `html.dreamitbiz.com`

## License

This project is for educational purposes.

---

Designed by Ph.D Aebon Lee
