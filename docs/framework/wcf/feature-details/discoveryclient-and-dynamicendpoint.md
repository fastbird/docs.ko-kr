---
title: "DiscoveryClient 및 DynamicEndpoint | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# DiscoveryClient 및 DynamicEndpoint
<xref:System.ServiceModel.Discovery.DiscoveryClient> 및 <xref:System.ServiceModel.Discovery.DynamicEndpoint>는 클라이언트 측에서 서비스를 검색하는 데 사용되는 두 클래스입니다.<xref:System.ServiceModel.Discovery.DiscoveryClient>는 특정 조건 집합과 일치하는 서비스 목록을 제공하며 이를 통해 서비스에 연결할 수 있습니다.<xref:System.ServiceModel.Discovery.DynamicEndpoint>는 동일한 작업을 수행하는 것 이외에도 검색된 서비스 중 하나에 자동으로 연결합니다.모든 끝점을 <xref:System.ServiceModel.Discovery.DynamicEndpoint>로 만들 수 있고 구성을 통해 검색 조건을 추가할 수 있으므로 <xref:System.ServiceModel.Discovery.DynamicEndpoint>는 솔루션에서 검색을 수행해야 하지만 클라이언트 논리는 수정하지 않으려는 경우, 즉 끝점만 수정해야 하는 경우에 유용합니다.반면에 <xref:System.ServiceModel.Discovery.DiscoveryClient>는 검색 작업을 보다 세부적으로 제어하는 데 사용할 수 있습니다.각 클래스의 사용 방법과 이점은 아래에 자세히 설명되어 있습니다.  
  
## DiscoveryClient  
 <xref:System.ServiceModel.Discovery.DiscoveryClient>는 동기 및 비동기 Find 메서드와 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 및 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트를 정의하며,동기 및 비동기 Resolve 메서드와 <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> 이벤트도 정의합니다.<xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 또는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> 메서드를 사용하면 서비스를 검색할 수 있습니다.두 클래스는 모두 계약 형식 이름, 범위, 요청된 최대 결과 수 및 범위 일치 규칙을 지정할 수 있는 <xref:System.ServiceModel.Discovery.FindCriteria> 인스턴스를 사용합니다.<xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 및 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> 메서드를 호출할 때 사용할 수 있습니다.<xref:System.ServiceModel.Discovery.DiscoveryClient>가 서비스에서 응답을 수신할 때마다 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>가 발생합니다.이 이벤트는 찾기 작업의 진행률을 보여 주는 진행률 표시줄을 표시하는 데 사용할 수 있으며,찾기 응답이 수신될 때 찾기 응답을 처리하는 데도 사용할 수 있습니다.<xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 이벤트는 찾기 작업이 완료될 때 발생합니다.찾기 작업은 최대 응답 수에 도달했거나 <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>이 경과한 경우에 완료될 수 있습니다.찾기 작업이 완료되면 <xref:System.ServiceModel.Discovery.FindResponse> 인스턴스에 결과가 반환됩니다.<xref:System.ServiceModel.Discovery.FindResponse>에는 일치하는 서비스의 주소, 계약 형식 이름, 확장, 수신 대기 URI 및 범위가 들어 있는 <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>의 컬렉션이 포함됩니다.이 정보를 사용하면 일치하는 서비스 중 하나에 연결하고 이를 호출할 수 있습니다.다음 예제에서는 [the M:System.ServiceModel.Discovery.DiscoveryClient.Find\(System.ServiceModel.Discovery.FindCriteria\)](assetId:///the M:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)?qualifyHint=False&autoUpgrade=True) 메서드를 호출하고 반환된 메타데이터를 사용하여 찾은 서비스를 호출하는 방법을 보여 줍니다.<xref:System.ServiceModel.Discovery.DiscoveryClient>를 사용하면 찾은 끝점 목록을 캐시하고 나중에 이러한 끝점을 사용할 수 있다는 이점이 있습니다.이 캐시를 사용하면 사용자 지정 논리를 빌드하여 다양한 실패 조건을 처리할 수 있습니다.  
  
```  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
FindCriteria criteria = new FindCriteria(typeof(ICalculatorService));  
FindResponse fr = dc.Find(criteria);  
  
if (fr.Endpoints.Count > 0)  
{  
   EndpointAddress ep = fr.Endpoints[0].Address;  
   CalculatorServiceClient client = new CalculatorServiceClient();  
  
    // Connect to the discovered service endpoint  
   client.Endpoint.Address = endpointAddress;  
   Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
   double value1 = 100.00D;  
   double value2 = 15.99D;  
  
   // Call the Add service operation.  
   double result = client.Add(value1, value2);  
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
}  
else  
   Console.WriteLine(“No matching endpoints found”);  
  
```  
  
 다음 예제에서는 찾기 작업을 비동기적으로 수행하는 방법을 보여 줍니다.  
  
```  
static void FindServiceAsync()  
{  
   DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());   
   dc.FindCompleted += new EventHandler<FindCompletedEventArgs>( discoveryClient_FindCompleted);  
   dc.FindProgressChanged += new EventHandler<FindProgressChangedEventArgs>(discoveryClient_FindProgressChanged);  
   dc.FindAsync(new FindCriteria(typeof(ICalculatorService)));   
}   
static void discoveryClient_FindProgressChanged(object sender, FindProgressChangedEventArgs e)  
{  
   Console.WriteLine("Found service at: " + e.EndpointDiscoveryMetadata.Address  
}   
  
static void discoveryClient_FindCompleted(object sender, FindCompletedEventArgs e)  
{    
      if (e.Result.Endpoints.Count > 0)  
            {  
                EndpointAddress ep = e.Result.Endpoints[0].Address;  
                CalculatorServiceClient client = new CalculatorServiceClient();  
  
                // Connect to the discovered service endpoint  
                client.Endpoint.Address = ep;  
                Console.WriteLine("Invoking CalculatorService at {0}", ep);  
  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
            }  
            else  
                Console.WriteLine("No matching endpoints found");  
  
        }  
  
```  
  
 비동기 찾기 호출[!INCLUDE[crabout](../../../../includes/crabout-md.md)][비동기 찾기](../../../../docs/framework/wcf/samples/asynchronous-find-sample.md)을 참조하십시오.  
  
 <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> 및 <xref:System.ServiceModel.Discovery.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> 메서드를 사용하면 끝점 주소를 기반으로 서비스를 찾을 수 있습니다.이는 네트워크를 통해 끝점 주소에 액세스할 수 없는 경우에 유용합니다.Resolve 메서드는 <xref:System.ServiceModel.Discovery.ResolveCriteria>의 인스턴스를 사용하므로 확인할 서비스의 끝점 주소, 확인 작업의 최대 기간 및 확장 집합을 지정할 수 있습니다.다음 예제에서는 <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> 메서드를 사용하여 서비스를 확인하는 방법을 보여 줍니다.  
  
```  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
  
```  
  
## DynamicEndpoint  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>는 검색을 수행하고 일치하는 서비스를 자동으로 선택하는 표준 끝점입니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][표준 끝점](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)을 참조하십시오.검색할 계약과 사용할 바인딩을 전달하여 <xref:System.ServiceModel.Discovery.DynamicEndpoint>를 만들고 <xref:System.ServiceModel.Discovery.DynamicEndpoint> 인스턴스를 WCF 클라이언트에 전달합니다.다음 예제에서는 <xref:System.ServiceModel.Discovery.DynamicEndpoint>를 만들고 사용하여 계산기 서비스를 호출하는 방법을 보여 줍니다.검색은 클라이언트가 열릴 때마다 수행됩니다.구성에 정의된 끝점은 `kind =”dynamicEndpoint”` 특성을 끝점 구성 요소에 추가하여 <xref:System.ServiceModel.Discovery.DynamicEndpoint>로 만들 수 있습니다.  
  
```  
  
DynamicEndpoint dynamicEndpoint = new DynamicEndpoint(ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());  
CalculatorServiceClient client = new CalculatorServiceClient(dynamicEndpoint);  
  
Console.WriteLine("Invoking CalculatorService");  
Console.WriteLine();  
  
double value1 = 100.00D;  
double value2 = 15.99D;  
  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
## 참고 항목  
 [범위를 사용한 검색](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)   
 [비동기 찾기](../../../../docs/framework/wcf/samples/asynchronous-find-sample.md)   
 [Basic](../../../../docs/framework/wcf/samples/basic-sample.md)