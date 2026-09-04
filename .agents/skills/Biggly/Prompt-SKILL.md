---
name: Biggly-2
description: 링크 모음 페이지의 흑백 굵은 선화 및 브랜드 디자인 시스템, 컬러 팔레트, 폰트 지침, 컴포넌트 코드 및 가이드라인
---

# Biggly 디자인 시스템 & 컴포넌트 가이드

## 1. 디자인 콘셉트 & 주요 컬러 팔레트

Biggly 브랜드의 디자인 콘셉트는 **흑백 굵은 선화(Doodle Line Art)**와 **아기자기한 감성 손글씨 폰트(Paperlogy)**의 조화입니다.

```css
:root {
  /* Main Brand Colors */
  --color-main-line: #18181b;       /* 선명한 흑백 메인 테두리 & 텍스트 */
  --color-bg-container: #fafafa;    /* 모바일 카드 메인 배경 */
  --color-bg-body: #f4f4f5;         /* 메인 웹 페이지 바디 배경 */
  --color-bg-card: #ffffff;         /* 링크 카드/모달 화이트 배경 */
  --color-text-sub: #52525b;        /* 서브 텍스트 & 부가 설명 정보 */
  --color-text-muted: #71717a;      /* 보조 카드 정보 텍스트 */

  /* Point Accent Colors */
  --color-accent-red: #ff4757;      /* 카톡 스타일 알림 뱃지 포인트 레드 */
  --color-accent-yellow: #fef08a;   /* 모달 팝업 아이콘 뱃지 파스텔 노랑 */
  --color-overlay-dim: rgba(0, 0, 0, 0.55); /* 모달 팝업 어두운 딤 배경 */

  /* Structural Dimensions & Shadows */
  --border-thick-main: 2.5px solid var(--color-main-line);
  --border-radius-card: 22px;
  --border-radius-modal: 26px;
  --shadow-doodle: 4px 4px 0px var(--color-main-line);
  --shadow-doodle-hover: 6px 6px 0px var(--color-main-line);
  --shadow-doodle-active: 2px 2px 0px var(--color-main-line);
}
```

---

## 2. 폰트 및 타이포그래피 지침

모든 텍스트는 **페이퍼로지(Paperlogy)** 웹폰트를 기본으로 사용합니다.

| 용도 / 요소 | Font Family | Weight (굵기) | Font Size | 비고 |
| :--- | :--- | :---: | :---: | :--- |
| **페이지 프로필 이름** | `'Paperlogy', sans-serif` | 800 (ExtraBold) | 26px | 메인 프로필 제목 (`.profile-name`) |
| **카드 제목** | `'Paperlogy', sans-serif` | 700 (Bold) | 17px | 링크 카드 메인 라벨 (`.card-title`) |
| **모달 팝업 타이틀** | `'Paperlogy', sans-serif` | 800 (ExtraBold) | 18px | 팝업 헤더 제목 (`.modal-title`) |
| **프로필 한줄 소개 / 소식 문구** | `'Paperlogy', sans-serif` | 500 (Medium) | 15px | 프로필 뱃지 및 모달 본문 텍스트 |
| **카드 부가 정보 / 설명글** | `'Paperlogy', sans-serif` | 500 (Medium) | 13px | 링크 카드 보조 설명 문구 (`.card-subinfo`) |
| **푸터 카피라이트** | `'Paperlogy', sans-serif` | 500 (Medium) | 13px | 하단 카피라이트 (`.footer`) |

---

## 3. 주요 예시 코드(Key Component Examples)

### 🔹 1. 손그림 라인 아트 링크 카드 (Link Card)
```html
<a href="https://byeoldomi.tistory.com/" target="_blank" rel="noopener noreferrer" class="link-card">
  <div class="card-image-wrapper">
    <img src="assets/blog.jpg" alt="티스토리 블로그 대표 이미지" class="card-image">
  </div>
  <div class="card-text-group">
    <h2 class="card-title">티스토리 블로그</h2>
    <p class="card-subinfo">개발 스토리 읽어보기</p>
  </div>
  <div class="card-arrow">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
      <path d="M5 12h14M12 5l7 7-7 7"/>
    </svg>
  </div>
</a>
```

```css
.link-card {
  display: flex;
  align-items: center;
  background-color: var(--color-bg-card);
  border: var(--border-thick-main);
  border-radius: var(--border-radius-card);
  padding: 14px 18px;
  text-decoration: none;
  color: inherit;
  box-shadow: var(--shadow-doodle);
  transition: all 0.18s cubic-bezier(0.4, 0, 0.2, 1);
}

.link-card:hover {
  transform: translate(-2px, -2px);
  box-shadow: var(--shadow-doodle-hover);
}

.link-card:active {
  transform: translate(2px, 2px);
  box-shadow: var(--shadow-doodle-active);
}
```

### 🔹 2. 종 모양 알림 버튼 & 카톡 스타일 숫자 뱃지
```html
<button id="notifBtn" class="notification-btn" aria-label="최신 소식 알림">
  <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
    <path d="M18 8A6 6 0 0 0 6 8c0 7-3 9-3 9h18s-3-2-3-9"></path>
    <path d="M13.73 21a2 2 0 0 1-3.46 0"></path>
  </svg>
  <span class="notif-badge">1</span>
</button>
```

---

## 4. 신규 컴포넌트/페이지 구현 체크리스트

- [ ] **배경 시인성 & 컬러 토큰**: `:root`에 정의된 CSS 변수 토큰(`--color-main-line`, `--color-bg-container`)을 참조하고 배경과 대비가 명확한지 확인합니다.
- [ ] **모서리 곡률 & 선 굵기**: 카드 요소는 `22px` 곡률과 `2.5px solid #18181b` 굵은 테두리를 유지합니다.
- [ ] **오프셋 스케치 그림자 & 호버 애니메이션**:
  - 기본 상태: `box-shadow: 4px 4px 0px #18181b`
  - 호버 시: `translate(-2px, -2px)` 및 `box-shadow: 6px 6px 0px #18181b`
  - 액티브 시: `translate(2px, 2px)` 및 `box-shadow: 2px 2px 0px #18181b`
- [ ] **모바일 래퍼 규격**: 모바일 전용 컨테이너(`max-width: 440px`, `min-height: 100vh`) 레이아웃 기준 적용 여부를 확인합니다.
- [ ] **이미지 일러스트 스타일**: 대표 아이콘(1:1) 및 OG 미리보기 이미지(16:9) 제작 시 흑백 굵은 선화 손그림 스타일 톤앤매너를 유지합니다.
