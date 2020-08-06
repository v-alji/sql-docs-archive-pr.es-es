---
title: Tarea Reorganizar índice (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.defrag.f1
helpviewer_keywords:
- Reorganize Index Task dialog box
ms.assetid: e9cbebbd-f36f-4176-9832-382a46ac946c
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bbb154045b781f8a92dfce9c9d2f6ee2d819c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671511"
---
# <a name="reorganize-index-task-maintenance-plan"></a><span data-ttu-id="0ca10-102">Tarea Reorganizar índice (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="0ca10-102">Reorganize Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="0ca10-103">Use el cuadro de diálogo **Tarea Reorganizar índice** para mover las páginas del índice en un orden de búsqueda más eficaz.</span><span class="sxs-lookup"><span data-stu-id="0ca10-103">Use the **ReorganizeIndex Task** dialog to move index pages into a more efficient search order.</span></span> <span data-ttu-id="0ca10-104">Esta tarea utiliza la instrucción `ALTER INDEX REORGANIZE` con bases de datos de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ca10-104">This task uses the `ALTER INDEX REORGANIZE` statement with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] databases.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ca10-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="0ca10-105">Options</span></span>  
 <span data-ttu-id="0ca10-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="0ca10-106">**Connection**</span></span>  
 <span data-ttu-id="0ca10-107">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0ca10-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="0ca10-108">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="0ca10-108">**New**</span></span>  
 <span data-ttu-id="0ca10-109">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0ca10-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="0ca10-110">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="0ca10-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="0ca10-111">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="0ca10-111">**Databases**</span></span>  
 <span data-ttu-id="0ca10-112">Especifique las bases de datos a las que afecta esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0ca10-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="0ca10-113">**Todas las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="0ca10-113">**All databases**</span></span>  
  
     <span data-ttu-id="0ca10-114">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de tempdb.</span><span class="sxs-lookup"><span data-stu-id="0ca10-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="0ca10-115">**Todas las bases de datos del sistema**</span><span class="sxs-lookup"><span data-stu-id="0ca10-115">**All system databases**</span></span>  
  
     <span data-ttu-id="0ca10-116">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="0ca10-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="0ca10-117">No se ejecutarán tareas de mantenimiento en las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ca10-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="0ca10-118">**Todas las bases de datos de usuario**</span><span class="sxs-lookup"><span data-stu-id="0ca10-118">**All user databases**</span></span>  
  
     <span data-ttu-id="0ca10-119">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ca10-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="0ca10-120">No se ejecutarán tareas de mantenimiento en las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ca10-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="0ca10-121">**Las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="0ca10-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="0ca10-122">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento únicamente en las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="0ca10-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="0ca10-123">Si elige esta opción, deberá seleccionar al menos una base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="0ca10-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="0ca10-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="0ca10-124">**Object**</span></span>  
 <span data-ttu-id="0ca10-125">Limite la cuadrícula **Selección** para mostrar tablas, vistas o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="0ca10-125">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="0ca10-126">**Selección**</span><span class="sxs-lookup"><span data-stu-id="0ca10-126">**Selection**</span></span>  
 <span data-ttu-id="0ca10-127">Especifique las tablas o índices que se ven afectados por esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0ca10-127">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="0ca10-128">No estará disponible cuando se seleccione **Tablas y vistas** en el cuadro de diálogo **Objeto** .</span><span class="sxs-lookup"><span data-stu-id="0ca10-128">Not available when **Tables and Views** is selected in the **Object** box.</span></span>  
  
 <span data-ttu-id="0ca10-129">**Compactar objetos grandes**</span><span class="sxs-lookup"><span data-stu-id="0ca10-129">**Compact large objects**</span></span>  
 <span data-ttu-id="0ca10-130">Cancela la asignación de espacio para tablas y vistas cuando es posible.</span><span class="sxs-lookup"><span data-stu-id="0ca10-130">Deallocate space for tables and views when possible.</span></span> <span data-ttu-id="0ca10-131">Esta opción utiliza `ALTER INDEX LOB_COMPACTION = ON`.</span><span class="sxs-lookup"><span data-stu-id="0ca10-131">This option uses `ALTER INDEX LOB_COMPACTION = ON`.</span></span>  
  
 <span data-ttu-id="0ca10-132">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="0ca10-132">**View T-SQL**</span></span>  
 <span data-ttu-id="0ca10-133">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="0ca10-133">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ca10-134">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="0ca10-134">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="0ca10-135">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="0ca10-135">New Connection Dialog Box</span></span>  
 <span data-ttu-id="0ca10-136">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="0ca10-136">**Connection name**</span></span>  
 <span data-ttu-id="0ca10-137">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="0ca10-137">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="0ca10-138">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="0ca10-138">**Select or enter a server name**</span></span>  
 <span data-ttu-id="0ca10-139">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="0ca10-139">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="0ca10-140">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="0ca10-140">**Refresh**</span></span>  
 <span data-ttu-id="0ca10-141">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="0ca10-141">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="0ca10-142">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="0ca10-142">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="0ca10-143">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0ca10-143">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="0ca10-144">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="0ca10-144">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="0ca10-145">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="0ca10-145">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="0ca10-146">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="0ca10-146">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="0ca10-147">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ca10-147">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="0ca10-148">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="0ca10-148">This option is not available.</span></span>  
  
 <span data-ttu-id="0ca10-149">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="0ca10-149">**User name**</span></span>  
 <span data-ttu-id="0ca10-150">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="0ca10-150">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="0ca10-151">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="0ca10-151">This option is not available.</span></span>  
  
 <span data-ttu-id="0ca10-152">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="0ca10-152">**Password**</span></span>  
 <span data-ttu-id="0ca10-153">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="0ca10-153">Provide a password to use when authenticating.</span></span> <span data-ttu-id="0ca10-154">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="0ca10-154">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca10-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ca10-155">See Also</span></span>  
 <span data-ttu-id="0ca10-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ca10-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="0ca10-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ca10-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql)  
  
  
