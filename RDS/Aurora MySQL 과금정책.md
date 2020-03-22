Amazon Aurora Mysql을 사용하며 발생한 과금 정책 파악
(POC용 클러스터로 2GB의 매우 작은 Storage 이용중)

## DB Instance Specification
* db.t3.small(2vCPU, 2GB RAM)
* mysql 5.6.10a

#### 1. Amazon Aurora Storage and I/O
* USD 0.12 per GB-month of consumed storage for Aurora MySQL  
-> DB에 저장된 Storage의 총합을 계산 하는 것으로 확인(저장된 용량과는 다른 것을 확인)  
-> Provisioning
* USD 0.24 per 1 million I/O requests for Aurora MySQL  
-> 백만 I/O당 0.24$

#### 2. Amazon Relational Database Service for Aurora MySQL
* USD 0.023 per GB-month of backup storage exceeding free allocation for Aurora MySQL  
-> Backup Storage의 무료 할당 용량을 초과하는 GB당 과금
* USD 0.063 per db.t3.small Single-AZ instance hour (or partial hour) running Aurora MySQL  
-> Instance Tier에 따른 Instance 구동 시간
