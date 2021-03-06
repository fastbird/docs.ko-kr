---
title: "컨테이너 및 마이크로 서비스 기반 응용 프로그램 설계"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 컨테이너 및 마이크로 서비스 기반 응용 프로그램 설계"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 246605b301f6bcea4cced2cb7d1c494e9f66aa4a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="architecting-container--and-microservice-based-applications"></a>컨테이너 및 마이크로 서비스 기반 응용 프로그램 설계

*마이크로 서비스는 기존 아키텍처에 비해 다양한 이점이 있지만, 해결해야 할 새로운 과제도 있습니다. 마이크로 서비스 아키텍처 패턴은 마이크로 서비스 기반 응용 프로그램을 만들 때 중추적인 역할을 합니다.*

이 가이드의 초반부에서는 컨테이너와 Docker에 대한 기본 개념을 알아보았습니다. 이러한 개념은 컨테이너를 시작하는 데 필요한 최소한의 정보입니다. 컨테이너를 사용하면 마이크로 서비스를 제대로 구현할 수 있지만, 컨테이너는 마이크로 서비스 아키텍처의 필수 요소는 아니며 이 아키텍처 섹션의 대다수 아키텍처 개념은 컨테이너 없이도 적용할 수 있습니다. 그러나 이미 컨테이너의 중요성을 소개했으므로 이 참고 자료에서는 컨테이너와 Docker의 공통점을 집중적으로 알아보겠습니다.

엔터프라이즈 응용 프로그램은 복잡할 수 있으며 단일 서비스 기반 응용 프로그램 대신 여러 서비스로 구성된 경우가 많습니다. 이러한 경우 마이크로 서비스, 특정 DDD(도메인 기반 디자인) 패턴 및 컨테이너 오케스트레이션 개념과 같은 추가 아키텍처 접근 방법을 이해해야 합니다. 이 장에서는 컨테이너에서의 마이크로 서비스뿐만 아니라 컨테이너화된 응용 프로그램에 대해서도 설명합니다.

## <a name="container-design-principles"></a>컨테이너 디자인 원칙

컨테이너 모델에서 컨테이너 이미지 인스턴스는 단일 프로세스를 나타냅니다. 컨테이너 이미지를 프로세스 경계로 정의하여 프로세스 크기를 조정하거나 일괄 처리하는 데 사용할 수 있는 기본 형식을 만들 수 있습니다.

컨테이너 이미지를 디자인할 때 Dockerfile에서 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/) 정의가 표시됩니다. 이는 컨테이너의 수명을 제어하는 수명의 프로세스를 정의합니다. 프로세스가 완료되면 컨테이너 수명 주기가 종료됩니다. 컨테이너는 웹 서버와 같은 장기 실행 프로세스를 나타낼 수 있지만 이전에 Azure [WebJobs](https://docs.microsoft.com/azure/app-service-web/websites-webjobs-resources)로 구현되었을 수 있는 일괄 작업과 같은 단기 실행 프로세스를 나타낼 수도 있습니다.

프로세스에 실패할 경우 컨테이너가 종료되며 조정자가 이어서 프로세스를 진행합니다. 조정자가 5개의 인스턴스는 실행하고 1개는 실패하도록 구성된 경우 조정자는 실패한 프로세스를 바꾸기 위해 다른 컨테이너 인스턴스를 만듭니다. 일괄 작업에서 프로세스는 매개 변수와 함께 시작됩니다. 프로세스가 완료되면 작업이 완료됩니다. 이 설명서의 뒷부분에서는 오케스트레이터에 대해 자세히 설명합니다.

여러 프로세스를 단일 컨테이너에서 실행하려는 시나리오가 발생할 수 있습니다. 이러한 시나리오의 경우 컨테이너 1개당 진입점 1개만 허용되므로 필요에 따라 가능한 한 많은 프로그램을 시작하는 컨테이너에서 스크립트를 실행할 수 있습니다. 예를 들어 [감독자](http://supervisord.org/) 또는 비슷한 도구를 사용하여 단일 컨테이너 내에서 여러 프로세스를 시작하는 것을 관리할 수 있습니다. 그러나 컨테이너당 여러 프로세스를 실행하는 아키텍처를 확인할 수 있을지라도 이러한 접근 방식은 매우 일반적인 방법이 아닙니다.


>[!div class="step-by-step"]
[이전] (../net-core-net-framework-containers/official-net-docker-images.md) [다음] (containerize-monolithic-applications.md)
