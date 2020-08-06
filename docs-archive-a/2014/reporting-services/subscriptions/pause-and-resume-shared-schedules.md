---
title: Pausar y reanudar las programaciones compartidas| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- report-specific schedules [Reporting Services]
- shared schedules [Reporting Services], resuming
- resuming schedules
- continuing schedules
- schedules [Reporting Services], resuming
- schedules [Reporting Services], pausing
ms.assetid: e416be75-5234-4aa6-a3de-77f60f25169a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f525a15b07b79b5c0d37f9a88ed9483b351af326
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673457"
---
# <a name="pause-and-resume-shared-schedules"></a><span data-ttu-id="790a8-102">Pausar y reanudar las programaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="790a8-102">Pause and Resume Shared Schedules</span></span>
  <span data-ttu-id="790a8-103">Existe la posibilidad de pausar y reanudar las programaciones compartidas en uso.</span><span class="sxs-lookup"><span data-stu-id="790a8-103">You can pause and resume a shared schedule that is in use.</span></span> <span data-ttu-id="790a8-104">Pausar una programación compartida es un modo de congelar temporalmente una programación que se emplea para desencadenar el procesamiento de los informes y las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="790a8-104">Pausing a shared schedule provides a way to temporarily freeze a schedule that is used to trigger report processing and subscriptions.</span></span> <span data-ttu-id="790a8-105">Solo es posible pausar y reanudar las programaciones compartidas.</span><span class="sxs-lookup"><span data-stu-id="790a8-105">Only shared schedules can be paused and resumed.</span></span> <span data-ttu-id="790a8-106">Las programaciones específicas del informe no admiten la operación de pausa.</span><span class="sxs-lookup"><span data-stu-id="790a8-106">You cannot pause report-specific schedules.</span></span>  
  
 <span data-ttu-id="790a8-107">Los procesos de los informes en curso no pueden pausarse ni reanudarse.</span><span class="sxs-lookup"><span data-stu-id="790a8-107">You cannot pause and resume report processing that is in progress.</span></span> <span data-ttu-id="790a8-108">Solo se pueden pausar y reanudar las programaciones de la cola de programación del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="790a8-108">You can only pause and resume schedules that are in the scheduling queue of SQL Server Agent service.</span></span> <span data-ttu-id="790a8-109">Los trabajos en curso quedan fuera del alcance del motor de programación.</span><span class="sxs-lookup"><span data-stu-id="790a8-109">A job that is in progress is outside the scope of the scheduling engine.</span></span> <span data-ttu-id="790a8-110">Para más información, vea [Administrar un proceso en ejecución](manage-a-running-process.md).</span><span class="sxs-lookup"><span data-stu-id="790a8-110">For more information, see [Manage a Running Process](manage-a-running-process.md)</span></span>  
  
 <span data-ttu-id="790a8-111">Mientras una programación compartida está pausada, cualquier operación que hubiera tenido lugar puede detenerse.</span><span class="sxs-lookup"><span data-stu-id="790a8-111">While a shared schedule is paused, any operations that would have occurred are allowed to lapse.</span></span> <span data-ttu-id="790a8-112">Una vez reanudada la programación compartida, el procesamiento de la suscripción y del informe se produce durante la siguiente programación (según la hora local del servidor).</span><span class="sxs-lookup"><span data-stu-id="790a8-112">After you resume a shared schedule, report and subscription processing occurs at the next scheduled time, using the local time of the server.</span></span> <span data-ttu-id="790a8-113">El servidor de informes en modo nativo o las aplicaciones de servicio de SharePoint no recuperan las operaciones programadas que se habrían realizado si la programación no se hubiera pausado.</span><span class="sxs-lookup"><span data-stu-id="790a8-113">The native mode report server or SharePoint service applications, do not make up scheduled operations that would have occurred had the schedule not been paused.</span></span>  
  
 <span data-ttu-id="790a8-114">En este tema:</span><span class="sxs-lookup"><span data-stu-id="790a8-114">In this Topic:</span></span>  
  
-   [<span data-ttu-id="790a8-115">Pausar y reanudar las programaciones compartidas (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="790a8-115">Pause and Resume Shared Schedules (Native Mode)</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="790a8-116">Pausar y reanudar las programaciones compartidas (modo de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="790a8-116">Pause and Resume Shared Schedules (SharePoint mode)</span></span>](#bkmk_sharepoint)  
  
##  <a name="pause-and-resume-shared-schedules-native-mode"></a><a name="bkmk_native"></a> <span data-ttu-id="790a8-117">Pausar y reanudar las programaciones compartidas (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="790a8-117">Pause and Resume Shared Schedules (Native Mode)</span></span>  
 <span data-ttu-id="790a8-118">Use la página Programaciones del Administrador de informes para pausar y reanudar una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="790a8-118">To pause and resume a shared schedule, use the Schedules page in Report Manager.</span></span> <span data-ttu-id="790a8-119">No puede usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], ya que no proporciona las opciones necesarias para pausar y reanudar las programaciones.</span><span class="sxs-lookup"><span data-stu-id="790a8-119">You cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]; it does not provide options for pausing and resuming schedules.</span></span> <span data-ttu-id="790a8-120">Para obtener más información, consulte [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="790a8-120">For more information, see [Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md).</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="790a8-121">Para pausar o reanudar una programación compartida</span><span class="sxs-lookup"><span data-stu-id="790a8-121">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="790a8-122">En el Administrador de informes, haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="790a8-122">From Report Manager Click, **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="790a8-123">Haga clic en **Programaciones**.</span><span class="sxs-lookup"><span data-stu-id="790a8-123">Click **Schedules**.</span></span>  
  
3.  <span data-ttu-id="790a8-124">Seleccione la programación y haga clic en **Pausar** o **Reanudar** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="790a8-124">Select the schedule, and click **Pause** or **Resume** in the ribbon.</span></span> <span data-ttu-id="790a8-125">Si una programación está pausada actualmente, la columna **Estado** contendrá **En pausa**.</span><span class="sxs-lookup"><span data-stu-id="790a8-125">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
##  <a name="pause-and-resume-shared-schedules-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="790a8-126">Pausar y reanudar las programaciones compartidas (modo de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="790a8-126">Pause and Resume Shared Schedules (SharePoint mode)</span></span>  
 <span data-ttu-id="790a8-127">Para pausar y reanudar una programación compartida, use la página Configuración del sitio o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="790a8-127">To pause and resume a shared schedule, use the Site Settings page or PowerShell.</span></span> <span data-ttu-id="790a8-128">Las programaciones se administran por sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="790a8-128">Schedules are managed per SharePoint site.</span></span>  
  
#### <a name="to-pause-or-resume-a-shared-schedule"></a><span data-ttu-id="790a8-129">Para pausar o reanudar una programación compartida</span><span class="sxs-lookup"><span data-stu-id="790a8-129">To pause or resume a shared schedule</span></span>  
  
1.  <span data-ttu-id="790a8-130">Haga clic en **Acciones del sitio**.</span><span class="sxs-lookup"><span data-stu-id="790a8-130">Click **Site Actions**.</span></span>  
  
2.  <span data-ttu-id="790a8-131">Haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="790a8-131">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="790a8-132">En la sección Reporting Services, haga clic en **Administrar programaciones compartidas**.</span><span class="sxs-lookup"><span data-stu-id="790a8-132">In the Reporting Services section, click **Manage Shared Schedules**.</span></span>  
  
4.  <span data-ttu-id="790a8-133">Seleccione la programación y haga clic en **Pausar programaciones seleccionadas** o **Ejecutar programaciones seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="790a8-133">Select the schedule, and click **Pause Selected Schedules** or **Run Selected Schedules**.</span></span> <span data-ttu-id="790a8-134">Si una programación está pausada actualmente, la columna **Estado** contendrá **En pausa**.</span><span class="sxs-lookup"><span data-stu-id="790a8-134">If a Schedule is currently paused, the **Status** column will contain **Paused**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790a8-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="790a8-135">See Also</span></span>  
 <span data-ttu-id="790a8-136">[Programaciones](schedules.md) </span><span class="sxs-lookup"><span data-stu-id="790a8-136">[Schedules](schedules.md) </span></span>  
 <span data-ttu-id="790a8-137">[Crear, modificar y eliminar programaciones](create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="790a8-137">[Create, Modify, and Delete Schedules](create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="790a8-138">[Cambiar las zonas horarias y la configuración del reloj en un servidor de informes](change-time-zones-and-clock-settings-on-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="790a8-138">[Change Time Zones and Clock Settings on a Report Server](change-time-zones-and-clock-settings-on-a-report-server.md) </span></span>  
 [<span data-ttu-id="790a8-139">Administración de un proceso en ejecución</span><span class="sxs-lookup"><span data-stu-id="790a8-139">Manage a Running Process</span></span>](manage-a-running-process.md)  
  
  
