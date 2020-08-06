---
title: Tarea Actualizar estadísticas (Plan de mantenimiento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.statistics.f1
helpviewer_keywords:
- Updates Statistics Task dialog box
ms.assetid: 22902fd0-eb39-4f18-af94-3fcb69d2a3a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486ef2da96785ed200900f497435117ef6437cb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677629"
---
# <a name="update-statistics-task-maintenance-plan"></a><span data-ttu-id="bd9ff-102">Tarea Actualizar estadísticas (Plan de mantenimiento)</span><span class="sxs-lookup"><span data-stu-id="bd9ff-102">Update Statistics Task (Maintenance Plan)</span></span>
  <span data-ttu-id="bd9ff-103">Use el cuadro de diálogo **Tarea Actualizar estadísticas** para actualizar la información de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sobre los datos de tablas e índices.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-103">Use the **Update Statistics Task** dialog to update [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information about the data in the tables and indexes.</span></span> <span data-ttu-id="bd9ff-104">Esta tarea vuelve a muestrear las estadísticas de distribución de cada índice creado en las tablas de usuario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-104">This task resamples the distribution statistics of each index created on user tables in the database.</span></span> <span data-ttu-id="bd9ff-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza las estadísticas de distribución para optimizar la navegación de las tablas durante el procesamiento de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd9ff-105">The distribution statistics are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize navigation through tables during the processing of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="bd9ff-106">Para generar automáticamente las estadísticas de distribución, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muestrea periódicamente los datos de la tabla correspondiente para cada índice.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-106">To build the distribution statistics automatically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically samples the data in the corresponding table for each index.</span></span> <span data-ttu-id="bd9ff-107">Este tamaño de la muestra se basa en el número de filas de la tabla y en la frecuencia de modificación de los datos.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-107">This size of the sample is based on the number of rows in the table and the frequency of data modification.</span></span> <span data-ttu-id="bd9ff-108">Utilice esta opción para realizar un muestreo adicional con el porcentaje especificado de datos de las tablas.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-108">Use this option to perform an additional sampling using the specified percentage of data in the tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bd9ff-109">utiliza esta información para crear planes de consultas mejores.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-109">uses this information to create better query plans.</span></span>  
  
 <span data-ttu-id="bd9ff-110">Esta tarea ejecuta la instrucción UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-110">This task executes the UPDATE STATISTICS statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bd9ff-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="bd9ff-111">Options</span></span>  
 <span data-ttu-id="bd9ff-112">**Connection**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-112">**Connection**</span></span>  
 <span data-ttu-id="bd9ff-113">Seleccione la conexión al servidor que va a utilizar para la realización de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-113">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="bd9ff-114">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-114">**New**</span></span>  
 <span data-ttu-id="bd9ff-115">Cree una nueva conexión de servidor que utilizará al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-115">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="bd9ff-116">El cuadro de diálogo **Nueva conexión** se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-116">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="bd9ff-117">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-117">**Databases**</span></span>  
 <span data-ttu-id="bd9ff-118">Especifique las bases de datos a las que afecta esta tarea.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-118">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="bd9ff-119">**Todas las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-119">**All databases**</span></span>  
  
     <span data-ttu-id="bd9ff-120">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de tempdb.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-120">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, except tempdb.</span></span>  
  
-   <span data-ttu-id="bd9ff-121">**Todas las bases de datos del sistema**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-121">**All system databases**</span></span>  
  
     <span data-ttu-id="bd9ff-122">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a excepción de tempdb.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-122">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="bd9ff-123">No se ejecutarán tareas de mantenimiento en las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-123">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="bd9ff-124">**Todas las bases de datos de usuario**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-124">**All user databases**</span></span>  
  
     <span data-ttu-id="bd9ff-125">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento en todas las bases de datos creadas por usuarios.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-125">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="bd9ff-126">No se ejecutarán tareas de mantenimiento en las bases de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd9ff-126">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="bd9ff-127">**Las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-127">**These specific databases**</span></span>  
  
     <span data-ttu-id="bd9ff-128">Genera un plan de mantenimiento que ejecuta tareas de mantenimiento únicamente en las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-128">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="bd9ff-129">Si elige esta opción, deberá seleccionar al menos una base de datos de la lista.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-129">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="bd9ff-130">**Nota** Los planes de mantenimiento solo se pueden ejecutar en bases de datos con un nivel de compatibilidad de 80 o superior.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-130">**Note** Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="bd9ff-131">Las bases de datos con un nivel de compatibilidad de 70 o inferior no se muestran.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-131">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="bd9ff-132">**Object**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-132">**Object**</span></span>  
 <span data-ttu-id="bd9ff-133">Limite la cuadrícula **Selección** para mostrar tablas, vistas o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-133">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="bd9ff-134">**Selección**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-134">**Selection**</span></span>  
 <span data-ttu-id="bd9ff-135">Especifique las tablas o índices que se ven afectados por esta tarea.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-135">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="bd9ff-136">No estará disponible cuando se seleccione **Tablas y vistas** en el cuadro Objeto.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-136">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="bd9ff-137">**Todas las estadísticas existentes**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-137">**All existing statistics**</span></span>  
 <span data-ttu-id="bd9ff-138">Actualiza las estadísticas tanto de las columnas como de los índices.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-138">Update statistics for both columns and indexes.</span></span>  
  
 <span data-ttu-id="bd9ff-139">**Solo estadísticas de columna**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-139">**Column statistics only**</span></span>  
 <span data-ttu-id="bd9ff-140">Solo actualiza las estadísticas de las columnas.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-140">Only update column statistics.</span></span>  
  
 <span data-ttu-id="bd9ff-141">**Solo estadísticas de índice**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-141">**Index statistics only**</span></span>  
 <span data-ttu-id="bd9ff-142">Solo actualiza las estadísticas de los índices.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-142">Only update index statistics.</span></span>  
  
 <span data-ttu-id="bd9ff-143">**Tipo de recorrido**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-143">**Scan type**</span></span>  
 <span data-ttu-id="bd9ff-144">Tipo de recorrido usado para obtener estadísticas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-144">Type of scan used to gather updated statistics.</span></span>  
  
 <span data-ttu-id="bd9ff-145">**Recorrido completo**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-145">**Full scan**</span></span>  
 <span data-ttu-id="bd9ff-146">Lee todas las filas de la tabla o vista para obtener las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-146">Read all rows in the table or view to gather the statistics.</span></span>  
  
 <span data-ttu-id="bd9ff-147">**Muestrear por**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-147">**Sample by**</span></span>  
 <span data-ttu-id="bd9ff-148">Especifica el porcentaje de la tabla o vista indizada, o el número de filas del que se tomarán muestras cuando se recopilen las estadísticas de tablas o vistas de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-148">Specify the percentage of the table or indexed view, or the number of rows to sample when collecting statistics for larger tables or views.</span></span>  
  
 <span data-ttu-id="bd9ff-149">**Ver T-SQL**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-149">**View T-SQL**</span></span>  
 <span data-ttu-id="bd9ff-150">Muestra las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] realizadas en el servidor para esta tarea, en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-150">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd9ff-151">Si el número de objetos afectados es elevado, es posible que deba esperar un rato hasta que se muestren.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-151">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="bd9ff-152">Cuadro de diálogo Nueva conexión</span><span class="sxs-lookup"><span data-stu-id="bd9ff-152">New Connection Dialog Box</span></span>  
 <span data-ttu-id="bd9ff-153">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-153">**Connection name**</span></span>  
 <span data-ttu-id="bd9ff-154">Escriba un nombre para la nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-154">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="bd9ff-155">**Seleccionar o especificar un nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-155">**Select or enter a server name**</span></span>  
 <span data-ttu-id="bd9ff-156">Seleccione un servidor al que conectarse cuando se realice esta tarea.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-156">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="bd9ff-157">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-157">**Refresh**</span></span>  
 <span data-ttu-id="bd9ff-158">Actualiza la lista de servidores disponibles.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-158">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="bd9ff-159">**Especificar información para iniciar sesión en el servidor**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-159">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="bd9ff-160">Especifica el modo de autenticación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-160">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="bd9ff-161">**Usar seguridad integrada de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-161">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="bd9ff-162">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] con autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-162">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="bd9ff-163">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-163">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="bd9ff-164">Conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] mediante autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9ff-164">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="bd9ff-165">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-165">This option is not available.</span></span>  
  
 <span data-ttu-id="bd9ff-166">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-166">**User name**</span></span>  
 <span data-ttu-id="bd9ff-167">Proporcione un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-167">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="bd9ff-168">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-168">This option is not available.</span></span>  
  
 <span data-ttu-id="bd9ff-169">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="bd9ff-169">**Password**</span></span>  
 <span data-ttu-id="bd9ff-170">Proporcione una contraseña para que se utilice en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-170">Provide a password to use when authenticating.</span></span> <span data-ttu-id="bd9ff-171">Esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="bd9ff-171">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9ff-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd9ff-172">See Also</span></span>  
 [<span data-ttu-id="bd9ff-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd9ff-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
