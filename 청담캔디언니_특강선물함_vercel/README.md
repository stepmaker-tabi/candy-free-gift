# 캔디언니 사업 비밀노트 · 특강 선물함 (Vercel 배포용)

## 폴더 구성
```
청담캔디언니_특강선물함_vercel/
├── vercel.json              # 배포 설정 (public 폴더 배포, 검색 노출 차단, 캐시)
├── README.md
└── public/
    ├── index.html           # 메인: 선물 3종 + 무료특강 일정·커리큘럼  →  /
    ├── masterclass/
    │   └── index.html       # 선물 3종 + 마스터클래스 4기 신청 배너   →  /masterclass
    ├── cover/vod1~4.jpg     # VOD 표지
    ├── files/bn-diag-7q4x.pdf  # 실전 비즈니스 진단서
    ├── og.png               # 카톡·SNS 공유 미리보기 이미지 (1200×630)
    └── favicon.svg
```

## 배포 방법 (택 1)
```
[A] 드래그 앤 드롭
1. vercel.com 로그인 → Add New → Project
2. 폴더 통째로 업로드(또는 GitHub 저장소 연결)
3. Framework Preset: Other / Build Command: 비움 / Output Directory: public
4. Deploy

[B] CLI
npm i -g vercel
cd 청담캔디언니_특강선물함_vercel
vercel          # 미리보기 배포
vercel --prod   # 실서비스 배포
```

## 배포 후 체크
```
- 비밀번호: 1028  (선물 2·3 잠금 해제)
- 공유 미리보기(og.png)는 절대주소가 더 안정적이에요.
  도메인 확정 후 두 index.html의 og:image 를 https://도메인/og.png 로 바꿔주세요.
- 4기 신청 링크: public/masterclass/index.html 의  const APPLY_URL = "";  에 결제 URL 입력
- 카톡 미리보기가 예전 이미지로 뜨면: developers.kakao.com/tool/debugger/sharing 에서 캐시 초기화
```

## 비밀번호를 바꾸려면
선물 2·3 링크는 비밀번호로 암호화(AES-GCM)돼 있어서, HTML에서 단어만 바꾸면 안 돼요.
새 비밀번호로 다시 생성해야 하니 요청해 주세요.
