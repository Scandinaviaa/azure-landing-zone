# 1. Landing-Zone의 정의
퍼블릭 클라우드(AWS, Azure, GCP 등)의 자동화 구현 및 관리를 위한 템플릿으로써, 표준아키텍처를 기반으로 각 영역 별 코드로 구성 한다.

본 Repository 에서는 Azure용 Landing-Zone 구현을 설명한다.


# 2.필요조건
  <H3>2.1 Terraform 설치는 다음 링크를 참조한다.  </H3>
[https://sarc.io/index.php/cloud/1743-linux-terraform-installation]  

# 3. Infrastructure Diagram  
![iso27001-ase-sql-workload-blueprint-sample-design](https://user-images.githubusercontent.com/30038150/75132423-32b96b00-571a-11ea-8c1a-0a0870720862.png)  
![02_hubspoke4](https://user-images.githubusercontent.com/30038150/75123212-d853e680-56e8-11ea-8c40-330ba8050592.png)  

ISO-27001

# 4. Azure Policy
3.1 Azure Subscription  

3.2 Azure Resource Group  
리소스 그룹- Azure 솔루션의 관련 리소스를 보관하는 컨테이너입니다. 리소스 그룹에 솔루션의 모든 리소스를 포함할 수도 있고 그룹으로 관리할 리소스만 포함할 수도 있습니다. 무엇이 조직에 가장 적합한지에 따라 리소스 그룹에 리소스를 할당할 방법을 결정합니다.  

3.1 계정 관리 - Azure Resource Group (리소스 그룹 관리)  
![Azure Line of Business](https://user-images.githubusercontent.com/30038150/75131075-9fca0200-5714-11ea-9e6c-5489c7049363.png)

  3.1.1 유저  
  3.1.1 그룹  
3.2 식별 및 접근관리 (IAM - Identity and Access Management)  
3.3 인증관리
3.3 보안 및 거버넌스 관리
3.4 로그 관리
3.5 네트워크
3.6 공통서비스  
  3.6.1 네트워크 모니터링, 인프라 모니터링, 알람, 어플리케이션, 시스템
  3.6.2 
3.7 컨테이너 관리
3.8 자동화 관리
3.9 배치
3.10 백업
3.11 스크립트 관리
3.12 키 관리
3.13 DNS 관리
3.10 인프라 관리
3.10 배포
3.10 백업  
3.11 인터페이스 관리
3.12 운영환경
3.13 개발환경  
3.14 QA환경  
3.15 샌드박스 환경  



# Developing the Provider


# Using the Provider
