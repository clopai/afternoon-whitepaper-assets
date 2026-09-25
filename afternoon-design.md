---
name: AfterNOON Design System
version: 0.3.3-draft
updated: 2026-09-24
owner: CLOP Inc. (clop.ai)
status: internal-draft
source_of_truth:
  brand_ci: "Dropbox/[00] CLOP/[11] Branding (허브 사본 context-reference/design/brand-assets · 판독 결과 DESIGN 01)"
  ui_tokens: "Figma Dev Mode variables (애프터눈 제품 파일). v0.3 = 인앱·포털·어드민·커넥트·설문 페이지 변수 33종 실측 (2026-06-24) — 관찰 출처. 사용 승인값의 정본은 이 파일(판정 규칙은 허브 02 §5)"
confidence_legend:
  confirmed_ci: "CI/BI PDF 인쇄값·로고 실측"
  confirmed_figma: "Figma 제품 변수 실측"
  to_confirm: "초안값/관례 제안 — Figma 미정의(추출 불가) 또는 추가 확인 필요"
colors:
  # 브랜드 식별(마케팅·로고) — 그라데이션
  brand_gradient: { from: "#1EF074", to: "#1ECAFA", angle: "135deg" }   # 색=BI PDF p.8 인쇄값 · 135deg=Figma 브랜드 애셋 fill 실측(디지털 관례). PDF 인쇄 각도는 −60°(Illustrator 표기). 각도는 자유 변수
  accent_lime: "#D8FF00"   # BI PDF p.8 서브 컬러(역할 기재 없음) — 좁은 면적 포인트. 로고 꼬리·스파클 액센트는 brand_extended.green
  # 제품 UI 주색 (confirmed_figma: Primary/*)
  primary:
    base:   "#00CE90"   # 기본 액션·강조·success
    strong: "#009669"   # pressed 보더·표시선·포커스 링 — 버튼 hover 면은 #00AF7A(Q-13, 2026-09-24)
    light:  "#8CE9CD"   # 연한 강조·뱃지
    subtle: "#F3FFFB"   # 선택 배경·연한 면
  # 중립 (confirmed_figma: Gray/* + White + TEXT) — 밝음→어두움
  neutral:
    white: "#FFFFFF"
    "25":  "#FAFAFA"
    "50":  "#F5F5F5"
    "100": "#EEEEEE"
    "200": "#E0E0E0"   # border 기본
    "300": "#BDBDBD"   # disabled 장식(비활성 글자는 #757575, Q-15)
    "400": "#9E9E9E"   # 라이트 글자 금지 — placeholder도 #757575(Q-12). 다크 placeholder만
    "500": "#757575"   # secondary text(흰 배경) · placeholder(Q-12) · 비활성 글자(Q-15)
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
    warning: "#FFC72C"   # 면·아이콘 전용, 조건부 허용(Q-14, 2026-09-24) — 글자 #8C6B06·배경 #FFF4DD, 포털·어드민 업무 상태부터. Figma 미관찰
    focus-ring: "#009669" # 제안 — 비텍스트 3:1 충족(흰 배경 3.77:1). 구 제안 #00CE90은 2.05:1로 미달 (v0.3.1)
  # 보조 액센트 (confirmed_figma)
  accent:
    violet: "#881DFF"    # Sub/881DFF — 제품 UI 전용. 인쇄·브랜드·시각화 보라는 brand_extended.violet #8B1DFF (2026-09-24 분리 확정)
  kiosk:
    blue-gray: "#BFCEE5" # Kiosk 전용 면색
  # 브랜드/다이어그램 액센트 (마케팅·시각화) — green=로고 꼬리·스파클 정본(BI PDF p.8, 2026-09-24 오너 확정; 구 #1AE592는 Figma 브랜드 애셋·2023 PNG 값) · cyan-deep은 BI 외 가독용(to_confirm) · violet=인쇄·브랜드·시각화용 BI 인쇄값(제품 UI는 accent.violet)
  brand_extended: { green: "#3AFF71", cyan: "#1ECAFA", cyan-deep: "#0EA5C4", lime: "#D8FF00", pink: "#DC71FF", violet: "#8B1DFF" }
  # CLOP 마스터 (confirmed_ci) — 모회사·코퍼릿 전용
  clop_master: { violet: "#440099", yellow: "#FFC72C", ink: "#212121", violet-300: "#8848ED", violet-200: "#ADABFF", cool-gray-200: "#C6CBE0" }
typography:
  family: "Pretendard"        # confirmed_figma: 제품 전 영역
  display_en: "Montserrat"    # 오너 확정(2026-09-24): CI 영문 제목 서체 Mundial 대신 Montserrat — 디지털 서체는 Pretendard·Montserrat·Google Fonts에서 고른다(CI 국문 제목 서체 나눔스퀘어 네오는 기존 사용처 유지)
  serif: "Noto Serif"         # CLOP CI p.11 국문 본문 견본
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

> 🔒 **CLOP 내부 전용 v0.3.3.** 애프터눈 서비스·리서치의 **브랜드·디자인 단일 원천(SSOT)**. Vercel `vercel.com/design.md`(Geist) 패턴. 정본 위치·층 구조·편차·접근성 판정은 디자인 허브 `context-reference/DESIGN.md`.
>
> **에이전트 사용법**: 인포그래픽·다이어그램·PPT·카드뉴스·웹/화면 제작 시 이 토큰을 그대로 인용한다. 값 추측 금지. 상단 YAML이 토큰 원본.
>
> **신뢰 라벨**: ✅CI = CI/BI PDF에 인쇄된 값 · ✅FIG = Figma 제품 변수 실측 · 허브 채택 = PDF에 없는 규칙을 허브가 채택 · ⚠ = 초안값/관례 제안.

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
- `linear-gradient(135deg, #1EF074 0%, #1ECAFA 100%)` — 로고·히어로·표지·마케팅·데이터 시각화 주강조. 135°는 Figma 브랜드 애셋 fill 실측 디지털 관례(BI PDF 인쇄 각도 −60°) — 두 정지점만, 각도만 자유.

### 1.2 제품 UI 주색 (Primary) ✅FIG
| 토큰 | HEX | 용도 |
|---|---|---|
| primary | `#00CE90` | 기본 버튼·링크·선택·success |
| primary-strong | `#009669` | hover / active / pressed |
| primary-light | `#8CE9CD` | 연한 강조·뱃지·배경 |
| primary-subtle | `#F3FFFB` | 선택 배경·연한 면 |

### 1.3 악센트 ✅CI
- **Lime `#D8FF00`** — BI 서브 컬러, 좁은 면적 포인트(PDF에 역할 기재 없음). **로고 꼬리·스파클 액센트 = `#3AFF71`**(BI PDF p.8 인쇄 서브 컬러·렌더 실측, 2026-09-24 오너 확정). 기존 로고 파일(2023 PNG 꼬리 `#1AE592`·화이트판 `#D8FF00`)은 그대로 쓰고 재채색하지 않는다.

### 1.4 중립(그레이) ✅FIG
| HEX | 역할 |
|---|---|
| `#FFFFFF` | 배경/표면 |
| `#FAFAFA` · `#F5F5F5` | 연한 면 |
| `#EEEEEE` | 구분 면 |
| `#E0E0E0` | border 기본 |
| `#BDBDBD` | disabled 장식(비활성 글자는 `#757575`, Q-15) |
| `#9E9E9E` | 라이트 글자 금지(placeholder도 `#757575`, Q-12) |
| `#757575` | 보조 텍스트(흰 배경) · placeholder · 비활성 글자 |
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
| focus-ring | `#009669` | 제안 — 비텍스트 3:1 충족(3.77:1). 구 제안 `#00CE90`은 2.05:1 (v0.3.1) |

### 1.6 보조 액센트·기타 ✅FIG
- **Violet `#881DFF`** (Sub) — 제품 UI 보조 강조 전용. 인쇄·브랜드·시각화에는 BI 인쇄값 `#8B1DFF`를 쓴다(2026-09-24 분리 확정).
- **Kiosk `#BFCEE5`** — 키오스크 전용 면색.
- 다이어그램/마케팅 액센트: green `#3AFF71`(로고 꼬리·스파클 정본, 2026-09-24 — 구 `#1AE592`)·cyan `#1ECAFA`·cyan-deep `#0EA5C4`(⚠ BI 외, 흰 배경 가독용)·lime `#D8FF00`·pink `#DC71FF`·violet `#8B1DFF`(BI 인쇄값, 시각화용).

### 1.7 CLOP 마스터 ✅CI (모회사·코퍼릿)
Violet `#440099` · Yellow `#FFC72C` · Ink `#212121` · 틴트 `#8848ED`/`#ADABFF`/`#C6CBE0`. 제품 그린과 동등 비중 혼용 금지.

---

## 2. 타이포그래피 ✅FIG (Pretendard)
**제품 전 영역 = Pretendard.** weight: Regular 400 / Medium 500 / SemiBold 600(=‘bold’ 토큰). 영문 제목 Montserrat(2026-09-24 오너 확정 — CI 영문 제목 서체 Mundial 대신. 디지털 서체는 Pretendard·Montserrat·Google Fonts에서 고른다), 세리프 Noto Serif(CI p.11 국문 본문 견본). 로고 워드마크는 로고 전용.

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
- 본문 대비 **4.5:1 이상**(WCAG AA, 반올림 전 값으로 판정). 보조 텍스트 `#757575`=흰 배경 4.6:1(충족, 연한 면 위는 `#616161`), `#9E9E9E`는 3:1 미만이므로 **라이트에서 글자 금지 — placeholder도 `#757575`(흰 입력 면, `::placeholder{opacity:1}`)**(Q-12, 2026-09-24).
- 모든 인터랙티브 요소 **`:focus-visible` 링**(`#009669` — 비텍스트 3:1, v0.3.1). 초록 면 위에서는 `#222222` 2중 링. 터치 타깃 **44×44pt(iOS)·44 CSS px(웹)** 이상, 환자 표면 48·주요 컨트롤 52(Q-16).
- 색 단독 정보전달 금지(아이콘·라벨 병기). 동작 최소화 존중, 깜빡임 금지.

## 8. 보이스 & 카피 (허브 채택 — PDF 미기재)
- 신뢰·전문·과장 금지. 근거수준(검증/추정/향후) 구분. 환자 대면은 쉽고 짧게.
- 표기: **AfterNOON**(NOON 대문자) / **애프터눈**. "지역 안과"(=지역 1차의료기관 안과).
- 적용처: 알림톡·에러·빈 상태·본인인증/간편가입 안내 등 마이크로카피.

## 9. 서브브랜드 아키텍처 ✅CI
| 브랜드 | 색 주도 | 심볼 |
|---|---|---|
| 애프터눈 | 그라데이션(식별) + 그린 #00CE90(UI) | ∞ 눈 + ✦ + 콤마 |
| 애프터눈 리서치 | 녹색 주도 | 동일 + "Research/리서치" |
| 애프터뷰 | (BI 별도) — 광각안저사진 판독 CDSS, **개발 중지**(2026-09-24 오너 확인, 재개 계획 없음) | 원형 심볼 없이 워드마크 + 4각 스파클 |
| CLOP(모회사) | 보라 #440099 + 옐로 #FFC72C | 보라 원형 마크 |

로고 변형: 가로/세로/심볼 × 컬러/화이트/모노(PDF 인쇄). 최소 여백·크기 준수, 그라데이션 변형·기울임·그림자 금지 — 이 금지 규칙은 허브 채택(PDF 미기재. 여백은 CLOP CI p.3에만, 최소 크기는 4종 모두 없음 → DESIGN 01 §2).

## 10. 로고·심볼 자산 (raw URL) ✅
베이스 `https://raw.githubusercontent.com/clopai/afternoon-whitepaper-assets/main/` — `brand/brand-logo-h-color.png`·`-h-white.png`·`brand-logo-v-white.png`·`brand-appicon-gradient.png`·`brand/svg/brand-symbol-eye-color.svg`·`brand/svg/brand-wordmark-black.svg`. 전체: `url_map.md`/`manifest.json`. 허브 사본(원 파일명 `BRAND_*`): `context-reference/design/brand-assets/afternoon-digital/`.

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
| v0.3.1 | 2026-09-24 | **라벨 정정(값 불변)**: 각도 135°=Figma 브랜드 애셋 실측 디지털 관례(PDF 인쇄 −60°) · Montserrat=디지털 관례(CI 제목 서체 Mundial) · §8 보이스·§9 로고 금지 규칙=허브 채택 · lime 역할 기재 삭제. **값 결정**: 로고 꼬리·스파클 액센트 `#3AFF71`(brand_extended.green, 구 `#1AE592`) · focus-ring 제안 `#00CE90`→`#009669`. 애프터뷰 개발 중지 표기. 정본 위치 = `context-reference/design/tokens/`(디자인 허브 Q-03·Q-04, 오너 승인). **줄 번호 불변**(doctors 인용 보호) |
| v0.3.2 | 2026-09-24 | **오너 결정 반영**: violet 분리 — 제품 UI `#881DFF`(accent.violet·Figma Sub 변수) / 인쇄·브랜드·시각화 `#8B1DFF`(brand_extended.violet, BI PDF 인쇄값). 서체 — CI 영문 제목 서체 Mundial 대신 Montserrat, 디지털 서체는 Pretendard·Montserrat·Google Fonts에서 고른다(나눔스퀘어 네오는 기존 사용처 유지). 줄 번호 불변 |
| v0.3.3 | 2026-09-24 | **오너 위임 결정 반영**(Q-12·Q-13·Q-14·Q-15·Q-16 일부 — astra 제안·Fable 상의): §7 `#9E9E9E` 라이트 글자 금지·placeholder `#757575`(`::placeholder{opacity:1}`)·반올림 전 판정·초록 면 위 2중 포커스 링·터치 타깃 단위와 환자 48/52 · §1.4 역할 문구 · YAML 주석(strong·neutral·warning)과 `ui_tokens`=관찰 출처. 표 HEX·헤딩·줄 번호 불변. §1.2 122행(hover)은 doctors 인용 줄이라 유지(허브 D-39) |
