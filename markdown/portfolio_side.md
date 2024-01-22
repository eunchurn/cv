-   DAQ 데이터 브로커 앱 개발

    -   개발 기간: 2주

    -   개발 인원: 1명

    -   개발한 서비스

        -   실시간 센서 모니터링을 위한 DAQ 브로커

        -   NI LabVIEW 데이터 파서

        -   개발 스택: NI LabVIEW, TypeScript, Docker, NextJS

-   SHM 플랫폼 개발

    -   개발 기간: 1년

    -   개발 인원: 4명 (센서 및 장비설치 1인, 백엔드 1인, 프론트 1인,
        디자이너 1인)

    -   개발한 서비스

        -   실시간 센서 데이터 송수신 Worker 개발: Redis, InfluxDB,
            Minio

        -   실시간 센서 데이터 차트

        -   히스토리 데이터 차트: 데이터 구간별 차트 Resampling

        -   이벤트 리스트 및 이벤트 알림

    -   인프라 구성

        -   Bare metal 쿠버네티스 클러스터 구성: PostgreSQL, Prometheus,
            Grafana, NginX, Cert-manager, InfluxDB, Deployment(Web,
            Worker, API)

        -   인프라 관리: OpenLens

        -   배포 파이프라인: Github Action, Github container registry,
            ArgoCD

    -   개발 스택:

        -   Turbo Repo, TypeScript, NextJS(App router), Apollo Server,
            Paljs, Nexus GraphQL, MQTTjs, Redis 등

<figure>
<div class="fullwidth">
<img src="images/nvcshm-auth.png" style="width:35.0%" />
<img src="images/nvcshm-map.png" style="width:35.0%" />
<img src="images/nvcshm-building.png" style="width:35.0%" />
<img src="images/nvcshm-sensors.png" style="width:35.0%" />
<img src="images/nvcshm-sensor-realtime.png" style="width:35.0%" />
<img src="images/nvcshm-events.png" style="width:35.0%" />
<img src="images/nvcshm-event-detail.png" style="width:35.0%" />
<img src="images/nvcshm-history-list.png" style="width:35.0%" />
<img src="images/nvcshm-history-1hr.png" style="width:35.0%" />
<img src="images/nvcshm-history-24hr.png" style="width:35.0%" />
<img src="images/nvcshm-history-1w.png" style="width:35.0%" />
<img src="images/nvcshm-history-1m.png" style="width:35.0%" />
</div>
<figcaption>History past 1 Month</figcaption>
</figure>
