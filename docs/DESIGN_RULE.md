# HTML 프로토타입 구현 규칙

> DESIGN.md(디자인 시스템)를 HTML로 구현할 때 적용하는 보충 규칙.
> DESIGN.md에 정의된 토큰/컬러/타이포는 그대로 따르며, 이 문서는 구현 환경과 오늘 확정된 스타일 결정만 다룬다.

---

## 1. HTML 프레임 규격

| 항목 | 값 |
|------|-----|
| 컨테이너 클래스 | `.app-container` |
| 크기 | width: 390px, height: 844px |
| 정렬 | margin: 0 auto |
| 스크롤 | overflow-y: auto, overflow-x: hidden |
| 외곽 | box-shadow: 0 0 0 1px rgba(0,0,0,0.05) |
| body 배경 | bg-gray-100 (프리뷰 대비용) |
| 컨테이너 배경 | surface (#fcf9f7) |

---

## 2. 아이콘 규칙

| 항목 | 규칙 |
|------|------|
| 라이브러리 | Google Material Symbols Outlined |
| font-variation-settings | `'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24` |
| FILL 값 | **항상 0** (라인형). 유일한 예외: 바텀 네비게이션 활성 탭 아이콘만 FILL 1 허용 |
| 기본 크기 | 24px |
| 소형 | 18~20px (칩 내부, 보조 인디케이터) |
| 대형 | 28~32px (카드 내 메인 아이콘) |

---

## 3. 입력 필드

```css
background: #f0edeb;
border: none;
border-radius: 16px;
height: 52px; /* 단일행 */
padding: 16px; /* 다중행(textarea) */
```

| 상태 | 스타일 |
|------|--------|
| 기본 | border 없음, bg만으로 영역 구분 |
| focus | box-shadow: 0 0 0 2px #755849 |
| placeholder | color: #82746e (outline) |
| textarea 필수 | `border-none focus:ring-0` (Tailwind forms 플러그인 기본 border 제거) |

---

## 4. soft-card (카드 통일 스타일)

```css
.soft-card {
  background-color: #f0edeb;
  border: 1px solid #d3c3bc;
  box-shadow: 0 8px 30px rgba(117, 88, 73, 0.08);
  border-radius: 16px; /* 기본 */
  /* 대형 카드(대시보드 등): 32px */
}
```

- active(탭 피드백): transform scale(0.98)
- 순백(#ffffff) 카드 배경 사용 금지 — 항상 soft-card 스타일 사용

---

## 5. CTA 버튼

| 유형 | 스타일 |
|------|--------|
| 주 CTA | rounded-full, h 56px, `background: linear-gradient(135deg, #755849 0%, #5b4133 100%)`, text white, shadow `0 8px 30px rgba(117,88,73,0.15)` |
| 보조 CTA | rounded-full, h 48px, bg transparent, border 1px #755849, text #5b4133 |
| 텍스트 버튼 | no bg/border, text primary (#5b4133), font-weight 700 |
| 비활성 | opacity 40%, cursor-not-allowed |

---

## 6. 칩 (ChoiceChip / FilterChip)

| 상태 | 스타일 |
|------|--------|
| 미선택 | h 44px, rounded-full, bg #f6f3f1, border 1px #d3c3bc, text #4f443f |
| 선택 | bg #ffd8c4, border 1px #755849, text #5b4133 |

---

## 7. 바텀 네비게이션 (메인 화면만)

- 5탭: 홈 / 지표 / 기록 / 앨범 / 설정
- 높이: 80px
- 배경: surface-container-lowest (#ffffff)
- 모양: rounded-t-xl, shadow-lg
- 활성 탭: pill bg secondary-container (#ffd8c4), 아이콘 FILL 1 (유일한 예외)
- 비활성: text on-surface-variant, FILL 0

---

## 8. FAB (Floating Action Button)

- 크기: 56px 원형
- 배경: fab-gradient (`linear-gradient(135deg, #755849 0%, #5b4133 100%)`)
- 아이콘: `add`, 32px, white
- 그림자: `0 8px 30px rgba(117,88,73,0.15)`
- 위치: right margin-page, bottom 100px (BottomNav 위)

---

## 9. 바텀시트

| 항목 | 값 |
|------|-----|
| 상단 radius | 32px |
| 핸들바 | 36px × 4px, rounded-full, bg #d3c3bc |
| 시트 배경 | #ffffff |
| dim overlay | bg-black/30 ~ bg-black/40 |

---

## 10. 블로킹 게이트 화면

`docs/design/prototype/1/design.md`의 "Blocking Gate Screens 통일 규칙" 섹션을 따름.
단, 아이콘은 이 문서의 규칙(FILL 0)으로 통일.

---

## 11. 금지 사항

| 금지 | 대안 |
|------|------|
| 순백(#ffffff) 카드 배경 | soft-card 스타일 사용 |
| Material Symbols FILL 1 | FILL 0 (바텀네비 활성 예외) |
| 순검정 그림자 (rgba(0,0,0,x)) | 항상 primary 틴트 rgba(117,88,73,x) |
| 90도 각진 모서리 | 최소 radius 8px |
| 입력 필드 visible border | border:none, focus시 box-shadow만 |
| emoji를 카테고리 아이콘으로 사용 | Material Symbols 사용 |

---

## 12. Top App Bar (메인 화면 공통)

> 홈·지표·앨범·설정 탭의 최상단 헤더. 인증/온보딩 화면은 별도 패턴(arrow_back 등).

| 항목 | 값 |
|------|-----|
| 높이 | 56px |
| 배경 | surface (#fcf9f7) |
| 좌측 | 프로필 아바타(36px 원, bg secondary-container) + 아이 이름 (Plus Jakarta Sans 18/700, primary) |
| 우측 | notifications + calendar_month + more_vert (24px, on-surface) |
| 패딩 | px margin-page (24px) |
| FILL 예외 | 좌측 person 아이콘만 FILL 1 허용 (프로필 용도) |

```html
<header class="flex items-center justify-between px-[24px] h-[56px] flex-shrink-0 bg-surface">
  <div class="flex items-center gap-[10px]">
    <div class="w-[36px] h-[36px] rounded-full bg-secondary-container flex items-center justify-center">
      <span class="material-symbols-outlined" style="font-size: 20px; font-variation-settings: 'FILL' 1;">person</span>
    </div>
    <h1 class="font-headline text-[18px] font-bold text-primary">아이이름</h1>
  </div>
  <div class="flex items-center gap-[8px]">
    <button class="w-[40px] h-[40px] flex items-center justify-center"><span class="material-symbols-outlined text-on-surface" style="font-size: 24px;">notifications</span></button>
    <button class="w-[40px] h-[40px] flex items-center justify-center"><span class="material-symbols-outlined text-on-surface" style="font-size: 24px;">calendar_month</span></button>
    <button class="w-[40px] h-[40px] flex items-center justify-center"><span class="material-symbols-outlined text-on-surface" style="font-size: 24px;">more_vert</span></button>
  </div>
</header>
```

---

## 13. 서브탭 (홈 탭 내부: 상태/기록/AI분석)

> 홈 탭 내부에서 콘텐츠를 전환하는 서브 네비게이션.

| 항목 | 값 |
|------|-----|
| 배치 | Top App Bar 바로 아래, `sticky top-[56px]` (스크롤 시 앱바 하단 고정) |
| 높이 | 자동 (py-3 = 48px 영역) |
| 배경 | surface (#fcf9f7) |
| 하단선 | `border-b border-outline-variant/30` (전체 구분) |
| 균등 분배 | `flex-1` (탭 너비 균등) |
| 활성 탭 | `text-primary font-bold border-b-2 border-primary` |
| 비활성 탭 | `text-on-surface-variant font-medium` (border 없음) |
| 폰트 | Quicksand 14px (font-body text-[14px]) |

```html
<nav class="flex border-b border-outline-variant/30 sticky top-[56px] bg-surface z-40 flex-shrink-0">
  <button class="flex-1 py-3 font-body text-[14px] font-bold text-primary border-b-2 border-primary">상태</button>
  <button class="flex-1 py-3 font-body text-[14px] font-medium text-on-surface-variant">기록</button>
  <button class="flex-1 py-3 font-body text-[14px] font-medium text-on-surface-variant">AI분석</button>
</nav>
```

### pill 탭과의 차이 (사용처 구분)

| 스타일 | 사용처 | 예시 |
|--------|--------|------|
| **border-b (본 규칙)** | 메인 탭 내부 서브 네비게이션 | 홈 > 상태/기록/AI분석 |
| **pill (bg #ffd8c4)** | 콘텐츠 내부 필터/차트 탭 | 지표 > 성장/모유/분유/수면 |

---

## 14. Tailwind 환경 설정

- CDN: `https://cdn.tailwindcss.com?plugins=forms,container-queries`
- 폰트: Google Fonts — Plus Jakarta Sans (400~800), Quicksand (400~700)
- Material Symbols: `https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap`
- tailwind.config: `docs/design/prototype/2/DESIGN.md`의 토큰을 extend에 매핑
