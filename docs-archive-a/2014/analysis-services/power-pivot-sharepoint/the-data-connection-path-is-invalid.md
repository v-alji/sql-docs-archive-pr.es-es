---
title: 'La ruta de acceso de la conexión de datos en el libro señala a un archivo en la unidad local o es un URI no válido. No se pudieron actualizar las siguientes conexiones: datos PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bd22e41a-0931-4d32-888a-633a3046fc5e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3349af08290e2ff659db1441d849b2afef51e95b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672304"
---
# <a name="the-data-connection-path-in-the-workbook-points-to-a-file-on-the-local-drive-or-is-an-invalid-uri-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="973f3-103">La ruta de acceso de la conexión de datos en el libro señala a un archivo en la unidad local o es un URI no válido.</span><span class="sxs-lookup"><span data-stu-id="973f3-103">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="973f3-104">No se pudieron actualizar las siguientes conexiones: datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="973f3-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="973f3-105">En los libros de Excel que contienen los datos PowerPivot, Excel Services devuelve este error si no puede conectarse a orígenes de datos incrustados.</span><span class="sxs-lookup"><span data-stu-id="973f3-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="973f3-106">Detalles</span><span class="sxs-lookup"><span data-stu-id="973f3-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="973f3-107">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="973f3-107">Applies to</span></span>|<span data-ttu-id="973f3-108">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="973f3-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="973f3-109">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="973f3-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="973f3-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="973f3-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="973f3-111">Causa</span><span class="sxs-lookup"><span data-stu-id="973f3-111">Cause</span></span>|<span data-ttu-id="973f3-112">Excel Services se configura para permitir únicamente las conexiones de datos de archivos .odc que estén en una biblioteca de conexiones de datos de confianza.</span><span class="sxs-lookup"><span data-stu-id="973f3-112">Excel Services is configured to only allow data connections from .odc files that are in a trusted data connection library.</span></span>|  
|<span data-ttu-id="973f3-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="973f3-113">Message Text</span></span>|<span data-ttu-id="973f3-114">La ruta de acceso de la conexión de datos en el libro señala a un archivo en la unidad local o es un URI no válido.</span><span class="sxs-lookup"><span data-stu-id="973f3-114">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="973f3-115">No se pudieron actualizar las siguientes conexiones: datos PowerPivot</span><span class="sxs-lookup"><span data-stu-id="973f3-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="973f3-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="973f3-116">Explanation</span></span>  
 <span data-ttu-id="973f3-117">Los libros PowerPivot contienen conexiones de datos incrustados.</span><span class="sxs-lookup"><span data-stu-id="973f3-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="973f3-118">Para admitir la interacción de los libros a través de segmentaciones y filtros, Servicios de Excel se debe configurar para permitir el acceso de datos externos a través de la información de las conexiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="973f3-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="973f3-119">Se requiere acceso a los datos externos para recuperar los datos PowerPivot que se cargan en los servidores de PowerPivot de la granja.</span><span class="sxs-lookup"><span data-stu-id="973f3-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="973f3-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="973f3-120">User Action</span></span>  
 <span data-ttu-id="973f3-121">Cambie la configuración para permitir conexiones a orígenes de datos incrustados.</span><span class="sxs-lookup"><span data-stu-id="973f3-121">Change the configuration settings to allow embedded data source connections.</span></span>  
  
1.  <span data-ttu-id="973f3-122">En Administración central, en Administración de aplicaciones, haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="973f3-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="973f3-123">Haga clic en **Aplicación de Servicios de Excel**.</span><span class="sxs-lookup"><span data-stu-id="973f3-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="973f3-124">Haga clic en **Ubicación de archivo de confianza**.</span><span class="sxs-lookup"><span data-stu-id="973f3-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="973f3-125">Haga clic en **http://** o en la ubicación que quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="973f3-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="973f3-126">En Datos externos, en Permitir datos externos, haga clic en **Bibliotecas de conexiones de datos de confianza e incrustadas**.</span><span class="sxs-lookup"><span data-stu-id="973f3-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="973f3-127">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="973f3-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="973f3-128">O bien, puede crear una nueva ubicación de confianza para los sitios que contienen los libros PowerPivot y, a continuación, modificar la configuración solo para ese sitio.</span><span class="sxs-lookup"><span data-stu-id="973f3-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="973f3-129">Para obtener más información, consulte [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="973f3-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
