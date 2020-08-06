---
title: Cancelar trabajos del servidor de informes (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.cancelreportserverjobs.f1
ms.assetid: 1c5b4975-49e9-4d0b-b298-2638e81edbfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0ef8ada32aab4ac368871da711d0fe63fff7620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748633"
---
# <a name="cancel-report-server-jobs-management-studio"></a><span data-ttu-id="1e605-102">Cancelar trabajos del servidor de informes (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1e605-102">Cancel Report Server Jobs (Management Studio)</span></span>
  <span data-ttu-id="1e605-103">Use el cuadro de diálogo **Cancelar trabajos del Servidor de informes** para ver o cancelar los informes en curso.</span><span class="sxs-lookup"><span data-stu-id="1e605-103">Use the **Cancel Report Server Jobs** dialog box to view or cancel in-progress reports.</span></span> <span data-ttu-id="1e605-104">Este cuadro de diálogo muestra todos los trabajos que se están ejecutando actualmente en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="1e605-104">This dialog box shows all jobs that are currently running on the report server.</span></span> <span data-ttu-id="1e605-105">Aunque no puede pausar o reiniciar trabajos que se están procesando actualmente, puede cancelar todos los trabajos o los trabajos individuales si están tardando demasiado tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="1e605-105">Although you cannot pause or restart jobs that are currently processing, you can cancel all jobs or individual jobs if they are taking too long to complete.</span></span>  
  
 <span data-ttu-id="1e605-106">Se pueden cancelar trabajos de usuario y del sistema.</span><span class="sxs-lookup"><span data-stu-id="1e605-106">You can cancel user jobs and system jobs.</span></span>  
  
-   <span data-ttu-id="1e605-107">Un trabajo de usuario es cualquier trabajo que haya iniciado un usuario individual;</span><span class="sxs-lookup"><span data-stu-id="1e605-107">A user job is any job that is initiated by an individual user.</span></span> <span data-ttu-id="1e605-108">por ejemplo, ejecutar un informe a petición, crear manualmente una instantánea del historial de informes o crear manualmente una instantánea de ejecución de informe.</span><span class="sxs-lookup"><span data-stu-id="1e605-108">This includes running a report on-demand, manually creating a report history snapshot, or manually creating report execution snapshot.</span></span> <span data-ttu-id="1e605-109">Una suscripción estándar en curso es también un trabajo de usuario.</span><span class="sxs-lookup"><span data-stu-id="1e605-109">An in-progress standard subscription is also a user job.</span></span>  
  
-   <span data-ttu-id="1e605-110">Un trabajo del sistema es un trabajo iniciado por el servidor de informes;</span><span class="sxs-lookup"><span data-stu-id="1e605-110">A system job is one that is initiated by the report server.</span></span> <span data-ttu-id="1e605-111">Los trabajos del sistema incluyen el procesamiento de informes programados.</span><span class="sxs-lookup"><span data-stu-id="1e605-111">System jobs include scheduled report processing.</span></span>  
  
 <span data-ttu-id="1e605-112">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a un servidor de informes, haga clic con el botón derecho en **Trabajos**y, después, haga clic en **Cancelar todos los trabajos**.</span><span class="sxs-lookup"><span data-stu-id="1e605-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Jobs**, and then click **Cancel All Jobs**.</span></span> <span data-ttu-id="1e605-113">También puede abrir **Trabajos**, hacer clic con el botón derecho en un trabajo que se está ejecutando en el servidor de informes y seleccionar **Cancelar trabajos**.</span><span class="sxs-lookup"><span data-stu-id="1e605-113">You can also open **Jobs**, right-click a job that is running on the report server, and select **Cancel Job(s)**.</span></span>  
  
 <span data-ttu-id="1e605-114">Antes de cancelar un trabajo, puede ver sus propiedades para determinar cuándo se inició el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1e605-114">Before cancelling a job, you can view its properties to determine when the job started.</span></span> <span data-ttu-id="1e605-115">Para obtener más información, vea [Propiedades del trabajo &#40;Management Studio&#41;](job-properties-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="1e605-115">For more information, see [Job Properties &#40;Management Studio&#41;](job-properties-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e605-116">Esta característica no se admite en [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] con Advanced Services.</span><span class="sxs-lookup"><span data-stu-id="1e605-116">This feature is not supported in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] with Advanced Services.</span></span> <span data-ttu-id="1e605-117">La página no aparece cuando se ejecuta [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e605-117">The page does not appear when you are running [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e605-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="1e605-118">Options</span></span>  
 <span data-ttu-id="1e605-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1e605-119">**Name**</span></span>  
 <span data-ttu-id="1e605-120">Muestra el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="1e605-120">Shows the name of the report.</span></span> <span data-ttu-id="1e605-121">Las suscripciones se identifican con su descripción.</span><span class="sxs-lookup"><span data-stu-id="1e605-121">Subscriptions are identified by their descriptions.</span></span>  
  
 <span data-ttu-id="1e605-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1e605-122">**Type**</span></span>  
 <span data-ttu-id="1e605-123">Los valores válidos son **Usuario** y **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="1e605-123">Valid values are **User** and **System**.</span></span>  
  
 <span data-ttu-id="1e605-124">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="1e605-124">**Start Time**</span></span>  
 <span data-ttu-id="1e605-125">Muestra cuándo se inició el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1e605-125">Shows when the job started.</span></span>  
  
 <span data-ttu-id="1e605-126">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="1e605-126">**User Name**</span></span>  
 <span data-ttu-id="1e605-127">Para los trabajos iniciados por un usuario, esta columna muestra el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e605-127">For jobs that are initiated by a user, this column shows the name of the user.</span></span>  
  
 <span data-ttu-id="1e605-128">**Estado**</span><span class="sxs-lookup"><span data-stu-id="1e605-128">**Status**</span></span>  
 <span data-ttu-id="1e605-129">Muestra el estado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="1e605-129">Shows the status of the job.</span></span> <span data-ttu-id="1e605-130">Los valores válidos son **Nuevo** y **En ejecución**.</span><span class="sxs-lookup"><span data-stu-id="1e605-130">Valid values are **New** and **Running**.</span></span> <span data-ttu-id="1e605-131">Estado siempre es **Nuevo** cuando comienza el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1e605-131">Status is always **New** when the job begins.</span></span> <span data-ttu-id="1e605-132">Después de 60 segundos, el estado cambia a **En ejecución**.</span><span class="sxs-lookup"><span data-stu-id="1e605-132">After 60 seconds, status changes to **Running**.</span></span> <span data-ttu-id="1e605-133">Debe actualizar la página para que se refleje el cambio.</span><span class="sxs-lookup"><span data-stu-id="1e605-133">You must refresh the page to pick up the change.</span></span>  
  
 <span data-ttu-id="1e605-134">**OK (CORRECTO)**</span><span class="sxs-lookup"><span data-stu-id="1e605-134">**OK**</span></span>  
 <span data-ttu-id="1e605-135">Cancele un trabajo único o varios trabajos.</span><span class="sxs-lookup"><span data-stu-id="1e605-135">Cancel a single job or multiple jobs.</span></span> <span data-ttu-id="1e605-136">Los trabajos se cancelan inmediatamente y no se pueden reanudar.</span><span class="sxs-lookup"><span data-stu-id="1e605-136">The jobs are cancelled immediately and cannot be resumed.</span></span> <span data-ttu-id="1e605-137">Si cancela un trabajo por error, debe solicitar de nuevo el informe o la suscripción para iniciar un nuevo trabajo.</span><span class="sxs-lookup"><span data-stu-id="1e605-137">If you mistakenly cancel a job, you must request the report or subscription again to start a new job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e605-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e605-138">See Also</span></span>  
 <span data-ttu-id="1e605-139">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1e605-139">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="1e605-140">[Conectar con un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1e605-140">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="1e605-141">Administración de un proceso en ejecución</span><span class="sxs-lookup"><span data-stu-id="1e605-141">Manage a Running Process</span></span>](../subscriptions/manage-a-running-process.md)  
  
  
