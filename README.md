# 회원 관리 시스템

직원들이 공통으로 사용할 수 있는 회원 관리 웹 애플리케이션입니다.

## 기능

- **회원 정보 관리** – 이름, 연락처, 이메일, 주소, 생년월일, 등급(신규/일반/VIP)
- **주문 내역 관리** – 상품명, 금액, 수량, 주문일, 비고 / 총 구매금액 자동 계산
- **메모** – 직원별 메모 작성/삭제, 작성자 이름 + 시간 기록
- **검색 & 필터** – 이름·연락처 검색, 등급별 필터
- **다크 모드 UI** – 눈에 편한 다크 테마

## 사용 방법

파일 하나(`index.html`)로 구성되어 있어 별도 서버 없이 브라우저에서 바로 열어 사용할 수 있습니다.

```
index.html 파일을 더블클릭 → 브라우저에서 열기
```

> 데이터는 각 브라우저의 **localStorage**에 저장됩니다.  
> **직원들이 함께 같은 데이터를 보려면 아래 "공유 서버 배포" 방법을 사용하세요.**

---

## 직원 공유 방법 (권장)

### 방법 1: GitHub Pages (무료, 권장)

1. GitHub 저장소에 이 파일을 올립니다.
2. 저장소 Settings → Pages → Branch: main, / (root) 선택 후 Save
3. 생성된 URL을 직원들과 공유

⚠️ 단, GitHub Pages + localStorage는 **각자 브라우저에 별도 저장**됩니다.  
진짜 공유 데이터를 원하면 방법 2 또는 3을 사용하세요.

---

### 방법 2: 백엔드 연동 (데이터 실제 공유)

공유 데이터가 필요하면 간단한 백엔드(예: Firebase Realtime DB, Supabase)를 붙이는 것을 추천합니다.

**Firebase Realtime Database 예시 (무료)**
1. [Firebase Console](https://console.firebase.google.com) 에서 프로젝트 생성
2. Realtime Database 생성
3. `index.html`의 localStorage 부분을 Firebase SDK로 교체

필요하면 Firebase 연동 버전도 만들어 드릴 수 있습니다.

---

### 방법 3: 로컬 네트워크 (사내)

```bash
# Python이 설치된 경우
python3 -m http.server 8080

# 사내 직원들은 같은 WiFi에서 http://[내IP]:8080 접속
```

---

## 파일 구조

```
member-manager/
└── index.html   # 전체 앱 (HTML + CSS + JS 단일 파일)
```

## 기술 스택

- 순수 HTML / CSS / JavaScript (프레임워크 없음)
- 구글 폰트: Noto Sans KR, DM Mono
- 외부 의존성 없음 (인터넷 연결 시 폰트만 로드)
