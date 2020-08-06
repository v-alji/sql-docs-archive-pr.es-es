---
title: No se pudo cargar el archivo o ensamblado &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39; | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6e350b67-5e18-4b90-8fb7-a0109cbb27b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: b7ba75bdbd8e25f98d11d822c22fa7881352ad88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675580"
---
# <a name="could-not-load-file-or-assembly-39microsoftanalysisservicessharepointintegration39"></a><span data-ttu-id="d03f7-102">No se pudo cargar el archivo o ensamblado &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39;</span><span class="sxs-lookup"><span data-stu-id="d03f7-102">Could not load file or assembly &#39;Microsoft.AnalysisServices.SharePoint.Integration&#39;</span></span>
  <span data-ttu-id="d03f7-103">En entornos de SharePoint 2010 que tienen PowerPivot para SharePoint, este error se producirá si la solución del nivel de aplicación para PowerPivot no se implementó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d03f7-103">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if the application-level solution for PowerPivot did not deploy correctly.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d03f7-104">Detalles</span><span class="sxs-lookup"><span data-stu-id="d03f7-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d03f7-105">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d03f7-105">Applies to</span></span>|<span data-ttu-id="d03f7-106">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="d03f7-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="d03f7-107">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d03f7-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="d03f7-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d03f7-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="d03f7-109">Causa</span><span class="sxs-lookup"><span data-stu-id="d03f7-109">Cause</span></span>|<span data-ttu-id="d03f7-110">La solución Powerpivotwebapp no está implementada o no se implementó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d03f7-110">Powerpivotwebapp solution is not deployed or did not deploy correctly.</span></span>|  
|<span data-ttu-id="d03f7-111">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d03f7-111">Message Text</span></span>|<span data-ttu-id="d03f7-112">No se pudo cargar el archivo o ensamblado 'Microsoft.AnalysisServices.SharePoint.Integration'</span><span class="sxs-lookup"><span data-stu-id="d03f7-112">Could not load file or assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d03f7-113">Explicación</span><span class="sxs-lookup"><span data-stu-id="d03f7-113">Explanation</span></span>  
 <span data-ttu-id="d03f7-114">PowerPivot para SharePoint utiliza paquetes de soluciones para implementar sus características en un servidor de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d03f7-114">PowerPivot for SharePoint uses solution packages to deploy its features on a SharePoint server.</span></span> <span data-ttu-id="d03f7-115">Una de las soluciones no se implementó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d03f7-115">One of the solutions is not deployed correctly.</span></span> <span data-ttu-id="d03f7-116">Como resultado, este error aparece siempre que se intenta abrir la Galería de PowerPivot u otras páginas de aplicaciones de PowerPivot en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d03f7-116">As a result, this error appears whenever you try to open PowerPivot Gallery or other PowerPivot application pages on a SharePoint site.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d03f7-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d03f7-117">User Action</span></span>  
 <span data-ttu-id="d03f7-118">Implementar el paquete de soluciones.</span><span class="sxs-lookup"><span data-stu-id="d03f7-118">Deploy the solution package.</span></span>  
  
1.  <span data-ttu-id="d03f7-119">En Administración central, en Configuración del sistema, haga clic en **Administrar soluciones del conjunto de servidores**.</span><span class="sxs-lookup"><span data-stu-id="d03f7-119">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="d03f7-120">Haga clic en **Powerpivotwebapp**.</span><span class="sxs-lookup"><span data-stu-id="d03f7-120">Click **Powerpivotwebapp**.</span></span>  
  
3.  <span data-ttu-id="d03f7-121">Haga clic en **Implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="d03f7-121">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="d03f7-122">Elija la aplicación web con la que se está produciendo este error.</span><span class="sxs-lookup"><span data-stu-id="d03f7-122">Choose the web application for which this error is occurring.</span></span> <span data-ttu-id="d03f7-123">Si hay más de una, implemente de nuevo la solución para todas.</span><span class="sxs-lookup"><span data-stu-id="d03f7-123">If there is more than one web application, redeploy the solution for all of hem.</span></span>  
  
5.  <span data-ttu-id="d03f7-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d03f7-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d03f7-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d03f7-125">See Also</span></span>  
 [<span data-ttu-id="d03f7-126">Implementar las soluciones de PowerPivot en SharePoint</span><span class="sxs-lookup"><span data-stu-id="d03f7-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
