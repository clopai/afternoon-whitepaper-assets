# AfterNOON 제품 UI 디자인 시스템 — 정본 확장 afternoon-ui-tokens.md v1.0 (2026-09-25)

> **정본 확장**(B-13, 2026-09-25). 원천은 Claude Design R-01 v1.2(허브 `design-handoffs/afternoon_product_ui_design_handoff/`, 수령·검수 2026-09-25)이고, 허브 결정 Q-12~Q-21을 반영했다.
> - 값의 원천은 `afternoon-ui-tokens.css`다. `afternoon-ui-tokens.json`은 같은 값의 사본이고, 생성 파이프라인(B-17) 전까지는 둘 다 고친다.
> - 기본 원시값·doctors 계약은 `afternoon-design.md` v0.3.3이 맡는다. 이 문서는 역할·다크·스케일·키오스크·컴포넌트 계약을 맡는다.
> - 편집은 허브 `design/tokens/`에서만 한다. 아래 본문은 R-01 v1.2 문서이고, 허브에서 고친 곳은 §5 글자 크기 3단계와 손으로 적은 대비 수치 2건이다.

적용 범위: 환자 인앱·웹, 의원 포털·어드민, 키오스크(1280×800), 결과지. 기준 문서 01(✅FIG·v0.3.x 불변) → 03(병원용 확정) → 04(설문 확정) 순으로 흡수했다. 다른 값을 택한 곳은 **[다름]** 표시와 이유를 붙였다. 대비는 WCAG 2.x 상대휘도(02 §4 재현식)로 계산했다.

파일: `afternoon-ui-tokens.css`(라이트·다크·스케일) · `afternoon-ui-tokens.json`(같은 값) · 핸드오프 보드 `components.dc.html`(참고용 — 컴포넌트×상태 정적 보드, 라이트+다크, §14 대비표(검수 스크립트가 tokens.css 실측값에서 생성), §16 경계 프레임. 서체는 jsDelivr CDN에서 로드하며 오프라인에서는 시스템 sans로 대체된다). 로고는 R-02 `../design-handoffs/brand_logo_system_handoff/svg/` 파일을 파일명으로 참조한다(`brand/` 사본 없음).

---

## 1. 토큰 구조 — 2단

```
원시(primitive)  --p-green-500 #00CE90 …   테마와 무관한 값. 01 정본 + 신설 변형
      ↓
의미 역할(semantic)  --primary, --on-primary, --indicator, --focus-ring …   테마(라이트/다크)·스케일별로 원시를 다시 가리킨다
      ↓
컴포넌트          의미 역할만 참조한다. 원시 토큰·HEX 직접 사용 금지
```

- 테마 전환: `:root`(라이트) · `[data-theme="dark"]` · OS `prefers-color-scheme: dark`(단, `[data-theme="light"]`로 고정 가능). 보드에서는 `data-theme` 래퍼 하나만 바꿔 같은 마크업을 두 테마로 그린다.
- 표면 스케일: `[data-surface="portal"]`(포털·어드민 타입) · `[data-surface="kiosk"]`(라이트 역할 고정, §7) · `[data-scale="large"]`(환자 대형) · `[data-scale="xl"]`("더 크게", Q-20 채택).
- **스케일 블록은 타입·치수만 바꾼다. 색은 테마 블록만 바꾼다.** 구판은 `[data-scale="large"]`가 `--text`·`--text-secondary`·`--border-strong`을 바꿔 OS 다크 + `data-theme` 없는 루트 아래에서 `#222222` on `#222222`(1.00)·`#616161` 2.57이 생겼다(검수 반영). 04의 본문 `#222222`·보조 `#616161`·빈 테두리 `#616161`은 라이트 테마 값(`#000000`·`#616161`·`#757575` 4.61)으로 흡수한다 **[다름]**.
- 테마 블록의 역할 목록은 세 곳이 같아야 한다: `[data-theme="dark"]` = OS 다크 `:root:not([data-theme="light"])` ⊆ `[data-surface="kiosk"]`. 보드 §15 검수 스크립트가 tokens.css 원문을 읽어 대조한다.
- 원시 색은 01 정본 값 + **oklch 명도 변형만** 추가했다(색상·채도 유지, `N` 표시). 새 브랜드 색은 없다.

### 1.1 원시 색 (추가분만 — 나머지는 01 §1 그대로)
| 토큰 | HEX | 출처 | 왜 |
|---|---|---|---|
| green-600 | `#00AF7A` | 04 설문 | 주 버튼 hover 면. `#222222` 라벨 5.62 (면 전용, 표시선으로는 2.83 미달) |
| green-800 | `#00775A` | 02 후보 채택 | 본문용 초록. 흰 배경 5.55, `#F3FFFB` 위 5.42. `#00CE90` 색상(oklch H 2.84→2.94, L .75→.51) |
| green-950 | `#00321F` | N | 다크 선택·성공 면(`#00CE90` L .28) |
| gray-850 | `#2C2C2C` | N | 다크 raised·hover 면 |
| gray-950 | `#191919` | 요청서 §4 | 다크 캔버스(BI 모노) |
| red-800 | `#B42318` | 04 설문 | 위험 버튼 hover 면(흰 라벨 6.57) |
| red-400 | `#FF615B` | N | 다크 error-text. `#FF3E3E` oklch L .66→.75: `#222222` 5.39 · `#2C2C2C` 4.73 · `#3B0002` 5.99 |
| red-950 / blue-50 / blue-400 / blue-950 / yellow-50 / yellow-700 / yellow-800 / yellow-950 / violet-50 / violet-300 / violet-950 | 표 참조 `tokens.json` | N | 상태 배경·다크 글자. 각 값의 대비는 §3·보드 대비표 |

---

## 2. 신설 역할 토큰 (02 §5 "정할 것 9가지" 답)

| # | 역할 | 라이트 | 다크 | 근거(대비) |
|---|---|---|---|---|
| 1 | **focus-ring** | `#009669` 2px, offset 2px | `#009669` 유지 | v0.3.1 확정. 흰 3.77 · `#F3FFFB` 3.68 · `#222222` 4.22 · `#191919` 4.66 — 모두 3:1 이상. 대형 스케일은 3px(04) |
| 1 | **indicator**(라디오 점·탭 밑줄·진행 fill·토글 on·선택 보더) | `#009669` | `#00CE90` | 라이트 3.77 / 다크 7.75. **[다름]** 04 설문의 `#00AF7A`(2.83)는 02 §5-1 지적대로 표시선 미달 → `#009669`로 교체 |
| 1 | **indicator-fill**(체크박스 fill) | `#00CE90` + 체크 `#222222` + 보더 `#009669` | 같음 | 체크 표시 7.75(면 대비), 박스 경계 3.77 — 02 권고 |
| 2 | **on-primary** | `#222222` | `#222222` | `#00CE90` 위 7.75. 흰 글자는 2.05로 금지. 03·04와 동일 |
| 3 | **error-text** | `#CC3232` | `#FF615B` | 라이트: 흰 5.16 · `#FFECEC` 4.54 · pressed 면 `#F5F5F5` 4.73 (03 코드 고정값 채택). **[다름]** 04의 `#B42318`(6.57)은 통과하지만 값 하나로 모으기 위해 `--danger-hover`로 재배치. 다크: red-400 `#FF615B` — `#222222` 5.39 · `#2C2C2C` 4.73 · `#191919` 5.96 · `#3B0002` 5.99. `#FF3E3E`는 `#2C2C2C` 위 4.00 미달(검수 반영). 보더·아이콘 `--error`는 `#FF3E3E` 유지 |
| 3 | error(보더·아이콘) | `#FF3E3E` | `#FF3E3E` | 3.49 / 4.55 — 비텍스트 3:1 |
| 4 | **green-text** | `#00775A` | `#8CE9CD` | 5.55 / 11.1. 현행 인앱의 `#00CE90` 글자(2.05) 대체 |
| 5 | **warning** 면 / 보더 / 글자 / 배경 | `#FFC72C` / `#B98E0C` / `#8C6B06` / `#FFF4DD` | `#FFC72C` / `#FFC72C` / `#FFC72C` / `#302200` | 라이트 글자 `#8C6B06` 흰 배경 **4.98**(구판의 4.61은 오기), `#FFF4DD` 위 4.56 · on-warning `#222222` 10.2 · 다크 글자 10.2. 보더 `#B98E0C`는 흰 3.03이지만 `#FFF4DD` 위 **2.77**이라 **장식**으로 분류 — warning 상태는 아이콘 + 글자로 전달한다. **적용 범위**: 포털·어드민의 업무 상태부터 쓰고 환자 표면은 초기에 쓰지 않는다. 입력 필드에는 warning 상태를 두지 않는다(valid·error만). **상태색(success·warning·error)을 임상 판정(정상/질환)에 연결하지 않는다** — 판정은 글자로 쓴다. **[다름]** 03은 사용 금지였음 — 색은 01 후보 `#FFC72C`를 면·아이콘으로 한정하고 글자는 명도 변형으로 채움. 업무 상태 의미는 CLOP 승인 후 |
| 6 | **link** | `#0B50D0` + 밑줄 | `#5790FA` + 밑줄 | 6.83 / 4.51(`#191919` 5.67). 03과 같음. info 텍스트는 같은 색, 밑줄 없음 |
| 6-1 | **focus-ring-on-primary** | `#222222` 2중 링 | 같음 | 초록 면 위 요소(헤더 CTA 등)의 포커스. `#009669` 링은 `#00CE90` 위 1.84로 금지. 2px `#222222` 링 + 2px 면색 간격, 7.75 |
| 6-2 | **surface-on-primary** | `#FFFFFF` | 같음 | 초록 면 위 CTA의 면. 라벨 `--on-primary` 15.91 + 2px `--on-primary` 보더. `--primary` 면 CTA는 헤더에 묻힌다 |
| 6-3 | **pressed** | 면 = hover 면 `#F5F5F5` + 2px `--border-strong` | 면 = `#2C2C2C` + 2px `--border-strong` | **[다름]** 구판 pressed 면(`#EEEEEE`/`#424242`)은 글자 대비 미달: 라이트 error-text 4.45, 다크 link 3.24 · accent 3.25 · error-text 3.40. 글자가 있는 행·카드·버튼의 pressed는 면을 바꾸지 않고 보더·형태로 표시한다 |
| 6-4 | **placeholder** | `#757575` + `::placeholder{opacity:1}` | `#9E9E9E` | 흰 입력 면 4.61 / 5.94. 연한 면 입력은 `--text-placeholder-on-subtle` `#616161`. Firefox 기본 opacity .54를 tokens.css 끝의 `::placeholder` 규칙이 1로 고정 **[다름]** 01의 `#9E9E9E` placeholder(2.68) 대신 |
| 7 | selected | bg `#F3FFFB` + 보더 2px `#009669` | bg `#00321F` + 보더 `#00CE90` | 3.68 / 6.93. 03: 좌측 2px만(표 행), 04: 전체 2px(선택 카드) — 둘 다 허용, 컴포넌트별 명시 |
| 8 | 환자 대형 스케일 | `[data-scale="large"]` | 같음 | §5 |
| 9 | 다크 모드 | — | `#191919` 캔버스·`#222222` 표면 | §6 |

추가 역할 2건(보드 대비표에서 드러난 미달을 막기 위해 신설):
- **라이트 `--text-secondary` = `#616161`(FIG gray-700)로 통일**(검수 반영). `#757575`(4.61)는 흰 배경에서만 통과하고 연한 면에서 미달한다: `#F5F5F5` 4.23(표 머리글·중립 배지) · `#F3FFFB` 4.50(선택 카드·행) · `#FFECEC` 4.05(오류 행) · `#FAFAFA` 4.41. `#616161`은 같은 면에서 5.68 · 6.05 · 5.44 · 5.93. `#757575`는 **입력 보더(`--border-strong`)·비활성(`--text-disabled`)에만** 쓴다. `--text-secondary-strong`은 호환용 별칭(같은 값). 다크는 `#BDBDBD` 그대로.
- `--toggle-knob` = 라이트 `#FFFFFF`(on 트랙 `#009669` 위 3.77) / 다크 `#222222`(on 트랙 `#00CE90` 위 7.75; 흰 손잡이는 2.05 미달).

그 밖의 역할: `--danger`(위험 버튼 면 `#CC3232`, 흰 라벨 5.16) · `--accent-text`(`#881DFF` 5.73 / 다크 `#A47AFE` — `#222222` 5.15 · `#2C2C2C` 4.52) · `--guide`(`#223A58` 11.58 / 다크 `#BDBDBD`) · `--text-disabled`(`#757575` — **[다름]** 03의 `#BDBDBD` 1.88 대신 `#EEEEEE` 면 위 3.97. 비활성은 WCAG 면제지만 고령 사용자가 "있음"은 읽어야 한다).

### 2.1 초록 면 위 라벨 규칙 (전 컴포넌트 공통)
- `#00CE90` 면 위에는 **`--on-primary`(#222222) 하나만** 놓는다. 흰 글자·아이콘·`#009669` 아이콘(1.84) 금지.
- `#00CE90`은 흰 배경 글자·의미 아이콘으로 쓰지 않는다. 초록 글자가 필요하면 `--green-text`.
- 진행 막대·토글·라디오 점처럼 *형태로 상태를 전하는 표시선*은 `--indicator`(#009669)다. 면(#00CE90)과 표시선(#009669)을 구분한다.
- 초록 면 위 조작 요소의 포커스는 `--focus-ring-on-primary`(#222222 2중 링). 초록 면 위 CTA는 `--surface-on-primary`(흰 면) + `--on-primary` 라벨 + 2px `--on-primary` 보더.

### 2.2 로고 — 테마가 아니라 배경으로 고른다

| 토큰 | R-02 파일(`brand_logo_system_handoff/svg/`) | 배경 | 근거 |
|---|---|---|---|
| `--logo-on-light` | `afternoon-horizontal-ko-color.svg` | 흰·연한 면(`#FFFFFF`·`#FAFAFA`·`#F5F5F5`·`#F3FFFB`), 키오스크 흰 카드 | 컬러 심볼 + 검정 워드마크 |
| `--logo-on-dark` | `afternoon-horizontal-ko-white.svg` | `#191919`·`#222222`·`#2C2C2C` | 흰 단색판 15.9 |
| `--logo-on-primary` | `afternoon-horizontal-ko-black.svg` | **`#00CE90` 면(결과지 헤더 포함)** | 검정 단색판만. "검정 워드마크 + 컬러 심볼" 조립은 심볼 양끝이 `#00CE90` 위 1.35(`#1EF074`)·1.06(`#1ECAFA`)이라 금지, 흰판은 2.05라 금지. 다크 테마에서도 헤더가 초록이면 같은 파일 |
| `--logo-on-gradient` | `afternoon-horizontal-ko-white-accent.svg` | 브랜드 그라데이션(마케팅 전용) | UI 면에는 그라데이션이 없으므로 제품 UI에서는 쓰이지 않는다 |

테마 블록은 로고 토큰을 덮어쓰지 않는다. 키오스크 캔버스 `#BFCEE5` 위에는 로고를 두지 않는다(흰판 1.59) — 흰 카드 위 `--logo-on-light`. 재채색·필터·opacity 금지.

---

## 3. 대비 요약 (전체 표는 components.html 하단)

전체 표는 보드 §14 — 손으로 옮긴 값이 아니라 검수 스크립트가 tokens.css 실측값에서 생성하고, 판정은 반올림 전 값으로 한다(예: `#757575` on `#F3FFFB` = 4.4996 → 미달).

라이트(흰 배경 `#FFFFFF`): 본문 `#000000` 21 · 제목 `#222222` 15.91 · 보조 `#616161` 6.19(`#F5F5F5` 5.68 · `#F3FFFB` 6.05 · `#FFECEC` 5.44) · 링크 6.83 · error-text 5.16(pressed `#F5F5F5` 4.73) · green-text 5.55 · warning-text **4.98** · accent 5.73 · placeholder `#757575` 4.61. 표시: focus/indicator 3.77 · focus-on-primary `#222222` on `#00CE90` 7.75 · error 보더 3.49 · warning 보더 3.03(장식) · 입력 보더 `#757575` 4.61.
다크(표면 `#222222` / raised·hover·pressed `#2C2C2C`): 본문 `#EEEEEE` 13.71 / 12.04 · 제목 `#FFFFFF` 15.91 · 보조 `#BDBDBD` 8.47 / 7.43 · 링크 `#5790FA` 5.13 / 4.51 · error-text `#FF615B` 5.39 / 4.73 · accent `#A47AFE` 5.15 / 4.52 · green-text `#8CE9CD` 11.1 / 9.74 · warning `#FFC72C` 10.2 / 8.95 · placeholder `#9E9E9E` 5.94. 표시: focus `#009669` 4.22(`#191919` 4.66 · `#2C2C2C` 3.70) · indicator `#00CE90` 7.75 · 입력 보더 `#9E9E9E` 5.94. 경계: 다크 안 키오스크 카드는 라이트 값(accent `#881DFF` 5.73 — 다크 값 `#A47AFE`면 3.09) · 다크 안 large 본문 `#EEEEEE` 13.71(구판 1.00).

---

## 4. 간격 · 모서리 · 그림자 · 모션

- **간격** 4px 스케일: 4·8·12·16·20·24·32·40 운영 / 64·96 마케팅·공개 화면만(03). 20은 04 인앱 좌우 여백.
- **모서리**: control 10 · surface 12 · pill 9999 · sm 4(체크박스·태그). 01 관례이자 03 코드 고정값. **[다름]** 04 설문의 8px은 10으로 수렴 권고 — 52px 버튼에서 8과 10은 식별되지 않고, 제품 전체에 모서리 한 가족만 둔다.
- **그림자** 3단: 카드·표면 없음(03) → `--shadow-1` 팝오버·드롭다운 `0 4px 12px 8%` → `--shadow-2` 모달·드로어 `0 8px 24px 8%`(03 D13) → `--shadow-3` 바텀시트(위 방향). 다크는 알파 50–60% + 표면 명도 차로 층을 만든다.
- **모션**: fast 120 · base 180(04 문항 전환) · slow 240, ease-out. `prefers-reduced-motion`에서 0.01ms(03). 깜빡임·자동 이동 금지.
- **포커스**: 모든 조작 요소 `outline: var(--focus-ring-w) solid var(--focus-ring); outline-offset: 2px`. 초록 면 위 요소는 `--focus-ring-on-primary`(#222222). 보더 교체·outline 제거 금지(03 §9).
- **pressed**: 면은 hover 면 그대로(`--bg-pressed` = `--bg-hover`), 표시는 `box-shadow: inset 0 0 0 2px var(--border-strong)` 또는 기존 2px 보더 강조. 주 버튼은 `--primary-hover` 면 + 2px `--primary-pressed-border`.
- **조작 치수**: 기본 44 · 모바일 고정 CTA 48(03) · 대형 52 · 키오스크 56.

## 5. 타입 스케일과 "환자 대형 스케일"

| 역할 | 인앱 기본(✅FIG) | 포털·어드민(✅FIG) | **대형 `[data-scale=large]`**(04) | 키오스크 |
|---|---|---|---|---|
| h1 | 600/28/36 | 600/28/36 (Title 40은 마케팅 hero만 · Montserrat 600은 라틴 글리프만 있어 한글이 섞이면 그 글자는 `--font-display-en` 폴백인 Pretendard 600으로 렌더된다 — hero 제목은 영문만, 국문 hero는 Pretendard) | **600/28/36** (인앱 기본보다 작아지지 않는다 **[다름]** 04의 24는 title-sm으로 흡수) | 600/40/52 |
| title(섹션·문항) | 600/16/24 | 600/16/24 · 패널 600/20/28 | **500/20/30** | 600/24/34 |
| title-sm(화면 제목·상태·시트) | 600/14/20 | — | **600/24/34** (04 화면 제목 24 · 시트 22→24) | — |
| body | 400/16/24 | 400/16/24 · lg 400/18/26 | **400/17/26** | 400/20/30 |
| body-sm · label | 400·500/14/20 | 400·600/14/20 | 400·500/15/22 | 400·500/17/26 |
| meta | 400/12/16 +1 | 400/12/16 +1 | 400/15/22 | 400/17/26 |
| caption | **400/12/16** — 인앱 최소 12px. Figma Caption 10은 `--font-caption-10-fig`로 기록만, **사용 금지(법정 표기 포함)** | 600/12/14 | 400/15/22 (환자 프로필 최소 15) | — |

자간 `-2px`(h1)·`-1px`(title·대형 h1)·`+1px`(meta·Title 40)은 Figma 변수의 단위(px / %) 확인 전까지 **확인 필요**로 둔다. 확인되면 값 그대로 단위만 맞춘다.

**관계와 제안**: 대형 스케일은 인앱 기본의 *역할 이름을 그대로 두고 타입·치수 값만 바꾸는 모드*다(색은 바꾸지 않는다). 컴포넌트는 `--font-body` 등 역할만 참조하므로 `data-scale="large"` 래퍼 하나로 화면 전체가 커진다(15px 미만 글자 0, 컨트롤 52, 터치 48, 포커스 링 3px).
- **글자 크기 3단계**(Q-16 개정·Q-20, 2026-09-25 — 고령 환자와 일반 사용 모두): 일반(`data-scale` 없음, 인앱 기본) · 크게(`large`) · 더 크게(`xl`).
  - 환자 설문·결과지·안내 등 **환자가 읽는 인앱 화면의 첫 기본값은 `large`**다.
  - 사용자가 설정에서 **양방향으로** 고르고, 고른 단계를 기억한다.
- **`[data-scale="xl"]`(더 크게, Q-20 채택)**: h1 600/32/42 · title 500/24/34 · title-sm 600/26/36 · 본문 400/20/30 · 보조·label 400·500/18/28 · meta 18/28 · 컨트롤 56 · 터치 52 · 표시 28 · 토글 60×34. tokens.css §8-1에 블록으로 두었다.
- OS 큰 글씨(iOS Larger Text / Android 글꼴 크기) 자동 적용은 **네이티브·WebView 브리지가 값을 넘겨줄 때만** 한다. 카카오톡 인앱 브라우저 등 브리지가 없는 환경에서는 감지하지 않고 `large` 기본 + 토글로 둔다.
- 포털·어드민·키오스크에는 적용하지 않는다(키오스크는 자체 스케일).
- **키오스크는 라이트 전용**: `[data-surface="kiosk"]` 블록이 다크 블록이 바꾸는 역할 **전체(54개, accent·disabled·skeleton·shadow 포함)**를 라이트 값으로 되돌린다(`color-scheme: light` 포함). 선택자에 `:root[data-surface="kiosk"]`(0,2,0)·`[data-theme="dark"][data-surface="kiosk"]`를 더해 OS 다크의 `:root:not([data-theme="light"])`(0,2,0)와 명시 다크 아래에서도 이 블록이 이긴다(같은 명시도 → 파일 뒤쪽 우선). 보드 §15가 두 블록의 역할 목록을 대조하고 §16-1이 다크 안 키오스크를 렌더 실측한다(검수 반영). 로고는 `--logo-on-light`(흰 카드 위).

## 6. 다크 모드

- 캔버스 `#191919`, 표면 `#222222`, raised·hover·pressed `#2C2C2C`(pressed는 보더로 표시 — `#424242` 면은 링크 3.24·accent 3.25·error-text 3.40 미달). 순수 검정 없음. 층은 그림자보다 명도 차 + 1px 보더(`#424242`)로 만든다.
- 글자: 본문 `#EEEEEE`(흰색은 제목만) · 보조 `#BDBDBD` · placeholder `#9E9E9E`(5.94, 다크에선 본문 기준도 통과).
- 초록: 면 `#00CE90`은 그대로(`#191919` 위 8.57), 라벨은 여전히 `#222222`. 표시선은 `#00CE90`으로 올려 7.75. 포커스 링은 확정값 `#009669` 유지(4.22–4.66).
- 상태 배경은 각 색의 L .22–.28 변형(`#00321F` `#3B0002` `#302200` `#001B5F` `#2E0060`); 그 위 본문 `#EEEEEE` 12–15, 상태 글자 4.5 이상(표 참조).
- 로고: 배경으로 고른다(§2.2). 다크 면 위 `--logo-on-dark`, 초록 헤더 위는 다크에서도 `--logo-on-primary`.
- **적용 범위**: 환자 인앱 **읽기·안내 화면**의 **사용자 선택형 시험**(기본 라이트, 설정에서 켬). **결과지 화면은 제외**(인쇄·공유 PDF와 같은 모습을 유지). 병원용·설문·키오스크는 라이트 고정 → 해당 루트에 `data-theme="light"`(키오스크는 블록이 고정). 확대는 CLOP이 정한다.

## 7. 레이아웃 그리드

| 표면 | 프레임 | 컬럼·거터 | 좌우 여백 | 폭 제한 |
|---|---|---|---|---|
| 모바일 인앱 | 360·390·430 (카카오 인앱: 상단 52 바, 하단 safe-area) | 4열 · 16 | 20 | 태블릿 768+에서 콘텐츠 640 가운데(04) |
| 포털·어드민(03) | <768 / 768–1199 / 1200–1279 / 1280–1599 / ≥1600 | 12열 · 24 | 16 / 32 / 40(≥1600) | 로그인 480 · 폼 640 · 읽기 720 · 패널 360 · 콘텐츠 960(≥1600) · 데이터 화면 제한 없음. 헤더 64/56, 사이드바 232/72 |
| 키오스크 | 1280×800 고정 | 12열 · 24 | 48 | 캔버스 `#BFCEE5`, 컨트롤·글자·로고는 흰 `--bg-surface` 카드 위에만(`#009669`가 `#BFCEE5` 위 2.37, 흰 로고 1.59, `#616161` 3.89로 미달 — 캔버스 위는 `#222222` 제목·안내만). 색 역할은 라이트 고정(§5) |

## 8. 현행 인앱 결과지 헤더 교정안 (06 in-app_result)

현행: 헤더 면 `#00CE90` 위 흰 제목·흰 워드마크·흰 CTA 라벨(2.05), 의원명 `#00CE90` 글자(2.05), 장식 원은 그라데이션에 가까운 반투명 겹침.

교정(보드 §13 · §16-3 프레임, 마크업 하나 + `--result-header-*` 토큰):
1. **A(기본, 화면)**: 헤더 면 `--result-header-bg` = `--primary`, 제목 `--result-header-ink` = `--on-primary`(#222222, 7.75). 로고는 `--result-header-logo` = `--logo-on-primary` = **R-02 `afternoon-horizontal-ko-black.svg`** — "검정 워드마크 + 컬러 심볼" 조립(심볼 양끝 1.35·1.06)과 흰판(2.05)은 금지. 장식 원은 `--result-header-deco`(`--primary-light` #8CE9CD) 단색 1개, 글자와 겹치지 않는 위치.
2. **헤더 안 CTA**(공유·저장 등): `--surface-on-primary`(흰 면) + `--on-primary` 라벨 + 2px `--on-primary` 보더. `--primary` 면 CTA는 헤더에 묻혀 경계가 사라지므로 헤더 안에서는 쓰지 않는다. 포커스는 `--focus-ring-on-primary`(#222222 2중 링: 2px 링 + 2px 면색 간격, 7.75) — `#009669` 링은 1.84.
3. 본문의 주 CTA("결과지 해석 보기")는 흰 캔버스 위이므로 `--primary` 면 + `--on-primary`.
4. 의원명 등 초록 강조 글자 → `--green-text`(#00775A, 5.55). 카드 테두리 초록은 `--indicator`(#009669).
5. **B(인쇄·공유 PDF)**: 같은 마크업에 `@media print` 또는 `[data-print="pdf"]`가 걸리면 `--result-header-bg` 흰 · `--result-header-ink` #222222 · `--result-header-band` 8px 초록 띠 · `--result-header-logo` = `--logo-on-light` · 장식 원 투명. 테마와 무관하게 B로 찍힌다.
6. 다크: 헤더 면 `--primary` 그대로(`#191919` 위 8.57), 잉크 #222222, 로고는 **같은 검정판**(로고는 배경으로 고른다). 결과지 화면은 다크 시험 범위에서 제외(§6).

## 9. 컴포넌트 계약 요약 (상세 상태는 components.html)

- **버튼** 주(면 `--primary`/hover `--primary-hover`/pressed +2px `--primary-pressed-border`) · 보조(표면 + `--border-strong`, pressed는 `--bg-pressed`(= hover 면) + 2px `--indicator` 보더) · 텍스트(`--link` 밑줄, 44px 터치, pressed는 hover 면 + inset 2px `--border-strong`) · 위험(`--danger`, 흰 라벨) · 초록 면 위 CTA(`--surface-on-primary` + `--on-primary` + 2px 보더). loading은 라벨 유지 + 스피너, disabled와 구별(03). **[다름]** 03 "hover에 primary-strong 면" → hover 면은 `#00AF7A`: `#222222` 라벨이 `#009669` 위 4.22로 미달하기 때문. `#009669`는 pressed 보더로 남긴다.
- **입력·셀렉트·OTP** 44px, 보더 `--border-strong`, label 500/14 → 8 → hint/error 4(03). placeholder `--text-placeholder`(#757575) + `::placeholder{opacity:1}`; 연한 면 입력은 `--text-placeholder-on-subtle`. error는 `--error` 보더 + `--error-text` 메시지 + `role=alert`. valid는 `--success-border` + 체크 아이콘. **warning 상태 없음**. readonly는 `--bg-subtle` 면·보더 없음·값 유지.
- **라디오·체크·토글** 표시 20px(대형 24), 빈 테두리 `--border-strong` 2px. 선택: 라디오 점 `--indicator` / 체크 fill `--indicator-fill` + `--on-primary` 체크 / 토글 on 트랙 `--indicator` + 흰 손잡이(3.77).
- **탭** 44px, 밑줄 2px `--indicator`, 라벨 선택 시 `--text-heading` 600.
- **표·목록 행** 44(상호작용)/40/36, hover `--bg-hover`, pressed = hover 면 + inset 2px `--border-strong`, selected `--selected-bg` + 좌측 2px `--selected-border`(03).
- **카드** radius 12 · 1px `--border` · 16 패딩 · 무그림자. 선택 카드는 전체 2px `--selected-border`(04).
- **모달 480/720 · 드로어 360 · 바텀시트** 스크림 `--bg-scrim`, 초기 포커스·Tab trap·Escape·복귀(03).
- **배지·칩** 배지는 상태 배경+상태 글자+아이콘 병기(warning 배지는 포털·어드민 업무 상태만, 보더는 장식). 칩 selected는 포털 금지(03), 인앱 필터 칩만 허용. 상태색을 임상 판정에 쓰지 않는다.
- **토스트·인라인 알림** info/success/error/warning 4종, 아이콘+글자 병기, 자동 해제 없음(success 유지, 03).
- **빈 상태** 이유 1문장 + 다음 행동 1개. **진행 표시** 막대 `--indicator`/트랙 `--divider` + 숫자 병기, 단계형 완료·현재·잠금. **하단 고정 바** 상단 1px 보더, safe-area, 이전 112 + 주 버튼 flex.

## 10. 자체 검수 (요청서 §6)
- ✅FIG 값·`#009669` focus-ring·`#881DFF` violet 불변 — 원시 토큰 주석에 출처 표기
- 컴포넌트 15종 × 상태(default·hover·focus·pressed·selected·disabled·loading·error·success + valid·readonly) 라이트·다크 보드 + §16 경계 프레임(다크 안 키오스크 · 다크+하위 large · 초록 헤더 라이트/다크/PDF) — 로고·accent·비활성·스켈레톤·본문 값을 렌더 실측으로 표시
- 포커스·선택·체크 표시 3:1 이상 — 보드 §14 표 C·D (흰·`#F3FFFB`·`#F5F5F5`·초록 면·`#222222`·`#191919`·`#2C2C2C`·`#00321F`)
- 텍스트 4.5:1(큰 글자 3:1) — 보드 §14 표 A·B·E·F. 표는 검수 스크립트가 tokens.css 실측값에서 생성하고 판정은 반올림 전 값
- 테마 블록 역할 목록 일치(다크 = OS 다크 ⊆ 키오스크) · `[data-scale="large"]` 색 선언 0 — §15 스크립트 판정
- 초록 면 위 라벨 = `--on-primary` 단일 — §2.1, 보드 전 컴포넌트
- 보드 값 = tokens.css(`var()`만, HEX 0) — 보드 검수 스크립트가 인라인 스타일의 HEX를 세어 표시
- 서체 Pretendard·Montserrat만 — 둘 다 jsDelivr CDN(`@font-face`)에서 로드한다. 내장(base64)이 아니라 오프라인에서는 시스템 sans로 대체된다. Montserrat은 라틴 서브셋만 로드하므로 한글은 Pretendard로 떨어진다
- 결정마다 근거 주석 — 보드 각 섹션 하단 + 이 문서 [다름] 항목
- 보드 대비표에서 채택 행 미달 0 — 1차 검수 4건(보조 `#616161` · 다크 error-text `#FF615B` · 키오스크 라이트 고정 · `#2C2C2C` 열) + 2차 검수 10건(키오스크 역할 54개 전체·`:root` 명시도 · large 색 제거 · pressed 면 = hover 면 · 로고 4토큰·R-02 파일명 · 헤더 CTA 흰 면·#222222 2중 링·print B · 대형 h1 28·xl 제안 · caption 10 금지 · placeholder #757575+opacity 1 · warning·다크 범위·자간 확인 필요 문서화) 반영. 의도적으로 남긴 미달 행: disabled(면제), "(참고)"·"(금지)"·"(장식)" 행
