@@@@es 설치


홈디렉토리(/ella/shop/)에 프로젝트 복사
홈디렉토리 777부여 ssdev:ssdev
----
docker-compose up -d
---
홈디렉토리 shop**-data 디렉토리 777, ssdev 부여
---
container restart
---
에러 발생시
max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

> vi /etc/sysctl.conf
추가 vm.max_map_count=262144
> sysctl -w vm.max_map_count=262144

///////////////////////////////////
@kibana
홈디렉토리에 프로젝트복사
777, ssdev:ssdev
-----------
docker-compose up -d

/////////////////////////////////

@logstash


홈디렉토리에 프로젝트 복사
777, ssdev:ssdev
----------
docker-compose up -d
