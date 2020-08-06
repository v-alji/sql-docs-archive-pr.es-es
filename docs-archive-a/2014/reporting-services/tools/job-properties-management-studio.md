---
title: Propiedades del trabajo (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.jobproperties.f1
ms.assetid: 807ffd0e-9363-4f8f-9c36-c5d746ad19fd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4d309ba78a21114cf51c48f0a5c5b3b2f7c2500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746131"
---
# <a name="job-properties-management-studio"></a><span data-ttu-id="5180f-102">Propiedades del trabajo (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5180f-102">Job Properties (Management Studio)</span></span>
  <span data-ttu-id="5180f-103">Use la página **Propiedades del trabajo** para ver información sobre una suscripción o un informe en curso antes de cancelarlo.</span><span class="sxs-lookup"><span data-stu-id="5180f-103">Use the **Job Properties** page to view information about an in-progress report or subscription before you cancel it.</span></span>  
  
 <span data-ttu-id="5180f-104">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a un servidor de informes y abra la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="5180f-104">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, and open the **Jobs** folder.</span></span> <span data-ttu-id="5180f-105">Haga clic con el botón derecho en un trabajo que se está ejecutando y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5180f-105">Right-click a job that is running, and then click **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5180f-106">Esta característica no se admite en [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] con Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="5180f-106">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="5180f-107">La página no aparece cuando se ejecuta [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5180f-107">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="5180f-108">Tareas</span><span class="sxs-lookup"><span data-stu-id="5180f-108">Tasks</span></span>  
 <span data-ttu-id="5180f-109">Para poder ver información acerca de un trabajo, actualice la página para recuperar información sobre los trabajos que se están ejecutando actualmente en el servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="5180f-109">Before you can view information about a job, refresh the page to retrieve information about jobs that are currently running on the report server:</span></span>  
  
1.  <span data-ttu-id="5180f-110">Abra la carpeta del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5180f-110">Open the report server folder.</span></span>  
  
2.  <span data-ttu-id="5180f-111">Haga clic con el botón derecho en **Trabajos**y luego haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="5180f-111">Right-click **Jobs**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="5180f-112">Si un trabajo aparece en una lista, haga clic con el botón derecho en él y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5180f-112">If a job is listed, right-click the job, and then click **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5180f-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="5180f-113">Options</span></span>  
 <span data-ttu-id="5180f-114">**Id. del trabajo**</span><span class="sxs-lookup"><span data-stu-id="5180f-114">**Job ID**</span></span>  
 <span data-ttu-id="5180f-115">Un GUID que se asigna a un trabajo mientras se está procesando.</span><span class="sxs-lookup"><span data-stu-id="5180f-115">A GUID that is assigned to a job while it is processing.</span></span> <span data-ttu-id="5180f-116">El valor se genera de forma aleatoria cada vez que se ejecuta un informe o suscripción.</span><span class="sxs-lookup"><span data-stu-id="5180f-116">The value is randomly generated each time a report or subscription runs.</span></span>  
  
 <span data-ttu-id="5180f-117">**Estado del trabajo**</span><span class="sxs-lookup"><span data-stu-id="5180f-117">**Job Status**</span></span>  
 <span data-ttu-id="5180f-118">Los valores válidos son **Nuevo** y **En ejecución**.</span><span class="sxs-lookup"><span data-stu-id="5180f-118">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="5180f-119">Estado siempre es **Nuevo** cuando comienza el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5180f-119">Status is always **New** when the job begins.</span></span> <span data-ttu-id="5180f-120">Después de 60 segundos, el estado cambia a **En ejecución**.</span><span class="sxs-lookup"><span data-stu-id="5180f-120">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="5180f-121">Debe actualizar la página para que se refleje el cambio.</span><span class="sxs-lookup"><span data-stu-id="5180f-121">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="5180f-122">**Tipo de trabajo**</span><span class="sxs-lookup"><span data-stu-id="5180f-122">**Job Type**</span></span>  
 <span data-ttu-id="5180f-123">Los valores válidos son **Usuario** y **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="5180f-123">Valid values are **User** and **System**.</span></span> <span data-ttu-id="5180f-124">Un trabajo de usuario es cualquier trabajo que haya iniciado un usuario individual;</span><span class="sxs-lookup"><span data-stu-id="5180f-124">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="5180f-125">por ejemplo, ejecutar un informe a petición, generar manualmente una instantánea del historial de informes o crear manualmente una instantánea de ejecución de informe.</span><span class="sxs-lookup"><span data-stu-id="5180f-125">This includes running a report on-demand, manually generating a report history snapshot, or manually creating a report execution snapshot.</span></span> <span data-ttu-id="5180f-126">Una suscripción estándar en curso es también un trabajo de usuario.</span><span class="sxs-lookup"><span data-stu-id="5180f-126">An in-progress standard subscription is also a user job.</span></span> <span data-ttu-id="5180f-127">Un trabajo del sistema es un trabajo iniciado por el servidor de informes;</span><span class="sxs-lookup"><span data-stu-id="5180f-127">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="5180f-128">Los trabajos del sistema incluyen el procesamiento de informes que se desencadena por una programación.</span><span class="sxs-lookup"><span data-stu-id="5180f-128">System jobs include report processing that is triggered by a schedule.</span></span>  
  
 <span data-ttu-id="5180f-129">**Acción del trabajo**</span><span class="sxs-lookup"><span data-stu-id="5180f-129">**Job Action**</span></span>  
 <span data-ttu-id="5180f-130">Para los informes, esta columna muestra qué procesos de ejecución de informe están en curso.</span><span class="sxs-lookup"><span data-stu-id="5180f-130">For reports, this column shows which report execution processes are underway.</span></span> <span data-ttu-id="5180f-131">Este valor siempre es **Representar**.</span><span class="sxs-lookup"><span data-stu-id="5180f-131">This value is always **Render**.</span></span>  
  
 <span data-ttu-id="5180f-132">**Descripción del trabajo**</span><span class="sxs-lookup"><span data-stu-id="5180f-132">**Job Description**</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5180f-133">no proporciona descripciones de trabajo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5180f-133">does not provide job descriptions by default.</span></span>  
  
 <span data-ttu-id="5180f-134">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="5180f-134">**Server Name**</span></span>  
 <span data-ttu-id="5180f-135">Muestra el nombre del servidor de informes que está procesando el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5180f-135">Shows the name of the report server that is processing the job.</span></span> <span data-ttu-id="5180f-136">Si configurara una implementación escalada, este valor mostrará qué servidor está procesando el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5180f-136">If you configured a scale-out deployment, this value will show which server is processing the job.</span></span>  
  
 <span data-ttu-id="5180f-137">**Nombre del informe**</span><span class="sxs-lookup"><span data-stu-id="5180f-137">**Report Name**</span></span>  
 <span data-ttu-id="5180f-138">Muestra el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="5180f-138">Shows the name of the report.</span></span> <span data-ttu-id="5180f-139">Las suscripciones se identifican con su descripción.</span><span class="sxs-lookup"><span data-stu-id="5180f-139">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="5180f-140">**Ruta de acceso del informe**</span><span class="sxs-lookup"><span data-stu-id="5180f-140">**Report Path**</span></span>  
 <span data-ttu-id="5180f-141">Muestra la ruta de acceso del informe en la jerarquía de carpetas del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5180f-141">Shows the path of the report in the report server folder hierarchy.</span></span>  
  
 <span data-ttu-id="5180f-142">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="5180f-142">**Start Time**</span></span>  
 <span data-ttu-id="5180f-143">Muestra cuándo se inició el proceso.</span><span class="sxs-lookup"><span data-stu-id="5180f-143">Shows when the process started.</span></span>  
  
 <span data-ttu-id="5180f-144">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="5180f-144">**User Name**</span></span>  
 <span data-ttu-id="5180f-145">Para los procesos iniciados por un usuario, esta columna muestra el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="5180f-145">For processes initiated by a user, this column shows the name of the user.</span></span> <span data-ttu-id="5180f-146">Para los trabajos del sistema, éste es el nombre del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5180f-146">For system jobs, this is the name of the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5180f-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5180f-147">See Also</span></span>  
 <span data-ttu-id="5180f-148">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="5180f-148">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="5180f-149">[Conectar con un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5180f-149">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="5180f-150">Administración de un proceso en ejecución</span><span class="sxs-lookup"><span data-stu-id="5180f-150">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
