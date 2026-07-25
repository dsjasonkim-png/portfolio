← [전체 개요로 돌아가기](../README.md)

# 온·오프라인 통합 개인화 추천 & 고객 데이터 자산화

**회사/기간**: 가전 리테일 · 2024.03 ~ 현재
**역할**: 매니저(파트장) — 과제 기획, 아키텍처 설계, 팀 리딩

## 배경

오프라인 매장 상담 데이터와 온라인 행동 데이터가 분리되어 있어, 고객 한 명의 관심사·재구매 주기를 통합적으로 파악하기 어려운 상태였습니다. 이를 온·오프라인 전 채널에서 활용 가능한 통합 고객 프로파일로 만드는 것이 과제였습니다.

## 아키텍처

![개인화 추천 및 CDP 통합 아키텍처](../assets/personalized-recommendation-architecture.svg)

## 상세 내용

### 1. 고객 세그먼트 기반 추천 로직 개발
고객 생애주기와 구매성향 지표를 조합해 **729개 고객 세그먼트**를 구성했습니다. 고객별 관심 상품군과 재구매주기를 반영한 추천 로직을 개발해, 오프라인 매장 상담용 태블릿에 고객별 추천 상품군·상품 리스트를 제공했습니다.

**기술**: Python · SQL · Recommendation · Customer Segmentation

### 2. 구매가망모형(Lift 기반 타겟팅)
GA 행동 데이터, 과거 구매 이력, 고객 세그먼트를 변수로 활용해 머신러닝 기반 구매가망모형을 개발하고, **Lift 지표 기준**으로 마케팅 타겟 고객군을 선정했습니다.

**기술**: Python · SQL · Machine Learning · Lift Analysis

### 3. CDP 통합 및 고객 프로파일 구조화
고객 세그먼트, 추천 상품군, 재구매주기 데이터를 CDP로 이관해 온·오프라인 채널에서 활용 가능한 통합 고객 프로파일로 구성했습니다. CDP 고객 Feature를 쇼핑 AI Agent의 개인화 컨텍스트, CRM 활용 데이터와 연계하는 구조를 설계했습니다.

**기술**: CDP · Customer Profile Integration · Data Architecture

## 성과

추천 상위 5개 상품의 1주 이내 구매율 **47%**를 확인했고, 오프라인 상담 데이터를 디지털·AI 채널에서 재활용할 수 있는 기반을 확보했습니다.

## 전체 기술 스택

`Python` `SQL` `Recommendation` `Customer Segmentation` `Lift Analysis` `CDP` `Customer Profile Integration`
