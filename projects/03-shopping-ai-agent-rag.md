← [전체 개요로 돌아가기](../README.md)

# 쇼핑 AI Agent / RAG 기반 상품 탐색·추천 PoC

**회사/기간**: 가전 리테일 · 2024.03 ~ 현재
**역할**: 매니저(파트장) — PoC 설계·구현

## 배경

고객이 자연어로 질의했을 때, 제품군·예산·사용 맥락·필수 조건을 해석하고 상품 지식을 검색·재정렬해 추천 근거와 함께 응답을 생성하는 대화형 추천 구조를 검증하는 PoC입니다.

## 아키텍처

![쇼핑 AI Agent RAG 구조](../assets/rag-agent-architecture.svg)

## 상세 내용

### 1. AI Agent 구조 검토 및 프로토타입 설계
LangChain·LangGraph 기반으로 고객 질의에서 제품군, 예산, 사용 맥락, 핵심 조건을 추출하는 질의 해석 구조를 설계했습니다. 추천 Agent, 지식 Agent, CS Agent 등 멀티 Agent 기반 쇼핑 지원 구조를 검토하고, 상품 데이터 파이프라인을 설계했습니다.

**기술**: LangChain · LangGraph · Multi-Agent 설계

### 2. 상품 지식 기반 검색·추천
상품 속성, 판매논리, 구매동기, 사용 맥락을 결합한 상품 지식 구조를 Vector DB 기반 검색 체계로 구축했습니다. Gemma3 모형을 활용해 질의 분류 → RAG → 답변 생성 구조의 PoC를 수행했습니다.

**기술**: RAG · Vector DB · Gemma3

### 3. Semantic Search 및 Reranking
Semantic Search와 Reranking을 적용해 고객 조건에 부합하는 상품 후보를 탐색하고 추천 근거를 생성했습니다. 상품설명 문구를 벡터 DB로 변환해 시맨틱 검색에 활용했습니다.

**기술**: Semantic Search · Reranking

### 4. 개인화 컨텍스트 연계
CDP에 통합된 고객 세그먼트·재구매주기 데이터를 추천 Agent의 개인화 컨텍스트로 연계해, 고객별 관심 상품군과 재구매 예상 시점을 AI 추천 후보군 생성에 반영했습니다.

**기술**: CDP 연계 · Personalization

## 성과

상품 데이터와 고객 프로파일을 결합한 대화형 상품 탐색·추천 구조의 적용 가능성을 검증했습니다.

## 전체 기술 스택

`LLM` `LangChain` `LangGraph` `RAG` `Vector DB` `Semantic Search` `Reranking` `Gemma3` `Multi-Agent 설계`
