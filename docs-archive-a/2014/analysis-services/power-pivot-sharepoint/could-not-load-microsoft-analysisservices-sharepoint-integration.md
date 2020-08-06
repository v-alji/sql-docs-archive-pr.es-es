---
title: No se pudo cargar el archivo o ensamblado &#39;Microsoft. Data. Services, version = 3.5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; o una de sus dependencias. El sistema no encuentra el archivo especificado. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f9eed7ad90c1e720d07c714e351c24ae6657717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675579"
---
# <a name="could-not-load-file-or-assembly-39microsoftdataservices-version3500-cultureneutral-publickeytokenb77a5c561934e08939-or-one-of-its-dependencies-the-system-cannot-find-the-file-specified"></a><span data-ttu-id="d94e3-104">No se pudo cargar el archivo o ensamblado &#39;Microsoft. Data. Services, version = 3.5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; o una de sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="d94e3-104">Could not load file or assembly &#39;Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089&#39; or one of its dependencies.</span></span> <span data-ttu-id="d94e3-105">El sistema no encuentra el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="d94e3-105">The system cannot find the file specified.</span></span>
  <span data-ttu-id="d94e3-106">En entornos de SharePoint 2010 que tienen PowerPivot para SharePoint, este error se producirá si intenta realizar la exportación de una fuente de distribución de datos y el sistema no tiene la versión necesaria de Microsoft ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="d94e3-106">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if you attempt a data feed export and the system is missing the required version of Microsoft ADO.NET Data Services.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d94e3-107">Detalles</span><span class="sxs-lookup"><span data-stu-id="d94e3-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d94e3-108">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d94e3-108">Applies to</span></span>|<span data-ttu-id="d94e3-109">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94e3-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="d94e3-110">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="d94e3-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="d94e3-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d94e3-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="d94e3-112">Causa</span><span class="sxs-lookup"><span data-stu-id="d94e3-112">Cause</span></span>|<span data-ttu-id="d94e3-113">No se encontró ADO.NET Data Services 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="d94e3-113">ADO.NET Data Services 3.5 SP1 was not found.</span></span>|  
|<span data-ttu-id="d94e3-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d94e3-114">Message Text</span></span>|<span data-ttu-id="d94e3-115">No se puede cargar el archivo o ensamblado 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' ni una de sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="d94e3-115">Could not load file or assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies.</span></span> <span data-ttu-id="d94e3-116">El sistema no encuentra el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="d94e3-116">The system cannot find the file specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d94e3-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="d94e3-117">Explanation</span></span>  
 <span data-ttu-id="d94e3-118">SharePoint 2010 incluye un botón Exportar como fuente de distribución de datos que puede utilizar para exportar una lista de SharePoint como una fuente de distribución de datos XML.</span><span class="sxs-lookup"><span data-stu-id="d94e3-118">SharePoint 2010 includes an Export as Data Feed button that you can use to export a SharePoint list as an XML data feed.</span></span> <span data-ttu-id="d94e3-119">Además, tanto Reporting Services en el modo de SharePoint como PowerPivot para SharePoint admiten las características de fuentes de distribución de datos que requieren ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="d94e3-119">In addition, both Reporting Services in SharePoint mode and PowerPivot for SharePoint support data feed features that require ADO.NET Data Services.</span></span>  
  
 <span data-ttu-id="d94e3-120">Si no está instalado ADO.NET Data Services, este error se producirá al solicitar una fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="d94e3-120">If ADO.NET Data Services is not installed, this error will occur when you request a data feed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d94e3-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d94e3-121">User Action</span></span>  
  
1.  <span data-ttu-id="d94e3-122">Vaya a la documentación sobre los requisitos de hardware y software para SharePoint 2010, [determinar los requisitos de hardware y software (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) ( https://go.microsoft.com/fwlink/?LinkId=169734) .</span><span class="sxs-lookup"><span data-stu-id="d94e3-122">Go to the hardware and software requirements documentation for SharePoint 2010, [Determine Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) (https://go.microsoft.com/fwlink/?LinkId=169734).</span></span>  
  
2.  <span data-ttu-id="d94e3-123">En **Instalar requisitos previos de software**, busque el vínculo de ADO.NET Data Services 3.5 correspondiente al sistema operativo que está usando.</span><span class="sxs-lookup"><span data-stu-id="d94e3-123">In **Installing software prerequisites**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using.</span></span>  
  
3.  <span data-ttu-id="d94e3-124">Haga clic en el vínculo y ejecute el programa de instalación que instala el servicio.</span><span class="sxs-lookup"><span data-stu-id="d94e3-124">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94e3-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d94e3-125">See Also</span></span>  
 [<span data-ttu-id="d94e3-126">Implementar las soluciones de PowerPivot en SharePoint</span><span class="sxs-lookup"><span data-stu-id="d94e3-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
