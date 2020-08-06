---
title: Este libro contiene al menos una consulta que actualiza los datos externos. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aa65c992-eb41-4032-9e11-a9ba871b6a3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b2095e13d6151c68eb4a3507400dfdb1739564
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672305"
---
# <a name="this-workbook-contains-one-or-more-queries-that-refresh-external-data"></a><span data-ttu-id="484d7-103">Este libro contiene al menos una consulta que actualiza los datos externos.</span><span class="sxs-lookup"><span data-stu-id="484d7-103">This workbook contains one or more queries that refresh external data.</span></span>
  <span data-ttu-id="484d7-104">En los libros de Excel que contienen datos PowerPivot, Excel Services muestra esta advertencia cuando detecta información de conexión y le indica que habilite o deshabilite las consultas para este libro.</span><span class="sxs-lookup"><span data-stu-id="484d7-104">For Excel workbooks that contain PowerPivot data, Excel Services shows this warning when it detects connection information and prompts you to enable or disable queries for this workbook.</span></span>  
  
## <a name="details"></a><span data-ttu-id="484d7-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="484d7-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="484d7-106">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="484d7-106">Product Name</span></span>|<span data-ttu-id="484d7-107">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="484d7-107">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="484d7-108">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="484d7-108">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="484d7-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="484d7-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="484d7-110">Causa</span><span class="sxs-lookup"><span data-stu-id="484d7-110">Cause</span></span>|<span data-ttu-id="484d7-111">Servicios de Excel se configura para advertir al realizar la actualización de datos.</span><span class="sxs-lookup"><span data-stu-id="484d7-111">Excel Services is configured to warn on data refresh.</span></span>|  
|<span data-ttu-id="484d7-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="484d7-112">Message Text</span></span>|<span data-ttu-id="484d7-113">Este libro contiene al menos una consulta que actualiza los datos externos.</span><span class="sxs-lookup"><span data-stu-id="484d7-113">This workbook contains one or more queries that refresh external data.</span></span> <span data-ttu-id="484d7-114">Un usuario malintencionado podría diseñar una consulta para obtener acceso a información confidencial y distribuirla a los otros usuarios o llevar a cabo otras acciones perjudiciales.</span><span class="sxs-lookup"><span data-stu-id="484d7-114">A malicious user can design a query to access confidential information and distribute it to other users or perform other harmful actions.</span></span><br /><br /> <span data-ttu-id="484d7-115">Si la fuente de este libro es de confianza, haga clic en Sí para permitir consultas a datos externos al libro.</span><span class="sxs-lookup"><span data-stu-id="484d7-115">If you trust the source of this workbook, click Yes to enable queries to external data in this workbook.</span></span> <span data-ttu-id="484d7-116">Si no está seguro, haga clic en No de forma que los cambios no se implementen en el libro.</span><span class="sxs-lookup"><span data-stu-id="484d7-116">If you are not sure, click No so that changes are not applied to your workbook.</span></span><br /><br /> <span data-ttu-id="484d7-117">¿Desea permitir las consultas a los datos externos de este libro?</span><span class="sxs-lookup"><span data-stu-id="484d7-117">Do you want to enable queries to external data in this workbook?</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="484d7-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="484d7-118">Explanation</span></span>  
 <span data-ttu-id="484d7-119">Los libros PowerPivot contienen cadenas de conexión de datos incrustadas que usa Excel para comunicarse con un servidor de PowerPivot externo que carga y calcula los datos.</span><span class="sxs-lookup"><span data-stu-id="484d7-119">PowerPivot workbooks contain embedded data connection strings that are used by Excel to communicate with an external PowerPivot server that loads and calculates the data.</span></span> <span data-ttu-id="484d7-120">Cuando se habilitan las advertencias de la actualización de datos, Servicios de Excel detecta esta cadena de conexión y advierte al usuario en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="484d7-120">When warn on data refresh is enabled, Excel Services detects this connection string and warns the user accordingly.</span></span>  
  
 <span data-ttu-id="484d7-121">Para filtrar y segmentar los datos PowerPivot del libro, las consultas deben estar habilitadas.</span><span class="sxs-lookup"><span data-stu-id="484d7-121">To filter and slice PowerPivot data in the workbook, queries must be enabled.</span></span> <span data-ttu-id="484d7-122">Asegúrese de habilitar las consultas solo para aquellos libros PowerPivot en los que confíe.</span><span class="sxs-lookup"><span data-stu-id="484d7-122">Be sure that you enable queries for only those PowerPivot workbooks that you trust.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="484d7-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="484d7-123">User Action</span></span>  
 <span data-ttu-id="484d7-124">Haga clic en **Sí** para habilitar las consultas.</span><span class="sxs-lookup"><span data-stu-id="484d7-124">Click **Yes** to enable queries.</span></span>  
  
 <span data-ttu-id="484d7-125">También puede cambiar la configuración de forma que la advertencia de la actualización ya no se produzca:</span><span class="sxs-lookup"><span data-stu-id="484d7-125">You can also change the configuration settings so that warn on refresh no longer occurs:</span></span>  
  
1.  <span data-ttu-id="484d7-126">En Administración central, en Administración de aplicaciones, haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="484d7-126">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="484d7-127">Haga clic en **Aplicación de Servicios de Excel**.</span><span class="sxs-lookup"><span data-stu-id="484d7-127">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="484d7-128">Haga clic en **Ubicación de archivo de confianza**.</span><span class="sxs-lookup"><span data-stu-id="484d7-128">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="484d7-129">Haga clic en **http://** o en la ubicación que quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="484d7-129">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="484d7-130">En Datos externos, desactive la casilla de **Advertencia en actualización de datos**.</span><span class="sxs-lookup"><span data-stu-id="484d7-130">In External Data, clear the checkbox for **Warn on data refresh**.</span></span>  
  
6.  <span data-ttu-id="484d7-131">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="484d7-131">Click **OK**.</span></span>  
  
 <span data-ttu-id="484d7-132">O bien, puede crear una nueva ubicación de confianza para los sitios que contienen los libros PowerPivot y, a continuación, modificar la configuración solo para ese sitio.</span><span class="sxs-lookup"><span data-stu-id="484d7-132">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="484d7-133">Para obtener más información, consulte [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="484d7-133">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
