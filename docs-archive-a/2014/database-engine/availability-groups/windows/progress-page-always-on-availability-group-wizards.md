---
title: Página progreso (asistentes para grupos de disponibilidad AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.progress.f1
- sql12.swb.newagwizard.progress.f1
- sql11.swb.failoverwizard.progress.f1
- sql11.swb.adddatabasewizard.progress.f1
- sql11.swb.addreplicawizard.progress.f1
- sql11.swb.newagwizard.progress.f1
- sql12.swb.adddatabasewizard.progress.f1
- sql12.swb.failoverwixard.progress.f1
ms.assetid: bd3b0306-8384-4120-a1c9-03825f0ae26a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7de8df6906d930215d71a0adc562bd7cef961ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749494"
---
# <a name="progress-page-alwayson-availability-group-wizards"></a><span data-ttu-id="665ea-102">Página Progreso (asistentes para grupos de disponibilidad AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="665ea-102">Progress Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="665ea-103">Utilice este cuadro de diálogo para ver el progreso del asistente de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] que esté ejecutando en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="665ea-103">Use this dialog box to view the progress of a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] wizard that you are running in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="665ea-104">La barra de progreso indica el progreso relativo de los pasos que el asistente realiza.</span><span class="sxs-lookup"><span data-stu-id="665ea-104">The progress bar indicates the relative progress of the steps that the wizard is performing.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="665ea-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="665ea-105">UI element list</span></span>  
 <span data-ttu-id="665ea-106">**Más detalles**</span><span class="sxs-lookup"><span data-stu-id="665ea-106">**More details**</span></span>  
 <span data-ttu-id="665ea-107">Haga clic en la flecha abajo para mostrar una cuadrícula de progreso que enumera los pasos completados, en orden, seguida de la operación en curso actual.</span><span class="sxs-lookup"><span data-stu-id="665ea-107">Click the down arrow to display a progress grid that lists any completed steps, in order, followed by the current in-progress operation.</span></span> <span data-ttu-id="665ea-108">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="665ea-108">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="665ea-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="665ea-109">**Name**</span></span>  
 <span data-ttu-id="665ea-110">Muestra una frase que describe un paso concreto.</span><span class="sxs-lookup"><span data-stu-id="665ea-110">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="665ea-111">**Estado**</span><span class="sxs-lookup"><span data-stu-id="665ea-111">**Status**</span></span>  
 <span data-ttu-id="665ea-112">Indica el resultado de los pasos completados y el porcentaje de finalización del paso actual, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="665ea-112">Indicates the outcome of completed steps and the percentage of completion of the current step, as follows:</span></span>  
  
|<span data-ttu-id="665ea-113">Resultado</span><span class="sxs-lookup"><span data-stu-id="665ea-113">Result</span></span>|<span data-ttu-id="665ea-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="665ea-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="665ea-115">**Error**</span><span class="sxs-lookup"><span data-stu-id="665ea-115">**Error**</span></span>|<span data-ttu-id="665ea-116">Indica que la operación para este paso ha experimentado un error.</span><span class="sxs-lookup"><span data-stu-id="665ea-116">Indicates the operation for this step experienced an error.</span></span> <span data-ttu-id="665ea-117">Haga clic en el vínculo para mostrar un cuadro de diálogo de mensaje que describe el error.</span><span class="sxs-lookup"><span data-stu-id="665ea-117">Click the link to display a message dialog box that describes the error.</span></span>|  
|<span data-ttu-id="665ea-118">**En curso (** *porcentaje completado* **)**</span><span class="sxs-lookup"><span data-stu-id="665ea-118">**In Progress (** *percentage-completed* **)**</span></span>|<span data-ttu-id="665ea-119">Indica que la operación se está produciendo ahora y calcula el porcentaje completado de este paso.</span><span class="sxs-lookup"><span data-stu-id="665ea-119">Indicates that the operation is occurring now and estimates the percentage of this step that has completed.</span></span>|  
|<span data-ttu-id="665ea-120">**Success**</span><span class="sxs-lookup"><span data-stu-id="665ea-120">**Success**</span></span>|<span data-ttu-id="665ea-121">Indica que la operación correspondiente a este paso se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="665ea-121">Indicates the operation for this step completed successfully.</span></span>|  
  
 <span data-ttu-id="665ea-122">**Menos detalles**</span><span class="sxs-lookup"><span data-stu-id="665ea-122">**Fewer Details**</span></span>  
 <span data-ttu-id="665ea-123">Haga clic para ocultar la cuadrícula de progreso.</span><span class="sxs-lookup"><span data-stu-id="665ea-123">Click to hide the progress grid.</span></span>  
  
 <span data-ttu-id="665ea-124">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="665ea-124">**Cancel**</span></span>  
 <span data-ttu-id="665ea-125">Haga clic para omitir las operaciones restantes y salir del asistente.</span><span class="sxs-lookup"><span data-stu-id="665ea-125">Click to skip any remaining operations and then exit the wizard.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="665ea-126">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="665ea-126">Related Tasks</span></span>  
  
-   [<span data-ttu-id="665ea-127">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="665ea-127">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="665ea-128">Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="665ea-128">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="665ea-129">Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="665ea-129">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
-   [<span data-ttu-id="665ea-130">Usar el Asistente para grupo de disponibilidad de conmutación por error &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="665ea-130">Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="665ea-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="665ea-131">See Also</span></span>  
 [<span data-ttu-id="665ea-132">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="665ea-132">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
