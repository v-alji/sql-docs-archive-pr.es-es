---
title: Monitor de actividad de trabajo (Configuración del filtro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.filter.f1
ms.assetid: 89cb0055-5262-447f-8464-7203d4caba78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feba7b992d5d1d375b93df12135487a092792ee1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675346"
---
# <a name="job-activity-monitor-filter-settings"></a><span data-ttu-id="a4d53-102">Monitor de actividad de trabajo (Configuración del filtro)</span><span class="sxs-lookup"><span data-stu-id="a4d53-102">Job Activity Monitor (Filter Settings)</span></span>
  <span data-ttu-id="a4d53-103">Utilice esta página para reducir el número de filas visibles en el Monitor de actividad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4d53-103">Use this page to reduce the number of rows visible in the Job Activity Monitor.</span></span> <span data-ttu-id="a4d53-104">Inserte criterios en uno o varios de los cuadros disponibles, para mostrar solo las filas que coinciden con los valores especificados.</span><span class="sxs-lookup"><span data-stu-id="a4d53-104">Enter criteria in one or several of the available boxes, to show only the rows that meet the specified values.</span></span> <span data-ttu-id="a4d53-105">Algunos cuadros, como **Estado** o **Tipo de bloqueo** ofrecen un número determinado de valores posibles, en una lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a4d53-105">Some of the boxes, such as **Status** or **Blocking Type** offer a finite number of possible values, provided by a drop-down list.</span></span> <span data-ttu-id="a4d53-106">Otros, como **Aplicación** , permiten indicar un número indeterminado de valores, como una lista separada por comas.</span><span class="sxs-lookup"><span data-stu-id="a4d53-106">Others, such as **Application,** allow you to enter whatever value and as many values as you wish, as a comma separated list.</span></span> <span data-ttu-id="a4d53-107">Los iconos de barra de herramientas permiten ordenar los cuadros disponibles alfabéticamente o por categoría.</span><span class="sxs-lookup"><span data-stu-id="a4d53-107">Toolbar icons allow you to sort the available boxes by category or alphabetically.</span></span> <span data-ttu-id="a4d53-108">Haga clic en los criterios para consultar una descripción breve.</span><span class="sxs-lookup"><span data-stu-id="a4d53-108">Click the criteria to show a short description of the each one.</span></span>  
  
 <span data-ttu-id="a4d53-109">Para filtrar el Monitor de actividad de trabajo, proporcione los criterios de filtro que desee, haga clic en **Aplicar filtro**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4d53-109">To filter the Job Activity Monitor, provide as many filter criteria as you want, click **Apply filter**, and then click **OK**.</span></span>  
  
## <a name="all-jobs"></a><span data-ttu-id="a4d53-110">Todos los trabajos</span><span class="sxs-lookup"><span data-stu-id="a4d53-110">All Jobs</span></span>  
 <span data-ttu-id="a4d53-111">Este grupo de criterios de filtro está disponible cuando se filtra el Monitor de actividad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4d53-111">This group of filter criteria is available when filtering the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="a4d53-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a4d53-112">**Name**</span></span>  
 <span data-ttu-id="a4d53-113">Filtra trabajos por nombre.</span><span class="sxs-lookup"><span data-stu-id="a4d53-113">Filter jobs by name.</span></span>  
  
 <span data-ttu-id="a4d53-114">**Siguiente ejecución**</span><span class="sxs-lookup"><span data-stu-id="a4d53-114">**Next Run**</span></span>  
 <span data-ttu-id="a4d53-115">Filtra por la fecha de la siguiente ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4d53-115">Filter by the date next scheduled to run.</span></span>  
  
 <span data-ttu-id="a4d53-116">**Ejecutable**</span><span class="sxs-lookup"><span data-stu-id="a4d53-116">**Runnable**</span></span>  
 <span data-ttu-id="a4d53-117">Muestra trabajos que se pueden ejecutar o trabajos que no se pueden ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a4d53-117">View jobs that can be run, or jobs that cannot be run.</span></span> <span data-ttu-id="a4d53-118">Seleccione **Sí** para ver solo los trabajos que se pueden ejecutar, seleccione **No** para ver únicamente los trabajos que no se pueden ejecutar, o bien seleccione **Todos** para ver los dos tipos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4d53-118">Select **Yes** to view only jobs that can be run, select **No** to view only jobs that cannot be run, or select **All** to view both jobs that can be run and those that cannot.</span></span>  
  
 <span data-ttu-id="a4d53-119">**Última ejecución**</span><span class="sxs-lookup"><span data-stu-id="a4d53-119">**Last Run**</span></span>  
 <span data-ttu-id="a4d53-120">Filtra por la fecha de la última ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4d53-120">Filter by the date last run.</span></span>  
  
 <span data-ttu-id="a4d53-121">**Resultado de la última ejecución**</span><span class="sxs-lookup"><span data-stu-id="a4d53-121">**Last Run Outcome**</span></span>  
 <span data-ttu-id="a4d53-122">Filtra trabajos por el estado de la última ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4d53-122">Filter jobs by the status last time the jobs were run.</span></span>  
  
 <span data-ttu-id="a4d53-123">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="a4d53-123">**Enabled**</span></span>  
 <span data-ttu-id="a4d53-124">Muestra solo trabajos habilitados o no habilitados.</span><span class="sxs-lookup"><span data-stu-id="a4d53-124">View only enabled or not enabled jobs</span></span>  
  
 <span data-ttu-id="a4d53-125">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="a4d53-125">**Category**</span></span>  
 <span data-ttu-id="a4d53-126">Filtra trabajos por su categoría.</span><span class="sxs-lookup"><span data-stu-id="a4d53-126">Filter jobs by the job category.</span></span>  
  
 <span data-ttu-id="a4d53-127">**Programada**</span><span class="sxs-lookup"><span data-stu-id="a4d53-127">**Scheduled**</span></span>  
 <span data-ttu-id="a4d53-128">Muestra todos los trabajos con o sin programaciones.</span><span class="sxs-lookup"><span data-stu-id="a4d53-128">View all jobs with schedules, or without schedules.</span></span>  
  
 <span data-ttu-id="a4d53-129">**Estado**</span><span class="sxs-lookup"><span data-stu-id="a4d53-129">**Status**</span></span>  
 <span data-ttu-id="a4d53-130">Filtra trabajos por el estado.</span><span class="sxs-lookup"><span data-stu-id="a4d53-130">Filter jobs by the status.</span></span>  
  
## <a name="description-area"></a><span data-ttu-id="a4d53-131">Descripción (área)</span><span class="sxs-lookup"><span data-stu-id="a4d53-131">Description Area</span></span>  
 <span data-ttu-id="a4d53-132">**Descripción (cuadro)**</span><span class="sxs-lookup"><span data-stu-id="a4d53-132">**Description Box**</span></span>  
 <span data-ttu-id="a4d53-133">Este cuadro sin nombre proporciona una descripción breve de los criterios a medida que se seleccionan.</span><span class="sxs-lookup"><span data-stu-id="a4d53-133">This unnamed box provides a short description of the criteria as they are selected.</span></span>  
  
 <span data-ttu-id="a4d53-134">**Aplicar filtro**</span><span class="sxs-lookup"><span data-stu-id="a4d53-134">**Apply filter**</span></span>  
 <span data-ttu-id="a4d53-135">Para aplicar el filtro, haga clic en **aplicar filtro** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4d53-135">To apply the filter, click **Apply filter** and then click **OK**.</span></span> <span data-ttu-id="a4d53-136">Para conservar la configuración del filtro en el cuadro de diálogo **configuración del filtro** , pero no aplicarla, desactive **aplicar filtro**y, a continuación, haga clic en **Aceptar**para mostrar todas las filas.</span><span class="sxs-lookup"><span data-stu-id="a4d53-136">To retain the filter settings in the **Filter Settings** dialog box, but not apply them, uncheck **Apply filter**, and then click **OK**, to display all rows.</span></span>  
  
 <span data-ttu-id="a4d53-137">**Borrar**</span><span class="sxs-lookup"><span data-stu-id="a4d53-137">**Clear**</span></span>  
 <span data-ttu-id="a4d53-138">Recupera la configuración predeterminada del filtro.</span><span class="sxs-lookup"><span data-stu-id="a4d53-138">Returns the filter settings back to the default settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d53-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4d53-139">See Also</span></span>  
 [<span data-ttu-id="a4d53-140">Actividad de trabajos de monitor</span><span class="sxs-lookup"><span data-stu-id="a4d53-140">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
