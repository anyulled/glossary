---
title: 컨테이너화 (Containerization)
status: Completed
category: 기술
---

## 개념

컨테이너화(containerization)는 애플리케이션과 그 의존 요소들을 [컨테이너 이미지](/container-image/) 형태로 포장하는 것(bundling)을 의미한다. 컨테이너 빌드 프로세스는 [OCI(Open Container Initiative)](https://opencontainers.org) 표준을 준수해야 한다. 컨테이너화의 결과물이 이 표준을 준수하는 컨테이너 이미지이기만 한다면, 어떠한 컨테이너화 도구라도 사용할 수 있다.

## 다루는 문제

컨테이너가 보편화되기 전에는, 단일 [베어메탈 머신](/bare_metal_machine/) 상에 여러 애플리케이션을 오케스트레이션(orchestration) 하기 위해 가상 머신(VM)에 의존했다. VM은 컨테이너보다 훨씬 크며 이를 실행하기 위해 하이퍼바이저(hypervisor)를 필요로 한다. 상대적으로 크기가 큰 VM 템플릿(template)을 저장, 백업, 전송해야 하기 때문에, VM 템플릿을 생성하는 속도 또한 느리다. 추가적으로, VM은 [불변성(immutability)](/immutable_infrastructure/) 원칙에 위배되는 구성 변경(configuration drift) 문제를 겪을 수도 있다.

## 문제 해결 방식

컨테이너 이미지는 (전통적인 VM과 달리) 가볍고, 컨테이너화 프로세스에는 의존 요소 목록이 기재된 파일이 필요하다. 이 파일은 버전 관리될 수 있으며 빌드 과정은 자동화될 수 있으므로, 자동화 프로세스가 빌드를 처리하는 동안 다른 우선 순위에 집중할 수 있다. 컨테이너 이미지는 정확한 내용물 및 구성에 해당되는 고유 식별자를 사용하여 저장된다. 컨테이너가 스케줄링 및 재스케줄링될 때마다, 컨테이너는 처음 상태로 초기화되며, 이 덕분에 구성 변경 문제를 겪지 않는다.
