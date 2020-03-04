## 1. Landing-Zone의 정의

퍼블릭 클라우드(AWS, Azure, GCP 등)의 자동화 구현 및 관리를 위한 템플릿으로써, 표준아키텍처를 기반으로 각 영역 별 코드로 구성 한다.

본 Repository 에서는 Azure용 Landing-Zone 구현을 설명한다.

## 2. 사전 설치조건

<H3>2.1 Terraform 설치는 다음 링크를 참조한다.  </H3>  
<H3>[https://sarc.io/index.php/cloud/1743-linux-terraform-installation]</H3>    



## 3. Architecture Overview

![iso27001-ase-sql-workload-blueprint-sample-design](https://user-images.githubusercontent.com/30038150/75132423-32b96b00-571a-11ea-8c1a-0a0870720862.png)  
![02_hubspoke4](https://user-images.githubusercontent.com/30038150/75123212-d853e680-56e8-11ea-8c40-330ba8050592.png)  

## 4. 구성요소

<H2>4.1 계정관리</H2>

+ Azure Organizaion
+ Azure 계정 구조 (다중 계정 관리)
+ Subscription
  + zure Subcription은 블라블라~~  
+ Azure Resource Group  
  + 리소스 그룹- Azure 솔루션의 관련 리소스를 보관하는 컨테이너입니다. 리소스 그룹에 솔루션의 모든 리소스를 포함할 수도 있고 그룹으로 관리할 리소스만 포함할 수도 있습니다. 무엇이 조직에 가장 적합한지에 따라 리소스 그룹에 리소스를 할당할 방법을 결정합니다.  

![Azure Line of Business](https://user-images.githubusercontent.com/30038150/75136202-3acbd780-5727-11ea-8c18-e093fdd0c386.png)  



<H2>4.2 식별 및 접근관리 (IAM - Identity and Access Management)</H2>  

+ 인증관리 
  + MFA
  + Limited Access
  + Force Password Reset
  + Trusted & Compliant Devices
  + Geo-location 
  + Azure ATP
+ Multi-Account 관리  
+ 리소스 태깅
  + 태깅 구조
  + 태깅 정책

<H2> 4.3 Infrastructure </H2>

- 네트워크
  - 그룹사 공통
    - Network Security Group
      - 제한시간 사용
    - Access Control List
    - Traffic Management
      - Istio
      - Azure Traffic Manager
    - SSL Certificate
    - API I/F
  - 대외(DMZ망)
    - 인터넷 게이트 웨이
    - 라우트 테이블
    - VNET Internet Ingress Traffic
    - NAT
    - API I/F
  - 대내
    - 공통 보안
      - VNET
        - 서브넷
    - 개발 환경
    - 테스트 환경
    - 운영 환경
    - 개발자 Sand Box
  - Vnet 내부
    - Region 간 통신
  - 전용선 (Azure <-> On-Premise 구간)
    - 그룹사 간
    - 그룹사 내 도메인/사업부 간
    - 그룹사 - 그룹 공통망 간
      - Transit Vnet
      - ExpressRoute
        - On-premise Ingress Traffic
        - On-Premise Egress Traffic
        - Zone-redundant Virtual Network Gateways
  - DNS
    - 외부 DNS
      - DNS Health Cehck
      - DNS Failover
    - 내부 DNS
      - DNS Health Cehck
  - 로드밸런서
  - 연동 관리
    - 서비스 메쉬
    - API I/F
    - Proxy
    - Router
- 가상환경 (컴퓨팅, 스토리지, 데이터베이스)
  - VM
  - 컨테이너
  - 스토리지
    - 블록 스토리지
    - 오브젝트 스토리지
    - Queue 스토리지
  - 데이터베이스
    - RDBMS
    - NO SQL
    - Cache
      - Redis Cache
      - CDN
    - Streming Data
  - 캐쉬
    - CDN
    - Application Cache
  - Platform as a Service
    - Kunbernetes
      - Azure Kubernetes Services
        - Azure Kubernetes Registry
    - Azure Web App
    - Azure Monitor
    - Azure AKS
  - Software as a Service
    - Azure Functions
    - Azure Monitor
- 보안 장비
  - Azure Security Center
    - Microsoft Antimalware for Azure
    - Azure Sentinel
    - Azure Log Analytics
  - WAF
  - Firewall
  - Dos/DDos
  - IPS/IDS
  - 침해탐지

## 4.4 보안 프레임워크 

+ 개요
  + 그룹 보안 컨설팅 결과 반영 예정
  + 구성요소
+ 네트워크 보안
+ 키관리
  + Azure Key Vault (서비스)
  + 3rd Party Solutions
+ 암호화
+ Secret Management
+ 보안 모니터링
+ Administrator Access



## 4.5 자동화 프레임워크

+ 개요
+ Infrastructure as a Code
  + Terraform
  + Ansible
+ Git Repository
  + Gitlab
+ Bootstrp Process
+ 자동화 관리
  + 배치 및 스크립트
  + 백업
    + VM 백업
      + Azure VM Backup (기능)
      + Packer (솔루션)
    + Container 백업
      + Azure Container Registry (ACR 기능)
      + Packer
    + 스토리지 백업
    + 데이터 베이스 백업
  + DR 
    + Region 간 DR
    + On-premise DR
    + Site Recovery
  + 알람
    + 빌링 Trigger
    + 리소스 Trigger
    + Azure 패치
    + Azure 장애

## 4.6 모니터링 및 공통서비스

+ 개요

+ 로그 관리

  + 네트워크

  + VM
  + 미들웨어
  + 컨테이너
  + 스토리지
    + Queue 
  + 데이터 베이스

+ 접근제어
  + 계정 접근제어
  + VM
  + 컨테이너
  + 데이터 베이스
+ 보안
  + Security Management
    + Azure Security Center
    + Azure Sentinel
    + Azure Log Analytics
  + WAF
  + Firewall
  + Dos/DDos
  + IPS/IDS
  + 침해탐지
  + 트래픽 추적
    - Network Watcher
+ On-Premise 인터페이스

## 5. 비용

+ 리소스 비용
+ 테스트 비용
+ 기타 비용

## Appendix 1.  아키텍처 세부 표준

+ 리소스 네이밍
+ 리소스 태깅
  + 태깅 구조
  + 태깅 정책

<H2> Appendix 2. DevOps </H2> 

+ 

<H2> Appendix 3. Azure Limits </H2>

+ 

<H2> Appendix 4. 블라블라 </H2>

+ 



## Using the Provider
