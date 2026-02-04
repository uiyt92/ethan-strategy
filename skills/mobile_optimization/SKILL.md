---
name: Mobile Optimization Standard
description: A comprehensive guide and checklist for ensuring top-tier mobile user experience in web pages.
version: 1.0.0
---

# Mobile Optimization Standard (모바일 최적화 표준)

## 1. Core Principles (핵심 원칙)
> **"Mobile is not an afterthought, it is the primary experience."**
> (모바일은 나중에 고려하는 것이 아니라, 가장 먼저 설계되어야 하는 경험입니다.)

1.  **Readable (가독성)**: 작은 화면에서도 눈이 편안해야 한다.
2.  **Touchable (터치 친화성)**: 손가락으로 누르기 쉬워야 한다.
3.  **Fast (속도)**: 데이터 환경이 좋지 않아도 빠르게 로딩되어야 한다.
4.  **Flow (흐름)**: 스크롤 흐름이 끊기지 않고 자연스러워야 한다.

---

## 2. Text Optimization (텍스트 최적화)

### 2.1. Word Breaking (단어 줄바꿈)
한글 콘텐츠에서 단어 중간이 끊기는 것(예: "안녕하\n세요")은 가독성을 크게 떨어뜨립니다.
- **Rule**: Body 또는 텍스트 컨테이너에 `word-break: keep-all` 적용.
- **Code**:
  ```css
  body { word-break: keep-all; }
  /* Tailwind */
  <p class="break-keep">...</p>
  ```

### 2.2. Poetic Line Breaks (감성적 줄바꿈)
데스크탑의 긴 호흡 문장은 모바일에서 벽돌처럼 보일 수 있습니다. 의미 단위로 의도적인 줄바꿈을 시도하세요.
- **Rule**: `<br class="md:hidden">`을 사용하여 모바일에서만 줄바꿈 적용.
- **Example**:
  ```html
  <h1 class="text-4xl md:text-6xl">
      당신이 원하는<br class="md:hidden">
      여자는 왜<br class="md:hidden">
      <span class="gold-gradient">매번 실패할까요?</span>
  </h1>
  ```

### 2.3. Responsive Typography (반응형 폰트)
- **Rule**: `text-base` (16px) 이상을 기본으로 하되, 헤드라인은 화면 폭에 비례하게 조정.
- **Scale**: `text-2xl md:text-4xl lg:text-5xl`

---

## 3. Layout & Spacing (레이아웃 및 여백)

### 3.1. Grid to Stack
- **Rule**: 데스크탑의 Grid/Flex `row` 레이아웃은 모바일에서 필연적으로 `col` (세로 쌓기)로 변환되어야 합니다.
- **Code**:
  ```html
  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Cards will stack on mobile -->
  </div>
  ```

### 3.2. Padding Clean-up
모바일에서 데스크탑만큼의 과도한 좌우 패딩은 콘텐츠 영역을 좁게 만듭니다.
- **Rule**: `px-4` or `px-6` for Mobile, `md:px-12` or container centered for Desktop.
- **Safe Zone**: 콘텐츠가 화면 가장자리에 딱 붙지 않도록 최소한의 여백(`px-4`)은 항상 유지하세요.

### 3.3. Center Alignment (중앙 정렬)
모바일에서는 시선이 중앙에 집중됩니다. 특히 짧은 문구나 통계, 아이콘은 중앙 정렬이 훨씬 안정적입니다.
- **Check**: 통계 숫자, 아이콘, 짧은 제목이 왼쪽으로 치우치지 않았는지 확인.

---

## 4. Interaction (인터랙션)

### 4.1. Touch Targets
- **Rule**: 모든 클릭 가능한 요소(버튼, 링크)는 최소 **44x44px** 이상의 터치 영역을 가져야 합니다.
- **Tip**: 패딩을 넉넉하게 주어 터치 미스를 방지하세요. (`p-3`, `p-4`)

### 4.2. Hover States
- **Warning**: 모바일에는 `hover`가 없습니다. `hover`에 중요한 정보를 숨기지 마세요.
- **Alternative**: 중요한 정보는 항상 보이게 하거나(`block`), 클릭(`active/focus`)으로 동작하게 하세요.

---

## 5. Media (이미지 및 비디오)

### 5.1. Object Fits
- **Rule**: 이미지 비율이 깨지거나 잘리지 않도록 `object-fit: cover` 또는 `contain`을 의도에 맞게 명시하세요.
- **Carousel**: 캐러셀 이미지는 모바일에서 전체가 잘 보이도록 `object-contain`과 적절한 패딩(`p-4`)을 사용하세요.

---

## 6. Pre-flight Checklist (배포 전 체크리스트)

- [ ] **단어 끊김**: 텍스트가 부자연스럽게 잘리는 곳이 없는가? (`keep-all`)
- [ ] **가독성**: 폰트 크기가 너무 작거나(14px 미만) 줄 간격이 너무 좁지 않은가?
- [ ] **줄바꿈**: 헤드라인이 의미 단위로 적절히 끊기는가? (`br` 태그 확인)
- [ ] **숨겨진 요소**: 가로 스크롤이 발생하거나 화면 밖으로 튀어나간 요소는 없는가? (`overflow-hidden`)
- [ ] **터치 영역**: 버튼이 너무 작거나 서로 붙어있지 않은가?
- [ ] **이미지**: 주요 이미지가 잘리거나 얼굴이 가려지지 않는가?
- [ ] **정렬**: 통계나 주요 포인트가 모바일에서 중앙 정렬되어 안정감을 주는가?

---
*Created by Antigravity Agent for Ethan Strategy Project.*
