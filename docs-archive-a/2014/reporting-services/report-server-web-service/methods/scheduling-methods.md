---
title: Métodos de programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- schedules [Reporting Services], methods
- reports [Reporting Services], scheduling
- shared schedules [Reporting Services], methods
- methods [Reporting Services], scheduling
ms.assetid: 68ae13f9-d91e-4572-a82a-8fa42001569e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 735da4f22d523fd40dd031f55e203fa9a4204f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663894"
---
# <a name="scheduling-methods"></a><span data-ttu-id="e7197-102">Métodos de programación</span><span class="sxs-lookup"><span data-stu-id="e7197-102">Scheduling Methods</span></span>
  <span data-ttu-id="e7197-103">Puede utilizar estos métodos para crear y administrar las programaciones compartidas para la ejecución y la entrega de informes, así como para almacenar en memoria caché los planes de actualización que utiliza el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e7197-103">You can use these methods to create and manage shared schedules for report execution and delivery, and to cache refresh plans utilized by the report server.</span></span>  
  
|<span data-ttu-id="e7197-104">Método</span><span class="sxs-lookup"><span data-stu-id="e7197-104">Method</span></span>|<span data-ttu-id="e7197-105">Acción</span><span class="sxs-lookup"><span data-stu-id="e7197-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateCacheRefreshPlan%2A>|<span data-ttu-id="e7197-106">Crea un plan de actualización de caché para un elemento.</span><span class="sxs-lookup"><span data-stu-id="e7197-106">Creates a cache refresh plan for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateSchedule%2A>|<span data-ttu-id="e7197-107">Crea una nueva programación compartida.</span><span class="sxs-lookup"><span data-stu-id="e7197-107">Creates a new shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteCacheRefreshPlan%2A>|<span data-ttu-id="e7197-108">Elimina un plan de actualización de caché.</span><span class="sxs-lookup"><span data-stu-id="e7197-108">Deletes a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteSchedule%2A>|<span data-ttu-id="e7197-109">Elimina una programación compartida según un identificador de programación concreto.</span><span class="sxs-lookup"><span data-stu-id="e7197-109">Deletes a shared schedule based on a specific schedule ID.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheRefreshPlanProperties%2A>|<span data-ttu-id="e7197-110">Devuelve las propiedades del plan de actualización de caché especificado.</span><span class="sxs-lookup"><span data-stu-id="e7197-110">Returns the properties of the specified cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetScheduleProperties%2A>|<span data-ttu-id="e7197-111">Devuelve los valores de las propiedades de una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="e7197-111">Returns the values of properties of a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListCacheRefreshPlans%2A>|<span data-ttu-id="e7197-112">Devuelve una lista de los planes de actualización de memoria caché asociada a un elemento de catálogo.</span><span class="sxs-lookup"><span data-stu-id="e7197-112">Returns a list of the cache refresh plans associated with a catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduledItems%2A>|<span data-ttu-id="e7197-113">Devuelve una lista de los elementos que están asociados a una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="e7197-113">Returns a list of items that are associated with a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSchedules%2A>|<span data-ttu-id="e7197-114">Devuelve una lista de todas las programaciones compartidas en el servidor de informes o el sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e7197-114">Returns a list of all shared schedules at the report server or the SharePoint site.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduleStates%2A>|<span data-ttu-id="e7197-115">Devuelve una lista de estados de programación admitidos.</span><span class="sxs-lookup"><span data-stu-id="e7197-115">Returns a list of supported schedule states.</span></span>|  
|<xref:ReportService2010.ReportingService2010.PauseSchedule%2A>|<span data-ttu-id="e7197-116">Pausa la ejecución de una programación determinada.</span><span class="sxs-lookup"><span data-stu-id="e7197-116">Pauses the execution of a given schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ResumeSchedule%2A>|<span data-ttu-id="e7197-117">Reanuda una programación compartida que se ha pausado.</span><span class="sxs-lookup"><span data-stu-id="e7197-117">Resumes a shared schedule that has been paused.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheRefreshPlanProperties%2A>|<span data-ttu-id="e7197-118">Establece las propiedades de un plan de actualización de caché.</span><span class="sxs-lookup"><span data-stu-id="e7197-118">Sets the properties of a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetScheduleProperties%2A>|<span data-ttu-id="e7197-119">Establece el valor de las propiedades de una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="e7197-119">Sets the value of properties of a shared schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7197-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7197-120">See Also</span></span>  
 <span data-ttu-id="e7197-121">[Creación de aplicaciones con el servicio web y .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="e7197-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="e7197-122">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="e7197-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="e7197-123">[Métodos del servicio web del servidor de informes](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="e7197-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="e7197-124">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e7197-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
