---
name: AfterNOON Design System
version: 0.3-draft
updated: 2026-06-24
owner: CLOP Inc. (clop.ai)
status: internal-draft
source_of_truth:
  brand_ci: "Dropbox/[00] CLOP/[11] Branding/20250326_CI BI 정리"
  ui_tokens: "Figma Dev Mode variables (애프터눈 제품 파일). v0.3 = 인앱·포털·어드민·커넥트·설문 페이지 변수 33종 실측 (2026-06-24)"
confidence_legend:
  confirmed_ci: "CI/BI 정본·로고 실측"
  confirmed_figma: "Figma 제품 변수 실측"
  to_confirm: "초안값/관례 제안 — Figma 미정의(추출 불가) 또는 추가 확인 필요"
colors:
  # 브랜드 식별(마케팅·로고) — 그라데이션
  brand_gradient: { from: "#1EF074", to: "#1ECAFA", angle: "135deg" }   # confirmed_ci
  accent_lime: "#D8FF00"   # confirmed_ci: 콤마/하이라이트
  # 제품 UI 주색 (confirmed_figma: Primary/*)
  primary:
    base:   "#00CE90"   # 기본 액션·강조·success
    strong: "#009669"   # hover/active/pressed
    light:  "#8CE9CD"   # 연한 강조·뱃지
    subtle: "#F3FFFB"   # 선택 배경·연한 면
  # 중립 (confirmed_figma: Gray/* + White + TEXT) — 밝음→어두움
  neutral:
    white: "#FFFFFF"
    "25":  "#FAFAFA"
    "50":  "#F5F5F5"
    "100": "#EEEEEE"
    "200": "#E0E0E0"   # border 기본
    "300": "#BDBDBD"   # disabled
    "400": "#9E9E9E"   # placeholder
    "500": "#757575"   # secondary text
    "700": "#616161"
    "800": "#424242"
    "900": "#222222"   # heading
    text:  "#000000"
  # 시맨틱 (confirmed_figma: Sub/* · Guide/*)
  semantic:
    success: "#00CE90"   # = primary.base
    error:   "#FF3E3E"   # Sub (alt 변형 #CC3232 설문에서 관찰)
    info:    "#0B50D0"   # Guide (링크·안내 블루)
    guide-navy: "#223A58" # Guide (짙은 안내 텍스트, 설문에서 관찰)
    warning: "#FFC72C"   # to_confirm (CLOP yellow 차용 제안 — Figma 미관찰)
    focus-ring: "#00CE90" # 제안 (primary 기반)
  # 보조 액센트 (confirmed_figma)
  accent:
    violet: "#881DFF"    # Sub/881DFF (= 브랜드 보라, 다이어그램 강조)
  kiosk:
    blue-gray: "#BFCEE5" # Kiosk 전용 면색
  # 브랜드/다이어그램 액센트 (마케팅·시각화 — 일부 to_confirm)
  brand_extended: { green: "#1AE592", cyan: "#1ECAFA", cyan-deep: "#0EA5C4", lime: "#D8FF00", pink: "#DC71FF", violet: "#881DFF" }
  # CLOP 마스터 (confirmed_ci) — 모회사·코퍼릿 전용
  clop_master: { violet: "#440099", yellow: "#FFC72C", ink: "#212121", violet-300: "#8848ED", violet-200: "#ADABFF", cool-gray-200: "#C6CBE0" }
typography:
  family: "Pretendard"        # confirmed_figma: 제품 전 영역
  display_en: "Montserrat"    # confirmed_ci: 브랜드·영문 제목
  serif: "Noto Serif"         # confirmed_ci
  logo_wordmark: "rounded geometric sans (로고 전용, 본문 금지)"
  weights: { regular: 400, medium: 500, semibold: 600 }   # SemiBold=‘bold’ 토큰
  # 인앱(환자) 스케일 — confirmed_figma  [size/weight/lineHeight/letterSpacing]
  inapp:
    title-28-bold: "600 / 28 / 36 / -2"
    title-16-bold: "600 / 16 / 24 / -1"
    title-14-bold: "600 / 14 / 20 / 0"
    title-12-bold: "600 / 12 / 16 / 0"
    body-16-medium: "500 / 16 / 24 / 0"
    body-16-regular:"400 / 16 / 24 / 0"
    body-14-medium: "500 / 14 / 20 / 0"
    body-14-regular:"400 / 14 / 20 / 0"
    body-12-regular:"400 / 12 / 16 / 1"
    caption-10-regular:"400 / 10 / auto / 0"
  # 포털·어드민(의원·관리자) 스케일 — confirmed_figma
  portal_admin:
    title-40-bold: "600 / 40 / 36 / 1"
    title-16-bold: "600 / 16 / 24 / 0"
    body-18-bold:  "600 / 18 / 26 / 0"
    body-18-regular:"400 / 18 / 26 / 0"
    body-16-bold:  "600 / 16 / 24 / 0"
    body-16-regular:"400 / 16 / 24 / 0"
    body-14-bold:  "600 / 14 / 20 / 0"
    body-14-regular:"400 / 14 / 20 / 0"
    caption-12-bold:"600 / 12 / 14 / 0"
figma_variable_collections:
  color: ["Primary/", "Gray/", "White/", "TEXT/", "Sub/", "Guide/", "Kiosk/"]
  type:  ["인앱/", "포털,어드민/"]
spacing_base: 4   # to_confirm — Figma에 spacing 변수 없음(토큰화 안 됨). 관례로 4px 스케일 권장.
radius:           # to_confirm — Figma에 radius 변수 없음. 관례 제안값.
  surface: 12
  control: 10
  pill: 9999
---

# AfterNOON Design System (`afternoon-design.md`)

> 🔒 **CLOP 내부 전용 v0.3.** 애프터눈 서비스·리서치의 **브랜드·디자인 단일 원천(SSOT)**. Vercel `vercel.com/design.md`(Geist) 패턴.
>
> **에이전트 사용법**: 인포그래픽·다이어그램·PPT·카드뉴스·웹/화면 제작 시 이 토큰을 그대로 인용한다. 값 추측 금지. 상단 YAML이 토큰 원본.
>
> **신뢰 라벨**: ✅CI = CI/BI 정본 · ✅FIG = Figma 제품 변수 실측 · ⚠ = 초안값/관례 제안.

---

## 0. 브랜드 한눈에
- **이름**: AfterNOON(영문, 대문자 NOON) / 애프터눈(국문). 모회사 **CLOP**(클롭).
- **심볼**: 무한대(∞) = 양쪽 눈/안경 + 우안 반짝임(✦) + 콤마 악센트.
- **색의 두 층**: **브랜드 식별=그라데이션** `#1EF074→#1ECAFA` / **제품 UI 주색=솔리드 그린** `#00CE90`.
- **표면 2체계**: `인앱`(환자) / `포털,어드민`(의원·관리자). 그 외 커넥트·키오스크·트라이얼·알림톡·DCT·리서치 화면군.
- **서브브랜드**: 애프터눈 · 애프터눈 리서치 · 애프터뷰 (→ §9).

---

## 1. 컬러

### 1.1 브랜드 코어 — 그라데이션 ✅CI
- `linear-gradient(135deg, #1EF074 0%, #1ECAFA 100%)` — 로고·히어로·표지·마케팅·데이터 시각화 주강조.

### 1.2 제품 UI 주색 (Primary) ✅FIG
| 토큰 | HEX | 용도 |
|---|---|---|
| primary | `#00CE90` | 기본 버튼·링크·선택·success |
| primary-strong | `#009669` | hover / active / pressed |
| primary-light | `#8CE9CD` | 연한 강조·뱃지·배경 |
| primary-subtle | `#F3FFFB` | 선택 배경·연한 면 |

### 1.3 악센트 ✅CI
- **Lime `#D8FF00`** — 콤마·포인트(좁은 면적).

### 1.4 중립(그레이) ✅FIG
| HEX | 역할 |
|---|---|
| `#FFFFFF` | 배경/표면 |
| `#FAFAFA` · `#F5F5F5` | 연한 면 |
| `#EEEEEE` | 구분 면 |
| `#E0E0E0` | border 기본 |
| `#BDBDBD` | disabled |
| `#9E9E9E` | placeholder |
| `#757575` | 보조 텍스트 |
| `#616161` · `#424242` | 강한 텍스트 |
| `#222222` | 헤딩 |
| `#000000` | 본문 텍스트 |

### 1.5 시맨틱 ✅FIG / ⚠
| 토큰 | HEX | 신뢰 |
|---|---|---|
| success | `#00CE90` | ✅FIG (= primary) |
| error | `#FF3E3E` | ✅FIG (Sub · 변형 `#CC3232` 관찰) |
| info | `#0B50D0` | ✅FIG (Guide, 링크·안내 블루) |
| guide-navy | `#223A58` | ✅FIG (짙은 안내 텍스트) |
| warning | `#FFC72C` | ⚠ (Figma 미관찰 — CLOP yellow 차용 제안) |
| focus-ring | `#00CE90` | 제안 (primary 기반) |

### 1.6 보조 액센트·기타 ✅FIG
- **Violet `#881DFF`** (Sub) — 보조 강조. 브랜드 보라·다이어그램 강조와 동일 계열.
- **Kiosk `#BFCEE5`** — 키오스크 전용 면색.
- 다이어그램/마케팅 액센트(일부 ⚠): green `#1AE592`·cyan `#1ECAFA`·cyan-deep `#0EA5C4`·lime `#D8FF00`·pink `#DC71FF`·violet `#881DFF`.

### 1.7 CLOP 마스터 ✅CI (모회사·코퍼릿)
Violet `#440099` · Yellow `#FFC72C` · Ink `#212121` · 틴트 `#8848ED`/`#ADABFF`/`#C6CBE0`. 제품 그린과 동등 비중 혼용 금지.

---

## 2. 타이포그래피 ✅FIG (Pretendard)
**제품 전 영역 = Pretendard.** weight: Regular 400 / Medium 500 / SemiBold 600(=‘bold’ 토큰). 영문 제목 Montserrat ✅CI, 세리프 Noto Serif ✅CI. 로고 워드마크는 로고 전용.

### 2.1 인앱(환자) 스케일 — `weight / size / lineHeight / letterSpacing`
| 토큰 | 값 |
|---|---|
| Title 28 bold | 600 / 28 / 36 / −2 |
| Title 16 bold | 600 / 16 / 24 / −1 |
| Title 14 bold | 600 / 14 / 20 / 0 |
| Title 12 bold | 600 / 12 / 16 / 0 |
| Body 16 medium / regular | 500·400 / 16 / 24 / 0 |
| Body 14 medium / regular | 500·400 / 14 / 20 / 0 |
| Body 12 regular | 400 / 12 / 16 / 1 |
| Caption 10 regular | 400 / 10 / auto / 0 |

### 2.2 포털·어드민(의원·관리자) 스케일
| 토큰 | 값 |
|---|---|
| Title 40 bold | 600 / 40 / 36 / 1 |
| Title 16 bold | 600 / 16 / 24 / 0 |
| Body 18 bold / regular | 600·400 / 18 / 26 / 0 |
| Body 16 bold / regular | 600·400 / 16 / 24 / 0 |
| Body 14 bold / regular | 600·400 / 14 / 20 / 0 |
| Caption 12 bold | 600 / 12 / 14 / 0 |

---

## 3. 레이아웃 · 간격 ⚠ (Figma 미토큰화)
- **발견**: 이 Figma 파일은 색·타이포만 변수화돼 있고 **간격·radius·elevation은 변수가 없다**(프레임마다 raw 값). → 토큰이 아니라 **관례로 통일**해야 함.
- 권장 베이스: **4px 스케일** — 4 · 8 · 12 · 16 · 24 · 32 · 40 · 64 · 96.

## 4. 모양(radius) ⚠ (관례 제안)
- surface(카드/모달) `12px` · control(버튼/인풋) `10px` · pill `9999px`. 둥근 심볼에 맞춰 둥근 모서리 지향. (정확값 필요 시 컴포넌트에서 get_design_context로 CSS 추출.)

## 5. 고도(elevation) ⚠
- 카드·팝오버·모달 그림자 3단계 관례화 필요(변수 없음).

## 6. 모션 ⚠
- 짧은 트랜지션(150–250ms, ease-out). **`prefers-reduced-motion` 존중**.

---

## 7. 접근성 ✅ (의료·고령 사용자 — 강제 규칙)
- 본문 대비 **4.5:1 이상**(WCAG AA). 보조 텍스트 `#757575`=흰 배경 4.6:1(충족), `#9E9E9E`는 3:1 미만이므로 **본문 금지·placeholder 한정**.
- 모든 인터랙티브 요소 **`:focus-visible` 링**(`#00CE90`). 터치 타깃 **44×44pt** 이상.
- 색 단독 정보전달 금지(아이콘·라벨 병기). 동작 최소화 존중, 깜빡임 금지.

## 8. 보이스 & 카피 ✅CI
- 신뢰·전문·과장 금지. 근거수준(검증/추정/향후) 구분. 환자 대면은 쉽고 짧게.
- 표기: **AfterNOON**(NOON 대문자) / **애프터눈**. "지역 안과"(=지역 1차의료기관 안과).
- 적용처: 알림톡·에러·빈 상태·본인인증/간편가입 안내 등 마이크로카피.

## 9. 서브브랜드 아키텍처 ✅CI
| 브랜드 | 색 주도 | 심볼 |
|---|---|---|
| 애프터눈 | 그라데이션(식별) + 그린 #00CE90(UI) | ∞ 눈 + ✦ + 콤마 |
| 애프터눈 리서치 | 녹색 주도 | 동일 + "Research/리서치" |
| 애프터뷰 | (BI 별도) | 동일 계열 |
| CLOP(모회사) | 보라 #440099 + 옐로 #FFC72C | 보라 원형 마크 |

로고 변형: 가로/세로/심볼 × 컬러/화이트/모노. 최소 여백·크기 준수, 그라데이션 변형·기울임·그림자 금지.

## 10. 로고·심볼 자산 (raw URL) ✅
베이스 `https://raw.githubusercontent.com/clopai/afternoon-whitepaper-assets/main/` — `brand/brand-logo-h-color.png`·`-h-white.png`·`brand-logo-v-white.png`·`brand-appicon-gradient.png`·`brand/svg/brand-symbol-eye-color.svg`·`brand/svg/brand-wordmark-black.svg`. 전체: `url_map.md`/`manifest.json`.

## 11. Figma 변수 컬렉션 매핑 ✅FIG
| 컬렉션 | 역할 |
|---|---|
| `Primary/` | 제품 주색(그린 계열) |
| `Gray/` · `White/` · `TEXT/` | 중립·면·텍스트 |
| `Sub/` | error(#FF3E3E)·accent violet(#881DFF) |
| `Guide/` | info 블루(#0B50D0)·navy(#223A58) |
| `Kiosk/` | 키오스크 전용 |
| `인앱/` · `포털,어드민/` | 표면별 타입 |

> 동기화: Figma 변수명 ↔ 본 토큰. "2026.06 최신화" 페이지들은 아직 변수 미바인딩(0건) → 변수는 기존 메인 페이지에서 추출.

## 12. ⚠ 남은 항목
1. **간격·radius·elevation 정식화** — Figma 변수 없음 → 컴포넌트 get_design_context(CSS)로 실측하거나 관례 확정.
2. **컴포넌트 토큰** — 버튼/인풋/뱃지/카드 사이즈·상태(hover·active·disabled·focus).
3. **warning 정식 토큰** · **다크 모드**(`afternoon-design.dark.md` 분리).

---

## 변경 이력
| 버전 | 일자 | 내용 |
|---|---|---|
| v0.1 | 2026-06-24 | CI/BI 정본(색·폰트·서브브랜드)+로고 실측. UI 토큰 초안값. |
| v0.2 | 2026-06-24 | Figma 설문 프레임 변수 실측(primary·gray·danger·guide·타입 4종). 그라데이션/솔리드 구분 명문화. |
| v0.3 | 2026-06-24 | **Figma 5개 페이지 변수 33종 실측 병합**. Primary 4단계·Gray 10단계·Sub(error #FF3E3E·violet #881DFF)·Guide(info #0B50D0·navy #223A58)·Kiosk·**인앱/포털어드민 타입 스케일 전체**. 발견: 간격·radius·elevation은 Figma 미토큰화 → 관례화 필요. |
