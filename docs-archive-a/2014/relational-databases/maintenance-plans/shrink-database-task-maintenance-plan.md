---
title: Tarea Reducir base de datos (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.shrink.f1
- Shrink Database Task
- Shrink Database(s) Task
helpviewer_keywords:
- Shrink Database Task dialog box
ms.assetid: a9874cac-cded-4145-9c38-8aafd267dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8ee6060a4ee6ca3272434cf3d9115638a675e62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745740"
---
# <a name="shrink-database-task-maintenance-plan"></a><span data-ttu-id="724c9-102">Tarea Reducir base de datos (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="724c9-102">Shrink Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="724c9-103">Utilice el cuadro de diálogo **Tarea Reducir base de datos** para crear una tarea que intente reducir el tamaño de las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="724c9-103">Use the **Shrink Database Task** dialog to create a task that attempts to reduce the size of the selected databases.</span></span> <span data-ttu-id="724c9-104">Utilice las opciones que se indican a continuación para determinar el espacio disponible que se mantiene en la base de datos después de reducir su tamaño (cuanto mayor sea el porcentaje, menos se podrá reducir la base de datos).</span><span class="sxs-lookup"><span data-stu-id="724c9-104">Use the options below to determine the amount of unused space to remain in the database after the database is shrunk (the larger the percentage, the less the database can shrink).</span></span> <span data-ttu-id="724c9-105">El valor se basa es un porcentaje de los datos reales de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="724c9-105">The value is based on the percentage of the actual data in the database.</span></span> <span data-ttu-id="724c9-106">Por ejemplo, una base de datos de 100 MB que contenga 60 MB de datos y 40 MB de espacio disponible, con un porcentaje de espacio disponible del 50 por ciento, dará como resultado 60 MB de datos y 30 MB de espacio disponible (porque el 50 por ciento de 60 MB es 30 MB).</span><span class="sxs-lookup"><span data-stu-id="724c9-106">For example, a 100-MB database containing 60 MB of data and 40 MB of free space, with a free space percentage of 50 percent, would result in 60 MB of data and 30 MB of free space (because 50 percent of 60 MB is 30 MB).</span></span> <span data-ttu-id="724c9-107">Solo se elimina el espacio de la base de datos que exceda el porcentaje indicado.</span><span class="sxs-lookup"><span data-stu-id="724c9-107">Only excess space in the database is eliminated.</span></span> <span data-ttu-id="724c9-108">Los valores válidos son de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="724c9-108">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="724c9-109">La reducción de los archivos de datos permite recuperar espacio moviendo páginas de datos del final del archivo a espacio desocupado próximo al principio del archivo.</span><span class="sxs-lookup"><span data-stu-id="724c9-109">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="724c9-110">Cuando se crea suficiente espacio disponible al final del archivo, las páginas de datos situadas al final del mismo se pueden desasignar y devolver al sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="724c9-110">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="724c9-111">Los datos que se mueven para reducir un archivo se pueden dispersar en cualquier ubicación disponible en el archivo.</span><span class="sxs-lookup"><span data-stu-id="724c9-111">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="724c9-112">Esto produce la fragmentación de índices y puede reducir el rendimiento de las consultas que buscan un intervalo del índice.</span><span class="sxs-lookup"><span data-stu-id="724c9-112">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="724c9-113">Para eliminar la fragmentación, considere la posibilidad de volver a generar los índices en el archivo después de la reducción.</span><span class="sxs-lookup"><span data-stu-id="724c9-113">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
 <span data-ttu-id="724c9-114">Esta tarea ejecuta la instrucción DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="724c9-114">This task executes the DBCC SHRINKDATABASE statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="724c9-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="724c9-115">Options</span></span>  
 <span data-ttu-id="724c9-116">**Connection**</span><span class="sxs-lookup"><span data-stu-id="724c9-116">**Connection**</span></span>  
 <span data-ttu-id="724c9-117">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="724c9-117">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="724c9-118">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="724c9-118">**New**</span></span>  
 <span data-ttu-id="724c9-119">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="724c9-119">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="724c9-120">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="724c9-120">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="724c9-121">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="724c9-121">**Databases**</span></span>  
 <span data-ttu-id="724c9-122">Especifique las bases de datos a las que afecta esta tarea.</span><span class="sxs-lookup"><span data-stu-id="724c9-122">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="724c9-123">**Todas las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="724c9-123">**All databases**</span></span>  
  
     <span data-ttu-id="724c9-124">Genere un plan de mantenimiento que ejecute tareas de mantenimiento en todas las bases de datos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a excepción de tempdb.</span><span class="sxs-lookup"><span data-stu-id="724c9-124">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="724c9-125">**Todas las bases de datos del sistema**</span><span class="sxs-lookup"><span data-stu-id="724c9-125">**All system databases**</span></span>  
  
     <span data-ttu-id="724c9-126">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de tempdb.</span><span class="sxs-lookup"><span data-stu-id="724c9-126">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="724c9-127">No se ejecutarán tareas de mantenimiento en las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="724c9-127">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="724c9-128">**Todas las bases de datos de usuario**</span><span class="sxs-lookup"><span data-stu-id="724c9-128">**All user databases**</span></span>  
  
     <span data-ttu-id="724c9-129">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="724c9-129">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="724c9-130">No se ejecutarán tareas de mantenimiento en las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="724c9-130">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="724c9-131">**Las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="724c9-131">**These databases**</span></span>  
  
     <span data-ttu-id="724c9-132">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento únicamente en las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="724c9-132">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="724c9-133">Si elige esta opción, deberá seleccionar al menos una base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="724c9-133">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="724c9-134">Los planes de mantenimiento solo se ejecutan en bases de datos con un nivel de compatibilidad de 80 o superior.</span><span class="sxs-lookup"><span data-stu-id="724c9-134">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="724c9-135">Las bases de datos con un nivel de compatibilidad de 70 o inferior no se muestran.</span><span class="sxs-lookup"><span data-stu-id="724c9-135">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="724c9-136">**Reducir la base de datos cuando se incremente por encima de**</span><span class="sxs-lookup"><span data-stu-id="724c9-136">**Shrink database when it grows beyond**</span></span>  
 <span data-ttu-id="724c9-137">Especifique el tamaño en megabytes que provoca la ejecución de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="724c9-137">Specify the size in megabytes that causes the task to execute.</span></span>  
  
 <span data-ttu-id="724c9-138">**Espacio disponible tras la reducción**</span><span class="sxs-lookup"><span data-stu-id="724c9-138">**Amount of free space to remain after shrink**</span></span>  
 <span data-ttu-id="724c9-139">Detiene la reducción cuando el espacio disponible en los archivos de base de datos alcanza este tamaño.</span><span class="sxs-lookup"><span data-stu-id="724c9-139">Stop shrinking when free space in database files reaches this size.</span></span>  
  
 <span data-ttu-id="724c9-140">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="724c9-140">**View T-SQL**</span></span>  
 <span data-ttu-id="724c9-141">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="724c9-141">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="724c9-142">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="724c9-142">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="724c9-143">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="724c9-143">New Connection Dialog Box</span></span>  
 <span data-ttu-id="724c9-144">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="724c9-144">**Connection name**</span></span>  
 <span data-ttu-id="724c9-145">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="724c9-145">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="724c9-146">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="724c9-146">**Select or enter a server name**</span></span>  
 <span data-ttu-id="724c9-147">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="724c9-147">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="724c9-148">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="724c9-148">**Refresh**</span></span>  
 <span data-ttu-id="724c9-149">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="724c9-149">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="724c9-150">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="724c9-150">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="724c9-151">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="724c9-151">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="724c9-152">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="724c9-152">**Use Windows NT Integrated security**</span></span>  
 <span data-ttu-id="724c9-153">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="724c9-153">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="724c9-154">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="724c9-154">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="724c9-155">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="724c9-155">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="724c9-156">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="724c9-156">This option is not available.</span></span>  
  
 <span data-ttu-id="724c9-157">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="724c9-157">**User name**</span></span>  
 <span data-ttu-id="724c9-158">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="724c9-158">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="724c9-159">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="724c9-159">This option is not available.</span></span>  
  
 <span data-ttu-id="724c9-160">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="724c9-160">**Password**</span></span>  
 <span data-ttu-id="724c9-161">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="724c9-161">Provide a password to use when authenticating.</span></span> <span data-ttu-id="724c9-162">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="724c9-162">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724c9-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="724c9-163">See Also</span></span>  
 [<span data-ttu-id="724c9-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="724c9-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql)  
  
  
