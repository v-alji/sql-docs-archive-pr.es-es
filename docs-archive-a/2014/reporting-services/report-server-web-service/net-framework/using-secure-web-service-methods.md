---
title: Usar métodos de servicio web seguros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], secure connections
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: 87329299-c2ea-4517-9148-d855726768a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e88a164602f9bbe6ad42c3897285a484cac94466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749069"
---
# <a name="using-secure-web-service-methods"></a><span data-ttu-id="8efd4-102">Usar métodos de servicio web seguros</span><span class="sxs-lookup"><span data-stu-id="8efd4-102">Using Secure Web Service Methods</span></span>
  <span data-ttu-id="8efd4-103">Ciertos métodos de servicio web del servidor de informes pueden requerir una conexión segura al invocarlos.</span><span class="sxs-lookup"><span data-stu-id="8efd4-103">Certain Report Server Web service methods may require a secure connection when you invoke them.</span></span> <span data-ttu-id="8efd4-104">La opción `SecureConnectionLevel` determina los métodos que requieren una conexión segura en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="8efd4-104">The methods that require a secure connection are determined by the `SecureConnectionLevel` setting in the RSReportServer.config file.</span></span> <span data-ttu-id="8efd4-105">El valor de esta opción es un número entero comprendido entre 0 y superior.</span><span class="sxs-lookup"><span data-stu-id="8efd4-105">The value of the setting is an integer value with a valid range of 0 and higher.</span></span> <span data-ttu-id="8efd4-106">Estos valores se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="8efd4-106">The following table describes these values.</span></span>  
  
|<span data-ttu-id="8efd4-107">Nivel</span><span class="sxs-lookup"><span data-stu-id="8efd4-107">Level</span></span>|<span data-ttu-id="8efd4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8efd4-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8efd4-109">**0**</span><span class="sxs-lookup"><span data-stu-id="8efd4-109">**0**</span></span>|<span data-ttu-id="8efd4-110">Sin seguridad.</span><span class="sxs-lookup"><span data-stu-id="8efd4-110">Not secure.</span></span> <span data-ttu-id="8efd4-111">Las llamadas realizadas a la API SOAP de Reporting Services no requieren una conexión segura.</span><span class="sxs-lookup"><span data-stu-id="8efd4-111">Calls made to the Reporting Services SOAP API do not require a secure connection.</span></span>|  
|<span data-ttu-id="8efd4-112">Mayor que **0**</span><span class="sxs-lookup"><span data-stu-id="8efd4-112">Greater than **0**</span></span>|<span data-ttu-id="8efd4-113">Seguro.</span><span class="sxs-lookup"><span data-stu-id="8efd4-113">Secure.</span></span> <span data-ttu-id="8efd4-114">Todas las llamadas realizadas a la API SOAP de Reporting Services requieren una conexión segura.</span><span class="sxs-lookup"><span data-stu-id="8efd4-114">All calls made to the Reporting Services SOAP API require a secure connection.</span></span>|  
  
 <span data-ttu-id="8efd4-115">Puede utilizar el método <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> del servicio web para devolver una lista de los métodos del servicio web que requieren una conexión segura según la configuración actual del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8efd4-115">You can use the <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> method of the Web service to return a list of Web service methods that require a secure connection according to the current configuration of the report server.</span></span> <span data-ttu-id="8efd4-116">En un escenario SSL, debería evaluar la lista de métodos que devuelve <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> y cambiar el nombre de esquema de URI del servicio web por "https" o "http", según el método que se vaya a llamar.</span><span class="sxs-lookup"><span data-stu-id="8efd4-116">In an SSL scenario, you should evaluate the list of methods that are returned by <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> and change the scheme name of the Web service URI to "https" or "http" depending on the method being called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efd4-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8efd4-117">See Also</span></span>  
 <span data-ttu-id="8efd4-118">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="8efd4-118">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="8efd4-119">Servicio web del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="8efd4-119">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
