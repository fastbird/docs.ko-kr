---
title: "SQL Server에서 인증"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e3b597d04ee53a094d9c50dff406f57e5fd57b00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="authentication-in-sql-server"></a>SQL Server에서 인증
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서는 Windows 인증 모드와 혼합 모드의 두 가지 인증 모드를 지원합니다.  
  
-   Windows 인증은 기본 인증이며 흔히 통합 보안이라고 하는데, 그 이유는 이 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 보안 모델이 Windows와 긴밀하게 통합되기 때문입니다. 이 보안 모델에서는 특정 Windows 사용자 및 그룹 계정에 SQL Server에 로그인할 수 있는 권한을 부여합니다. 이미 인증된 Windows 사용자는 추가 자격 증명을 제공할 필요가 없습니다.  
  
-   혼합 모드에서는 Windows 인증과 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 인증을 모두 지원하며 사용자 이름 및 암호 쌍이 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 내에서 유지 관리됩니다.  
  
> [!IMPORTANT]
>  가급적 Windows 인증을 사용하는 것이 좋습니다. Windows 인증은 일련의 암호화된 메시지를 사용하여 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서 사용자를 인증합니다. [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 로그인을 사용하는 경우 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 로그인 이름과 암호가 네트워크를 통해 전달되므로 Windows 인증에 비해 보안이 떨어집니다.  
  
 Windows 인증을 사용하는 경우 사용자가 Windows에 이미 로그온되어 있으므로 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에 별도로 로그온할 필요가 없습니다. 다음 `SqlConnection.ConnectionString`은 사용자 이름이나 암호를 제공할 필요가 없는 Windows 인증을 지정합니다.  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  로그인은 데이터베이스 사용자와는 다른 개념입니다. 따라서 로그인이나 Windows 그룹을 데이터베이스 사용자나 역할에 매핑하는 작업을 별도로 수행해야 합니다. 그런 다음 데이터베이스 개체에 액세스할 수 있도록 사용자나 역할에 권한을 부여합니다.  
  
## <a name="authentication-scenarios"></a>인증 시나리오  
 일반적으로 Windows 인증은 다음과 같은 환경에서 가장 적합합니다.  
  
-   도메인 컨트롤러가 있는 경우  
  
-   응용 프로그램과 데이터베이스가 동일한 컴퓨터에 있는 경우  
  
-   [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express 또는 LocalDB의 인스턴스를 사용하는 경우  
  
 SQL Server 로그인은 대개 다음과 같은 환경에서 사용합니다.  
  
-   작업 그룹이 있는 경우  
  
-   사용자가 신뢰할 수 없는 여러 도메인에서 연결하는 경우  
  
-   [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]과 같은 인터넷 응용 프로그램  
  
> [!NOTE]
>  Windows 인증을 지정하더라도 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 로그인이 비활성화되지는 않습니다. 따라서 ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 문을 사용하여 높은 수준의 권한이 있는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 로그인을 비활성화해야 합니다.  
  
## <a name="login-types"></a>로그인 유형  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서는 세 가지 유형의 로그인을 지원합니다.  
  
-   로컬 Windows 사용자 계정 또는 신뢰할 수 있는 도메인 계정. [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]는 Windows를 통해 Windows 사용자 계정을 인증합니다.  
  
-   Windows 그룹. Windows 그룹에 권한을 부여하면 해당 그룹에 속한 모든 Windows 사용자 로그인에도 동일한 권한이 부여됩니다.  
  
-   [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 로그인. [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서는 사용자 이름과 암호 해시를 모두 master 데이터베이스에 저장하고, 내부 인증 방법을 사용하여 로그인 시도가 유효한지 검사합니다.  
  
> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서는 코드 서명에만 사용되는 인증서 또는 비대칭 키에서 만들어진 로그인을 제공합니다. 이러한 로그인은 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에 연결하는 데 사용할 수 없습니다.  
  
## <a name="mixed-mode-authentication"></a>혼합 모드 인증  
 불가피하게 혼합 모드 인증을 사용하는 경우 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 로그인을 만들어야 합니다. 이 로그인은 SQL Server에 저장됩니다. 그런 다음 런타임에 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 사용자 이름과 암호를 제공해야 합니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]("system administrator"의 약어)라는 `sa` 로그인으로 설치됩니다. 따라서 `sa` 로그인에는 강력한 암호를 지정해야 하고 응용 프로그램에는 `sa` 로그인을 사용하지 않아야 합니다. `sa` 로그인은 전체 서버에 대해 취소할 수 없는 관리 자격 증명을 가지는 `sysadmin` 고정 서버 역할에 매핑됩니다. 따라서 공격자가 sa(시스템 관리자)로 액세스할 경우 입을 수 있는 피해는 상상을 초월합니다. Windows `BUILTIN\Administrators` 그룹(로컬 관리자 그룹)의 모든 멤버는 기본적으로 `sysadmin` 역할의 멤버이지만 이 역할에서 멤버를 제거할 수 있습니다.  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 이상 버전에서 실행되는 경우 [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] 로그인에 사용할 수 있는 Windows 암호 정책 메커니즘이 도입되었습니다. 암호 복잡성 정책은 가능한 암호의 수를 늘려 무차별 암호 대입 공격(brute force attack)을 방지하도록 설계되었습니다. [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에서는 [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)]에서 사용되는 것과 동일한 복잡성 및 만료 정책을 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 내부에 사용되는 암호에 적용할 수 있습니다.  
  
> [!IMPORTANT]
>  사용자 입력의 연결 문자열 연결로 인해 문자열 삽입 공격에 노출될 수 있습니다. <xref:System.Data.SqlClient.SqlConnectionStringBuilder>를 사용하면 런타임에 구문상 유효한 연결 문자열을 만들 수 있습니다. 자세한 내용은 참조 [연결 문자열 작성기](../../../../../docs/framework/data/adonet/connection-string-builders.md)합니다.  
  
## <a name="external-resources"></a>외부 리소스  
 자세한 내용은 다음 리소스를 참조하세요.  
  
|리소스|설명|  
|--------------|-----------------|  
|[보안 주체](http://msdn.microsoft.com/library/bb543165.aspx) 에 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서|[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]의 로그인 및 기타 보안 주체에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 응용 프로그램 보안](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server의 응용 프로그램 보안 시나리오](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [데이터 소스에 연결](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [연결 문자열](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
