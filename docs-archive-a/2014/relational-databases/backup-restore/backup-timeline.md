---
title: Escala de tiempo de copia de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.POINTINTIMERESTORE.F1
- sql12.swb.backuptimeline.f1
helpviewer_keywords:
- Backup Timeline
ms.assetid: ae3565f2-ddb2-4469-a992-7531d4f9ebb8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b075f8c9ec32cfe483c64e34e9f9b4e4b6e80e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677722"
---
# <a name="backup-timeline"></a><span data-ttu-id="b1e15-102">Escala de tiempo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b1e15-102">Backup Timeline</span></span>
  <span data-ttu-id="b1e15-103">Use el cuadro de diálogo **Escala de tiempo de la copia de seguridad** para buscar y especificar las copias de seguridad para restaurar una base de datos a un momento dado.</span><span class="sxs-lookup"><span data-stu-id="b1e15-103">Use the **Backup Timeline** dialog box to locate and specify backups to restore a database to a point-in-time.</span></span> <span data-ttu-id="b1e15-104">El acceso al cuadro de diálogo **Escala de tiempo de la copia de seguridad** se abre haciendo clic en **Escala de tiempo** en el panel **Restaurar base de datos (página General)** .</span><span class="sxs-lookup"><span data-stu-id="b1e15-104">The **Backup Timeline** dialog box is accessed by clicking **Timeline** on the **Restore Database (General Page)** pane.</span></span> <span data-ttu-id="b1e15-105">Este cuadro de diálogo permite ver una escala de tiempo de las operaciones de restauración realizadas sobre la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b1e15-105">This dialog box allows you to view a timeline of the restore operations performed on the database.</span></span>  
  
 <span data-ttu-id="b1e15-106">El Asesor para recuperación de base de datos se asegura de que solo estén seleccionadas las copias de seguridad necesarias para restaurar a ese momento específico.</span><span class="sxs-lookup"><span data-stu-id="b1e15-106">The Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected.</span></span> <span data-ttu-id="b1e15-107">Estas copias de seguridad seleccionadas componen el plan de restauraciones recomendado para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="b1e15-107">These selected backups make up the recommended restore plan for your restore operation.</span></span> <span data-ttu-id="b1e15-108">Debe usar solo las copias de seguridad seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="b1e15-108">You should use only the selected backups.</span></span> <span data-ttu-id="b1e15-109">Para obtener más información sobre el Asistente para recuperación de base de datos, vea [Información general sobre restauración y recuperación &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1e15-109">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
## <a name="restore-to"></a><span data-ttu-id="b1e15-110">Restaurar en</span><span class="sxs-lookup"><span data-stu-id="b1e15-110">Restore to</span></span>  
 <span data-ttu-id="b1e15-111">La**Última copia de seguridad realizada** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b1e15-111">**Last backup taken** is selected by default.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b1e15-112">seleccionará las copias de seguridad adecuadas para restaurar la base de datos y la restaurará hasta el momento de la última copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b1e15-112">will select the appropriate backups to restore the database, and will restore the database to the point of the last backup.</span></span> <span data-ttu-id="b1e15-113">Haga clic en **Fecha y hora específicas** para establecer manualmente la fecha y hora (seleccionando un punto concreto en el tiempo).</span><span class="sxs-lookup"><span data-stu-id="b1e15-113">Click **A specific date and time** to manually set the date and time (selecting a specific point in time).</span></span>  
  
 <span data-ttu-id="b1e15-114">**Fecha y hora específicas** permite detener la restauración en la fecha y hora específicas que seleccione.</span><span class="sxs-lookup"><span data-stu-id="b1e15-114">**Specific date and time** permits you stop the restore at a specific date and time that you select.</span></span> <span data-ttu-id="b1e15-115">La escala de tiempo muestra una representación de las operaciones de copia de seguridad realizadas en las 24 horas anteriores y posteriores a la fecha y hora seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="b1e15-115">The timeline shows a representation of the backup operations performed in the 24 hours around the select date and time.</span></span>  
  
 <span data-ttu-id="b1e15-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="b1e15-116">**Date**</span></span>  
 <span data-ttu-id="b1e15-117">Escriba o seleccione una fecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b1e15-117">Enter or select a date from the drop-down list.</span></span>  
  
 <span data-ttu-id="b1e15-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="b1e15-118">**Time**</span></span>  
 <span data-ttu-id="b1e15-119">Escriba o seleccione una fecha para designar el momento dado en que la restauración debe detenerse.</span><span class="sxs-lookup"><span data-stu-id="b1e15-119">Enter or select a date to designate the specific point-in-time for the restore to stop.</span></span>  
  
 <span data-ttu-id="b1e15-120">**Intervalo de escala de tiempo**</span><span class="sxs-lookup"><span data-stu-id="b1e15-120">**Timeline Interval**</span></span>  
 <span data-ttu-id="b1e15-121">Muestra las opciones para los tipos de intervalo visibles en la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b1e15-121">Displays the options for the interval types viewable on the timeline.</span></span>  
  
## <a name="timeline-and-legend"></a><span data-ttu-id="b1e15-122">Escala de tiempo y leyenda</span><span class="sxs-lookup"><span data-stu-id="b1e15-122">Timeline and Legend</span></span>  
 <span data-ttu-id="b1e15-123">Use las barras de desplazamiento situadas sobre la escala de tiempo para mover el cursor hacia delante y hacia atrás a lo largo de la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b1e15-123">Use the scroll bar beneath the timeline to move the cursor forward and backward along the timeline.</span></span> <span data-ttu-id="b1e15-124">Haga clic en una copia de seguridad para mover la barra de desplazamiento al final de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b1e15-124">Click on a backup to move the scroll bar to the end of that backup.</span></span> <span data-ttu-id="b1e15-125">Mantenga el mouse sobre un marcador para mostrar una Información en pantalla que proporciona información acerca del conjunto de copia de seguridad seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b1e15-125">Hover the mouse over a marker to display a ScreenTip providing information about the selected backup set.</span></span> <span data-ttu-id="b1e15-126">La información de copia de seguridad se muestra en la escala de tiempo mediante los siguientes marcadores.</span><span class="sxs-lookup"><span data-stu-id="b1e15-126">Backup information is shown on the timeline by the following markers.</span></span>  
  
 <span data-ttu-id="b1e15-127">Triángulo mayor</span><span class="sxs-lookup"><span data-stu-id="b1e15-127">Larger triangle</span></span>  
 <span data-ttu-id="b1e15-128">Representa las copias de seguridad completas realizadas sobre la base de datos, con indicación del momento concreto en el que se realizó cada copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="b1e15-128">Represents the full backups performed on the database, denoting the specific point in time each full backup was performed.</span></span>  
  
 <span data-ttu-id="b1e15-129">Triángulo menor</span><span class="sxs-lookup"><span data-stu-id="b1e15-129">Smaller triangle</span></span>  
 <span data-ttu-id="b1e15-130">Representa las copias de seguridad diferenciales realizadas sobre la base de datos, con indicación del momento concreto en el que se realizó cada copia de seguridad diferencial.</span><span class="sxs-lookup"><span data-stu-id="b1e15-130">Represents the differential backups performed on the database, denoting the specific point in time that each differential backup was performed.</span></span>  
  
 <span data-ttu-id="b1e15-131">Áreas en verde</span><span class="sxs-lookup"><span data-stu-id="b1e15-131">Green shaded areas</span></span>  
 <span data-ttu-id="b1e15-132">Representan la cobertura de la copia de seguridad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="b1e15-132">Represents the transaction log backup coverage.</span></span>  
  
 <span data-ttu-id="b1e15-133">Línea roja</span><span class="sxs-lookup"><span data-stu-id="b1e15-133">Red line</span></span>  
 <span data-ttu-id="b1e15-134">Solo puede colocarse a lo largo de la escala de tiempo donde es posible la restauración.</span><span class="sxs-lookup"><span data-stu-id="b1e15-134">Can only be positioned along the timeline where the restore is possible.</span></span> <span data-ttu-id="b1e15-135">Moviendo la línea roja a lo largo de la escala de tiempo se ajustará la fecha y hora mostrada en los cuadros **Fecha** y **Hora** .</span><span class="sxs-lookup"><span data-stu-id="b1e15-135">Moving the red line along the timeline adjusts the date and time displayed in the **Date** and **Time** boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e15-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1e15-136">See Also</span></span>  
 [<span data-ttu-id="b1e15-137">Restaurar la base de datos &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="b1e15-137">Restore Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
  
