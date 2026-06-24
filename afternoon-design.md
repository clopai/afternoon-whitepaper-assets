---
name: AfterNOON Design System
version: 0.1-draft
updated: 2026-06-24
owner: CLOP Inc. (clop.ai)
status: internal-draft
source_of_truth:
  brand_ci: "Dropbox/[00] CLOP/[11] Branding/20250326_CI BI 정리"
  ui_tokens: "Figma (애프터눈 환자웹·관리자) — variable_defs (★ 미확정 항목의 정본)"
confidence_legend:
  confirmed: "CI/BI 정본·로고 실측으로 확인"
  to_confirm: "초안값(합리적 기본) — Figma 변수로 확정 필요"
colors:
  brand_gradient:
    from: "#1EF074"   # green  (confirmed: 로고 샘플링)
    to:   "#1ECAFA"   # cyan   (confirmed: 로고 샘플링)
    angle: "135deg"
  accent_lime: "#D8FF00"   # confirmed: 콤마/하이라이트
  afternoon_palette:       # to_confirm in Figma
    green-deep:  "#00CE90"
    green:       "#1AE592"
    green-bright:"#1EF074"
    cyan:        "#1ECAFA"
    cyan-deep:   "#0EA5C4"
    lime:        "#D8FF00"
    pink:        "#DC71FF"
    violet:      "#8B1DFF"
  clop_master:             # confirmed: CLOP_CI_Guidelines_1.0
    violet:  "#440099"
    yellow:  "#FFC72C"
    ink:     "#212121"
    violet-300: "#8848ED"
    violet-200: "#ADABFF"
    cool-gray-200: "#C6CBE0"
  neutral:                 # to_confirm in Figma
    "0":   "#FFFFFF"
    "50":  "#F6F8FA"
    "100": "#EEF1F4"
    "200": "#E2E6EB"
    "300": "#C6CBE0"
    "500": "#8A93A3"
    "700": "#4B5563"
    "900": "#212121"
  semantic:                # to_confirm in Figma
    success: "#00CE90"
    info:    "#1ECAFA"
    warning: "#FFC72C"
    danger:  "#E5484D"
    focus-ring: "#1ECAFA"
typography:                # families confirmed (CI); scale to_confirm
  kr: "Pretendard"
  en: "Montserrat"
  serif: "Noto Serif"
  logo_wordmark: "rounded geometric sans (display only — 로고 전용, 본문 금지)"
spacing_base: 4            # to_confirm
radius:                    # to_confirm
  surface: 12
  control: 10
  pill: 9999
---

# AfterNOON Design System (`afternoon-design.md`)

> 🔒 **CLOP 내부 전용 초안 v0.1.** 애프터눈 서비스·리서치의 **브랜드·디자인 단일 원천(SSOT)** 을 사람과 AI 에이전트가 함께 읽도록 한 파일에 담았다. Vercel `vercel.com/design.md`(Geist) 패턴을 차용했다.
>
> **에이전트 사용법**: 인포그래픽·다이어그램·PPT·카드뉴스·웹/화면을 생성할 때 이 파일의 토큰(색·타이포·간격·radius)을 그대로 인용한다. 값을 추측하지 말 것. 상단 YAML이 토큰 원본, 아래 본문이 규칙이다.
>
> **신뢰 라벨**: ✅ = CI/BI 정본·실측 확정 · ⚠ = 초안값(Figma 변수로 확정 필요).

---

## 0. 브랜드 한눈에

- **이름**: AfterNOON(영문, 대문자 NOON) / 애프터눈(국문). 모회사 **CLOP**(클롭).
- **심볼**: 무한대(∞) = 양쪽 눈(또는 안경 두 알). 우안 안에 **반짝임(✦)**, 우하단에 **콤마 악센트**. "검사가 끝난 오후, 눈이 환해진다"는 의미.
- **톤**: 신뢰·전문(의료) + 친근·환함(환자 친화). 미니멀·고대비.
- **서브브랜드**: 애프터눈 · 애프터눈 리서치 · 애프터뷰 (→ §9).

---

## 1. 컬러 ✅(코어)/⚠(확장·시맨틱)

### 1.1 브랜드 코어 — 그라데이션 ✅
애프터눈의 1차 식별자는 **단색이 아니라 그라데이션**이다.

- **AfterNOON Gradient**: `#1EF074`(녹색) → `#1ECAFA`(시안), **135°** 선형.
- CSS: `linear-gradient(135deg, #1EF074 0%, #1ECAFA 100%)`
- 용도: 심볼, 핵심 강조 면/버튼, 히어로 배경, 데이터 시각화의 주강조.
- 단색 대체가 필요하면 그라데이션 중앙값 계열 녹–청록을 쓰되, 가능하면 그라데이션 유지.

### 1.2 악센트 ✅
- **Lime `#D8FF00`** — 콤마·포인트·하이라이트. 어두운 배경에서 특히 강하게 작동. 면적은 좁게(포인트로만).

### 1.3 애프터눈 확장 팔레트 ⚠ (Figma 확정 필요)
| 토큰 | HEX | 용도(제안) |
|---|---|---|
| green-deep | `#00CE90` | 성공·안정, 다이어그램 녹색 강조 |
| green | `#1AE592` | 보조 녹색 |
| green-bright | `#1EF074` | 그라데이션 시작점 |
| cyan | `#1ECAFA` | 그라데이션 끝점, info |
| cyan-deep | `#0EA5C4` | 다이어그램 청록 강조(가독 보강) |
| lime | `#D8FF00` | 악센트 |
| pink | `#DC71FF` | 보조 강조(카테고리 구분) |
| violet | `#8B1DFF` | 보조 강조, 다이어그램 보라 |

> 다이어그램에서 실제 사용 중인 강조 3색: 녹색 `#00CE90` · 보라 `#8B1DFF` · 청록 `#0EA5C4`.

### 1.4 CLOP 마스터 ✅ (모회사 — 코퍼릿 자료용)
| 토큰 | HEX | 비고 |
|---|---|---|
| CLOP Violet | `#440099` | 마스터 프라이머리 (PANTONE 지정) |
| CLOP Yellow | `#FFC72C` | 마스터 세컨더리 (PANTONE 지정) |
| Ink | `#212121` | 본문 잉크/거의 검정 |
| Violet-300 | `#8848ED` | 틴트 |
| Violet-200 | `#ADABFF` | 틴트 |
| Cool Gray-200 | `#C6CBE0` | 중립 틴트 |

> 애프터눈(제품) 자료는 그라데이션이 주역, CLOP 보라/옐로는 **모회사·코퍼릿 맥락**에서 사용. 둘을 한 화면에서 동등 비중으로 섞지 말 것.

### 1.5 중립(그레이) ⚠ & 시맨틱 ⚠
- 중립 스케일·시맨틱(success/info/warning/danger/focus)은 상단 YAML의 초안값을 사용하되 **Figma 변수로 확정**한다.
- 본문 텍스트 대비는 **WCAG AA(4.5:1) 이상** 필수(→ §7).

---

## 2. 타이포그래피 ✅(서체)/⚠(스케일)

| 역할 | 서체 | 비고 |
|---|---|---|
| 국문 본문/UI | **Pretendard** | 제품·문서 기본 ✅ |
| 영문/숫자 | **Montserrat** | 제목·영문 표기 ✅ |
| 세리프 강조 | **Noto Serif** | 인용·격조 강조 한정 ✅ |
| 로고 워드마크 | 라운드 지오메트릭 산세리프 | **로고 전용** — 본문/UI에 쓰지 말 것 ✅ |

- **타입 스케일(크기/굵기/행간)**: ⚠ Figma 확정. 임시 기준 — 본문 16px/line-height 1.6, 소제목 20–24, 제목 32+; 굵기 400/500/700.
- 국문은 Pretendard 단독으로 영문·숫자까지 처리 가능(혼용 시 베이스라인 점검).

---

## 3. 레이아웃 · 간격 ⚠
- **4px 베이스 스케일**(제안): 4 · 8 · 12 · 16 · 24 · 32 · 40 · 64 · 96.
- 카드/섹션 패딩, 그리드, 반응형 브레이크포인트는 Figma의 실제 환자웹·관리자 값으로 확정.

## 4. 모양(radius) ⚠
- surface(카드/모달) `12px` · control(버튼/인풋) `10px` · pill `9999px` (제안값).
- 심볼이 둥근 형태이므로 전반적으로 **둥근 모서리** 지향.

## 5. 고도(elevation) ⚠
- 카드·팝오버·모달용 그림자 3단계. Figma 값으로 확정.

## 6. 모션 ⚠
- 짧고 절제된 트랜지션(150–250ms, ease-out). **`prefers-reduced-motion` 존중**(고령 사용자·전정 민감 고려).

---

## 7. 접근성 ✅ (의료·고령 사용자 우선 — 강제 규칙)
애프터눈 환자층에 **고령 당뇨·안과 환자**가 많다. 아래는 권고가 아니라 **필수**다.

- 본문 텍스트 대비 **4.5:1 이상**, 큰 텍스트 3:1 이상(WCAG AA).
- 모든 인터랙티브 요소에 **`:focus-visible` 포커스 링**(focus-ring `#1ECAFA`, 2px + 2px 간격).
- **터치 타깃 최소 44×44pt**.
- 색만으로 정보 전달 금지(아이콘·라벨 병기). 그라데이션 위 텍스트는 충분한 대비 확보.
- 동작 최소화 옵션 존중. 자동재생·깜빡임 금지.

---

## 8. 보이스 & 카피 ✅
- **신뢰·전문, 과장 금지.** 학술적·정확. 근거수준(검증/추정/향후) 구분.
- 환자 대면 문구는 **쉽고 짧게**(겁주지 않기). 의료진 대면은 정확·간결.
- 표기: 영문 **AfterNOON**(NOON 대문자), 국문 **애프터눈**. "지역 안과"(=지역 1차의료기관 안과) 표준.
- 적용처: 알림톡, 에러 메시지, 빈 상태, 본인인증/간편가입 안내 등 마이크로카피.

---

## 9. 서브브랜드 아키텍처 ✅
모두 **CLOP 마스터** 아래, **공통 심볼(∞ 눈)** 을 공유한다.

| 브랜드 | 국/영문 | 색 주도 | 심볼 |
|---|---|---|---|
| 애프터눈 | 애프터눈 / afterNOON | 녹→청 그라데이션 | ∞ 눈 + ✦ + 콤마 |
| 애프터눈 리서치 | 애프터눈 리서치 / afterNOON Research | 녹색 주도 | 동일 심볼 + "Research/리서치" |
| 애프터뷰 | 애프터뷰 / Afterview | (BI 별도) | 동일 계열 |
| CLOP(모회사) | 클롭 / CLOP | 보라 `#440099` + 옐로 `#FFC72C` | 보라 원형 마크 |

- 로고 변형: 가로형/세로형/심볼, 컬러/화이트/모노(블랙). 최소 여백·최소 크기 준수, 그라데이션 임의 변경·기울임·그림자 금지.

---

## 10. 로고·심볼 자산 (호스팅 raw URL) ✅
> 같은 레포에 호스팅됨. 슬러그는 ASCII(한글 URL 회피).

- 가로 로고(컬러): `…/brand/brand-logo-h-color.png`
- 가로 로고(화이트): `…/brand/brand-logo-h-white.png`
- 세로 로고(화이트): `…/brand/brand-logo-v-white.png`
- 앱 아이콘(그라디언트): `…/brand/brand-appicon-gradient.png`
- 심볼 눈마크(벡터, 컬러): `…/brand/svg/brand-symbol-eye-color.svg`
- 워드마크(벡터, 블랙/화이트): `…/brand/svg/brand-wordmark-black.svg` · `…-white.svg`

베이스: `https://raw.githubusercontent.com/clopai/afternoon-whitepaper-assets/main/`
전체 목록: 같은 레포 `url_map.md` / `manifest.json`.

---

## 11. ⚠ Figma에서 확정할 것 (다음 단계)
정적 BI PDF는 **로고 중심**이라 아래 UI 토큰이 없다. 라이브 제품(환자웹·관리자) Figma의 **variables/styles**에서 확정한다.

1. **확장 팔레트 정본화** — §1.3 8색의 정확한 HEX + 틴트/셰이드 단계(예: 100–900).
2. **시맨틱 토큰** — background/surface/border/text-primary·secondary/success·warning·danger·info, 다크테마.
3. **타입 스케일** — 크기·굵기·행간 전 단계(§2).
4. **간격·radius·elevation** — 실제 사용값(§3–5).
5. **컴포넌트 토큰** — 버튼/인풋/뱃지/카드의 사이즈·상태(hover·active·disabled·focus).
6. **다크 모드** 토큰(제품에 있으면) → `afternoon-design.dark.md` 분리(Geist 패턴).

---

## 변경 이력
| 버전 | 일자 | 내용 |
|---|---|---|
| v0.1-draft | 2026-06-24 | 최초 초안. CI/BI 정본(색·폰트·서브브랜드)+로고 실측(그라데이션) 반영. UI 토큰은 ⚠ 초안값, Figma 확정 대기. |
