---
title: Tarea Comprobar la integridad de la base de datos (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.integrity.f1
- sql12.swb.maint.integrity.f1
helpviewer_keywords:
- Check Database Integrity Task dialog box
ms.assetid: 3534494a-5dfe-4738-b49a-e7fabd731c47
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f786755a3b7ed5d991b4cf0e32c067e355c111ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675356"
---
# <a name="check-database-integrity-task-maintenance-plan"></a><span data-ttu-id="1bf41-102">Tarea Comprobar la integridad de la base de datos (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="1bf41-102">Check Database Integrity Task (Maintenance Plan)</span></span>
  <span data-ttu-id="1bf41-103">Utilice el cuadro de diálogo **Tarea Comprobar la integridad de la base de datos** para comprobar la asignación e integridad estructural de las tablas de usuario y del sistema, y los índices de la base de datos por medio de la ejecución de la instrucción `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bf41-103">Use the **Check Database Integrity Task** dialog to check the allocation and structural integrity of user and system tables, and indexes in the database, by running the `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="1bf41-104">La ejecución de `DBCC` garantiza que se notifiquen todos los problemas de integridad que puedan existir en la base de datos, lo que permitirá su tratamiento posterior por parte de un administrador del sistema o del propietario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bf41-104">Running `DBCC` ensures that any integrity problems with the database are reported, thereby allowing them to be addressed later by a system administrator or database owner.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1bf41-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="1bf41-105">Options</span></span>  
 <span data-ttu-id="1bf41-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1bf41-106">**Connection**</span></span>  
 <span data-ttu-id="1bf41-107">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="1bf41-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="1bf41-108">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="1bf41-108">**New**</span></span>  
 <span data-ttu-id="1bf41-109">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="1bf41-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="1bf41-110">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="1bf41-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="1bf41-111">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="1bf41-111">**Databases**</span></span>  
 <span data-ttu-id="1bf41-112">Especifique las bases de datos a las que afecta esta tarea.</span><span class="sxs-lookup"><span data-stu-id="1bf41-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="1bf41-113">**Todas las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="1bf41-113">**All databases**</span></span>  
  
     <span data-ttu-id="1bf41-114">Genere un plan de mantenimiento que ejecute tareas de mantenimiento en todas las bases de datos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a excepción de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="1bf41-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except **tempdb**.</span></span>  
  
-   <span data-ttu-id="1bf41-115">**Todas las bases de datos del sistema**</span><span class="sxs-lookup"><span data-stu-id="1bf41-115">**All system databases**</span></span>  
  
     <span data-ttu-id="1bf41-116">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="1bf41-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="1bf41-117">No se ejecutarán tareas de mantenimiento en las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="1bf41-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="1bf41-118">**Todas las bases de datos de usuario**</span><span class="sxs-lookup"><span data-stu-id="1bf41-118">**All user databases**</span></span>  
  
     <span data-ttu-id="1bf41-119">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="1bf41-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="1bf41-120">No se ejecutarán tareas de mantenimiento en las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bf41-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="1bf41-121">**Las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="1bf41-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="1bf41-122">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento únicamente en las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="1bf41-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="1bf41-123">Si elige esta opción, deberá seleccionar al menos una base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="1bf41-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1bf41-124">Los planes de mantenimiento solo se ejecutan en bases de datos con un nivel de compatibilidad de 80 o superior.</span><span class="sxs-lookup"><span data-stu-id="1bf41-124">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="1bf41-125">Las bases de datos con un nivel de compatibilidad de 70 o inferior no se muestran.</span><span class="sxs-lookup"><span data-stu-id="1bf41-125">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="1bf41-126">**Incluir índices**</span><span class="sxs-lookup"><span data-stu-id="1bf41-126">**Include indexes**</span></span>  
 <span data-ttu-id="1bf41-127">Comprueba la integridad de todas las páginas de índice y de todas las páginas de datos de tabla.</span><span class="sxs-lookup"><span data-stu-id="1bf41-127">Check the integrity of all the index pages as well as the table data pages.</span></span>  
  
 <span data-ttu-id="1bf41-128">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="1bf41-128">**View T-SQL**</span></span>  
 <span data-ttu-id="1bf41-129">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="1bf41-129">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bf41-130">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="1bf41-130">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="1bf41-131">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="1bf41-131">New Connection Dialog Box</span></span>  
 <span data-ttu-id="1bf41-132">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="1bf41-132">**Connection name**</span></span>  
 <span data-ttu-id="1bf41-133">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="1bf41-133">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="1bf41-134">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="1bf41-134">**Select or enter a server name**</span></span>  
 <span data-ttu-id="1bf41-135">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="1bf41-135">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="1bf41-136">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="1bf41-136">**Refresh**</span></span>  
 <span data-ttu-id="1bf41-137">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="1bf41-137">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="1bf41-138">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="1bf41-138">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="1bf41-139">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1bf41-139">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="1bf41-140">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="1bf41-140">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="1bf41-141">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1bf41-141">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="1bf41-142">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="1bf41-142">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="1bf41-143">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bf41-143">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="1bf41-144">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1bf41-144">This option is not available.</span></span>  
  
 <span data-ttu-id="1bf41-145">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="1bf41-145">**User name**</span></span>  
 <span data-ttu-id="1bf41-146">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="1bf41-146">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="1bf41-147">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1bf41-147">This option is not available.</span></span>  
  
 <span data-ttu-id="1bf41-148">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="1bf41-148">**Password**</span></span>  
 <span data-ttu-id="1bf41-149">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="1bf41-149">Provide a password to use when authenticating.</span></span> <span data-ttu-id="1bf41-150">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1bf41-150">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf41-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bf41-151">See Also</span></span>  
 [<span data-ttu-id="1bf41-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf41-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
