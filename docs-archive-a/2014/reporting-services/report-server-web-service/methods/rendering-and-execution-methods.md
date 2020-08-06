---
title: Métodos de representación y ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0bc793e9a18e993989563fd3526ff12272f775c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747971"
---
# <a name="rendering-and-execution-methods"></a><span data-ttu-id="f3f86-102">Métodos de representación y ejecución</span><span class="sxs-lookup"><span data-stu-id="f3f86-102">Rendering and Execution Methods</span></span>
  <span data-ttu-id="f3f86-103">Puede utilizar estos métodos para administrar la ejecución de elementos, el almacenamiento en memoria caché y la representación de informes.</span><span class="sxs-lookup"><span data-stu-id="f3f86-103">You can use these methods to manage item execution and caching, and report rendering.</span></span>  
  
|<span data-ttu-id="f3f86-104">Método</span><span class="sxs-lookup"><span data-stu-id="f3f86-104">Method</span></span>|<span data-ttu-id="f3f86-105">Acción</span><span class="sxs-lookup"><span data-stu-id="f3f86-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|<span data-ttu-id="f3f86-106">Invalida la memoria caché para un elemento.</span><span class="sxs-lookup"><span data-stu-id="f3f86-106">Invalidates the cache for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|<span data-ttu-id="f3f86-107">Devuelve la configuración de la memoria caché para un elemento y la configuración que describe cuándo expira la copia del elemento en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="f3f86-107">Returns the cache configuration for an item and the settings that describe when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|<span data-ttu-id="f3f86-108">Devuelve la opción de ejecución y los valores asociados para un elemento individual.</span><span class="sxs-lookup"><span data-stu-id="f3f86-108">Returns the execution option and associated settings for an individual item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|<span data-ttu-id="f3f86-109">Devuelve una lista de valores de ejecución admitidos.</span><span class="sxs-lookup"><span data-stu-id="f3f86-109">Returns a list of supported execution settings.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|<span data-ttu-id="f3f86-110">Procesa el informe especificado y lo representa en un formato especificado.</span><span class="sxs-lookup"><span data-stu-id="f3f86-110">Processes the specified report and renders it in a specified format.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|<span data-ttu-id="f3f86-111">Configura un elemento para el almacenamiento en memoria caché y proporciona la configuración que especifica cuándo expira la copia del elemento en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="f3f86-111">Configures an item to be cached and provides settings that specify when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|<span data-ttu-id="f3f86-112">Establece las opciones de ejecución y las propiedades de ejecución asociadas para un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="f3f86-112">Sets execution options and associated execution properties for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|<span data-ttu-id="f3f86-113">Genera una instantánea de ejecución de elemento para un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="f3f86-113">Generates an item execution snapshot for a specified item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3f86-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3f86-114">See Also</span></span>  
 <span data-ttu-id="f3f86-115">[Creación de aplicaciones con el servicio web y .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="f3f86-115">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="f3f86-116">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="f3f86-116">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="f3f86-117">[Métodos del servicio web del servidor de informes](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="f3f86-117">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="f3f86-118">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f3f86-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
