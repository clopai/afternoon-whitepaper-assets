---
name: AfterNOON Design System
version: 0.2-draft
updated: 2026-06-24
owner: CLOP Inc. (clop.ai)
status: internal-draft
source_of_truth:
  brand_ci: "Dropbox/[00] CLOP/[11] Branding/20250326_CI BI 정리"
  ui_tokens: "Figma Dev Mode variables (애프터눈 제품). v0.2 = '필로스타 리서치 설문' 프레임 사용 변수 실측 (2026-06-24)"
confidence_legend:
  confirmed_ci: "CI/BI 정본·로고 실측"
  confirmed_figma: "Figma 제품 변수 실측"
  to_confirm: "초안값 — Figma 추가 추출 필요(미정의/미캡처 변수)"
colors:
  # 브랜드 식별(마케팅·로고) — 그라데이션
  brand_gradient:
    from: "#1EF074"   # green  (confirmed_ci: 로고 샘플링)
    to:   "#1ECAFA"   # cyan   (confirmed_ci: 로고 샘플링)
    angle: "135deg"
  accent_lime: "#D8FF00"   # confirmed_ci: 콤마/하이라이트
  # 제품 UI 주색 — 솔리드 (confirmed_figma: Primary/*)
  product_primary:
    primary:        "#00CE90"   # 기본 액션·강조
    primary-strong: "#009669"   # hover/active/pressed
    primary-subtle: "#F3FFFB"   # 선택 배경·연한 면
  # 중립 (confirmed_figma: Gray/* — Material gray ramp + White/TEXT)
  neutral:
    white: "#FFFFFF"
    "50":  "#F5F5F5"
    "100": "#EEEEEE"
    "200": "#E0E0E0"   # border 기본
    "300": "#BDBDBD"   # disabled
    "400": "#9E9E9E"   # placeholder
    "600": "#757575"   # secondary text
    "800": "#424242"
    "900": "#222222"   # heading
    text:  "#000000"   # 본문 텍스트(TEXT/000000)
  # 시맨틱
  semantic:
    success:   "#00CE90"   # confirmed_figma (= primary)
    danger:    "#CC3232"   # confirmed_figma (Sub/CC3232)
    guide-info:"#223A58"   # confirmed_figma (Guide/223A58)
    warning:   "#FFC72C"   # to_confirm (CLOP yellow 차용 제안)
    focus-ring:"#00CE90"   # 제안 (primary 기반)
  # 브랜드/다이어그램 액센트 (제품 UI 변수 아님 — 마케팅·시각화용)
  brand_extended:          # to_confirm (그라데이션·로고 외 사용 시)
    green:     "#1AE592"
    cyan:      "#1ECAFA"
    cyan-deep: "#0EA5C4"
    lime:      "#D8FF00"
    pink:      "#DC71FF"
    violet:    "#8B1DFF"
  # CLOP 마스터 (confirmed_ci: CLOP_CI_Guidelines_1.0) — 모회사·코퍼릿
  clop_master:
    violet:  "#440099"
    yellow:  "#FFC72C"
    ink:     "#212121"
    violet-300: "#8848ED"
    violet-200: "#ADABFF"
    cool-gray-200: "#C6CBE0"
typography:
  family: "Pretendard"        # confirmed_figma: 제품 전 영역 UI 본문/제목
  display_en: "Montserrat"    # confirmed_ci: 브랜드·영문 제목
  serif: "Noto Serif"         # confirmed_ci: 세리프 강조
  logo_wordmark: "rounded geometric sans (로고 전용, 본문 금지)"
  surfaces: ["인앱 (환자)", "포털,어드민 (의원·관리자)"]   # 변수 컬렉션 2체계
  tokens:                     # confirmed_figma (일부 — 전체 스케일은 to_confirm)
    inapp-title-28:        "Pretendard SemiBold 28 / lh36 / ls-2 / w600"
    portal-title-40:       "Pretendard SemiBold 40 / lh36 / ls1  / w600"
    portal-body-14-bold:   "Pretendard SemiBold 14 / lh20 / ls0  / w600"
    portal-body-14-regular:"Pretendard Regular  14 / lh20 / ls0  / w400"
figma_variable_collections:   # 동기화 매핑용 (confirmed_figma)
  color: ["Primary/", "Gray/", "White/", "TEXT/", "Sub/", "Guide/"]
  type:  ["인앱/", "포털,어드민/"]
spacing_base: 4               # to_confirm (변수 미정의 — 코드/프레임 실측 필요)
radius:                       # to_confirm
  surface: 12
  control: 10
  pill: 9999
---

# AfterNOON Design System (`afternoon-design.md`)

> 🔒 **CLOP 내부 전용 v0.2.** 애프터눈 서비스·리서치의 **브랜드·디자인 단일 원천(SSOT)** 을 사람과 AI 에이전트가 함께 읽도록 한 파일에 담았다. Vercel `vercel.com/design.md`(Geist) 패턴.
>
> **에이전트 사용법**: 인포그래픽·다이어그램·PPT·카드뉴스·웹/화면을 만들 때 이 파일의 토큰을 그대로 인용한다. 값 추측 금지. 상단 YAML이 토큰 원본, 아래 본문이 규칙.
>
> **신뢰 라벨**: ✅CI = CI/BI 정본 · ✅FIG = Figma 제품 변수 실측 · ⚠ = 초안값(Figma 추가 추출 필요).

---

## 0. 브랜드 한눈에

- **이름**: AfterNOON(영문, 대문자 NOON) / 애프터눈(국문). 모회사 **CLOP**(클롭).
- **심볼**: 무한대(∞) = 양쪽 눈(또는 안경 두 알) + 우안 반짝임(✦) + 콤마 악센트.
- **색의 두 층**:
  - **브랜드 식별(로고·마케팅) = 그라데이션** `#1EF074→#1ECAFA`.
  - **제품 UI 주색 = 솔리드 그린** `#00CE90`. (그라데이션을 버튼 등 UI 액션에 그대로 쓰지 않는다.)
- **톤**: 신뢰·전문(의료) + 친근·환함(환자 친화). 미니멀·고대비.
- **서브브랜드**: 애프터눈 · 애프터눈 리서치 · 애프터뷰 (→ §9).

---

## 1. 컬러

### 1.1 브랜드 코어 — 그라데이션 ✅CI
- **AfterNOON Gradient**: `#1EF074`(녹색) → `#1ECAFA`(시안), **135°** 선형.
- CSS: `linear-gradient(135deg, #1EF074 0%, #1ECAFA 100%)`
- 용도: **로고·히어로·표지·마케팅 비주얼·데이터 시각화 주강조**. 브랜드를 “느끼게” 하는 자리.

### 1.2 제품 UI 주색 — 솔리드 ✅FIG
실제 제품 화면은 그라데이션이 아니라 **솔리드 그린**으로 동작한다.

| 토큰 | HEX | 용도 |
|---|---|---|
| primary | `#00CE90` | 기본 버튼·링크·선택·강조 |
| primary-strong | `#009669` | hover / active / pressed |
| primary-subtle | `#F3FFFB` | 선택 배경·연한 강조 면 |

### 1.3 악센트 ✅CI
- **Lime `#D8FF00`** — 콤마·포인트·하이라이트(좁은 면적, 다크 배경에서 강함).

### 1.4 중립(그레이) ✅FIG
Material 계열 그레이 램프 + 텍스트.

| 토큰 | HEX | 용도 |
|---|---|---|
| white | `#FFFFFF` | 배경/표면 |
| gray-50 | `#F5F5F5` | 연한 면 |
| gray-100 | `#EEEEEE` | 구분 면 |
| gray-200 | `#E0E0E0` | border 기본 |
| gray-300 | `#BDBDBD` | disabled |
| gray-400 | `#9E9E9E` | placeholder |
| gray-600 | `#757575` | 보조 텍스트 |
| gray-800 | `#424242` | 강한 텍스트 |
| gray-900 | `#222222` | 헤딩 |
| text | `#000000` | 본문 텍스트 |

### 1.5 시맨틱 ✅FIG / ⚠
| 토큰 | HEX | 신뢰 |
|---|---|---|
| success | `#00CE90` | ✅FIG (= primary) |
| danger | `#CC3232` | ✅FIG (Sub) |
| guide-info | `#223A58` | ✅FIG (Guide, 안내·도움말 네이비) |
| warning | `#FFC72C` | ⚠ (CLOP yellow 차용 제안) |
| focus-ring | `#00CE90` | 제안 (primary 기반) |

### 1.6 브랜드/다이어그램 액센트 ⚠
로고·마케팅·시각화용(제품 UI 변수 아님): green `#1AE592` · cyan `#1ECAFA` · cyan-deep `#0EA5C4` · lime `#D8FF00` · pink `#DC71FF` · violet `#8B1DFF`. 다이어그램 강조 3색: 녹 `#00CE90`·보라 `#8B1DFF`·청록 `#0EA5C4`.

### 1.7 CLOP 마스터 ✅CI (모회사·코퍼릿)
Violet `#440099` · Yellow `#FFC72C` · Ink `#212121` · 틴트 `#8848ED`/`#ADABFF`/`#C6CBE0` (PANTONE 지정). 제품 자료에서 CLOP 보라/옐로를 애프터눈 그린과 동등 비중으로 섞지 말 것.

---

## 2. 타이포그래피

- **제품 UI 기본 = Pretendard** ✅FIG (인앱·포털·어드민 전 영역).
- **영문/브랜드 제목 = Montserrat** ✅CI, **세리프 강조 = Noto Serif** ✅CI.
- **로고 워드마크**(라운드 산세리프)는 로고 전용 — 본문/UI 금지 ✅CI.
- **표면 2체계**(변수 컬렉션): `인앱`(환자) / `포털,어드민`(의원·관리자).

### 확정된 타입 토큰 ✅FIG (일부)
| 토큰 | 정의 |
|---|---|
| 인앱/Title/28 | Pretendard SemiBold 28 / lh 36 / ls −2 / w600 |
| 포털,어드민/Title/40 | Pretendard SemiBold 40 / lh 36 / ls 1 / w600 |
| 포털,어드민/Body/14-bold | Pretendard SemiBold 14 / lh 20 / w600 |
| 포털,어드민/Body/14-regular | Pretendard Regular 14 / lh 20 / w400 |

> 전체 스케일(본문 16/소제목/캡션 등 나머지 단계)은 ⚠ — 해당 토큰을 쓰는 프레임 선택 시 추가 추출.

---

## 3. 레이아웃 · 간격 ⚠
- 현재 Figma에 **간격이 변수로 정의돼 있지 않음**(필로스타 설문 프레임 기준). 코드/프레임 실측 필요.
- 제안 베이스: **4px 스케일** — 4 · 8 · 12 · 16 · 24 · 32 · 40 · 64 · 96.

## 4. 모양(radius) ⚠
- surface(카드/모달) `12px` · control(버튼/인풋) `10px` · pill `9999px` (제안값, Figma 확정 대기). 심볼이 둥글어 전반적으로 둥근 모서리 지향.

## 5. 고도(elevation) ⚠
- 카드·팝오버·모달 그림자 3단계. Figma 값으로 확정.

## 6. 모션 ⚠
- 짧고 절제된 트랜지션(150–250ms, ease-out). **`prefers-reduced-motion` 존중**(고령·전정 민감 고려).

---

## 7. 접근성 ✅ (의료·고령 사용자 우선 — 강제 규칙)
- 본문 텍스트 대비 **4.5:1 이상**, 큰 텍스트 3:1 이상(WCAG AA). (`#757575` 보조 텍스트는 흰 배경 대비 4.6:1 — 본문 최소선 충족.)
- 모든 인터랙티브 요소에 **`:focus-visible` 포커스 링**(`#00CE90`).
- **터치 타깃 최소 44×44pt**.
- 색만으로 정보 전달 금지(아이콘·라벨 병기). 그라데이션 위 텍스트는 대비 확보.
- 동작 최소화 옵션 존중. 자동재생·깜빡임 금지.

---

## 8. 보이스 & 카피 ✅CI
- **신뢰·전문, 과장 금지.** 학술적·정확. 근거수준(검증/추정/향후) 구분.
- 환자 대면은 **쉽고 짧게**(겁주지 않기). 의료진 대면은 정확·간결.
- 표기: 영문 **AfterNOON**(NOON 대문자), 국문 **애프터눈**. "지역 안과"(=지역 1차의료기관 안과) 표준.
- 적용처: 알림톡, 에러 메시지, 빈 상태, 본인인증/간편가입 안내 등 마이크로카피.

---

## 9. 서브브랜드 아키텍처 ✅CI
모두 **CLOP 마스터** 아래, **공통 심볼(∞ 눈)** 공유.

| 브랜드 | 국/영문 | 색 주도 | 심볼 |
|---|---|---|---|
| 애프터눈 | 애프터눈 / afterNOON | 그라데이션(식별) + 그린 #00CE90(UI) | ∞ 눈 + ✦ + 콤마 |
| 애프터눈 리서치 | 애프터눈 리서치 / afterNOON Research | 녹색 주도 | 동일 심볼 + "Research/리서치" |
| 애프터뷰 | 애프터뷰 / Afterview | (BI 별도) | 동일 계열 |
| CLOP(모회사) | 클롭 / CLOP | 보라 `#440099` + 옐로 `#FFC72C` | 보라 원형 마크 |

- 로고 변형: 가로형/세로형/심볼, 컬러/화이트/모노(블랙). 최소 여백·최소 크기 준수, 그라데이션 임의 변경·기울임·그림자 금지.

---

## 10. 로고·심볼 자산 (호스팅 raw URL) ✅
베이스: `https://raw.githubusercontent.com/clopai/afternoon-whitepaper-assets/main/`
- 가로 로고(컬러/화이트): `…/brand/brand-logo-h-color.png` · `…-h-white.png`
- 세로 로고(화이트): `…/brand/brand-logo-v-white.png`
- 앱 아이콘(그라디언트): `…/brand/brand-appicon-gradient.png`
- 심볼 눈마크(벡터): `…/brand/svg/brand-symbol-eye-color.svg`
- 워드마크(벡터): `…/brand/svg/brand-wordmark-black.svg` · `…-white.svg`
- 전체 목록: 같은 레포 `url_map.md` / `manifest.json`.

---

## 11. Figma 변수 컬렉션 매핑 (동기화용) ✅FIG
| 컬렉션 | 역할 |
|---|---|
| `Primary/` | 제품 주색(그린) |
| `Gray/` | 중립 램프 |
| `White/` · `TEXT/` | 면·텍스트 |
| `Sub/` | danger 등 보조 |
| `Guide/` | 안내·도움말 |
| `인앱/` | 환자 앱 타입 |
| `포털,어드민/` | 의원·관리자 타입 |

> 동기화: Figma 변수명 ↔ 본 토큰. 변경 시 이 매핑으로 대조.

## 12. ⚠ 아직 확정 못 한 것 (다음 Figma 추출)
필로스타 설문 1개 프레임만 실측해서 아래가 비어 있음. **해당 토큰을 쓰는 프레임(어드민 대시보드·컴포넌트 라이브러리·디자인시스템 페이지)을 선택**하면 추가 추출 가능.
1. **타입 스케일 전체** — 본문 16/캡션/소제목 등 나머지 단계.
2. **간격·radius·elevation** — 변수화돼 있으면 추출, 아니면 코드 실측.
3. **컴포넌트 토큰** — 버튼/인풋/뱃지/카드 사이즈·상태(hover·active·disabled·focus).
4. **시맨틱 보강** — warning/info 정식 토큰, 라이트/다크.
5. **다크 모드** → `afternoon-design.dark.md` 분리(Geist 패턴).

---

## 변경 이력
| 버전 | 일자 | 내용 |
|---|---|---|
| v0.1-draft | 2026-06-24 | 최초 초안. CI/BI 정본(색·폰트·서브브랜드)+로고 실측(그라데이션). UI 토큰은 초안값. |
| v0.2-draft | 2026-06-24 | **Figma 제품 변수 실측 반영**(필로스타 설문 프레임). 제품 UI 주색 #00CE90·strong #009669·subtle #F3FFFB, Material gray 램프, danger #CC3232, guide #223A58, Pretendard 타입 토큰 4종 + 표면 2체계, 변수 컬렉션 매핑 추가. 그라데이션=브랜드식별 / 솔리드그린=제품UI 구분 명문화. 간격·radius·전체 타입스케일·컴포넌트·다크는 추가 추출 대기. |
