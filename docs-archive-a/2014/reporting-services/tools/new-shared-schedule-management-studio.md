---
title: Nueva programación compartida (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newschedule.f1
ms.assetid: b2c69586-d98e-4933-827d-f5e6c15c5203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6afd406730f815d3ab61e59cdebd21d564daa74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670791"
---
# <a name="new-shared-schedule-management-studio"></a><span data-ttu-id="944be-102">Nuevo Programación compartida (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="944be-102">New Shared Schedule (Management Studio)</span></span>
  <span data-ttu-id="944be-103">Use esta página para crear una programación compartida para ejecutar suscripciones e informes publicados.</span><span class="sxs-lookup"><span data-stu-id="944be-103">Use this page to create a shared schedule to run published reports and subscriptions.</span></span> <span data-ttu-id="944be-104">Las programaciones compartidas se pueden utilizar en lugar de las programaciones específicas del informe o de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="944be-104">Shared schedules can be used in place of report-specific or subscription-specific schedules.</span></span> <span data-ttu-id="944be-105">La información de programación centralizada y la capacidad de pausar y reanudar las operaciones programadas son dos características clave que distinguen las programaciones compartidas de las programaciones específicas de elemento.</span><span class="sxs-lookup"><span data-stu-id="944be-105">Centralized schedule information and the ability to pause and resume scheduled operations are two key features that distinguish shared schedules from item-specific schedules.</span></span>  
  
 <span data-ttu-id="944be-106">Una sola programación no admite todas las combinaciones de frecuencias.</span><span class="sxs-lookup"><span data-stu-id="944be-106">Not all frequency combinations can be supported in a single schedule.</span></span> <span data-ttu-id="944be-107">Por ejemplo, si desea ejecutar un informe todos los viernes a las 12:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="944be-107">For example, if you want to run a report at 12:00 P.M.</span></span> <span data-ttu-id="944be-108">y a las 4:00 p. m.</span><span class="sxs-lookup"><span data-stu-id="944be-108">and 4:00 P.M.</span></span> <span data-ttu-id="944be-109">debe crear dos programaciones diarias que especifiquen una fecha de ejecución en viernes, una con las 12:00 p. m. como hora de inicio</span><span class="sxs-lookup"><span data-stu-id="944be-109">every Friday, you must create two daily schedules that specify a Friday run date, one with a start time of 12:00 P.M.</span></span> <span data-ttu-id="944be-110">y otra con las 4:00 p. m. como hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="944be-110">and another with a start time of 4:00 P.M.</span></span>  
  
 <span data-ttu-id="944be-111">El procesamiento de programaciones se basa en la hora local del servidor de informes que hospeda y procesa la programación.</span><span class="sxs-lookup"><span data-stu-id="944be-111">Schedule processing is based on the local time of the report server that hosts and processes the schedule.</span></span>  
  
 <span data-ttu-id="944be-112">Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a un servidor de informes, haga clic con el botón derecho en **Programación compartida**y seleccione **Nueva programación**.</span><span class="sxs-lookup"><span data-stu-id="944be-112">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click **Shared Schedule**, and select **New Schedule**.</span></span> <span data-ttu-id="944be-113">Para guardar la programación, se debe estar ejecutando el servicio del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="944be-113">To save the schedule, SQL Server Agent service must be running.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="944be-114">Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="944be-114">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="944be-115">Para una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Características compatibles con las ediciones de SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span><span class="sxs-lookup"><span data-stu-id="944be-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="944be-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="944be-116">Options</span></span>  
 <span data-ttu-id="944be-117">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="944be-117">**Name**</span></span>  
 <span data-ttu-id="944be-118">Permite escribir el nombre de la programación compartida.</span><span class="sxs-lookup"><span data-stu-id="944be-118">Type a name for the shared schedule.</span></span> <span data-ttu-id="944be-119">Este nombre aparece en listas desplegables cuando los usuarios seleccionan una programación compartida para informes y suscripciones.</span><span class="sxs-lookup"><span data-stu-id="944be-119">This name appears in drop-down lists when users select a shared schedule for reports and subscriptions.</span></span> <span data-ttu-id="944be-120">Asegúrese de proporcionar un nombre descriptivo que se ajuste con facilidad dentro de una lista y que distinga con facilidad una programación compartida de otra.</span><span class="sxs-lookup"><span data-stu-id="944be-120">Be sure to provide a descriptive name that fits easily within a list and that easily distinguishes one shared schedule from another.</span></span> <span data-ttu-id="944be-121">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="944be-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="944be-122">También puede incluir espacios y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="944be-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="944be-123">No utilice los caracteres siguientes al especificar un nombre:</span><span class="sxs-lookup"><span data-stu-id="944be-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="944be-124">; ?</span><span class="sxs-lookup"><span data-stu-id="944be-124">; ?</span></span> <span data-ttu-id="944be-125">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="944be-125">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="944be-126">" /</span><span class="sxs-lookup"><span data-stu-id="944be-126">" /</span></span>  
  
 <span data-ttu-id="944be-127">**Empezar a ejecutar esta programación el**</span><span class="sxs-lookup"><span data-stu-id="944be-127">**Begin running this schedule on**</span></span>  
 <span data-ttu-id="944be-128">Permite especificar la fecha de inicio de esta programación.</span><span class="sxs-lookup"><span data-stu-id="944be-128">Specify a start date for this schedule.</span></span>  
  
 <span data-ttu-id="944be-129">**Detener esta programación el**</span><span class="sxs-lookup"><span data-stu-id="944be-129">**Stop this schedule on**</span></span>  
 <span data-ttu-id="944be-130">Permite especificar la fecha de expiración de esta programación.</span><span class="sxs-lookup"><span data-stu-id="944be-130">Specify an expiration date for this schedule.</span></span>  
  
 <span data-ttu-id="944be-131">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="944be-131">**Type**</span></span>  
 <span data-ttu-id="944be-132">Especifica si el patrón de periodicidad se basa principalmente en las horas, los días, las semanas o los meses.</span><span class="sxs-lookup"><span data-stu-id="944be-132">Specifies whether the recurrence pattern is based primarily on hours, days, weeks, or months.</span></span>  
  
 <span data-ttu-id="944be-133">**Hora (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="944be-133">**Hour (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="944be-134">Permite seleccionar las opciones correspondientes para ejecutar una operación programada en intervalos de horas (por ejemplo, ejecutar un informe cada 6 horas).</span><span class="sxs-lookup"><span data-stu-id="944be-134">Select options to run a scheduled operation in intervals of an hour (for example, to run a report every 6 hours).</span></span> <span data-ttu-id="944be-135">Puede especificar el intervalo en horas y minutos.</span><span class="sxs-lookup"><span data-stu-id="944be-135">You can specify the interval in hours and minutes.</span></span>  
  
 <span data-ttu-id="944be-136">**Día (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="944be-136">**Day (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="944be-137">Permite seleccionar las opciones correspondientes para ejecutar una operación programada en intervalos de días (por ejemplo, ejecutar un informe cada 2 días).</span><span class="sxs-lookup"><span data-stu-id="944be-137">Select options to run a scheduled operation in intervals of days (for example, to run a report every 2 days).</span></span> <span data-ttu-id="944be-138">Puede especificar el intervalo en días y a la hora y minutos en los que desea que se ejecute la programación.</span><span class="sxs-lookup"><span data-stu-id="944be-138">You can specify the interval in days and at the hour and minute you want the schedule to run.</span></span>  
  
 <span data-ttu-id="944be-139">**Semana (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="944be-139">**Week (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="944be-140">Permite seleccionar las opciones correspondientes para ejecutar una operación programada en intervalos de semanas o cuando el patrón que desea que se repita se base en semanas (por ejemplo, ejecutar un informe cada semana).</span><span class="sxs-lookup"><span data-stu-id="944be-140">Select options to run a scheduled operation in intervals of a week or when the pattern that you want to repeat is based on weeks (for example, to run a report every other week).</span></span> <span data-ttu-id="944be-141">Puede especificar una programación semanal para el día, hora y minuto en los que desea que se ejecute la programación.</span><span class="sxs-lookup"><span data-stu-id="944be-141">You can specify a weekly schedule to the day, hour, and minute that you want the schedule to run.</span></span>  
  
 <span data-ttu-id="944be-142">**Mes (patrón de periodicidad)**</span><span class="sxs-lookup"><span data-stu-id="944be-142">**Month (Recurrence Pattern)**</span></span>  
 <span data-ttu-id="944be-143">Permite seleccionar las opciones correspondientes para ejecutar una operación programada en intervalos de meses o cuando el patrón que desea que se repita se base en meses.</span><span class="sxs-lookup"><span data-stu-id="944be-143">Select options to run a scheduled operation in intervals of a month or when the pattern that you want to repeat is based on months.</span></span> <span data-ttu-id="944be-144">Puede especificar una programación mensual para el día, hora y minuto en los que desea que se ejecute la programación.</span><span class="sxs-lookup"><span data-stu-id="944be-144">You can specify a monthly schedule to the day, hour, and minute that you want the schedule to run.</span></span> <span data-ttu-id="944be-145">Puede quitar meses específicos de la programación.</span><span class="sxs-lookup"><span data-stu-id="944be-145">You can omit specific months from the schedule.</span></span>  
  
 <span data-ttu-id="944be-146">**Una vez**</span><span class="sxs-lookup"><span data-stu-id="944be-146">**Once**</span></span>  
 <span data-ttu-id="944be-147">Seleccione esta opción para crear una programación que se ejecute una sola vez o en una fecha y hora específicas.</span><span class="sxs-lookup"><span data-stu-id="944be-147">Select this option to create a schedule that runs only once, on a specific date and time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944be-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="944be-148">See Also</span></span>  
 <span data-ttu-id="944be-149">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="944be-149">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="944be-150">[Conectar con un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="944be-150">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="944be-151">[Crear, modificar y eliminar programaciones](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="944be-151">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="944be-152">[Programaciones](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="944be-152">[Schedules](../subscriptions/schedules.md) </span></span>  
 [<span data-ttu-id="944be-153">Servidor de informes en Management Studio (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="944be-153">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
