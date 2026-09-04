---
name: hand-drawn-doodle-theme
description: 흑백 손그림 선화(Doodle/Line Art) 및 페이퍼로지(Paperlogy) 폰트 기반의 모바일 링크트리 UI 디자인 스킬
---

# 🎨 Hand-Drawn Doodle Theme Guide

본 스킬은 흑백 굵은 선화(Doodle/Line Art) 일러스트와 **페이퍼로지(Paperlogy)** 웹폰트를 조합한 감성 모바일 UI 컴포넌트 개발 지침서입니다.

---

## 1. 디자인 시스템 (Color & Font)

### 🎨 컬러 팔레트
- **Main Line & Text**: `#18181b` (선명한 다크 딥 블랙)
- **Container Background**: `#fafafa` (오프화이트 메인 컨테이너)
- **Body Background**: `#f4f4f5` (차분한 연회색)
- **Sub Text / Secondary BG**: `#52525b` / `#f4f4f5`
- **Highlight Accent**:
  - 알림 뱃지: `#ff4757` (포인트 레드)
  - 모달 뱃지: `#fef08a` (파스텔 옐로우)
- **Shadow**: `box-shadow: 4px 4px 0px #18181b` (스케치 오프셋 그림자)

### 🔤 폰트 지침
- **Font Family**: `'Paperlogy', -apple-system, BlinkMacSystemFont, sans-serif`
- **CDN**: 눈누(Noonnu) 페이퍼로지 400/500/700/800
- **특징**: 손글씨 느낌의 아기자기함과 또렷한 가독성 제공

---

## 2. 주요 예시 코드

### 🔹 1. 손그림 드로잉 링크 카드 (Link Card)
```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer" class="link-card">
  <div class="card-image-wrapper">
    <img src="assets/icon.jpg" alt="아이콘" class="card-image">
  </div>
  <div class="card-text-group">
    <h2 class="card-title">카드 제목</h2>
    <p class="card-subinfo">카드 상세 설명 문구</p>
  </div>
  <div class="card-arrow">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
      <path d="M5 12h14M12 5l7 7-7 7"/>
    </svg>
  </div>
</a>
```

```css
.link-card {
  display: flex;
  align-items: center;
  background-color: #ffffff;
  border: 2.5px solid #18181b;
  border-radius: 22px;
  padding: 14px 18px;
  text-decoration: none;
  color: inherit;
  box-shadow: 4px 4px 0px #18181b;
  transition: all 0.18s cubic-bezier(0.4, 0, 0.2, 1);
}

.link-card:hover {
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0px #18181b;
}

.link-card:active {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0px #18181b;
}
```

### 🔹 2. 알림 종 버튼 & 뱃지 (Notification Bell & Badge)
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

## 3. 새로운 컴포넌트 / 페이지 추가 시 체크리스트

- [ ] **아이콘 일러스트 스타일**: 1:1 비율, 굵은 검은색 외곽선(Bold Black Outline), 흰색 배경의 흑백 손그림(Hand-drawn doodle line art) 유지
- [ ] **테두리 & 그림자**: 모든 카드/버튼 요소에 `border: 2.5px solid #18181b` 및 `box-shadow: 4px 4px 0px #18181b` 적용
- [ ] **터치 애니메이션**: 클릭/터치 시 `translate(2px, 2px)` 및 그림자가 줄어드는 쫄깃한 버튼 감성 구현
- [ ] **폰트 적용**: 요소 추가 시 `Paperlogy` 폰트 패밀리 지정 확인
- [ ] **OG 썸네일 통일성**: SNS 공유 이미지 생성 시 16:9 비율의 흑백 정면 고양이 캐릭터 및 굵은 라인 아트 스타일 적용
