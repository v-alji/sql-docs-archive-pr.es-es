---
title: Ventana de subprocesos
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Threads Window [Transact-SQL]
ms.assetid: e153f619-0049-4162-9076-c24a454f3278
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3460c892c182996a753c2a16076418a6b2008f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745186"
---
# <a name="threads-window"></a><span data-ttu-id="e5758-102">Ventana de subprocesos</span><span class="sxs-lookup"><span data-stu-id="e5758-102">Threads Window</span></span>
  <span data-ttu-id="e5758-103">La ventana **Subprocesos** muestra información sobre el subproceso de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que usa la sesión del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="e5758-103">The **Threads** window displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] thread that is used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor session that is being debugged.</span></span> <span data-ttu-id="e5758-104">Debe estar en modo de depuración para mostrar la información del subproceso.</span><span class="sxs-lookup"><span data-stu-id="e5758-104">You must be in debug mode to display the thread information.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="e5758-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="e5758-105">Task List</span></span>  
 <span data-ttu-id="e5758-106">**Para tener acceso a la ventana Subprocesos**</span><span class="sxs-lookup"><span data-stu-id="e5758-106">**To access the Threads window**</span></span>  
  
-   <span data-ttu-id="e5758-107">En el menú **Depurar** , haga clic en **Ventanas**y, a continuación, haga clic en **Subprocesos**.</span><span class="sxs-lookup"><span data-stu-id="e5758-107">On the **Debug** menu, click **Windows**, and then click **Threads**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="e5758-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="e5758-108">Columns</span></span>  
 <span data-ttu-id="e5758-109">**Id**</span><span class="sxs-lookup"><span data-stu-id="e5758-109">**ID**</span></span>  
 <span data-ttu-id="e5758-110">Es un número de identificación único que el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] asigna al subproceso.</span><span class="sxs-lookup"><span data-stu-id="e5758-110">Is a unique identifying number that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger assigns to the thread.</span></span> <span data-ttu-id="e5758-111">Puede encontrar más información sobre el subproceso seleccionando una fila de la vista de administración dinámica sys.dm_os_threads.</span><span class="sxs-lookup"><span data-stu-id="e5758-111">You can find more information about the thread by selecting a row from the sys.dm_os_threads dynamic management view.</span></span>  
  
 <span data-ttu-id="e5758-112">Si no está usando el modo de agrupación ligera, seleccione la fila en la que el valor de os_thread_id coincide con el valor de la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="e5758-112">If you are not running in lightweight pooling mode, select the row in which the value in os_thread_id matches the value in the **ID** column.</span></span> <span data-ttu-id="e5758-113">Si está usando el modo de agrupación ligera, seleccione la fila en la que el valor en fiber_context_address coincide con el valor de la columna **ID** .</span><span class="sxs-lookup"><span data-stu-id="e5758-113">If you are running in lightweight pooling mode, select the row in which the value in fiber_context_address matches the value in the **ID** column.</span></span>  
  
 <span data-ttu-id="e5758-114">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e5758-114">**Name**</span></span>  
 <span data-ttu-id="e5758-115">Muestra información sobre la sesión de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en el formato **nombreDeEquipo/nombreDeInstancia [SPID]** .</span><span class="sxs-lookup"><span data-stu-id="e5758-115">Displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] session in the format **ComputerName/InstanceName [SPID]**.</span></span>  
  
 <span data-ttu-id="e5758-116">**nombreDeEquipo**</span><span class="sxs-lookup"><span data-stu-id="e5758-116">**ComputerName**</span></span>  
 <span data-ttu-id="e5758-117">Nombre del equipo que ejecuta la instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] a la que la sesión del Editor de consultas está conectada.</span><span class="sxs-lookup"><span data-stu-id="e5758-117">The name of the computer that is running the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="e5758-118">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="e5758-118">**InstanceName**</span></span>  
 <span data-ttu-id="e5758-119">Nombre de la instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] a la que la sesión del Editor de consultas está conectada.</span><span class="sxs-lookup"><span data-stu-id="e5758-119">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="e5758-120">**[SPID]**</span><span class="sxs-lookup"><span data-stu-id="e5758-120">**[SPID]**</span></span>  
 <span data-ttu-id="e5758-121">Identificador del proceso de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que identifica de forma única esta sesión.</span><span class="sxs-lookup"><span data-stu-id="e5758-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session process ID that uniquely identifies this session.</span></span> <span data-ttu-id="e5758-122">Puede obtener más información sobre la sesión seleccionando la fila en la vista sys.sysprocesses que tenga el mismo valor en la columna spid.</span><span class="sxs-lookup"><span data-stu-id="e5758-122">You can obtain more information about the session by selecting the row in the sys.sysprocesses view that has the same value in the spid column.</span></span>  
  
 <span data-ttu-id="e5758-123">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="e5758-123">**Location**</span></span>  
 <span data-ttu-id="e5758-124">Muestra el nombre del archivo de script que se utiliza en la sesión del Editor de consultas que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="e5758-124">Displays the name of the script file that is used in the Query Editor session that is being debugged.</span></span>  
  
 <span data-ttu-id="e5758-125">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="e5758-125">**Priority**</span></span>  
 <span data-ttu-id="e5758-126">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] no admite esta característica.</span><span class="sxs-lookup"><span data-stu-id="e5758-126">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="e5758-127">**Suspender**</span><span class="sxs-lookup"><span data-stu-id="e5758-127">**Suspend**</span></span>  
 <span data-ttu-id="e5758-128">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] no admite esta característica.</span><span class="sxs-lookup"><span data-stu-id="e5758-128">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5758-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5758-129">See Also</span></span>  
 <span data-ttu-id="e5758-130">[Depurador de Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="e5758-130">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="e5758-131">[Ver información del depurador de Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="e5758-131">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="e5758-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e5758-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span></span>  
 [<span data-ttu-id="e5758-133">sys.sysprocesses &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5758-133">sys.sysprocesses &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql)  
