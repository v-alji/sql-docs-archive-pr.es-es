---
title: Tarea Limpieza de mantenimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.maintenancecleanuptask.f1
helpviewer_keywords:
- deleting files
- removing files
- Maintenance Cleanup task
ms.assetid: 73ad3cd6-9a6d-44cf-905f-c56aa658bf42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4d39dd775402adadbe51eaadc530f4feb288ab9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671612"
---
# <a name="maintenance-cleanup-task"></a><span data-ttu-id="b27d6-102">tarea, Limpieza de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="b27d6-102">Maintenance Cleanup Task</span></span>
  <span data-ttu-id="b27d6-103">La tarea Limpieza de mantenimiento quita archivos relacionados con planes de mantenimiento, entre los que se incluyen archivos de copia de seguridad de la base de datos e informes creados a partir de planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b27d6-103">The Maintenance Cleanup task removes files related to maintenance plans, including database backup files and reports created by maintenance plans.</span></span> <span data-ttu-id="b27d6-104">Para obtener más información, vea [Planes de mantenimiento](../../relational-databases/maintenance-plans/maintenance-plans.md) y [Realizar copias de seguridad y restaurar bases de datos de SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b27d6-104">For more information, see [Maintenance Plans](../../relational-databases/maintenance-plans/maintenance-plans.md) and [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="b27d6-105">El uso de la tarea Limpieza de mantenimiento permite que un paquete pueda quitar los archivos de copia de seguridad o los informes del plan de mantenimiento del servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="b27d6-105">By using the Maintenance Cleanup task, a package can remove the backup files or maintenance plan reports on the specified server.</span></span> <span data-ttu-id="b27d6-106">La tarea Limpieza de mantenimiento incluye una opción para quitar un archivo específico o un grupo de archivos de una carpeta.</span><span class="sxs-lookup"><span data-stu-id="b27d6-106">The Maintenance Cleanup task includes an option to remove a specific file or remove a group of files in a folder.</span></span> <span data-ttu-id="b27d6-107">También puede especificar la extensión de los archivos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="b27d6-107">Optionally you can specify the extension of the files to delete.</span></span>  
  
 <span data-ttu-id="b27d6-108">Cuando se configura la tarea Limpieza de mantenimiento para quitar archivos de copia de seguridad, la extensión del nombre de archivo predeterminada es BAK.</span><span class="sxs-lookup"><span data-stu-id="b27d6-108">When you configure the Maintenance Cleanup task to remove backup files, the default file name extension is BAK.</span></span> <span data-ttu-id="b27d6-109">Para archivos de informe, la extensión predeterminada es TXT.</span><span class="sxs-lookup"><span data-stu-id="b27d6-109">For report files, the default file name extension is TXT.</span></span> <span data-ttu-id="b27d6-110">Puede actualizar las extensiones para que se adapten a sus necesidades; la única limitación es que las extensiones deben tener una longitud inferior a 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b27d6-110">You can update the extensions to suit your needs; the only limitation is that extensions must be less than 256 characters long.</span></span>  
  
 <span data-ttu-id="b27d6-111">Normalmente, conviene quitar archivos los antiguos que ya no son necesarios; la tarea Limpieza de mantenimiento se puede configurar para eliminar archivos con una antigüedad específica.</span><span class="sxs-lookup"><span data-stu-id="b27d6-111">Typically, you want to remove old files that are no longer needed, and the Maintenance Cleanup task can be configured to delete files that have reached a specified age.</span></span> <span data-ttu-id="b27d6-112">Por ejemplo, se puede configurar la tarea para eliminar archivos que tienen más de cuatro semanas.</span><span class="sxs-lookup"><span data-stu-id="b27d6-112">For example, the task can be configured to delete files that are older than four weeks.</span></span> <span data-ttu-id="b27d6-113">También puede especificar la antigüedad de los archivos que desea eliminar en días, semanas, meses o años.</span><span class="sxs-lookup"><span data-stu-id="b27d6-113">You can specify the age of files to delete by using days, weeks, months, or years.</span></span> <span data-ttu-id="b27d6-114">Si no especifica la antigüedad mínima de los archivos que desea eliminar, se eliminan todos los archivos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="b27d6-114">If you do not specify the minimum age of files to delete, all files of the specified type are deleted.</span></span>  
  
 <span data-ttu-id="b27d6-115">A diferencia de versiones anteriores de la tarea Limpieza de mantenimiento, la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la tarea no elimina automáticamente los archivos incluidos en los subdirectorios del directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="b27d6-115">In contrast to earlier versions of the Maintenance Cleanup task, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version of the task does not automatically delete files in the subdirectories of the specified directory.</span></span> <span data-ttu-id="b27d6-116">Esta restricción reduce el área expuesta a cualquier ataque que pudiera utilizar la funcionalidad de la tarea Limpieza de mantenimiento para eliminar archivos de forma malintencionada.</span><span class="sxs-lookup"><span data-stu-id="b27d6-116">This constraint reduces the surface area of any attack that could exploit the functionality of the Maintenance Cleanup task to delete files maliciously.</span></span> <span data-ttu-id="b27d6-117">Para eliminar las subcarpetas del primer nivel, debe seleccionarlo explícitamente. Para ello, active la opción **Incluir subcarpetas de primer nivel** en el cuadro de diálogo **Tarea Limpieza de mantenimiento** .</span><span class="sxs-lookup"><span data-stu-id="b27d6-117">To delete the first-level subfolders, you must explicitly elect to do this by checking the **Include first-level subfolders** option in the **Maintenance Cleanup Task** dialog box.</span></span>  
  
## <a name="configuration-of-the-maintenance-cleanup-task"></a><span data-ttu-id="b27d6-118">Configuración de la tarea Limpieza de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="b27d6-118">Configuration of the Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="b27d6-119">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b27d6-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="b27d6-120">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b27d6-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b27d6-121">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="b27d6-121">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="b27d6-122">Tarea Limpieza de mantenimiento &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="b27d6-122">Maintenance Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/maintenance-cleanup-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="b27d6-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b27d6-123">Related Tasks</span></span>  
 <span data-ttu-id="b27d6-124">Para obtener información sobre cómo establecer estas propiedades en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Establecer las propiedades de tareas o contenedores](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="b27d6-124">For details about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27d6-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b27d6-125">See Also</span></span>  
 <span data-ttu-id="b27d6-126">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b27d6-126">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="b27d6-127">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="b27d6-127">Control Flow</span></span>](control-flow.md)  
  
  
