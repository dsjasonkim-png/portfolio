← [전체 개요로 돌아가기](../README.md)

# AI 기반 상품정보 생성·검증 자동화 파이프라인 (AX)

**회사/기간**: 가전 리테일 · 2024.03 ~ 현재
**역할**: 매니저(파트장) — 아키텍처 설계, 개발 리딩

## 배경

온라인몰 상품 상세 이미지를 담당자가 일일이 확인해 상품 속성·고시정보를 수작업으로 입력하던 프로세스를, OCR·LLM 기반 자동 구조화 파이프라인으로 전환하는 업무 프로세스 혁신 과제입니다.

## 아키텍처

![상품정보 자동화 파이프라인](../assets/pipeline-architecture.svg)

## 상세 내용

### 1. 서버 환경 및 데이터 생성 아키텍처 구축
VM 서버 환경 구성부터 OCR/LLM 기반 상품 속성 추출 프로세스 운영 구조를 설계했습니다. 상품 속성/고시정보 추출 서버, DB 적재 구조, 운영 관리 화면 연계 구조를 구성했습니다.

**기술**: Python · VM 서버 구성 · Database

### 2. 상품 이미지 OCR·LLM 정제 파이프라인 및 API 개발
상품 이미지 OCR 결과를 LLM으로 정제해 상품 속성/고시정보 데이터로 구조화했습니다. 추출 요청, 결과 조회, 검증 상태 관리, 재처리 기능을 위한 API를 개발했습니다.

**기술**: OCR(easyOCR) · LLM(Public LLM) · REST API

### 3. Taxonomy 설계 — 하향식 + 상향식 병행
- **하향식**: 상품 카테고리는 네이버·쿠팡 등 업계 표준 체계를 레퍼런스로 LLM 클러스터링 후 MD 검증을 거쳐 확정
- **상향식(Taxonomy Induction)**: 참고 표준이 없는 상품 속성은 OCR 원문을 LLM으로 그룹핑해 카테고리를 생성·매핑

### 4. FABEC 시맨틱 속성 구조화
수집된 속성을 Feature·Advantage·Benefit·Experience·Context(FABEC) 구조로 변환해 AI Agent가 활용 가능한 형태로 재구성했습니다. 상품 이미지에서 추출한 텍스트로 고객 판매 소구점·구매동기를 자극하는 FAB 구조 마케팅 문구 자동생성 프레임워크도 함께 개발했습니다.

**기술**: LLM · Prompt Engineering · FABEC Framework

### 5. 다단계 검증 Agent 및 품질 개선 체계
OCR 원문 대조, 상품 단위 정합성 검증, Web Search API grounding을 결합한 다단계 검증 Agent를 설계했습니다. 추출 결과 검수·오류 확인·재처리를 위한 운영 대시보드를 개발하고, 오류 유형을 품목군별 prompt/rule 개선에 반영하는 feedback loop를 구축했습니다.

**기술**: AI Agent · Web Search API Grounding · Dashboard

## 성과

상품정보 생성 → 검증 → 재처리 전 과정을 운영 가능한 구조로 자동화·표준화하여 반복 업무 효율과 데이터 품질 개선 기반을 마련했습니다. 결과 데이터는 검색·추천·AI 서비스용 공통 자산으로 구축되었습니다.

## 전체 기술 스택

`Python` `OCR(easyOCR)` `LLM` `AI Agent` `REST API` `Database` `Dashboard` `VM 서버 구성` `Prompt Engineering` `Web Search API Grounding`
