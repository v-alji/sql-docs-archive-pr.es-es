---
title: Orígenes de datos y métodos de conexión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- connections [Reporting Services], data sources
- reports [Reporting Services], data
- data sources [Reporting Services], methods
ms.assetid: 50999b52-fc7c-4333-9fb0-d04c37a4c90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29dd8dd1c002ab3b7d4594a4e25ec44bdb2cc8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747978"
---
# <a name="data-sources-and-connection-methods"></a><span data-ttu-id="97dce-102">Orígenes de datos y métodos de conexión</span><span class="sxs-lookup"><span data-stu-id="97dce-102">Data Sources and Connection Methods</span></span>
  <span data-ttu-id="97dce-103">Puede utilizar estos métodos para establecer y administrar las credenciales y las conexiones a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="97dce-103">You can use these methods to set and manage data source connections and credentials.</span></span>  
  
|<span data-ttu-id="97dce-104">Método</span><span class="sxs-lookup"><span data-stu-id="97dce-104">Method</span></span>|<span data-ttu-id="97dce-105">Acción</span><span class="sxs-lookup"><span data-stu-id="97dce-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataSource%2A>|<span data-ttu-id="97dce-106">Crea un nuevo origen de datos en la base de datos del servidor de informes o biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="97dce-106">Creates a new data source in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DisableDataSource%2A>|<span data-ttu-id="97dce-107">Deshabilita un origen de datos que está habilitado.</span><span class="sxs-lookup"><span data-stu-id="97dce-107">Disables a data source that is enabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.EnableDataSource%2A>|<span data-ttu-id="97dce-108">Habilita un origen de datos que está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="97dce-108">Enables a data source that is disabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetDataSourceContents%2A>|<span data-ttu-id="97dce-109">Devuelve el contenido de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="97dce-109">Returns the contents of a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSourcePrompts%2A>|<span data-ttu-id="97dce-110">Obtiene los mensajes del origen de datos para un elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="97dce-110">Gets the data source prompts for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSources%2A>|<span data-ttu-id="97dce-111">Devuelve los orígenes de datos para un elemento del catálogo.</span><span class="sxs-lookup"><span data-stu-id="97dce-111">Returns the data sources for an item in the catalog.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListDependentItems%2A>|<span data-ttu-id="97dce-112">Devuelve una lista de elementos de catálogo que hacen referencia a un elemento de catálogo especificado.</span><span class="sxs-lookup"><span data-stu-id="97dce-112">Returns a list of catalog items that reference a specified catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptionsUsingDataSource%2A>|<span data-ttu-id="97dce-113">Devuelve una lista de suscripciones que están asociadas a un origen de datos determinado.</span><span class="sxs-lookup"><span data-stu-id="97dce-113">Returns a list of subscriptions that are associated with a given data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetDataSourceContents%2A>|<span data-ttu-id="97dce-114">Establece las propiedades de conexión que están asociadas a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="97dce-114">Sets the connection properties that are associated with a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemDataSources%2A>|<span data-ttu-id="97dce-115">Establece los orígenes de datos para un elemento en una base de datos del servidor de informes o biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="97dce-115">Sets the data sources for an item in a report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForDataSourceDefinition%2A>|<span data-ttu-id="97dce-116">Prueba la conexión para un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="97dce-116">Tests the connection for a data source.</span></span> <span data-ttu-id="97dce-117">Este método admite las pruebas directas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="97dce-117">This method supports the direct testing of the data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForItemDataSource%2A>|<span data-ttu-id="97dce-118">Prueba la conexión para un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="97dce-118">Tests the connection for a data source.</span></span> <span data-ttu-id="97dce-119">Este método admite las pruebas de los orígenes de datos publicados que son utilizados por los informes o modelos, y por orígenes de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="97dce-119">This method supports the testing of published data sources that are used by reports or models and shared data sources.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97dce-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97dce-120">See Also</span></span>  
 <span data-ttu-id="97dce-121">[Creación de aplicaciones con el servicio web y .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="97dce-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="97dce-122">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="97dce-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="97dce-123">[Métodos del servicio web del servidor de informes](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="97dce-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="97dce-124">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="97dce-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
