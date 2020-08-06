---
title: Especificar criterios de consulta (Asistente para optimización basada en el uso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.specifyquerycriteria.f1
ms.assetid: 3193adc2-af9f-4234-a4cc-dea0c280a724
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3b93034a089ff3121155e35de4cec96846824a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670613"
---
# <a name="specify-query-criteria-usage-based-optimization-wizard"></a><span data-ttu-id="e7e3b-102">Especificar los criterios de consulta (Asistente para optimización basada en el uso)</span><span class="sxs-lookup"><span data-stu-id="e7e3b-102">Specify Query Criteria (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="e7e3b-103">Use la página **Especificar los criterios de consulta** para elegir una o más opciones de filtro con objeto de identificar las consultas que se deben optimizar.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-103">Use the **Specify Query Criteria** page to choose one or more filter options in order to identify queries to optimize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7e3b-104">Esta página esta deshabilitada si [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no puede conectarse al registro de consultas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-104">This page is disabled if [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cannot connect to the query log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e7e3b-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="e7e3b-105">Options</span></span>  
 <span data-ttu-id="e7e3b-106">**Estadísticas del registro de consultas**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-106">**Query log statistics**</span></span>  
 <span data-ttu-id="e7e3b-107">Muestra información acerca de las consultas almacenadas en el registro de consultas para las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-107">Displays information about the queries stored in the query log for the selected partitions.</span></span> <span data-ttu-id="e7e3b-108">Aparecen los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="e7e3b-108">The following items are displayed:</span></span>  
  
|<span data-ttu-id="e7e3b-109">Término</span><span class="sxs-lookup"><span data-stu-id="e7e3b-109">Term</span></span>|<span data-ttu-id="e7e3b-110">Definición</span><span class="sxs-lookup"><span data-stu-id="e7e3b-110">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e7e3b-111">**Total de consultas**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-111">**Total queries**</span></span>|<span data-ttu-id="e7e3b-112">Muestra el número total de consultas almacenadas en el registro de consultas para las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-112">Displays the total number of queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="e7e3b-113">**Consultas DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-113">**Distinct queries**</span></span>|<span data-ttu-id="e7e3b-114">Muestra el número de consultas distintivas almacenadas en el registro de consultas para las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-114">Displays the number of distinct queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="e7e3b-115">**Usuarios distintivos**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-115">**Distinct users**</span></span>|<span data-ttu-id="e7e3b-116">Muestra el número total de usuarios distintivos asociados con las consultas almacenadas en el registro de consultas para las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-116">Displays the total number of distinct users associated with queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="e7e3b-117">**Tiempo medio de respuesta**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-117">**Average response time**</span></span>|<span data-ttu-id="e7e3b-118">Muestra el tiempo de respuesta promedio para las consultas distintivas almacenadas en el registro de consultas para las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-118">Displays the average response time for queries stored in the query log for the selected partitions.</span></span>|  
  
 <span data-ttu-id="e7e3b-119">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-119">**Beginning date**</span></span>  
 <span data-ttu-id="e7e3b-120">Filtra consultas en el registro de consultas basándose en una fecha y hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-120">Filters queries in the query log based on a starting date and time.</span></span> <span data-ttu-id="e7e3b-121">Elija o escriba una fecha en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-121">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7e3b-122"> Si no se selecciona **Fecha de finalización** , se tienen en cuenta todas las consultas del registro de consultas de la fecha y hora especificada en esta opción o posteriores a ésta.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-122">If **Ending date** is not selected, all queries in the query log on or after the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="e7e3b-123">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-123">**Ending date**</span></span>  
 <span data-ttu-id="e7e3b-124">Filtra consultas en el registro de consultas basándose en una fecha y hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-124">Filters queries in the query log based on an ending date and time.</span></span> <span data-ttu-id="e7e3b-125">Elija o escriba una fecha en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-125">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7e3b-126"> Si no se selecciona **Fecha de inicio** , se tienen en cuenta todas las consultas del registro de consultas de la fecha y hora especificada en esta opción o anteriores a ésta.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-126">If **Beginning date** is not selected, all queries in the query log on or before the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="e7e3b-127">**Usuarios**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-127">**Users**</span></span>  
 <span data-ttu-id="e7e3b-128">Filtra consultas en el registro de consultas basándose en un conjunto de usuarios especificado.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-128">Filters queries in the query log based on a specified set of users.</span></span> <span data-ttu-id="e7e3b-129">Haga clic en el botón de puntos suspensivos (**...**) para mostrar el cuadro de diálogo **Selección de usuarios** y elegir los usuarios sobre los que filtrar las consultas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-129">Click the ellipsis (**...**) button to display the **User Selection** dialog box and choose users on which to filter queries.</span></span> <span data-ttu-id="e7e3b-130">Para obtener más información sobre el cuadro de diálogo **Selección de usuarios**, vea [Cuadro de diálogo Selección de usuarios &#40;Analysis Services - Datos multidimensionales&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e7e3b-130">For more information about the **User Selection** dialog box, see [User Selection Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e7e3b-131">**Consultas más frecuentes**</span><span class="sxs-lookup"><span data-stu-id="e7e3b-131">**Most frequent queries**</span></span>  
 <span data-ttu-id="e7e3b-132">Filtra consultas en el registro de consultas basándose en el porcentaje más alto de consultas distintas que se han ejecutado con más frecuencia en las particiones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-132">Filters queries in the query log based on the topmost percentage of the distinct queries most often run for the selected partitions.</span></span> <span data-ttu-id="e7e3b-133">Elija o escriba un valor de porcentaje en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="e7e3b-133">Choose or type a percent value in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e3b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7e3b-134">See Also</span></span>  
 <span data-ttu-id="e7e3b-135">[Asistente para optimización basada en el uso (ayuda F1)](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e7e3b-135">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="e7e3b-136">Analysis Services asistentes &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="e7e3b-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
