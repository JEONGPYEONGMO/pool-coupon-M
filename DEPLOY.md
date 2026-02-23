# 📲 수영장 쿠폰 PWA 배포 가이드

## 폴더 구조

```
pool-coupon-pwa/
├── index.html              ← 랜딩 페이지 (관리자/회원 선택)
├── admin.html              ← 관리자 앱
├── member.html             ← 회원 앱 (읽기 전용)
├── sw.js                   ← 서비스 워커 (오프라인 캐시)
├── manifest-admin.json     ← 관리자 PWA 설정
├── manifest-member.json    ← 회원 PWA 설정
└── icons/
    ├── admin-192.png
    ├── admin-512.png
    ├── member-192.png
    └── member-512.png
```

---

## Netlify 배포 (가장 빠름, 2분)

1. https://app.netlify.com 가입 (GitHub 계정으로 가능)
2. https://app.netlify.com/drop 접속
3. **ZIP 파일을 풀어서 나온 폴더**를 드래그 앤 드롭
4. 즉시 URL 생성!

### URL 커스텀 (선택)
- Site settings → Domain management → Custom domain
- 무료 도메인: `pool-coupon.netlify.app` 같은 이름으로 변경 가능

---

## GitHub Pages 배포 (영구 무료)

1. GitHub에서 새 Repository 생성 (`pool-coupon`)
2. ZIP 파일의 내용물 전체를 업로드
3. Settings → Pages → Branch: `main` → Save
4. 2분 후 URL:
   - `https://본인아이디.github.io/pool-coupon/`

> ⚠️ GitHub Pages 사용 시, 경로가 `/pool-coupon/admin.html`이 되므로
> manifest와 sw.js의 경로를 상대경로로 수정해야 합니다.

---

## 📲 홈 화면에 앱 설치

### Android (Chrome)
1. 배포된 URL 접속
2. 하단에 **"📲 앱으로 설치"** 배너 자동 표시
3. **설치** 터치 → 홈 화면에 앱 아이콘 생성

### iPhone (Safari)
1. 배포된 URL을 **Safari**로 접속 (카톡 인앱브라우저 X)
2. 하단 **공유 버튼 (□↑)** 터치
3. **"홈 화면에 추가"** 선택
4. 홈 화면에 앱 아이콘 생성

---

## 회원에게 공유

배포 완료 후 회원에게 전달할 것:

**카톡 메시지 예시:**

```
🏊 수영장 쿠폰 조회

아래 링크에서 내 쿠폰 잔여·이용 내역을 확인할 수 있습니다.

👉 https://pool-coupon.netlify.app/member.html

📲 설치 방법:
- 안드로이드: 링크 열면 하단 "앱으로 설치" 터치
- 아이폰: Safari로 열기 → 공유(□↑) → 홈 화면에 추가
```

---

## 관리자/회원 URL 정리

| 대상 | URL |
|------|-----|
| 랜딩 | `https://도메인/` |
| 관리자 | `https://도메인/admin.html` |
| 회원 | `https://도메인/member.html` |
