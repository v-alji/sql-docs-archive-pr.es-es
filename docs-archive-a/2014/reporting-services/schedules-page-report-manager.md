---
title: Página programaciones (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ef19d96e-9f00-4434-950e-152dda9c1ced
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e31bc25473aad23ecd2654f74ee3e837e65b65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671374"
---
# <a name="schedules-page-report-manager"></a><span data-ttu-id="9239b-102">Página de Programaciones (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="9239b-102">Schedules Page (Report Manager)</span></span>
  <span data-ttu-id="9239b-103">Use la página Programaciones para crear, modificar, eliminar, pausar o reanudar programaciones compartidas.</span><span class="sxs-lookup"><span data-stu-id="9239b-103">Use the Schedules page to create, modify, delete, pause, or resume shared schedules.</span></span> <span data-ttu-id="9239b-104">Una programación compartida es una programación con nombre que se puede crear y administrar independientemente de los informes, las suscripciones y los demás procesos que utilizan información de programación.</span><span class="sxs-lookup"><span data-stu-id="9239b-104">A shared schedule is a named schedule that you can create and manage separately from reports, subscriptions, and other processes that consume schedule information.</span></span> <span data-ttu-id="9239b-105">Los usuarios pueden seleccionar las programaciones compartidas que proporcione.</span><span class="sxs-lookup"><span data-stu-id="9239b-105">Users can select shared schedules that you provide.</span></span>  
  
 <span data-ttu-id="9239b-106">Para eliminar, pausar o reanudar una programación compartida, active la casilla que se encuentra junto a la programación compartida que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="9239b-106">To delete, pause, or resume a shared schedule, select the check box next to the shared schedule that you want to modify.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9239b-107">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9239b-107">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9239b-108">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="9239b-108">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="9239b-109">Navegación</span><span class="sxs-lookup"><span data-stu-id="9239b-109">Navigation</span></span>  
 <span data-ttu-id="9239b-110">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="9239b-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-schedules-page"></a><span data-ttu-id="9239b-111">Para abrir la página Programaciones</span><span class="sxs-lookup"><span data-stu-id="9239b-111">To open the Schedules page</span></span>  
  
1.  <span data-ttu-id="9239b-112">Abra el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="9239b-112">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="9239b-113">En la esquina superior derecha, haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="9239b-113">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="9239b-114">Esto abre la página de propiedades General del sitio.</span><span class="sxs-lookup"><span data-stu-id="9239b-114">This opens the General Properties page of the site.</span></span>  
  
3.  <span data-ttu-id="9239b-115">Seleccione la pestaña **Programaciones** .</span><span class="sxs-lookup"><span data-stu-id="9239b-115">Select the **Schedules** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9239b-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="9239b-116">Options</span></span>  
 <span data-ttu-id="9239b-117">**Nueva programación**</span><span class="sxs-lookup"><span data-stu-id="9239b-117">**New Schedule**</span></span>  
 <span data-ttu-id="9239b-118">Haga clic para abrir la página Programación, que se usa para especificar información de frecuencia.</span><span class="sxs-lookup"><span data-stu-id="9239b-118">Click to open the Scheduling page, which is used to specify frequency information.</span></span>  
  
 <span data-ttu-id="9239b-119">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="9239b-119">**Delete**</span></span>  
 <span data-ttu-id="9239b-120">Haga clic para quitar una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="9239b-120">Click to remove a shared schedule.</span></span>  
  
 <span data-ttu-id="9239b-121">**Pausar**</span><span class="sxs-lookup"><span data-stu-id="9239b-121">**Pause**</span></span>  
 <span data-ttu-id="9239b-122">Haga clic para impedir que una programación compartida se ejecute temporalmente.</span><span class="sxs-lookup"><span data-stu-id="9239b-122">Click to stop a shared schedule from running temporarily.</span></span> <span data-ttu-id="9239b-123">Al pausar una programación, se impide la ejecución de suscripciones y otros procesos programados.</span><span class="sxs-lookup"><span data-stu-id="9239b-123">Pausing a schedule prevents subscriptions and other scheduled processes from running.</span></span>  
  
 <span data-ttu-id="9239b-124">**Reanudar**</span><span class="sxs-lookup"><span data-stu-id="9239b-124">**Resume**</span></span>  
 <span data-ttu-id="9239b-125">Haga clic para restablecer una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="9239b-125">Click to reinstate a shared schedule.</span></span> <span data-ttu-id="9239b-126">Los procesos que estaban programados para ejecutarse mientras la programación estaba pausada no se completan.</span><span class="sxs-lookup"><span data-stu-id="9239b-126">Lapsed processes that were scheduled to run while the schedule was paused are not made up.</span></span>  
  
 <span data-ttu-id="9239b-127">**Programación**</span><span class="sxs-lookup"><span data-stu-id="9239b-127">**Schedule**</span></span>  
 <span data-ttu-id="9239b-128">Muestra las programaciones compartidas actualmente definidas.</span><span class="sxs-lookup"><span data-stu-id="9239b-128">Shows the shared schedules that are currently defined.</span></span> <span data-ttu-id="9239b-129">Haga clic en una programación compartida para ver o editar la información de frecuencia.</span><span class="sxs-lookup"><span data-stu-id="9239b-129">Click a shared schedule to view or edit frequency information.</span></span>  
  
 <span data-ttu-id="9239b-130">**Creador**</span><span class="sxs-lookup"><span data-stu-id="9239b-130">**Creator**</span></span>  
 <span data-ttu-id="9239b-131">Muestra el nombre del usuario que creó la programación compartida.</span><span class="sxs-lookup"><span data-stu-id="9239b-131">Shows the name of the user who created the shared schedule.</span></span>  
  
 <span data-ttu-id="9239b-132">**Última ejecución, Siguiente ejecución**</span><span class="sxs-lookup"><span data-stu-id="9239b-132">**Last Run, Next Run**</span></span>  
 <span data-ttu-id="9239b-133">Muestran cuándo se ejecutó la programación compartida por última vez y cuándo se volverá a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9239b-133">Shows when the shared schedule was last run and when it will run next.</span></span>  
  
 <span data-ttu-id="9239b-134">**Estado**</span><span class="sxs-lookup"><span data-stu-id="9239b-134">**Status**</span></span>  
 <span data-ttu-id="9239b-135">Indica si una programación compartida está en pausa o activa.</span><span class="sxs-lookup"><span data-stu-id="9239b-135">Shows whether a shared schedule is paused or active.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9239b-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9239b-136">See Also</span></span>  
 <span data-ttu-id="9239b-137">[Crear, modificar y eliminar programaciones](subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="9239b-137">[Create, Modify, and Delete Schedules](subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="9239b-138">Administrador de informes (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="9239b-138">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
