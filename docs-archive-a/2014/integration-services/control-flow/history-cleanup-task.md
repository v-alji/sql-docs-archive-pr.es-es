---
title: Tarea Limpieza de historial | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.historycleanuptask.f1
helpviewer_keywords:
- history tables [SQL Server]
- History Cleanup task [Integration Services]
ms.assetid: 5defc5b9-dfd3-4859-a7fe-ac8c2b5480f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84bc697b7fb18269fc581cea51e111aebc82c15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662198"
---
# <a name="history-cleanup-task"></a><span data-ttu-id="b2e79-102">Tarea Limpieza de historial</span><span class="sxs-lookup"><span data-stu-id="b2e79-102">History Cleanup Task</span></span>
  <span data-ttu-id="b2e79-103">La tarea Limpieza de historial elimina entradas de las siguientes tablas de historial de la base de datos msdb de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2e79-103">The History Cleanup task deletes entries in the following history tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
-   <span data-ttu-id="b2e79-104">backupfile</span><span class="sxs-lookup"><span data-stu-id="b2e79-104">backupfile</span></span>  
  
-   <span data-ttu-id="b2e79-105">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="b2e79-105">backupfilegroup</span></span>  
  
-   <span data-ttu-id="b2e79-106">backupmediafamily</span><span class="sxs-lookup"><span data-stu-id="b2e79-106">backupmediafamily</span></span>  
  
-   <span data-ttu-id="b2e79-107">backupmediaset</span><span class="sxs-lookup"><span data-stu-id="b2e79-107">backupmediaset</span></span>  
  
-   <span data-ttu-id="b2e79-108">backupset</span><span class="sxs-lookup"><span data-stu-id="b2e79-108">backupset</span></span>  
  
-   <span data-ttu-id="b2e79-109">restorefile</span><span class="sxs-lookup"><span data-stu-id="b2e79-109">restorefile</span></span>  
  
-   <span data-ttu-id="b2e79-110">restorefilegroup</span><span class="sxs-lookup"><span data-stu-id="b2e79-110">restorefilegroup</span></span>  
  
-   <span data-ttu-id="b2e79-111">restorehistory</span><span class="sxs-lookup"><span data-stu-id="b2e79-111">restorehistory</span></span>  
  
 <span data-ttu-id="b2e79-112">Un paquete puede utilizar la tarea Limpieza del historial para eliminar datos históricos relacionados con las actividades de copias de seguridad y restauración, trabajos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y planes de mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b2e79-112">By using the History Cleanup task, a package can delete historical data related to backup and restore activities, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, and database maintenance plans.</span></span>  
  
 <span data-ttu-id="b2e79-113">Esta tarea encapsula el procedimiento almacenado del sistema sp_delete_backuphistory y pasa la fecha especificada al procedimiento como un argumento.</span><span class="sxs-lookup"><span data-stu-id="b2e79-113">This task encapsulates the sp_delete_backuphistory system stored procedure and passes the specified date to the procedure as an argument.</span></span> <span data-ttu-id="b2e79-114">Para más información, vea [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2e79-114">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
## <a name="configuration-of-the-history-cleanup-task"></a><span data-ttu-id="b2e79-115">Configuración de la tarea Limpieza de historial</span><span class="sxs-lookup"><span data-stu-id="b2e79-115">Configuration of the History Cleanup Task</span></span>  
 <span data-ttu-id="b2e79-116">La tarea incluye una propiedad para especificar la fecha más antigua de los datos almacenados en las tablas de historial.</span><span class="sxs-lookup"><span data-stu-id="b2e79-116">The task includes a property for specifying the oldest date of data retained in the history tables.</span></span> <span data-ttu-id="b2e79-117">Puede indicar la fecha mediante el número de días, semanas, meses o años del día actual, y la tarea traducirá automáticamente el intervalo a una fecha.</span><span class="sxs-lookup"><span data-stu-id="b2e79-117">You can indicate the date by number of days, weeks, months, or years from the current day, and the task automatically translates the interval to a date.</span></span>  
  
 <span data-ttu-id="b2e79-118">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2e79-118">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="b2e79-119">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2e79-119">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b2e79-120">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2e79-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="b2e79-121">Tarea Limpieza de historial &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="b2e79-121">History Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/history-cleanup-task-maintenance-plan.md)  
  
 <span data-ttu-id="b2e79-122">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="b2e79-122">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="b2e79-123">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="b2e79-123">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2e79-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2e79-124">See Also</span></span>  
 <span data-ttu-id="b2e79-125">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b2e79-125">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="b2e79-126">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="b2e79-126">Control Flow</span></span>](control-flow.md)  
  
  
