---
title: Establecer la propiedad Url del servicio web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Url property
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: 4eac4e40-dafb-4403-acde-13df317c8ec8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 08178ae66a7bb53d6f155e7410bbc7436e048212
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674622"
---
# <a name="setting-the-url-property-of-the-web-service"></a><span data-ttu-id="e14f2-102">Establecer la propiedad Url del servicio web</span><span class="sxs-lookup"><span data-stu-id="e14f2-102">Setting the Url Property of the Web Service</span></span>
  <span data-ttu-id="e14f2-103">En cualquier momento en las [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] aplicaciones, puede modificar la dirección URL base del servicio Web del servidor de informes a la que se dirige actualmente su aplicación.</span><span class="sxs-lookup"><span data-stu-id="e14f2-103">At any time in your [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] applications, you can modify the base URL of the Report Server Web service to which your application is currently directed.</span></span> <span data-ttu-id="e14f2-104">Para ello, basta con establecer la propiedad **Url** del objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="e14f2-104">To do this, simply set the **Url** property of the service object.</span></span> <span data-ttu-id="e14f2-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e14f2-105">For example:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx"  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx";  
```  
  
 <span data-ttu-id="e14f2-106">El ejemplo siguiente recupera una definición de informe de un servidor de informes y utiliza esa definición para crear un informe idéntico en un servidor de informes diferente:</span><span class="sxs-lookup"><span data-stu-id="e14f2-106">The following example retrieves a report definition from one report server and uses that definition to create an identical report on a different report server:</span></span>  
  
```vb  
Imports System  
Imports System.Web.Services.Protocols  
  
Class Sample  
   Public Shared Sub Main()  
      Dim rs As New ReportingService2010()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      ' Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx"  
  
      Dim reportName As String = "/SampleReports/Company Sales"  
      Dim reportDefinition As Byte() = Nothing  
  
      Try  
         ' Get the report definition of a report on a source server  
         reportDefinition = rs.GetItemDefinition(reportName)  
         ' Set the base Web service URL of the destination server  
         rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx"  
         ' Create a copy of the report on the destination server  
         Dim warnings As Warning() = {}  
         rs.CreateCatalogItem("Report", "Company Sales Copy", "/", False, reportDefinition, Nothing, warnings)        
      Catch e As SoapException  
         Console.WriteLine(e.Detail.InnerXml.ToString())  
      End Try  
   End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.Web.Services.Protocols;  
  
class Sample  
{  
   public static void Main()  
   {  
      ReportingService2010 rs = new ReportingService2010();  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      // Set the base Web service URL of the source server  
      rs.Url = "http://<Server Name>/reportserver/reportservice2010.asmx";  
  
      string reportName = "/SampleReports/Company Sales";  
      byte[] reportDefinition = null;  
  
      try  
      {  
         reportDefinition = rs.GetItemDefinition(reportName);  
         // Set the base Web service URL of the destination server  
         rs.Url = "http://<Server Name>/reportserver/ReportService2010.asmx";  
         // Create a copy of the report on the destination server  
         Warning[] warnings = {};  
         rs.CreateCatalogItem("Report", "Company Sales Copy", "/", false, reportDefinition, null, out warnings);  
      }  
  
      catch (SoapException e)  
      {  
         Console.WriteLine(e.Detail.InnerXml.ToString());   
      }  
   }  
}  
```  
  
 <span data-ttu-id="e14f2-107">Para más información sobre cómo crear el proxy del servicio web inicial, vea [Crear el proxy del servicio web](creating-the-web-service-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="e14f2-107">For more information about creating the initial Web service proxy, see [Creating the Web Service Proxy](creating-the-web-service-proxy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e14f2-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e14f2-108">See Also</span></span>  
 <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A>   
 <xref:ReportService2010.ReportingService2010.GetItemDefinition%2A>   
 <span data-ttu-id="e14f2-109">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="e14f2-109">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="e14f2-110">Servicio web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="e14f2-110">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
