@@@@es 설치
.env 파일을 클러스터 서버에 맞게 .env-00 파일과 교체하여 사용한다.
---

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

;
----------
javacafe 플러그인 설치(사내에서는 이 프로젝트에 이미 설치되어 있는 interpark-analyzer를 사용하므로 설치하지 않아도 됨)
https://github.com/javacafe-project/elasticsearch-plugin/releases
설치한 ES 버전과 같은 버전으로 다운로드 받는다
    * ES 버전이 7.0.0 이상일경우
    7.0.0을 다운받아 압축해제 후 plugin-descriptor.properties 파일을 열어 elasticsearch.version을 사용할 es버전으로 변경하여 저장하고
    디렉토리명의 버전을 변경된 ES 버전으로 변경한뒤 재압축한다.
javacafe-analyzer**.zip 파일을 컨테이너 내부에 복사를하고
"elasticsearch-plugin install file://{복사한 zip 파일 절대 경로}" 명령어로 설치를 진행한다.
"elasticsearch-plugin list" 명령어로 설치 확인하고
ES를 재시작한다.