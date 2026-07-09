# html_bykiro_web — 웹 호스팅용 프로토타입

> GitHub Pages 등으로 배포하여 모바일/PC에서 화면 리뷰하는 용도.

---

## 새 화면 추가 시 체크리스트

### 1. 반응형 CSS 삽입

마지막 `</style>` 바로 앞에 아래 미디어쿼리를 추가한다.

```css
/* 모바일: 뷰포트 꽉 채움 (앱 느낌) */
@media (max-width: 430px) {
  .app-container {
    width: 100% !important;
    height: 100dvh !important;
    border-radius: 0 !important;
    box-shadow: none !important;
  }
  body {
    background: #fcf9f7 !important;
  }
}
```

**효과:**
- 모바일(≤430px): `.app-container`가 뷰포트 꽉 채움 → 앱처럼 보임
- PC(>430px): 기존 390×844 프레임 + 회색 배경 유지

---

### 2. 화면 이동 드롭다운 삽입

`.app-container`의 닫는 `</div>` 바로 앞에 아래 스니펫을 삽입한다.

```html
<!-- 🚨 [임시] 화면 이동 마스터 메뉴 시작 -->
<div style="position:absolute;bottom:12px;left:12px;z-index:9999;">
<select onchange="if(this.value)window.location.href=this.value" style="font-size:11px;padding:5px 7px;border-radius:8px;border:1px solid #d3c3bc;background:#f0edeb;color:#4f443f;font-family:'Quicksand',sans-serif;font-weight:600;box-shadow:0 4px 12px rgba(117,88,73,0.15);max-width:150px;cursor:pointer;opacity:0.85;">
<option value="">📱 화면 이동</option>
<option value="index.html">01-A 스플래시</option>
<option value="01-B-force-update.html">01-B 강제 업데이트</option>
<option value="01-C-server-maintenance.html">01-C 서버 점검</option>
<option value="02-A-auth-login.html">02-A 로그인</option>
<option value="03-A-auth-terms-agree.html">03-A 약관 동의</option>
<option value="04-A-auth-terms-reagree.html">04-A 약관 재동의</option>
<option value="05-A-server-notice-blocking.html">05-A 공지 (블로킹)</option>
<option value="05-B-server-notice-popup.html">05-B 공지 (팝업)</option>
<option value="06-A-onboarding-entry.html">06-A 온보딩 진입</option>
<option value="06-B-onboarding-invite-input.html">06-B 초대코드 입력</option>
<option value="06-C-onboarding-invite-confirm.html">06-C 초대 확인</option>
<option value="07-A-onboarding-baby-profile.html">07-A 아이 프로필</option>
<option value="09-A-home-record-timeline.html">09-A 기록 타임라인</option>
<option value="10-A-record-input-fab-select.html">10-A FAB 선택</option>
<option value="10-B-record-input-breast.html">10-B 모유 입력</option>
<option value="10-C-record-input-formula.html">10-C 분유 입력</option>
<option value="11-A-record-input-sleep.html">11-A 수면 입력</option>
<option value="11-B-record-input-diaper.html">11-B 기저귀 입력</option>
<option value="12-A-record-detail.html">12-A 기록 상세</option>
<option value="13-A-record-search.html">13-A 기록 검색</option>
<option value="14-A-todo-list.html">14-A 할일 목록</option>
<option value="15-A-todo-notice-detail.html">15-A 할일 상세</option>
<option value="16-A-metrics-charts.html">16-A 지표 차트</option>
<option value="17-A-settings-home.html">17-A 설정 홈</option>
</select>
</div>
<!-- 🚨 [임시] 화면 이동 마스터 메뉴 끝 -->
```

**새 화면 추가 시:** `<option>` 행을 추가하고, 기존 파일들의 드롭다운에도 같은 행을 추가한다.

---

### 3. 핵심 규칙

| 항목 | 값 |
|------|-----|
| 드롭다운 위치 | `position: absolute` (`.app-container` 기준, 좌하단) |
| `.app-container` | 반드시 `position: relative` 포함 |
| 출시 시 제거 | `🚨 [임시]` 주석 사이 블록 일괄 삭제 + 미디어쿼리 제거 |
| index.html | 01-A 스플래시 복사본 (진입점) |

---

### 4. 파일 목록 (현재 25개)

| 파일명 | 화면 |
|--------|------|
| index.html | 01-A 스플래시 (진입점) |
| 01-A-splash-loading.html | 스플래시 로딩 |
| 01-B-force-update.html | 강제 업데이트 |
| 01-C-server-maintenance.html | 서버 점검 |
| 02-A-auth-login.html | 소셜 로그인 |
| 03-A-auth-terms-agree.html | 약관 동의 |
| 04-A-auth-terms-reagree.html | 약관 재동의 |
| 05-A-server-notice-blocking.html | 서버 공지 (블로킹) |
| 05-B-server-notice-popup.html | 서버 공지 (팝업) |
| 06-A-onboarding-entry.html | 온보딩 진입 |
| 06-B-onboarding-invite-input.html | 초대코드 입력 |
| 06-C-onboarding-invite-confirm.html | 초대 확인 |
| 07-A-onboarding-baby-profile.html | 아이 프로필 등록 |
| 09-A-home-record-timeline.html | 홈 기록 타임라인 |
| 10-A-record-input-fab-select.html | FAB 카테고리 선택 |
| 10-B-record-input-breast.html | 모유 입력 |
| 10-C-record-input-formula.html | 분유 입력 |
| 11-A-record-input-sleep.html | 수면 입력 |
| 11-B-record-input-diaper.html | 기저귀 입력 |
| 12-A-record-detail.html | 기록 상세 |
| 13-A-record-search.html | 기록 검색 |
| 14-A-todo-list.html | 할일 목록 |
| 15-A-todo-notice-detail.html | 할일/공지 상세 |
| 16-A-metrics-charts.html | 지표 차트 |
| 17-A-settings-home.html | 설정 홈 |
