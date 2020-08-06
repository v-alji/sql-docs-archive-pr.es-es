---
title: Propiedades de la programación (página General) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.general.f1
ms.assetid: 20e43966-6caf-4972-a2e2-0d9131ac8f51
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a61837cd977526021be948d8c74a93eba6506e67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671361"
---
# <a name="schedule-properties-general-page"></a><span data-ttu-id="dcda4-102">Propiedades de la programación (página General)</span><span class="sxs-lookup"><span data-stu-id="dcda4-102">Schedule Properties (General Page)</span></span>
  <span data-ttu-id="dcda4-103">Utilice esta página para ver o modificar una programación compartida.</span><span class="sxs-lookup"><span data-stu-id="dcda4-103">Use this page to view or modify a shared schedule.</span></span> <span data-ttu-id="dcda4-104">Las programaciones compartidas se pueden utilizar en lugar de las programaciones específicas del informe o de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="dcda4-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="dcda4-105">Los cambios a la programación se aplican después de guardarla.</span><span class="sxs-lookup"><span data-stu-id="dcda4-105">Changes to the schedule are applied after you save the schedule.</span></span> <span data-ttu-id="dcda4-106">La edición de una programación no tiene ningún efecto en los trabajos que se encuentran actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="dcda4-106">Editing a schedule has no effect on jobs that are currently in progress.</span></span> <span data-ttu-id="dcda4-107">Si edita una programación mientras se usa, todas las suscripciones y los informes de procesamiento actualmente desencadenados de dicha programación podrán terminar.</span><span class="sxs-lookup"><span data-stu-id="dcda4-107">If you edit a schedule while it is being used, all currently processing reports and subscriptions triggered from that schedule will be allowed to finish.</span></span>  
  
 <span data-ttu-id="dcda4-108">Una sola programación no admite todas las combinaciones de frecuencias.</span><span class="sxs-lookup"><span data-stu-id="dcda4-108">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="dcda4-109">Por ejemplo, si desea ejecutar un informe todos los viernes a las 12:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="dcda4-109">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="dcda4-110">y a las 4:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="dcda4-110">and 4:00 P.M.</span></span> <span data-ttu-id="dcda4-111">debe crear dos programaciones diarias que especifiquen una fecha de ejecución en viernes, una con las 12:00 p. m. como hora de inicio</span><span class="sxs-lookup"><span data-stu-id="dcda4-111">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="dcda4-112">y otra con las 4:00 p. m. como hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="dcda4-112">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="dcda4-113">El procesamiento de programaciones se basa en la hora local del servidor de informes que hospeda y procesa la programación.</span><span class="sxs-lookup"><span data-stu-id="dcda4-113">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="dcda4-114">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a un servidor de informes, abra la carpeta **Programaciones compartidas** , haga clic con el botón secundario en una programación compartida y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dcda4-114">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcda4-115">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y esta página no aparece cuando se ejecuta una edición que no tiene esta característica.</span><span class="sxs-lookup"><span data-stu-id="dcda4-115">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and this page does not appear when you are running an edition which does not have this feature.</span></span> <span data-ttu-id="dcda4-116">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [características compatibles con las ediciones de SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="dcda4-116">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dcda4-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="dcda4-117">Options</span></span>  
 <span data-ttu-id="dcda4-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dcda4-118">**Name**</span></span>  
 <span data-ttu-id="dcda4-119">Especifica el nombre de la programación compartida.</span><span class="sxs-lookup"><span data-stu-id="dcda4-119">Specifies the name for the shared schedule.</span></span>  
  
 <span data-ttu-id="dcda4-120">**Empezar a ejecutar esta programación el**</span><span class="sxs-lookup"><span data-stu-id="dcda4-120">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="dcda4-121">Especifica una fecha de inicio para esta programación.</span><span class="sxs-lookup"><span data-stu-id="dcda4-121">Specifies a start date for this schedule.</span></span>  
  
 <span data-ttu-id="dcda4-122">**Detener esta programación el**</span><span class="sxs-lookup"><span data-stu-id="dcda4-122">**Stop this schedule on**</span></span>  
 <span data-ttu-id="dcda4-123">Especifica una fecha de expiración para esta programación.</span><span class="sxs-lookup"><span data-stu-id="dcda4-123">Specifies an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="dcda4-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dcda4-124">**Type**</span></span>  
 <span data-ttu-id="dcda4-125">Especifica si el patrón de periodicidad está basado principalmente en las horas, los días, las semanas, los meses o solo se ejecuta una vez.</span><span class="sxs-lookup"><span data-stu-id="dcda4-125">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, months, or only runs once.</span></span>  
  
 <span data-ttu-id="dcda4-126">**Hora (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="dcda4-126">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="dcda4-127">Especifica opciones para ejecutar una operación de programación en intervalos de una hora (por ejemplo, para ejecutar un informe cada 6 horas).</span><span class="sxs-lookup"><span data-stu-id="dcda4-127">Specifies options for running a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="dcda4-128">Puede especificar el intervalo en horas y minutos.</span><span class="sxs-lookup"><span data-stu-id="dcda4-128">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="dcda4-129">**Día (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="dcda4-129">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="dcda4-130">Especifica opciones para ejecutar una operación de programación en intervalos de días (por ejemplo, para ejecutar un informe cada 2 días).</span><span class="sxs-lookup"><span data-stu-id="dcda4-130">Specifies options for running a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="dcda4-131">Puede especificar el intervalo en días y a la hora y minutos en los que desea que se ejecute la programación.</span><span class="sxs-lookup"><span data-stu-id="dcda4-131">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="dcda4-132">**Semana (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="dcda4-132">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="dcda4-133">Especifica opciones para ejecutar una operación de programación en intervalos de una semana o cuando el patrón que desea repetir se basa en semanas (por ejemplo, para ejecutar un informe una semana sí y otra no).</span><span class="sxs-lookup"><span data-stu-id="dcda4-133">Specifies options for running a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="dcda4-134">Puede especificar una programación semanal para el día, hora y minuto en los que desea que se ejecute la programación.</span><span class="sxs-lookup"><span data-stu-id="dcda4-134">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="dcda4-135">**Mes (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="dcda4-135">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="dcda4-136">Especifica opciones para ejecutar una operación de programación en intervalos de un mes o cuando el patrón que desea repetir se basa en meses.</span><span class="sxs-lookup"><span data-stu-id="dcda4-136">Specifies options for running a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="dcda4-137">Puede especificar una programación mensual para el día, hora y minuto en los que desea que se ejecute la programación.</span><span class="sxs-lookup"><span data-stu-id="dcda4-137">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="dcda4-138">Puede quitar meses específicos de la programación.</span><span class="sxs-lookup"><span data-stu-id="dcda4-138">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="dcda4-139">**Una sola vez**</span><span class="sxs-lookup"><span data-stu-id="dcda4-139">**Once**</span></span>  
 <span data-ttu-id="dcda4-140">Especifica una programación que se ejecuta solamente una vez, en una fecha y hora específicas.</span><span class="sxs-lookup"><span data-stu-id="dcda4-140">Specifies a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcda4-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dcda4-141">See Also</span></span>  
 <span data-ttu-id="dcda4-142">[Servidor de informes en Management Studio ayuda de F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="dcda4-142">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="dcda4-143">[Conectarse a un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="dcda4-143">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="dcda4-144">[Crear, modificar y eliminar programaciones](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="dcda4-144">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 [<span data-ttu-id="dcda4-145">Programaciones</span><span class="sxs-lookup"><span data-stu-id="dcda4-145">Schedules</span></span>](../subscriptions/schedules.md)  
  
  
