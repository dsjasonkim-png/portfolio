← [전체 개요로 돌아가기](../README.md)

# 패션 리테일 수요예측·재고물류 최적화 프로젝트 (PM/PL)

**회사/기간**: 빅데이터 컨설팅 전문기업 · 2020.09 ~ 2023.08
**역할**: 과장 / PM·PL — 글로벌 패션 기업向 분석 컨설팅 프로젝트, 클라이언트 요청으로 PM/PL 발탁 (4인 팀)

> 클라이언트사명은 컨설팅 계약의 비밀유지 조항을 고려해 일반화했습니다.

## 배경

상품 기획·판매·재고·물류 데이터를 활용해 예측 및 운영 의사결정 과제를 개발·운영하는 대규모 분석 컨설팅 프로젝트였습니다. 약 20개 분석 과제를 동시에 운영하며 시즌·업무 정책 변경에 따른 로직 수정을 지속했습니다.

## 상세 내용

### 1. 상품 기획 및 수요 의사결정 지원 모델
상품 기본정보, 작업지시서, BOM 데이터를 활용해 신규 상품과 유사한 과거 상품군을 탐색하고, 판매실적·수요패턴·시즌성을 기반으로 초기 기획량 산정을 지원했습니다. 매장·품번·SKU 단위 주간 판매량이 0~3개 수준인 저빈도 수요 특성을 고려해 **회귀가 아닌 멀티클래스 분류 문제로 재정의**하고, Case Weight·Sampling을 적용해 예측 정확도 **75~80%** 수준을 달성했습니다.

**기술**: R · SQL · Machine Learning · Time Series · Similarity Modeling

### 2. 상품 Life Cycle 및 시즌 Exit 전략 분석
Bass Diffusion 모형으로 상품의 판매 확산 패턴과 주차별 판매 흐름을 예측하고, ML 모형(Random Forest)으로 정상판매 종료시점 및 리오더 판단 시점을 예측했습니다. Elbow Point를 활용해 판매 둔화 구간을 식별하고 이월상품 정리·신상품 전환 시점 판단 기준을 설계했습니다.

**기술**: R · SQL · Bass Diffusion · Product Life Cycle · Change Point Analysis

### 3. 재고 보충·매장 간 이동 및 물류 운영 최적화
매장·품번·SKU별 판매실적, 재고현황, 수요예측 결과를 기반으로 물류센터→매장 후보충 필요 물량과 매장 간 이동(RT) 대상·수량을 산정했습니다. 극단적 클래스 불균형으로 Accuracy 99%가 무의미한 상황에서 평가 지표를 **Recall 중심으로 재정의**하고, 샘플링·임계값 조정을 통해 Recall을 0.1% 수준에서 10~20% 수준으로 개선했습니다 (**100배 이상**). Transportation Algorithm을 적용해 출발 매장·도착 매장·이동 수량을 제안하는 재고 재배치 로직을 개발했습니다.

**기술**: R · SQL · Optimization · Transportation Algorithm · Inventory Analytics

### 4. 연관판매상품 제안 모형
상품(SKU) 간 연관판매 규칙을 분석하고, 지지도·신뢰도 지표를 활용해 연관판매상품을 도출·제안하는 모형을 개발했습니다.

**기술**: R · SQL · Association Rule Mining

### 5. Rule-based Fraud Detection 고도화
기존 SQL 기반 Rule-based Fraud Detection 과제를 인수해 운영·고도화했습니다. 기존 이상거래 탐지 룰의 구조와 로직을 분석하고, 지점·상품·거래 패턴 기반 이상 징후 탐지 조건을 신규 설계·반영했습니다.

**기술**: SQL · Rule-based Detection

### 6. 분석 과제 운영 및 현업 협업
약 20개 분석 과제의 운영·유지보수·고도화를 담당하고, Raw Data 처리부터 분석 데이터셋 생성, 모델 실행, 결과 검증까지 분석 운영 전 과정을 관리했습니다. Airflow 기반 정기 배치와 RStudio Server 분석 환경을 운영했습니다.

**기술**: R · SQL · Airflow · RStudio Server · PM/PL · Data Operations

## 성과

상품 출시 전 기획량부터 출시 후 리오더·물량 배분까지 단계별 데이터 의사결정 기준을 제공했고, 다수 분석 과제의 안정적 운영과 현업 정책 변화에 대한 지속적인 분석 서비스 대응 체계를 구축했습니다.

## 전체 기술 스택

`R` `SQL` `Machine Learning` `Time Series` `Similarity Modeling` `Bass Diffusion` `Product Life Cycle` `Change Point Analysis` `Optimization` `Transportation Algorithm` `Inventory Analytics` `Association Rule Mining` `Rule-based Detection` `Airflow` `RStudio Server` `PM/PL` `Data Operations`
