# 화면 상세 설계서 (Screen Specs)

> 템플릿: [_TEMPLATE.md](./_TEMPLATE.md) · 기반: [user_scenario.md](../user_scenario.md) · [screen_scenario.md](../screen_scenario.md)
> 디자인: 안 1 (Warm Taupe) / 안 2 (Dusty Blue) 중 택1 — design rc.4 기준
> API 정책: 데이터 needs는 구체적으로, 엔드포인트는 TBD (backend spec에서 역산)
> 번호 기준: **개발 구현 우선순위** (01 = 앱 진입점 → 27 = Phase 2 플레이스홀더)

---

## 진행 상태

### 인증·온보딩 (01~07)
| # | 화면 | 파일 | 시나리오 | 상태 |
|---|------|------|----------|------|
| 01 | 스플래시/앱상태 (강제업데이트·점검) | `01-auth-splash-appstate.md` | 13 | ✅ 완료 |
| 02 | 로그인 (소셜) | `02-auth-login.md` | 1, 2 | ✅ 완료 |
| 03 | 약관 동의 (최초) | `03-auth-terms-agree.md` | 13 | ✅ 완료 |
| 04 | 약관 재동의 (변경 차단) | `04-auth-terms-reagree.md` | 13 | ✅ 완료 |
| 05 | 서버 공지 (차단/팝업) | `05-server-notice.md` | 13 | ✅ 완료 |
| 06 | 온보딩 (홈 만들기/초대 수락) | `06-onboarding-entry.md` | 1, 2 | ✅ 완료 |
| 07 | 아이 프로필 등록 | `07-onboarding-baby-profile.md` | 1 | ✅ 완료 |

### 홈 탭 (08~15)
| # | 화면 | 파일 | 시나리오 | 상태 |
|---|------|------|----------|------|
| 08 | 홈 > 상태 (대시보드/TODO/공지) | `../home-status-spec.md` | 7, 11 | ✅ 완료 |
| 09 | 홈 > 기록 — 타임라인 | `09-home-record-timeline.md` | 3 | ✅ 완료 |
| 10 | 기록 입력 — 수유 | `10-home-record-input-feeding.md` | 3 | ✅ 완료 |
| 11 | 기록 입력 — 수면/기저귀/성장/병원/예방접종 | `11-home-record-input-others.md` | 3 | ✅ 완료 |
| 12 | 기록 상세 | `12-home-record-detail.md` | 3, 17 | ✅ 완료 |
| 13 | 기록 검색/필터 | `13-home-record-search.md` | 17 | ✅ 완료 |
| 14 | TODO 리스트 (진행/완료) | `14-home-todo-list.md` | 18 | ✅ 완료 |
| 15 | TODO 상세/작성, 공지 상세/작성 | `15-home-todo-notice-detail.md` | 11, 18 | ✅ 완료 |

### 지표 탭 (16)
| # | 화면 | 파일 | 시나리오 | 상태 |
|---|------|------|----------|------|
| 16 | 지표 탭 (성장·수유·수면 차트) | `16-metrics-charts.md` | 9 | ✅ 완료 |

### 설정 (17~24)
| # | 화면 | 파일 | 시나리오 | 상태 |
|---|------|------|----------|------|
| 17 | 설정 홈 | `17-settings-home.md` | — | ✅ 완료 |
| 18 | 아이 관리 | `18-settings-baby.md` | 12 | ✅ 완료 |
| 19 | 구성원·초대 관리 | `19-settings-members-invite.md` | 16 | ✅ 완료 |
| 20 | 홈 관리 | `20-settings-home-manage.md` | — | ✅ 완료 |
| 21 | 기기 관리 (등록 플로우) | `21-settings-device.md` | 6 | ✅ 완료 |
| 22 | 분유·젖병 캘리브레이션 | `22-settings-formula-bottle.md` | 4 | ✅ 완료 |
| 23 | 알림 설정 | `23-settings-notification.md` | 6장 | ✅ 완료 |
| 24 | 계정·회원 탈퇴 | `24-settings-account-withdraw.md` | 15 | ✅ 완료 |

### 공통 (25)
| # | 화면 | 파일 | 시나리오 | 상태 |
|---|------|------|----------|------|
| 25 | 공통 상태 패턴 (에러/빈/로딩/세션만료) | `25-common-states.md` | 14 | ✅ 완료 |

### Phase 2 플레이스홀더 (26~27)
| # | 화면 | 파일 | 시나리오 | 상태 |
|---|------|------|----------|------|
| 26 | 홈 > AI분석 (준비 중) | `26-home-ai-placeholder.md` | 8 | ✅ 완료 |
| 27 | 앨범 탭 (준비 중) | `27-album-placeholder.md` | 10 | ✅ 완료 |

---

## 작성 규칙
- 모든 화면은 `_TEMPLATE.md` 10개 섹션 준수
- 섹션 9는 9-1(초기) / 9-2(더미) 분리
- API 섹션: 데이터 needs 구체화 + 엔드포인트 TBD
- 권한(ADMIN/USER) 차이 반드시 명시
