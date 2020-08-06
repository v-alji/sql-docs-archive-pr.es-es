---
title: Llamar a métodos de servicio web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 87f1485b4e3c0ed064e42bb3b411fece96eba8d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745029"
---
# <a name="calling-web-service-methods"></a><span data-ttu-id="59779-102">Llamar a métodos de servicio web</span><span class="sxs-lookup"><span data-stu-id="59779-102">Calling Web Service Methods</span></span>
  <span data-ttu-id="59779-103">Cuando se usa una [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] clase de proxy para llamar a las operaciones del servicio Web, se hace con los métodos de esa clase.</span><span class="sxs-lookup"><span data-stu-id="59779-103">When you use a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class to call Web service operations, you do so by using the methods of that class.</span></span> <span data-ttu-id="59779-104">Estos métodos responden como cualquier otro de una clase de la biblioteca de clases de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59779-104">These methods respond like any other method of a class in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="59779-105">Todos los métodos de servicio web tienen acceso público y necesitan que se proporcione el número y tipos adecuados de argumentos.</span><span class="sxs-lookup"><span data-stu-id="59779-105">All Web service methods have public access and require you to supply the appropriate number of arguments and argument types.</span></span> <span data-ttu-id="59779-106">Después de crear una instancia de la clase de proxy en el proyecto, puede llamar a los métodos para realizar las operaciones del informe de errores a través del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="59779-106">After you have created an instance of the proxy class in your project, you can call the methods to perform reporting operations via the report server.</span></span> <span data-ttu-id="59779-107">En el código de C# siguiente se ilustra el uso del método <xref:ReportService2010.ReportingService2010.ListChildren%2A> de la clase de proxy de <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="59779-107">The following C# code illustrates the use of the <xref:ReportService2010.ReportingService2010.ListChildren%2A> method of the <xref:ReportService2010.ReportingService2010> proxy class.</span></span> <span data-ttu-id="59779-108">El código se utiliza para realizar una llamada recursiva al servicio web que devuelve una matriz de objetos <xref:ReportService2010.CatalogItem> que contiene una lista de todos los elementos de la base de datos del servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="59779-108">The code is used to make a recursive call to the Web service that returns an array of <xref:ReportService2010.CatalogItem> objects that contains a list of all items in the report server database:</span></span>  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a><span data-ttu-id="59779-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59779-109">See Also</span></span>  
 <span data-ttu-id="59779-110">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="59779-110">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="59779-111">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="59779-111">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="59779-112">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="59779-112">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
