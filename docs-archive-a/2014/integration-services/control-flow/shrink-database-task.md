---
title: Tarea Reducir base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.shrinkdatabasetask.f1
helpviewer_keywords:
- Shrink Database task
- database shrinking [Integration Services]
- shrinking databases
ms.assetid: e66286f8-97b1-4e5a-86b4-e56f1932b7d5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 587777928e362e87e4b691e3c46167c1239984cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676123"
---
# <a name="shrink-database-task"></a><span data-ttu-id="2739a-102">Reducir base de datos, tarea</span><span class="sxs-lookup"><span data-stu-id="2739a-102">Shrink Database Task</span></span>
  <span data-ttu-id="2739a-103">La tarea Reducir base de datos reduce el tamaño de los datos y los archivos de registro de bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2739a-103">The Shrink Database task reduces the size of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database data and log files.</span></span>  
  
 <span data-ttu-id="2739a-104">Un paquete puede utilizar la tarea Reducir base de datos para reducir los archivos de una o varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2739a-104">By using the Shrink Database task, a package can shrink files for a single database or multiple databases.</span></span>  
  
 <span data-ttu-id="2739a-105">La reducción de los archivos de datos permite recuperar espacio moviendo páginas de datos del final del archivo a espacio desocupado próximo al principio del archivo.</span><span class="sxs-lookup"><span data-stu-id="2739a-105">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="2739a-106">Cuando se crea suficiente espacio disponible al final del archivo, las páginas de datos situadas al final del mismo se pueden desasignar y devolver al sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="2739a-106">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="2739a-107">Los datos que se mueven para reducir un archivo se pueden dispersar en cualquier ubicación disponible en el archivo.</span><span class="sxs-lookup"><span data-stu-id="2739a-107">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="2739a-108">Esto produce la fragmentación de índices y puede reducir el rendimiento de las consultas que buscan un intervalo del índice.</span><span class="sxs-lookup"><span data-stu-id="2739a-108">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="2739a-109">Para eliminar la fragmentación, considere la posibilidad de volver a generar los índices en el archivo después de la reducción.</span><span class="sxs-lookup"><span data-stu-id="2739a-109">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="commands"></a><span data-ttu-id="2739a-110">Comandos:</span><span class="sxs-lookup"><span data-stu-id="2739a-110">Commands</span></span>  
 <span data-ttu-id="2739a-111">La tarea Reducir base de datos encapsula un comando DBCC SHRINKDATABASE, que incluye los siguientes argumentos y opciones:</span><span class="sxs-lookup"><span data-stu-id="2739a-111">The Shrink Database task encapsulates a DBCC SHRINKDATABASE command, including the following arguments and options:</span></span>  
  
-   <span data-ttu-id="2739a-112">*database_name*</span><span class="sxs-lookup"><span data-stu-id="2739a-112">*database_name*</span></span>  
  
-   <span data-ttu-id="2739a-113">*target_percent*</span><span class="sxs-lookup"><span data-stu-id="2739a-113">*target_percent*</span></span>  
  
-   <span data-ttu-id="2739a-114">NOTRUNCATE o TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="2739a-114">NOTRUNCATE or TRUNCATEONLY.</span></span>  
  
 <span data-ttu-id="2739a-115">Si la tarea Reducir base de datos reduce varias bases de datos, la tarea ejecuta varios comandos SHRINKDATABASE, uno para cada una de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2739a-115">If the Shrink Database task shrinks multiple databases, the task runs multiple SHRINKDATABASE commands, one for each database.</span></span> <span data-ttu-id="2739a-116">Todas las instancias del comando SHRINKDATABASE usan los mismos valores para los argumentos, excepto para el argumento *database_name* .</span><span class="sxs-lookup"><span data-stu-id="2739a-116">All instances of the SHRINKDATABASE command use the same argument values, except for the *database_name* argument.</span></span> <span data-ttu-id="2739a-117">Para obtener más información, vea [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2739a-117">For more information, see [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span></span>  
  
## <a name="configuration-of-the-shrink-database-task"></a><span data-ttu-id="2739a-118">Configuración de la tarea Reducir base de datos</span><span class="sxs-lookup"><span data-stu-id="2739a-118">Configuration of the Shrink Database Task</span></span>  
 <span data-ttu-id="2739a-119">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2739a-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="2739a-120">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2739a-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="2739a-121">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="2739a-121">For more information about the properties that you can set in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="2739a-122">Tarea Reducir base de datos &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="2739a-122">Shrink Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/shrink-database-task-maintenance-plan.md)  
  
 <span data-ttu-id="2739a-123">Para obtener más información sobre cómo configurar estas propiedades en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="2739a-123">For more information about setting these properties in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="2739a-124">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="2739a-124">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
