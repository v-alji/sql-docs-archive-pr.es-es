---
title: Instalación de PowerPivot para SharePoint 2010 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 8d47dde7-c941-4280-a934-e2fe3f9a938f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ba04dfdc69b1c510a800c062586e45f8873c8e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675710"
---
# <a name="powerpivot-for-sharepoint-2010-installation"></a><span data-ttu-id="8864d-102">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="8864d-102">PowerPivot for SharePoint 2010 Installation</span></span>
  [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] <span data-ttu-id="8864d-103">es una recopilación de componentes de servidor que permiten controlar la administración y el procesamiento de consultas para libros [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] que se publican en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8864d-103">is a collection of server components that provide query processing and management control over [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks that you publish to SharePoint.</span></span> <span data-ttu-id="8864d-104">Entre los servicios se incluyen el motor de Analysis Services y el Servicio de sistema de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8864d-104">Services include the Analysis Services engine and [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8864d-105">Para obtener información relacionada con [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] y la instalación con SharePoint Server 2013, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8864d-105">For information regarding [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] and installation with SharePoint Server 2013, see the following:</span></span>  
>   
>  -   <span data-ttu-id="8864d-106">La sección "SQL Server 2012 SP1" de [información general sobre la instalación de servicios de SQL Server](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span><span class="sxs-lookup"><span data-stu-id="8864d-106">The "SQL Server 2012 SP1" section of [Overview of SQL Server Servicing Installation](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span></span>  
  
 <span data-ttu-id="8864d-107">Analysis Services proporciona un procesamiento del lado servidor para los libros de Excel que contienen los datos de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8864d-107">Analysis Services provides server-side processing for Excel workbooks that contain [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span> <span data-ttu-id="8864d-108">El Servicio de sistema de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] funciona junto a Analysis Services, permite la integración de SharePoint, aporta el equilibrio de carga y permite la administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="8864d-108">[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service works alongside Analysis Services, adding SharePoint integration, load balancing and connection management.</span></span> [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]<span data-ttu-id="8864d-109">extiende Excel Services emparejando su capacidad de procesamiento de datos a gran escala con los servicios de representación de datos que proporciona Excel.</span><span class="sxs-lookup"><span data-stu-id="8864d-109">extends Excel Services by pairing its large scale data processing capability with the data rendering services that Excel provides.</span></span>  
  
 <span data-ttu-id="8864d-110">Para instalar [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use el disco de instalación de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8864d-110">To install [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]installation media.</span></span>  
  
 <span data-ttu-id="8864d-111">Para obtener instrucciones sobre escenarios de implementación avanzada, consulte lista de comprobación de la [implementación: Reporting Services, Power View y PowerPivot para SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) y [lista de comprobación de la implementación: escalado horizontal mediante la adición de servidores de PowerPivot a una granja de servidores de SharePoint 2010](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span><span class="sxs-lookup"><span data-stu-id="8864d-111">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Scale-out by adding PowerPivot Servers to a SharePoint 2010 farm](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8864d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8864d-112">In This Section</span></span>  
 [<span data-ttu-id="8864d-113">Instalar PowerPivot para SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="8864d-113">Install PowerPivot for SharePoint 2010</span></span>](../../../2014/sql-server/install/install-powerpivot-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="8864d-114">Instalar el proveedor OLE DB de Analysis Services en servidores de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8864d-114">Install the Analysis Services OLE DB Provider on SharePoint Servers</span></span>](../../../2014/sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md)  
  
 [<span data-ttu-id="8864d-115">Instalar ADOMD.NET en servidores front-end web ejecutando Administración central</span><span class="sxs-lookup"><span data-stu-id="8864d-115">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>](../../../2014/sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md)  
  
 [<span data-ttu-id="8864d-116">Instalar ADO.NET Data Services para admitir las exportaciones de fuentes de distribución de datos de las listas de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8864d-116">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>](../../../2014/sql-server/install/install-ado-net-data-services-to-support-data-feed-exports-of-sharepoint-lists.md)  
  
 [<span data-ttu-id="8864d-117">Instalar PowerPivot desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="8864d-117">Install PowerPivot from the Command Prompt</span></span>](../../../2014/sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
 [<span data-ttu-id="8864d-118">Desinstalar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="8864d-118">Uninstall PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/uninstall-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="8864d-119">Reparar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="8864d-119">Repair PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/repair-powerpivot-for-sharepoint.md)  
  
 [<span data-ttu-id="8864d-120">PowerPivot para SharePoint de &#40;de configuración inicial&#41;</span><span class="sxs-lookup"><span data-stu-id="8864d-120">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../../2014/sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
## <a name="see-also"></a><span data-ttu-id="8864d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8864d-121">See Also</span></span>  
 [<span data-ttu-id="8864d-122">Administración y configuración del servidor PowerPivot en Administración central</span><span class="sxs-lookup"><span data-stu-id="8864d-122">PowerPivot Server Administration and Configuration in Central Administration</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration)  
  
  
