<div align="center">

# 홈사이드 (Homeside)

### 🏡 AI가 분석하고, 전문가가 동행합니다

**부동산 거래의 불안함을 없애는 AI 기반 부동산 컨설팅 플랫폼**

[![Website](https://img.shields.io/badge/Website-homeside.co.kr-4A90E2?style=for-the-badge&logo=google-chrome&logoColor=white)](https://homeside.co.kr)
[![API](https://img.shields.io/badge/API-api.homeside.co.kr-6C47FF?style=for-the-badge&logo=swagger&logoColor=white)](https://api.homeside.co.kr)

</div>

---

## 소개

홈사이드는 **AI 분석**과 **전문가 동행**을 결합한 대한민국 부동산 컨설팅 플랫폼입니다.

- 고객은 원하는 조건을 입력하면 전문가가 매칭되어 직접 동행하며 컨설팅을 제공합니다.
- 전문 공인중개사가 매물 분석 리포트를 작성하고, 계약까지 안전하게 도움을 드립니다.
- 처음 집을 구하는 분부터 투자자까지, 부동산 거래의 모든 단계를 함께합니다.

---

## 플랫폼 구성

| 리포지토리 | 설명 | 기술 스택 |
|---|---|---|
| [homeside-landing](https://github.com/homeside-kr/homeside-landing) | 서비스 소개 랜딩 페이지 | HTML · CSS · Vanilla JS |
| [homeside-web](https://github.com/homeside-kr/homeside-web) | 웹 애플리케이션 (고객 · 전문가) | Next.js 14 · TypeScript · React Query |
| [homeside-app](https://github.com/homeside-kr/homeside-app) | iOS / Android 모바일 앱 | React Native · Expo |
| [homeside-api](https://github.com/homeside-kr/homeside-api) | REST API 백엔드 서버 | Spring Boot 3 · Java 17 · PostgreSQL |

---

## 아키텍처

```
┌───────────────────────────────────────────────────────────────────┐
│                          클라이언트 레이어                             │
│                                                                   │
│   ┌─────────────────┐          ┌──────────────────────────────┐   │
│   │  homeside-app   │          │        homeside-web          │   │
│   │ React Native    │◄────────►│      Next.js 14 (BFF)        │   │
│   │  (Expo)         │  WebView │   TypeScript · Zustand       │   │
│   └─────────────────┘          └──────────────────────────────┘   │
│                                              │                    │
│   ┌─────────────────────────────────────┐    │                    │
│   │        homeside-landing             │    │                    │
│   │     정적 HTML/CSS/JS 랜딩 페이지        │    │                    │
│   └─────────────────────────────────────┘    │                    │
└──────────────────────────────────────────────┼────────────────────┘
                                               │
                         HTTPS / REST API      │
                                               ▼
┌───────────────────────────────────────────────────────────────────┐
│                          서버 레이어                                 │
│                                                                   │
│   ┌──────────────────────────────────────────────────────────┐    │
│   │                    homeside-api                          │    │
│   │           Spring Boot 3 · Java 17 · JWT Auth             │    │
│   │        OAuth2 (Kakao · Apple) · Swagger / OpenAPI        │    │
│   └─────────────────────────────┬────────────────────────────┘    │
│                                 │                                 │
│       ┌─────────────────────────┼──────────────────────┐          │
│       ▼                         ▼                      ▼          │
│  ┌─────────┐             ┌──────────────┐       ┌────────────┐    │
│  │ AWS RDS │             │   AWS S3     │       │  Solapi    │    │
│  │ Postgres│             │  이미지/파일    │       │ SMS·알림톡   │    │
│  └─────────┘             └──────────────┘       └────────────┘    │
└───────────────────────────────────────────────────────────────────┘
```

---

## 주요 기능

### 👤 고객
- 카카오 / 애플 소셜 로그인
- 서비스 신청 (지역 · 예산 · 매물 유형 · 계약 유형 설정)
- 전문가 자동 매칭
- 동행 일정 조율 및 관리
- 매물 분석 리포트 수신
- 전문가 리뷰 작성

### 🏢 전문가
- 전문가 프로필 등록 및 승인 워크플로우
- 서비스 신청 처리 및 동행 관리
- 매물 분석 리포트 작성 (섹션 · 사진 포함)
- 리뷰 기반 평점 시스템
- 카카오 알림톡으로 고객 알림 발송

### 💳 결제 & 알림
- TossPayments 결제 연동
- Solapi 카카오 알림톡 / SMS 발송
- Amplitude 사용자 행동 분석

---

## 기술 스택

### Frontend
![Next.js](https://img.shields.io/badge/Next.js_14-000000?style=flat-square&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React_18-61DAFB?style=flat-square&logo=react&logoColor=black)
![React Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white)
![Zustand](https://img.shields.io/badge/Zustand-433E38?style=flat-square)
![NextAuth](https://img.shields.io/badge/NextAuth.js-000000?style=flat-square&logo=next.js)

### Mobile
![React Native](https://img.shields.io/badge/React_Native-61DAFB?style=flat-square&logo=react&logoColor=black)
![Expo](https://img.shields.io/badge/Expo-000020?style=flat-square&logo=expo&logoColor=white)
![EAS](https://img.shields.io/badge/EAS_Build-000020?style=flat-square&logo=expo)

### Backend
![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Java](https://img.shields.io/badge/Java_17-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black)

### Infrastructure
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![S3](https://img.shields.io/badge/S3-569A31?style=flat-square&logo=amazons3&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-232F3E?style=flat-square&logo=amazonaws)
![RDS](https://img.shields.io/badge/RDS-527FFF?style=flat-square&logo=amazonrds&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

---

## 서비스 흐름

```
고객 서비스 신청
      │
      ▼
전문가 매칭 (지역·전문 분야 기반)
      │
      ▼
동행 일정 조율
      │
      ▼
현장 동행 및 매물 분석
      │
      ▼
전문 리포트 작성 (알림톡 발송)
      │
      ▼
리뷰 & 평점 등록
```

---

## 인증 방식

- **소셜 로그인**: 카카오 OAuth 2.0, 애플 Sign-In
- **토큰**: JWT Access Token + Refresh Token 로테이션
- **역할**: 고객(Customer) / 전문가(Expert) / 관리자(Admin)

---

## 배포 환경

| 서비스 | URL | 인프라 |
|---|---|---|
| 랜딩 페이지 | [homeside.co.kr](https://homeside.co.kr) | AWS S3 + CloudFront |
| 웹 앱 | [app.homeside.co.kr](https://app.homeside.co.kr) | Vercel |
| API 서버 | [api.homeside.co.kr](https://api.homeside.co.kr) | AWS EC2 / Spring Boot |
| API 문서 | [api.homeside.co.kr/api](https://api.homeside.co.kr/api) | Swagger UI |

---

<div align="center">

**홈사이드와 함께 안전하고 현명한 부동산 거래를 시작하세요.**

© 2025 Homeside. All rights reserved.

</div>
