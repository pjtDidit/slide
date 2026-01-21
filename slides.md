---
title: DidIt 중간발표 (M1)
download: true
theme: academic
highlighter: shiki
lineNumbers: false
---

<!-- 1) 표지 -->
<div style="display:flex; gap:20px; align-items:center;">
  <img src="/logo.webp" alt="DidIt" style="width:92px; height:92px; border-radius:20px; background:#fff;" />
  <div>
    <h1 style="margin:0;">DidIt</h1>
    <p style="margin:6px 0 0; opacity:.8;">중간발표</p>

  </div>
</div>

---
layout: index
---

<h1>이번 발표에서 보여줄 것</h1>

- System Architecture
- FrontEnd Tech Stack
- FrontEnd Directory Structure
- Design Concepts
- Backend Tech Stack
- DataBase ERD
- Milestones Roadmap

---
layout: figure
figureUrl: "/architecture.svg"
figureCaption: "FE(React) → BE(Spring) → Redis(Event) / MySQL(SoT) / Elasticsearch(Search) / OpenVidu(미팅)"
---

<!-- 3) 아키텍처 -->
# System Architecture

<!-- 4) FE -->
---
layout: fact
---


# FrontEnd Tech Stack

<div class="stack-grid">
  <div class="stack-card"><div class="k">Build</div><div class="v">Vite</div><div class="t">최신</div></div>
  <div class="stack-card"><div class="k">Framework</div><div class="v">React</div><div class="t">18+</div></div>
  <div class="stack-card"><div class="k">Language</div><div class="v">JavaScript</div><div class="t">ES6+</div></div>

  <div class="stack-card"><div class="k">Styling</div><div class="v">Tailwind CSS</div><div class="t">4.1.x</div></div>
  <div class="stack-card"><div class="k">State</div><div class="v">Zustand</div><div class="t">최신</div></div>
  <div class="stack-card"><div class="k">Routing</div><div class="v">React Router</div><div class="t">최신</div></div>

  <div class="stack-card"><div class="k">Icons</div><div class="v">Lucide React</div><div class="t">최신</div></div>
</div>



---
layout: fact
---

# FrontEnd Directory Structure

```txt
src/
├── api/                  # 백엔드 API 호출 함수 (axios 등)
├── assets/               # 이미지, 폰트, 아이콘 등 정적 파일
├── components/
│   ├── common/           # 범용 컴포넌트 (Button, Input, Modal 등)
│   │   ├── Button/
│   │   │   ├── Button.jsx
│   │   │   ├── IconButton.jsx
│   │   │   └── index.js
│   │   ├── Input/
│   │   ├── Modal/
│   │   └── Card/
│   └── layout/           # 레이아웃 컴포넌트 (Navbar, Footer, Sidebar)
├── hooks/                # 커스텀 훅 (useTheme, useAuth 등)
├── pages/                # 라우팅 페이지 (Home, Login, DevTest 등)
│   └── DevTest.jsx
├── store/                # Zustand 전역 상태 관리
├── styles/
│   └── index.css         # Tailwind + 테마 변수
├── utils/                # 유틸 함수 (formatDate, cn 등)
├── App.jsx               # 라우팅 설정 및 최상위 컴포넌트
├── layouts               # 배치 (임시?)
└── main.jsx              # 진입점

```
---
layout: fact
---

# Design Concepts


<div class="palette-wrap">
  <div class="palette-section">
    <div class="palette-h">Primary Brand</div>
    <div class="brand-grid">
      <div class="swatch">
        <div class="chip" style="--c:#10B981"></div>
        <div class="meta">
          <div class="name">Primary</div>
          <div class="hex">#10B981</div>
        </div>
      </div>
      <div class="swatch">
        <div class="chip" style="--c:#059669"></div>
        <div class="meta">
          <div class="name">Hover</div>
          <div class="hex">#059669</div>
        </div>
      </div>
      <div class="swatch">
        <div class="chip" style="--c:#047857"></div>
        <div class="meta">
          <div class="name">Active</div>
          <div class="hex">#047857</div>
        </div>
      </div>
      <div class="swatch">
        <div class="chip" style="--c:#34D399"></div>
        <div class="meta">
          <div class="name">Light</div>
          <div class="hex">#34D399</div>
        </div>
      </div>
      <div class="swatch">
        <div class="chip" style="--c:#065F46"></div>
        <div class="meta">
          <div class="name">Dark</div>
          <div class="hex">#065F46</div>
        </div>
      </div>
    </div>
  </div>

  <div class="palette-section" style="margin-top:26px;">
    <div class="palette-h">Semantic Colors (Context Aware)</div>
    <div class="semantic-grid">
      <div class="semantic-card" style="--accent:#10B981; --bg:#D1FAE5; --fg:#065F46;">
        <div class="semantic-top">
          <span class="icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M20 6 9 17l-5-5"/>
            </svg>
          </span>
          <span class="label">Success</span>
        </div>
        <div class="semantic-body">Background</div>
      </div>
      <div class="semantic-card" style="--accent:#F59E0B; --bg:#FEF3C7; --fg:#92400E;">
        <div class="semantic-top">
          <span class="icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M10.3 3.2 1.9 18a2 2 0 0 0 1.7 3h16.8a2 2 0 0 0 1.7-3L13.7 3.2a2 2 0 0 0-3.4 0Z"/>
              <path d="M12 9v4"/><path d="M12 17h.01"/>
            </svg>
          </span>
          <span class="label">Warning</span>
        </div>
        <div class="semantic-body">Background</div>
      </div>
      <div class="semantic-card" style="--accent:#EF4444; --bg:#FEE2E2; --fg:#991B1B;">
        <div class="semantic-top">
          <span class="icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M18 6 6 18"/><path d="M6 6l12 12"/>
            </svg>
          </span>
          <span class="label">Error</span>
        </div>
        <div class="semantic-body">Background</div>
      </div>
      <div class="semantic-card" style="--accent:#3B82F6; --bg:#DBEAFE; --fg:#1E40AF;">
        <div class="semantic-top">
          <span class="icon">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="10"/><path d="M12 16v-4"/><path d="M12 8h.01"/>
            </svg>
          </span>
          <span class="label">Info</span>
        </div>
        <div class="semantic-body">Background</div>
      </div>
    </div>
  </div>
</div>

---
layout: fact
---

# Design Concepts
### UI Components Preview
<div class="ui-preview">
  <!-- Left: Meeting Card -->
  <div class="meeting-card">
    <div class="meeting-top">
      <span class="status-pill">진행중</span>
      <span class="time-range">10:00 AM - 11:30 AM</span>
      <span class="kebab">•••</span>
    </div>
    <div class="meeting-title">프론트엔드 주간 회의</div>
    <div class="meeting-desc">
      이번 주 스프린트 리뷰 및 다음 주 백로그 정리에 대한 논의를 진행합니다.
      이슈 #420 관련 디자인 QA 포함.
    </div>
    <div class="meeting-bottom">
      <div class="avatars">
        <span class="av">🧑‍💻</span>
        <span class="av">👩‍💻</span>
        <span class="more">+3</span>
      </div>
      <button class="btn-primary">참여하기</button>
    </div>
  </div>

  <!-- Right: Modal Preview -->
  <div class="modal-stage">
    <div class="modal">
      <div class="modal-head">
        <div class="modal-title">새 프로젝트</div>
        <div class="modal-x">×</div>
      </div>
      <div class="modal-body">
        <div class="field">
          <div class="label">프로젝트 명</div>
          <div class="input">Didit 리팩토링</div>
        </div>
      </div>
      <div class="modal-actions">
        <button class="btn-ghost">취소</button>
        <button class="btn-primary">생성</button>
      </div>
    </div>
  </div>
</div>

<!-- Status Badges -->
<div class="badge-panel">
  <div class="badge-title">Status Badges</div>
  <div class="badge-row">
    <span class="badge ok">Online</span>
    <span class="badge warn">Away</span>
    <span class="badge danger">Do Not Disturb</span>
    <span class="badge info">Meeting</span>
    <span class="badge neutral">Offline</span>
  </div>
</div>

---
layout: fact
---

# Backend Tech Stack


<div class="be-mini">
  <div class="mini">
    <div class="h">Core Backend</div>
    <div class="tags">
      <span class="a">Java</span>
      <span class="a">Spring Boot</span>
      <span class="a">WebFlux</span>
      <span class="a">JPA</span>
      <span class="a">SSE</span>
    </div>
  </div>

  <div class="mini">
    <div class="h">Data</div>
    <div class="tags">
      <span class="a">MySQL</span>
      <span class="a">Elasticsearch</span>
    </div>
  </div>

  <div class="mini">
    <div class="h">Messaging</div>
    <div class="tags">
      <span class="a">Redis</span>
      <span class="a">Pub/Sub</span>
    </div>
  </div>

  <div class="mini">
    <div class="h">Media</div>
    <div class="tags">
      <span class="a">OpenVidu</span>
      <span class="a">WebRTC</span>
    </div>
  </div>

  <div class="mini">
    <div class="h">Infra</div>
    <div class="tags">
      <span class="a">Docker</span>
      <span class="a">Compose</span>
      <span class="a">GitLab CI/CD</span>
    </div>
  </div>

  <div class="mini">
    <div class="h">Ingress / OS</div>
    <div class="tags">
      <span class="a">Traefik</span>
      <span class="a">Ubuntu</span>
      <span class="a">Alpine</span>
    </div>
  </div>
</div>

---
layout: figure
figureUrl: "/PERD.svg"
---

# DataBase ERD

---
layout: fact
---

# DataBase ERD
## Point
<div class="erd-board">
  <div class="erd-card">
    <div class="h">Identity</div>
    <div class="p"><b>USERS</b> ↔ <b>USER_GITHUB_AUTH</b></div>
    <div class="s">OAuth 토큰 분리(1:1)</div>
  </div>

  <div class="erd-card">
    <div class="h">Project / Membership</div>
    <div class="p"><b>PROJECTS</b> → <b>PROJECT_USERS</b></div>
    <div class="s">role(ADMIN/MEMBER) · status(PENDING/ACTIVE)</div>
  </div>

  <div class="erd-card">
    <div class="h">Invite</div>
    <div class="p"><b>PROJECT_INVITES</b></div>
    <div class="s">UUID PK · expires_at 만료</div>
  </div>

  <div class="erd-card">
    <div class="h">Meeting</div>
    <div class="p"><b>MEETINGS</b> → <b>MEETING_USERS</b></div>
    <div class="s">OpenVidu session_id · 참석 N:M</div>
  </div>

  <div class="erd-card">
    <div class="h">STT / Summary</div>
    <div class="p"><b>SPEECH_SCRIPTS</b> → <b>SUMMARY</b></div>
    <div class="s">구간 전사 · 요약 version 관리</div>
  </div>

  <div class="erd-card">
    <div class="h">Collaboration</div>
    <div class="p"><b>ISSUES</b> / <b>CHATS</b> / <b>READS</b></div>
    <div class="s">GitHub 매핑 · 채팅 soft edit/delete · 읽음상태</div>
  </div>
</div>

<div class="erd-note">
  중심축: <b>PROJECTS</b>에 회의·이슈·채팅이 붙고, 멤버십/초대로 확장되는 구조
</div>

---
layout: figure
figureUrl: "/DataGeneratePipeline.png"
---

# 이슈 중요도 추천 모델 데이터 생성 파이프라인

---
layout: figure
figureUrl: "/SurmaryAiModel.png"
---

# 회의요약 AI 모델

---
layout: fact
---

# Milestones Roadmap
<div class="ms4">
  <!-- M1 -->
  <div class="ms-col active">
    <div class="ms-dot">M1</div>
    <div class="ms-card">
      <div class="ms-head">
        <div class="ms-title">인증 <br/>+ Room</div>
        <div class="ms-date">1/19 ~ 1/21</div>
      </div>
      <ul class="ms-ul">
        <li>로그인/세션/로그아웃</li>
        <li>방 목록·생성·초대·참가</li>
        <li>참여자 목록 확인</li>
      </ul>
    </div>
  </div>

  <!-- M2 -->
  <div class="ms-col">
    <div class="ms-dot">M2</div>
    <div class="ms-card">
      <div class="ms-head">
        <div class="ms-title">라운지 <br/>+ 캘린더</div>
        <div class="ms-date">1/22 ~ 1/23</div>
      </div>
      <ul class="ms-ul">
        <li>최근 회의 <br/> 회의 리스트<br/> 진행중 이슈</li>
        <li>회의 예약 CRUD</li>
        <li>회의실 생성·삭제·이름수정</li>
      </ul>
    </div>
  </div>

  <!-- M3 -->
  <div class="ms-col">
    <div class="ms-dot">M3</div>
    <div class="ms-card">
      <div class="ms-head">
        <div class="ms-title">회의실 <br/>+ 채팅</div>
        <div class="ms-date">1/26 ~ 1/28</div>
      </div>
      <ul class="ms-ul">
        <li>OpenVidu 토큰 받아 <br/> 음성 참여</li>
        <li>채팅 최신 20개 <br/> + 더보기/무한스크롤</li>
        <li>본인 채팅 수정/삭제</li>
      </ul>
    </div>
  </div>

  <!-- M4 -->
  <div class="ms-col">
    <div class="ms-dot">M4</div>
    <div class="ms-card">
      <div class="ms-head">
        <div class="ms-title">STT/요약<br/>+ 이슈 생성</div>
        <div class="ms-date">1/29 ~ 1/30</div>
      </div>
      <ul class="ms-ul">
        <li>녹음 start/stop</li>
        <li>요약 생성 트리거 <br/> + Job 상태</li>
        <li>GitHub 이슈 생성 <br/> → 라운지 반영</li>
      </ul>
    </div>
  </div>
</div>

<div class="ms-goal">
  <span class="goal-pill">Goal</span>
  <span class="goal-text">1/30 데모 MVP: Auth · Room · Lounge · Chat · Meeting · Issue · Summary</span>
</div>

