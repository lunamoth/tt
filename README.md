# ✂️ 타래 재단사 (Thread Tailor)

> **"긴 글을 넣으면, SNS 맞춤형 타래(Thread)로 재단해 드립니다."**  
> 블루스카이, 트위터(X), 스레드 등 글자 수 제한이 있는 소셜 미디어에 긴 글을 올리기 쉽도록 자동으로 나누어주는 웹 도구입니다.

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
</p>

## ✨ 주요 기능 (Key Features)

### 1. 플랫폼별 맞춤 프리셋
원하는 플랫폼 버튼만 누르면 글자 수 제한과 URL 처리 방식이 자동으로 설정됩니다.
- **🦋 블루스카이 (Bluesky):** 300자 제한
- **🐦 트위터 (Twitter/X):** 280자 제한 + URL 가중치 계산 (t.co 기준 23자)
- **🧵 스레드 (Threads):** 500자 제한

### 2. 스마트한 텍스트 분할 엔진
- **`Intl.Segmenter` 사용:** 단순 `length` 속성이 아닌, 자소(Grapheme) 단위 분할로 한글, 이모지가 깨지지 않고 정확하게 카운팅됩니다.
- **문단 유지 모드:** 문맥이 끊기지 않도록 가급적 문단 단위로 글을 자릅니다.
- **URL 보호:** 긴 URL이 잘려서 링크가 깨지는 것을 방지합니다.

### 3. 강력한 커스터마이징
- **번호 서식:** `(1/n)`, `[1/n]`, `(🧵1/n)` 등 다양한 스타일 지원 및 사용자 정의 가능.
- **번호 위치:** 글 앞/뒤 선택 가능.
- **다크 모드:** 시스템 설정 자동 감지 및 수동 토글 지원.

### 4. 사용자 편의성
- **자동 저장 (LocalStorage):** 작성 중인 글과 설정값이 브라우저에 자동 저장되어 새로고침 해도 날아가지 않습니다.
- **파일 드래그 & 드롭:** `.txt` 파일을 끌어다 놓으면 즉시 로드됩니다.
- **원클릭 복사:** 분할된 카드를 클릭하면 바로 클립보드에 복사됩니다.
- **결과물 다운로드:** 전체 타래를 텍스트 파일로 저장할 수 있습니다.

---

## 🛠 기술적 특징 (Technical Details)

이 프로젝트는 외부 라이브러리나 프레임워크 없이 **순수 JavaScript**로 작성되었으며, 다음과 같은 최적화가 적용되어 있습니다.

### 아키텍처 (OOP 구조)
코드는 유지보수가 용이하도록 클래스 기반으로 구조화되어 있습니다.
- `AppController`: 앱의 전체 수명 주기, 이벤트 바인딩, 설정 관리.
- `TextEngine`: 텍스트 분할 알고리즘, 자소 카운팅, 포맷팅 로직 담당.
- `DOMHelper`: DOM 요소 생성 및 조작, XSS 방지.
- `ClipboardManager`: 클립보드 API 및 폴백(Fallback) 로직 처리.

### 보안 및 성능 (Security & Performance)
- **ReDoS 방지:** 정규식 처리 시 타임아웃을 두어 악의적인 입력으로 인한 브라우저 멈춤 현상 방지.
- **CSP (Content Security Policy):** 엄격한 메타 태그 설정을 통해 XSS 등 보안 위협 최소화.
- **디바운싱 (Debouncing):** 입력 시마다 불필요한 연산을 줄이기 위해 처리 로직 지연 실행.
- **No InnerHTML:** 텍스트 주입 시 `textContent`를 사용하여 XSS 취약점 원천 차단.

---

## 🚀 실행 방법 (How to Run)

이 프로젝트는 **단일 HTML 파일**로 구성되어 있어 별도의 빌드 과정이나 서버가 필요 없습니다.

1. 이 저장소를 클론하거나 `index.html` 파일을 다운로드합니다.
2. 브라우저(Chrome, Edge, Safari, Firefox 등)에서 `index.html`을 엽니다.
3. 바로 사용 가능합니다!

---

## 🔒 개인정보 처리 방침 (Privacy)

**타래 재단사는 서버가 없는(Serverless) 클라이언트 사이드 앱입니다.**
- 입력하신 모든 텍스트와 설정값은 사용자의 **브라우저 내부(Local Storage)에만 저장**됩니다.
- 외부 서버로 어떠한 데이터도 전송되지 않으므로 안심하고 사용하세요.

---

## 🤝 기여하기 (Contributing)

버그 제보나 기능 제안은 언제나 환영합니다!
@lunamoth 블루스카이, 트위터, 스레드로 댓글 주세요

---

## 📝 라이선스 및 크레딧

- **Created by:** Lunamoth & Gemini 3.0 Pro
- **License:** MIT License
- **Font:** [Pretendard](https://github.com/orioncactus/pretendard) (System fallback)

---
<p align="center">
  <i>✂️ 멋진 타래를 엮어보세요!</i>
</p>
