---
title: flagger一款渐进式服务交付工具
date: 2024-04-26 14:18:39
tags: kubernetes
categories:
    - flagger
    - kubernetes
    - k8s
    - cd
---
flagger是一款渐进式交付工具，可以自动执行在Kubernetes上运行的应用程序的发布过程。同时通过在测量指标和运行一致性测试的同时逐渐将流量转移到新版本，降低了在生产环境中发布新版本的风险。
flagger支持使用服务网格(App Mesh、Istio、Linkerd、Kuma、Open Service Mesh)或入口控制器(Contour、Gloo、Nginx、Skipper、Traefik、APISix、Skipper)进行流量路由控制。对于发布分析，flagger可以通过查询Prometheus、InfluxDB、Datadog、New Relic、CloudWatch、Stackdriver 或 Graphite进行，同时支持通过Slack、Teams、Discord和Rocket发出警报。
![flagger overview diagram](https://docs.flagger.app/~gitbook/image?url=https%3A%2F%2Fraw.githubusercontent.com%2Ffluxcd%2Fflagger%2Fmain%2Fdocs%2Fdiagrams%2Fflagger-overview.png&width=768&dpr=4&quality=100&sign=01e4ea0d35cde2170f594858cda56bc29f098620808a195c6616ea867c28a405)
flagger通过kubernetes的crd进行任务定义，并基于operator进行事件处理，因此可以轻松集成到CI/CD管道中。