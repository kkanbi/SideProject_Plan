# 🎨 Fairy Garden - UI 프로토타입 준비 문서

## 📋 문서 개요
**작성일**: 2025.11.02  
**목적**: UI 프로토타입 제작 전 필요한 문서 및 작업 정리  
**현재 상태**: PRD 완성 → 런칭 계획 완성 → **UI 프로토타입 준비 단계**

---

## 🔍 현재 문서 상태 점검

### ✅ 완성된 문서
- **PRD v1.0**: 기능 명세, 데이터 모델, 핵심 UX 루프
- **런칭 스케줄**: 14주 개발 일정, 마케팅 전략
- **FAQ & 엣지 케이스**: 예외 처리 시나리오

### ⚠️ 누락된 문서 (프로토타입 제작 전 필수)

1. **와이어프레임 명세서**
2. **비주얼 스타일 가이드**
3. **인터랙션 플로우 차트**
4. **AI 아트 프롬프트 문서**
5. **컴포넌트 라이브러리 정의**
6. **접근성 체크리스트**

---

## 📝 필수 문서 1: 와이어프레임 명세서

### 목적
- 프로토타입 제작의 blueprint
- 화면 간 전환 흐름 명확화
- 개발자-디자이너 간 소통 도구

### 포함 내용

#### 1. 온보딩 화면 (3단계)
```
[화면 1] 앱 소개
├─ 헤더: "Fairy Garden"
├─ 메인 비주얼: 스노우볼 테라리움 일러스트
├─ 카피: "당신의 목표가 요정을 자라게 해요"
├─ 서브 카피: 짧은 설명 2-3줄
└─ 하단: [다음] 버튼 + 페이지 인디케이터 (1/3)

[화면 2] 목표 설정 - 기간
├─ 제목: "몇 일 동안 프로젝트를 진행하실 건가요?"
├─ 선택지: 3개 카드
│  ├─ [15일] - 추천 (빠른 성취)
│  ├─ [30일] - 인기 (균형잡힌)
│  └─ [60일] - 도전 (장기 목표)
└─ 하단: [이전] [다음] 버튼

[화면 3] 목표 설정 - 하루 목표
├─ 제목: "하루에 몇 개의 뽀모도로를 목표로 하시나요?"
├─ 선택지: 4개 카드
│  ├─ [1개] - 부담없이
│  ├─ [2개] - 추천
│  ├─ [3개] - 열심히
│  └─ [4개] - 도전적으로
├─ 미리보기: "30일 동안 60개 달성 목표!"
└─ 하단: [이전] [시작하기] 버튼
```

#### 2. 메인 타이머 화면 (핵심)
```
레이아웃 구조:
┌─────────────────────────────┐
│ [상단 정보 바]              │
│ Lv3 · 42/60 (70%)           │
│ 졸업까지 18개               │
├─────────────────────────────┤
│                             │
│   [스노우볼 테라리움]       │
│   - 배경: 그라데이션 하늘   │
│   - 요정: 중앙 배치         │
│   - 크기: 화면의 50-60%     │
│                             │
├─────────────────────────────┤
│   [타이머 영역]             │
│   ⏱️ 25:00                  │
│   원형 프로그레스 바        │
├─────────────────────────────┤
│   [컨트롤 버튼]             │
│   ▶️ 시작하기               │
│   (또는 ⏸️ 일시정지)        │
├─────────────────────────────┤
│ [하단 네비게이션]           │
│ 📖 도감 | ⚙️ 설정          │
└─────────────────────────────┘

상태별 변화:
- 대기 중: 요정 idle 애니메이션
- 타이머 진행 중: 요정 움직임 + 타이머 감소
- 완료: 파티클 효과 + 성장 포인트 팝업
```

#### 3. 도감 화면
```
레이아웃:
┌─────────────────────────────┐
│ [헤더]                      │
│ 📖 나의 요정 도감           │
│ 3/10 마리 완성              │
├─────────────────────────────┤
│                             │
│ [졸업한 요정 카드 그리드]   │
│                             │
│ ┌───────┐  ┌───────┐        │
│ │ 요정1 │  │ 요정2 │        │
│ │ Lv4   │  │ Lv4   │        │
│ │ 60/60 │  │ 45/45 │        │
│ └───────┘  └───────┘        │
│                             │
│ ┌───────┐  ┌───────┐        │
│ │ 요정3 │  │  ???  │        │
│ │ Lv4   │  │       │        │
│ │ 90/90 │  │ 잠김  │        │
│ └───────┘  └───────┘        │
│                             │
├─────────────────────────────┤
│ [새 프로젝트 시작] 버튼     │
└─────────────────────────────┘

카드 상세 (탭 시 팝업):
- 요정 이미지 (크게)
- 완료일: 2025.01.30
- 최종 레벨: Lv4
- 총 뽀모도로: 60개
- 성공률: 85%
- 총 집중 시간: 25.5시간
```

#### 4. 설정 화면
```
섹션 구분:
┌─────────────────────────────┐
│ [타이머 설정]               │
│ ⏱️ 집중 시간: 25분          │
│ ☕ 휴식 시간: 5분           │
├─────────────────────────────┤
│ [알림 설정]                 │
│ 🔔 알림 받기: ON            │
│ 🔊 사운드: ON               │
├─────────────────────────────┤
│ [앱 설정]                   │
│ 💎 광고 제거 구매 ($2.99)   │
│ 🌐 언어: 한국어             │
├─────────────────────────────┤
│ [위험 영역]                 │
│ 🗑️ 프로젝트 초기화          │
│    (경고 아이콘)            │
├─────────────────────────────┤
│ [정보]                      │
│ 📄 개인정보 처리방침        │
│ 📜 이용약관                 │
│ 📧 문의하기                 │
│ ℹ️ 버전 정보: v1.0.0        │
└─────────────────────────────┘
```

---

## 🎨 필수 문서 2: 비주얼 스타일 가이드

### 색상 팔레트
```
Primary Colors:
━━━━━━━━━━━━━━━━━━━━━━━━━━
🟢 Mint        #A6E3B7  (메인 컬러)
🟢 Mint Dark   #7AA88C  (hover, active)

Secondary Colors:
━━━━━━━━━━━━━━━━━━━━━━━━━━
🔵 Sky Blue    #CDE6F7  (배경, 보조)
🟡 Cream       #FFF9F1  (카드 배경)
🔴 Accent      #ffb7c5  (강조, CTA)
🟡 Gold        #F7E7A9  (성공, 완료)

Neutral Colors:
━━━━━━━━━━━━━━━━━━━━━━━━━━
⚫ Ink         #223     (텍스트)
⚫ Muted       #6b7280  (보조 텍스트)
⚪ Background  #fafaf7  (앱 배경)
```

### 타이포그래피
```
Font Family: Pretendard (or Noto Sans KR)

계층 구조:
━━━━━━━━━━━━━━━━━━━━━━━━━━
H1 - Display      32px / Bold   / 130%  (온보딩 제목)
H2 - Heading      24px / Bold   / 140%  (섹션 제목)
H3 - Subheading   20px / SemiBold / 140%  (카드 제목)
Body - Regular    16px / Regular / 160%  (본문)
Caption - Small   14px / Regular / 150%  (보조 설명)
Label - Tiny      12px / Medium  / 140%  (라벨, 뱃지)

특수 용도:
━━━━━━━━━━━━━━━━━━━━━━━━━━
Timer Display     48px / Bold   / 100%  (타이머 숫자)
Progress Text     14px / SemiBold / 100%  (42/60)
```

### 그림자 & 효과
```
Card Shadow (Elevation 1):
box-shadow: 0 2px 8px rgba(0,0,0,0.08)

Card Shadow (Elevation 2):
box-shadow: 0 4px 16px rgba(0,0,0,0.12)

Modal Shadow:
box-shadow: 0 10px 40px rgba(0,0,0,0.2)

Border Radius:
━━━━━━━━━━━━━━━━━━━━━━━━━━
Button:     8px
Card:       12px
Modal:      16px
Container:  20px
```

### 아이콘 스타일
```
스타일: Line (선형) - 일관성 유지
크기:
- Small:  16x16px (인라인 텍스트)
- Medium: 24x24px (버튼, 네비게이션)
- Large:  32x32px (헤더, 강조)

추천 라이브러리:
- Lucide Icons (무료, 깔끔한 디자인)
- Material Symbols (구글 공식)

필요한 아이콘:
🏠 home, ⏱️ timer, 📖 book, ⚙️ settings,
▶️ play, ⏸️ pause, 🔔 bell, ✅ check,
❌ close, ➕ plus, ℹ️ info, 🗑️ trash
```

### 애니메이션 가이드
```
기본 Timing Function:
ease-in-out: 화면 전환, 모달
ease-out: 버튼 상호작용
spring: 성공 피드백, 레벨업

Duration:
━━━━━━━━━━━━━━━━━━━━━━━━━━
Fast:     150ms  (버튼 hover, 툴팁)
Normal:   300ms  (화면 전환, 페이드)
Slow:     500ms  (모달, 복잡한 애니메이션)
Special: 1000ms+ (레벨업 연출, 파티클)

주요 애니메이션:
━━━━━━━━━━━━━━━━━━━━━━━━━━
1. 타이머 진행 중 요정 움직임
   - Idle breathing 애니메이션 (2초 주기)
   - 좌우 이동 (3초마다 랜덤)
   - 미세한 날개 움직임

2. 레벨업 파티클
   - 화면 중앙에서 사방으로 퍼지는 반짝임
   - 1초 동안 fade out
   - 색상: #FFF7CC (골드)

3. 화면 전환
   - Fade + Slide (300ms)
   - 오른쪽에서 왼쪽으로 슬라이드

4. 버튼 피드백
   - Scale: 1.0 → 0.95 → 1.0 (150ms)
   - 햅틱: light impact
```

---

## 🔄 필수 문서 3: 인터랙션 플로우 차트

### A. 첫 사용자 온보딩 플로우
```
[앱 실행]
    ↓
[스플래시 화면 (2초)]
    ↓
[온보딩 1/3: 앱 소개]
    ↓ [다음]
[온보딩 2/3: 기간 선택]
    ↓ [선택 → 다음]
[온보딩 3/3: 하루 목표 선택]
    ↓ [선택 → 시작하기]
[메인 화면 진입]
    ↓
[알 상태 요정 표시]
    ↓
[튜토리얼 툴팁?]
"▶️ 버튼을 눌러 첫 뽀모도로를 시작하세요!"
```

### B. 뽀모도로 실행 플로우
```
[메인 화면 - 대기]
    ↓ [▶️ 시작 버튼 탭]
[타이머 시작 확인]
    ↓
[타이머 진행 중]
│ ├─ 요정 애니메이션 시작
│ ├─ 타이머 카운트다운
│ └─ [⏸️ 일시정지] 버튼 표시
    ↓
[타이머 완료] (25분 경과)
    ↓
[파티클 효과 연출]
    ↓
[성장 포인트 획득 팝업]
"🎉 25분 집중 완료! +1 포인트"
    ↓ [확인]
[레벨업 체크]
    ├─ 레벨업 조건 충족?
    │   ├─ YES → [레벨업 연출]
    │   │         "✨ Lv2 달성!"
    │   │         ↓
    │   └─ NO  → [메인 화면 복귀]
    └─ 졸업 조건 충족?
        ├─ YES → [졸업 팝업 표시]
        └─ NO  → [메인 화면 복귀]
```

### C. 타이머 중단 시나리오
```
[타이머 진행 중 (예: 15분 경과)]
    ↓
[유저가 앱 종료 or 홈 버튼]
    ↓
[백그라운드 모드]
│ OS 허용 → 타이머 계속
│ OS 차단 → 타이머 일시정지
    ↓
[앱 재시작]
    ↓
[중단된 세션 감지]
    ↓
[복귀 팝업 표시]
"⏱️ 중단된 세션이 있어요"
"15분 남았어요. 이어하시겠어요?"
    ├─ [이어하기] → 타이머 재시작
    └─ [포기하기] → 세션 취소 (기록 안됨)
```

### D. 졸업 플로우
```
[목표 달성 완료]
(예: 60개 뽀모도로 + 30일 경과 + Lv4)
    ↓
[메인 화면에서 자동 감지]
    ↓
[졸업 가능 알림 배너 표시]
"🎓 졸업 준비 완료! 축하해요!"
    ↓ [졸업하기 버튼]
[졸업 연출 시작]
│ 1. 요정이 성숙한 모습으로 변신
│ 2. 스노우볼에서 빛 번쩍
│ 3. 축하 메시지 + 파티클
    ↓
[졸업 완료 팝업]
"🎉 [프로젝트명] 완료!"
"총 60개 뽀모도로, 25시간 집중했어요"
    ↓ [도감에서 보기]
[도감 화면 이동]
    ↓
[새 요정 시작 안내]
"새로운 요정을 시작하시겠어요?"
    ├─ [시작하기] → 온보딩 2단계로
    └─ [나중에] → 메인 화면 (현재 요정 유지)
```

### E. 에러 케이스 플로우
```
1. 알림 권한 거부
[타이머 완료]
    ↓
[앱 내 팝업으로 알림]
"⏰ 25분 완료!"
    ↓
[설정에서 알림 권한 요청 안내]

2. 목표 미달성 (30일 경과, 40/60 달성)
[30일차 자정]
    ↓
[미달성 감지]
    ↓
[안내 팝업]
"😢 목표를 달성하지 못했어요"
"옵션을 선택해주세요"
    ├─ [연장하기 (+7일)] → 프로젝트 연장
    └─ [새로 시작] → 현재 프로젝트 종료

3. 10일 미접속 (잠든 상태)
[앱 실행]
    ↓
[잠든 상태 감지]
    ↓
[메인 화면에 흑백 필터 + 잠든 요정]
    ↓
[안내 팝업]
"😴 10일 동안 안 왔어요"
"요정이 잠들어 있어요"
    ↓ [뽀모도로 1개 완료 시]
[요정 깨어남 연출]
"✨ 요정이 깨어났어요!"
```

---

## 🤖 필수 문서 4: AI 아트 프롬프트 문서

### 작업 시기: Week 7 (12.13-12.19)

### 요정 레벨별 프롬프트 (총 4장)

#### Level 1 - 알
```
Prompt:
"fairy egg inside glass snow globe terrarium, pastel mint color gradient, 
tiny sparkles floating around, soft glow effect, miniature garden background 
with rolling hills, cute kawaii style, 2D game art, children's book illustration, 
warm lighting, dreamy atmosphere, white background, high quality, 4K"

Negative Prompt:
"realistic, 3D render, dark, scary, complex details, cluttered"

Style Reference:
- Animal Crossing
- Genshin Impact (chibi style)
- Monument Valley (색감)

크기: 512x512px
포맷: PNG (투명 배경)
```

#### Level 2 - 유아 요정
```
Prompt:
"tiny baby fairy character just hatched from egg, chibi style, 
pastel mint hair, transparent wings budding, big sparkling eyes, 
sitting pose, kawaii cute expression, inside glass terrarium, 
miniature garden setting, soft gradient sky background, 
warm pastel colors, 2D game sprite, children's illustration style, 
clean lines, white background, high quality"

Negative Prompt:
"adult, realistic, dark colors, scary, weapons, complex clothing"

특징:
- 크기: 알의 1.5배
- 날개: 투명하고 작음
- 표정: 호기심 많은
```

#### Level 3 - 청소년 요정
```
Prompt:
"teenage fairy character, chibi style, pastel mint green hair with flower crown, 
semi-transparent wings (medium size), standing confident pose, 
gentle smile, simple dress with nature motifs, 
inside glass snow globe terrarium, garden with tiny flowers, 
soft lighting, kawaii aesthetic, 2D game art, 
clean illustration style, white background, high quality"

Negative Prompt:
"adult proportions, realistic, dark, complex details, weapons"

특징:
- 크기: 알의 2배
- 날개: 중간 크기, 반투명
- 표정: 자신감 있는
- 복장: 단순한 드레스
```

#### Level 4 - 성인 요정
```
Prompt:
"mature fairy character, chibi style, long flowing pastel mint hair, 
large transparent wings with sparkles, elegant standing pose, 
serene smile, detailed nature-themed dress, holding small magic wand, 
inside glass terrarium garden, lush miniature landscape, 
golden hour lighting, kawaii aesthetic, 2D game art, 
professional illustration, white background, highest quality"

Negative Prompt:
"realistic anatomy, dark theme, scary, overly complex, anime style"

특징:
- 크기: 알의 3배
- 날개: 크고 화려함
- 표정: 성숙하고 평화로운
- 복장: 디테일 있는 드레스
- 소품: 작은 지팡이 or 꽃
```

### 배경 - 스노우볼 테라리움 (1장)
```
Prompt:
"glass snow globe terrarium background, miniature garden landscape inside, 
soft gradient sky from pale blue to mint green, rolling hills with tiny grass, 
small wildflowers, gentle sparkles in air, dreamy atmosphere, 
kawaii aesthetic, 2D game background art, children's book illustration style, 
warm pastel colors, clean design, white border, high quality, 4K"

Negative Prompt:
"realistic, complex details, dark, cluttered, busy composition"

크기: 1024x1024px (정사각형)
포맷: PNG
용도: 메인 화면 배경
```

### 졸업 연출용 이미지 (1장)
```
Prompt:
"graduation celebration scene, adult fairy character with diploma, 
confetti and sparkles, golden particles, achievement badge, 
inside glass terrarium, magical glow effect, kawaii celebration, 
2D game art, festive atmosphere, warm colors, 
white background, high quality"

크기: 512x512px
용도: 졸업 팝업
```

### AI 아트 제작 Tips
```
추천 툴:
1. Midjourney (유료, 최고 품질)
   - 월 $10 구독
   - --niji 모드 사용 (애니메이션 스타일)

2. DALL-E 3 (ChatGPT Plus)
   - 월 $20
   - 텍스트 이해도 높음

3. Stable Diffusion (무료)
   - ComfyUI or Automatic1111
   - 학습 필요

제작 프로세스:
1. 프롬프트 입력 → 4개 결과 생성
2. 마음에 드는 것 선택 → Upscale
3. Photoshop에서 미세 조정
4. 배경 제거 (remove.bg)
5. PNG 최적화 (TinyPNG)

일관성 유지:
- 같은 프롬프트 템플릿 사용
- Seed 번호 고정 (가능한 경우)
- 색상 팔레트 명시
- 스타일 키워드 일관성
```

---

## 🧩 필수 문서 5: 컴포넌트 라이브러리

### 재사용 가능한 UI 컴포넌트 정의

#### 1. Buttons
```
Primary Button
━━━━━━━━━━━━━━━━━━
색상: #A6E3B7 (배경), white (텍스트)
크기: Height 48px, Padding 16px 24px
모서리: border-radius 8px
상태:
  - Normal: 기본
  - Hover: #7AA88C (어둡게)
  - Active: Scale 0.95
  - Disabled: opacity 0.4

예시: [시작하기] [졸업하기]

---

Secondary Button
━━━━━━━━━━━━━━━━━━
색상: transparent (배경), #A6E3B7 (테두리), #7AA88C (텍스트)
크기: Height 48px, Padding 16px 24px
테두리: 2px solid
모서리: border-radius 8px

예시: [취소] [나중에]

---

Icon Button
━━━━━━━━━━━━━━━━━━
크기: 40x40px (터치 영역 44x44px)
아이콘: 24x24px
배경: transparent
상태:
  - Normal: #6b7280
  - Hover: #A6E3B7 배경
  - Active: Scale 0.9

예시: ⚙️ 설정, 📖 도감
```

#### 2. Cards
```
Basic Card
━━━━━━━━━━━━━━━━━━
배경: white
패딩: 16px
모서리: border-radius 12px
그림자: 0 2px 8px rgba(0,0,0,0.08)
테두리: 없음 (or 1px #e5e7eb)

---

Project Card (메인 화면 상단)
━━━━━━━━━━━━━━━━━━
┌────────────────────┐
│ Lv3 · 42/60 (70%)  │
│ 졸업까지 18개      │
└────────────────────┘
배경: linear-gradient(#A6E3B7, #7AA88C)
텍스트: white
패딩: 12px 16px
모서리: border-radius 12px

---

Gallery Card (도감)
━━━━━━━━━━━━━━━━━━
┌────────────┐
│   [이미지] │
│            │
│  요정 1    │
│  Lv4       │
│  60/60     │
│  2025.01.30│
└────────────┘
크기: 160x200px
배경: white
그림자: 0 4px 12px rgba(0,0,0,0.1)
hover: translateY(-4px)
```

#### 3. Progress Indicators
```
Level Progress Bar
━━━━━━━━━━━━━━━━━━
[████████░░] 42/60 (70%)

높이: 8px
배경: #e5e7eb
진행: #A6E3B7
모서리: border-radius 4px
애니메이션: width 0.3s ease

---

Circular Timer
━━━━━━━━━━━━━━━━━━
    ⏱️
   25:00

크기: 200x200px
선 두께: 8px
색상: #A6E3B7 (진행), #e5e7eb (배경)
중앙 텍스트: 48px Bold
```

#### 4. Modals & Popups
```
Alert Modal (일반 알림)
━━━━━━━━━━━━━━━━━━
┌─────────────────┐
│   🎉 제목       │
│                 │
│  내용 텍스트    │
│                 │
│    [확인]       │
└─────────────────┘
크기: 300x200px (가변)
배경: white
모서리: border-radius 16px
오버레이: rgba(0,0,0,0.5)

---

Confirm Modal (확인 필요)
━━━━━━━━━━━━━━━━━━
┌─────────────────┐
│   ⚠️ 경고       │
│                 │
│  정말 삭제할까요?│
│                 │
│  [취소] [확인]  │
└─────────────────┘

---

Level Up Modal (레벨업)
━━━━━━━━━━━━━━━━━━
┌─────────────────┐
│   ✨ Level Up!  │
│                 │
│  [요정 이미지]  │
│                 │
│   Lv2 달성!     │
│                 │
│    [확인]       │
└─────────────────┘
애니메이션: scale + fade in
```

#### 5. Input Fields
```
Number Picker
━━━━━━━━━━━━━━━━━━
  [−]  2  [+]

버튼: 32x32px
숫자: 24px Bold
범위: 1-4
간격: 8px

---

Segmented Control (기간 선택)
━━━━━━━━━━━━━━━━━━
┌────┬────┬────┐
│ 15일│30일│60일│
└────┴────┴────┘
선택: #A6E3B7 배경
미선택: transparent
전체 테두리: 2px #e5e7eb
```

---

## ♿ 필수 문서 6: 접근성 체크리스트

### 색상 대비
```
✅ WCAG AA 기준 준수
━━━━━━━━━━━━━━━━━━
텍스트 vs 배경: 최소 4.5:1
큰 텍스트 (18px+): 최소 3:1

체크 항목:
□ #223 (텍스트) vs #fafaf7 (배경)
□ white (텍스트) vs #A6E3B7 (버튼)
□ #6b7280 (보조 텍스트) vs #fafaf7

도구:
- WebAIM Contrast Checker
- Figma Contrast Plugin
```

### 터치 영역
```
✅ iOS HIG / Android Material 준수
━━━━━━━━━━━━━━━━━━
최소 터치 영역: 44x44px (iOS), 48x48px (Android)

체크 항목:
□ 버튼 최소 높이: 48px
□ 버튼 간 간격: 최소 8px
□ 아이콘 버튼: 44x44px
□ 카드: 터치 가능 영역 충분

실수하기 쉬운 곳:
- 설정 스위치 (너무 작게)
- 네비게이션 아이콘
- 카드 내부 버튼
```

### 텍스트 크기
```
✅ 가독성 확보
━━━━━━━━━━━━━━━━━━
최소 텍스트: 12px (라벨만)
권장 본문: 16px
제목: 20px+

체크 항목:
□ Dynamic Type 지원 (iOS)
□ Font Scale 지원 (Android)
□ 2줄 이상 넘어가는 텍스트 처리
```

### 피드백
```
✅ 사용자에게 명확한 피드백
━━━━━━━━━━━━━━━━━━
햅틱 피드백:
□ 버튼 탭: light impact
□ 완료: medium impact
□ 에러: notification (heavy)

사운드 피드백:
□ 타이머 완료: 부드러운 종소리
□ 레벨업: 성공 사운드
□ 에러: 짧은 경고음

비주얼 피드백:
□ 버튼 눌림: Scale 효과
□ 로딩: Spinner 또는 프로그레스
□ 성공: 체크마크 + 파티클
□ 에러: 빨간색 shake 애니메이션
```

### 상태 표시
```
✅ 현재 상태 명확히 표시
━━━━━━━━━━━━━━━━━━
□ 타이머 진행 중 vs 대기 중
□ 버튼 활성/비활성 구분
□ 로딩 상태 표시
□ 에러 메시지 명확
□ 성공 메시지 명확
```

---

## 🎯 작업 우선순위 및 일정

### Phase 0: 프로토타입 준비 (3-5일)

#### Day 1: 와이어프레임 (최우선)
```
시간 배분:
━━━━━━━━━━━━━━━━━━
오전 (3시간):
- 온보딩 3단계 레이아웃 스케치
- 메인 타이머 화면 레이아웃

오후 (3시간):
- 도감, 설정 화면 레이아웃
- 팝업/모달 디자인

저녁 (2시간):
- 화면 간 전환 흐름도 작성
- 누락된 화면 체크

결과물:
✅ 와이어프레임 5개 화면 완성
✅ 화면 전환 플로우 차트
```

#### Day 2: 스타일 가이드
```
시간 배분:
━━━━━━━━━━━━━━━━━━
오전 (2시간):
- 색상 팔레트 확정
- 타이포그래피 정의

오후 (3시간):
- 컴포넌트 라이브러리 정의
- 버튼, 카드, 모달 스타일

저녁 (2시간):
- 애니메이션 가이드 작성
- 아이콘 스타일 결정

결과물:
✅ 비주얼 스타일 가이드 완성
✅ 컴포넌트 정의서
```

#### Day 3: 인터랙션 & 플로우
```
시간 배분:
━━━━━━━━━━━━━━━━━━
오전 (3시간):
- 주요 사용자 시나리오 작성
- 인터랙션 플로우 차트

오후 (2시간):
- 에러 케이스 플로우
- 엣지 케이스 처리 방안

저녁 (2시간):
- 접근성 체크리스트 작성
- 피드백 가이드

결과물:
✅ 인터랙션 플로우 차트
✅ 접근성 체크리스트
```

#### Day 4: AI 아트 준비
```
시간 배분:
━━━━━━━━━━━━━━━━━━
오전 (2시간):
- AI 아트 프롬프트 초안 작성
- 레퍼런스 이미지 수집

오후 (2시간):
- 임시 플레이스홀더 에셋 준비
- 이모지 or 단순 도형

저녁 (1시간):
- Midjourney 계정 준비
- 프롬프트 테스트 (선택)

결과물:
✅ AI 아트 프롬프트 문서
✅ 임시 에셋 (🥚🐣🐥🦋)
```

#### Day 5: 최종 검토
```
시간 배분:
━━━━━━━━━━━━━━━━━━
오전 (2시간):
- 모든 문서 통합 검토
- 누락된 부분 체크

오후 (2시간):
- Figma 프로젝트 세팅
- 컴포넌트 라이브러리 구축 시작

저녁 (1시간):
- 다음 단계 계획 수립

결과물:
✅ 모든 준비 문서 완성
✅ Figma 프로젝트 세팅 완료
```

---

## 🎨 다음 단계: UI 프로토타입 제작

### Figma 프로토타입 제작 (3-5일)

#### 준비 사항
```
1. Figma 계정 (무료 플랜으로 가능)
2. 플러그인 설치:
   - Unsplash (무료 이미지)
   - Iconify (아이콘)
   - Content Reel (더미 텍스트)
3. 프로젝트 구조:
   - Pages: 와이어프레임 / 디자인 / 프로토타입
   - Frames: iPhone 14 Pro (393x852)
```

#### 제작 순서
```
1. 컴포넌트 먼저 만들기
   └─ Button, Card, Modal 등

2. 주요 화면 5개 제작
   ├─ 온보딩 (3화면을 1개로 대표)
   ├─ 메인 타이머
   ├─ 도감
   ├─ 설정
   └─ 주요 팝업 3개

3. 인터랙티브 프로토타입 연결
   └─ 주요 플로우만 (과도하지 않게)

4. 피드백 받기
   └─ 지인 2-3명에게 공유
```

---

## ✅ 최종 체크리스트

### 프로토타입 시작 전 확인
```
문서 준비:
□ 와이어프레임 5개 화면 완성
□ 비주얼 스타일 가이드 작성
□ 컴포넌트 라이브러리 정의
□ 인터랙션 플로우 차트 작성
□ AI 아트 프롬프트 문서 작성
□ 접근성 체크리스트 작성

에셋 준비:
□ 임시 에셋 준비 (이모지)
□ 아이콘 라이브러리 선택
□ 폰트 다운로드 (Pretendard)

툴 준비:
□ Figma 계정 생성
□ 필요한 플러그인 설치
□ 프로젝트 구조 세팅
```

### 프로토타입 완성 후 확인
```
기능 체크:
□ 모든 주요 화면 제작 완료
□ 화면 간 전환 연결
□ 주요 인터랙션 구현
□ 터치 영역 적절

품질 체크:
□ 색상 대비 확인 (WCAG AA)
□ 텍스트 크기 적절
□ 버튼 크기 44x44px 이상
□ 일관된 스타일 적용

공유 체크:
□ Figma 링크 생성
□ 주석 추가 (설명 필요한 부분)
□ 피드백 받을 사람 선정
```

---

## 📚 참고 자료

### 디자인 레퍼런스
```
1. Forest (포커스 앱 벤치마크)
   - 타이머 UI
   - 성장 시스템 연출

2. Animal Crossing Pocket Camp
   - 귀여운 컬렉션 UI
   - 도감 레이아웃

3. Genshin Impact
   - 캐릭터 성장 UI
   - 레벨업 연출

4. Duolingo
   - 온보딩 플로우
   - 진행도 표시
```

### 학습 자료
```
Figma 기초:
- Figma 공식 튜토리얼 (2시간)
- "Figma in 40 Minutes" (YouTube)

컴포넌트 시스템:
- "Design Systems in Figma" (YouTube)

프로토타이핑:
- "Interactive Prototypes in Figma" (YouTube)
```

### 유용한 링크
```
색상 도구:
- Coolors.co (팔레트 생성)
- Contrast Checker (대비 확인)

아이콘:
- Lucide Icons
- Material Symbols

폰트:
- Google Fonts (Pretendard)
- Font Squirrel (무료 폰트)

AI 아트:
- Midjourney.com
- OpenAI DALL-E 3
```

---

## 🎯 요약: 지금 해야 할 일

### 즉시 시작 가능한 작업 (우선순위 순)

1. **와이어프레임 스케치** (Day 1)
   - 종이에 손으로 그려도 OK
   - 5개 핵심 화면 레이아웃

2. **스타일 가이드 작성** (Day 2)
   - 색상, 폰트, 버튼 스타일

3. **Figma 프로젝트 세팅** (Day 3)
   - 무료 계정으로 시작
   - 컴포넌트 라이브러리 구축

4. **주요 화면 디자인** (Day 4-5)
   - 메인 타이머 화면부터
   - 임시 에셋 사용

5. **프로토타입 연결** (Day 5)
   - 클릭 가능하게 만들기
   - 지인에게 피드백 요청

---

**다음 작업을 도와드릴까요?**
1. 와이어프레임 템플릿 제공
2. Figma 컴포넌트 구조 제안
3. AI 아트 프롬프트 개선
4. 특정 화면 상세 레이아웃 작성
