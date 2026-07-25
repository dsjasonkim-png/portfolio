← [전체 개요로 돌아가기](../README.md)

# 개인 프로젝트 — 밀크코치 (Milk Coach)

**형태**: 1인 개발 · Google Play 비공개 테스트 진행 중

## 개요

모유·혼합수유 부모를 위한 수유·수면·기저귀·성장 기록 모바일 앱입니다. 기획부터 백엔드 설계, AI 기능 통합, 결제, 배포까지 전 과정을 혼자 진행하고 있습니다.

## 핵심 차별점

직수 수유량을 정확히 알기 어렵다는 육아 현장의 문제를 풀기 위해, 최근 유축 데이터와 회복시간 상수(recovery time constant)를 활용한 좌/우 상태 모델로 직수량을 추정합니다.

## 아키텍처

![밀크코치 아키텍처](../assets/milkcoach-architecture.svg)

## 상세 내용

### 클라이언트
Flutter/Dart로 개발한 Android 클라이언트 (iOS는 아직 미착수).

### 백엔드
Supabase 기반 — Postgres 데이터베이스, Auth 인증, Edge Functions(Deno)로 서버리스 로직을 처리합니다.

### AI 기능
Google Gemini API를 활용해 일일 육아 리포트를 생성하며, 클라이언트·서버 이중 세이프가드를 적용해 안전성을 확보했습니다.

### 결제 및 운영
Google Play Billing 기반 구독 결제를 연동했고, 관리자 콘솔은 Cloudflare Pages에 정적 호스팅했습니다.

## 현재 상태

Google Play 비공개 테스트 단계이며, 상업화 및 스토어 정식 출시를 준비 중입니다. 이 때문에 소스 코드는 비공개로 유지하고 있습니다.

## 전체 기술 스택

`Flutter` `Dart` `Supabase` `Postgres` `Auth` `Edge Functions(Deno)` `Google Gemini API` `Google Play Billing` `Cloudflare Pages`
