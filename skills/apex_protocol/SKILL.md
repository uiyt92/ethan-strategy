---
name: APEX Protocol
description: The definitive standard for creating high-converting, premium landing pages. Combines persuasive copywriting, authority design, psychological UX triggers, and mobile optimization.
version: 1.0.0
---

# APEX Protocol (에이펙스 프로토콜)
> **"최상위 포식자의 랜딩 페이지 제작 표준"**

---

## 1. COPYWRITING (설득의 글쓰기)

### 1.1. Frame Control Tone (프레임 장악 어조)
- ❌ "~하시면 좋습니다", "~해주세요" (청유형/요청형)
- ✅ "**~해라**", "**~하지 마라**", "**~이다**" (명령형/단정형)
- **Rule**: 독자가 "이 사람 말 따라야겠다"고 느끼게 하라.

### 1.2. Psychological Sequence (심리 시퀀스)
콘텐츠 배치 순서는 반드시 다음을 따른다:
1.  **Desire (욕망 자극)**: "이런 삶을 원하지 않는가?"
2.  **Crisis (위기 인식)**: "지금 이대로면 이렇게 된다"
3.  **Solution (해결책 제시)**: "우리가 해결해준다"
4.  **Proof (증거)**: 후기, 숫자, 권위
5.  **Action (행동 촉구)**: CTA

### 1.3. Poetic Line Breaks (시적 줄바꿈)
모바일에서 텍스트가 "벽돌"처럼 보이면 안 된다. 의미 단위로 끊어라.
```html
<h1>당신이 원하는<br class="md:hidden">
    여자는 왜<br class="md:hidden">
    매번 실패할까요?</h1>
```
- `<br class="md:hidden">`: 모바일에서만 줄바꿈
- `<br class="hidden md:inline">`: 데스크탑에서만 줄바꿈

---

## 2. DESIGN (권위적 디자인)

### 2.1. Color Palette (컬러 팔레트)
| Role | Color | Code/Gradient |
|------|-------|---------------|
| **Base** | Deep Black | `#050505`, `#0f0f0f` |
| **Accent (Gold)** | Metallic Foil | `linear-gradient(to right, #bf953f, #fcf6ba, #b38728, #fbf5b7, #aa771c)` |
| **Danger/Urgency** | Blood Red | `#ef4444`, `#dc2626` |
| **Crisis Section** | Reddish Black | `from-[#1a0505] via-[#0f0f0f] to-black` |
| **Solution Section** | Deep Slate | `#020617` |

### 2.2. Texture Rules (질감 규칙)
- **Gold 텍스트**: 반드시 5단계 Foil 그라데이션 적용 (단순 노란색 금지)
- **Glass 효과**: `backdrop-blur`, `bg-white/5`, `border-white/10` 조합
- **Red Glow**: 위기감 강조 시 `bg-red-900/10 mix-blend-overlay` 사용

### 2.3. Section Mood Control (섹션 분위기 제어)
- **Problem/Failure**: 어둡고 붉은 톤 → 불안감 조성
- **Guide/Solution**: 차분한 딥 슬레이트 → 신뢰감 형성
- **CTA**: Gold 배경 버튼 → 보상/지위 암시

---

## 3. UX TRIGGERS (심리적 장치)

### 3.1. Urgency (긴급성)
```html
<span class="urgency-badge bg-red-600 text-white px-4 py-2 rounded-full animate-pulse">
    <i class="fa-solid fa-fire mr-2"></i>마감 D-7
</span>
```
- 깜빡이는 배지로 즉각 행동 유도
- "잔여 석 3석", "오늘 마감" 등 구체적 숫자 사용

### 3.2. Social Proof (사회적 증명)
- **숫자는 크게**: `1,000+`, `300+` 등 통계는 눈에 띄게
- **모바일 중앙 정렬**: 통계 카드는 `flex-col items-center text-center`
- **후기 시퀀스**: Desire → Abundance → Emotion → Logic → Transformation

### 3.3. Friction Zero (저항 제거)
- **Q&A**: 아코디언(`<details>`)으로 접어두기
- **터치 영역**: 모든 버튼 최소 44x44px
- **CTA 위치**: 스크롤 없이 보이는 곳 + 페이지 끝

---

## 4. MOBILE (모바일 최적화)

### 4.1. Typography
- `word-break: keep-all` (단어 끊김 방지)
- 본문 최소 `text-base` (16px)
- 헤드라인: `text-2xl md:text-4xl lg:text-5xl`

### 4.2. Layout
- Grid: `grid-cols-1 md:grid-cols-2 lg:grid-cols-4`
- 패딩: `px-4` (모바일) → `md:px-8` (데스크탑)

### 4.3. Carousel (캐러셀 모바일 대응)
> ⚠️ **경고**: PC에서 멋져 보이는 캐러셀은 모바일에서 불편할 수 있다.

**문제점**:
- 버튼(좌/우 화살표)이 터치하기 어려움
- 이미지가 잘리거나 너무 작게 보임
- 스와이프 제스처가 스크롤과 충돌

**해결책**:
1.  **Swipe 우선**: 모바일에서는 버튼보다 **터치 스와이프**가 자연스럽다. JS에 터치 이벤트 지원 필수.
2.  **이미지 풀뷰**: 모바일에서는 이미지 높이를 줄이고(`h-[400px] md:h-[600px]`), 패딩을 넉넉히(`p-4`).
3.  **Dot 인디케이터**: 현재 위치를 알려주는 점(Dots)은 모바일에서 필수. 버튼은 숨겨도 됨.
4.  **대안 고려**: 모바일에서는 캐러셀 대신 **세로 스택(Stack)**으로 모두 보여주는 것도 방법.

**Code Example**:
```html
<!-- 모바일: 버튼 숨김, 스와이프 유도 -->
<button class="hidden md:flex ...">◀</button>
<button class="hidden md:flex ...">▶</button>

<!-- 모바일: 높이 축소 -->
<div class="h-[400px] md:h-[600px] ...">
    <img class="object-contain p-4 ...">
</div>
```

---

## 5. PRE-FLIGHT CHECKLIST (배포 전 점검)

- [ ] **어조**: 청유형이 아닌 명령/단정형인가?
- [ ] **시퀀스**: Desire → Crisis → Solution → Proof → Action 순서인가?
- [ ] **Gold**: 5단계 Foil 그라데이션이 적용되었는가?
- [ ] **배경 분리**: 섹션마다 분위기가 다른가?
- [ ] **줄바꿈**: 모바일에서 "시"처럼 읽히는가?
- [ ] **숫자**: 통계가 중앙 정렬되고 눈에 띄는가?
- [ ] **터치**: 버튼이 44px 이상인가?
- [ ] **긴급성**: Urgency 배지가 있는가?
- [ ] **후기**: 설득 시퀀스대로 배치되었는가?
- [ ] **CTA**: 스크롤 없이 보이고, 페이지 끝에도 있는가?

---
*APEX Protocol v1.0 | Created for Ethan Strategy*
