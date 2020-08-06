---
title: Establecer la opción de configuración del servidor Máximo de subprocesos de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- worker threads [SQL Server]
- max worker threads option
ms.assetid: abeadfa4-a14d-469a-bacf-75812e48fac1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4881cefee350d34d93b539c56be6f43866d3ddfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674338"
---
# <a name="configure-the-max-worker-threads-server-configuration-option"></a><span data-ttu-id="33a2a-102">Establecer la opción de configuración del servidor Máximo de subprocesos de trabajo</span><span class="sxs-lookup"><span data-stu-id="33a2a-102">Configure the max worker threads Server Configuration Option</span></span>
  <span data-ttu-id="33a2a-103">En este tema se describe cómo establecer la opción de configuración del servidor **máximo de subprocesos de trabajo** en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a2a-103">This topic describes how to configure the **max worker threads** server configuration option in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="33a2a-104">La opción de **máximo de subprocesos de trabajo** configura el número de subprocesos de trabajo disponibles para los procesos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33a2a-104">The **max worker threads** option configures the number of worker threads that are available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="33a2a-105">usa los servicios de subprocesos nativos de los sistemas operativos de forma que uno o varios subprocesos admitan cada red que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite de forma simultánea, otro subproceso controle los puntos de comprobación de la base de datos y un grupo de subprocesos controle a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="33a2a-105">uses the native thread services of the operating systems so that one or more threads support each network that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports simultaneously, another thread handles database checkpoints, and a pool of threads handles all users.</span></span> <span data-ttu-id="33a2a-106">El valor predeterminado de **máximo de subprocesos de trabajo** es 0.</span><span class="sxs-lookup"><span data-stu-id="33a2a-106">The default value for **max worker threads** is 0.</span></span> <span data-ttu-id="33a2a-107">Esto permite a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] configurar automáticamente el número de subprocesos de trabajo en el inicio.</span><span class="sxs-lookup"><span data-stu-id="33a2a-107">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically configure the number of worker threads at startup.</span></span> <span data-ttu-id="33a2a-108">El valor predeterminado es el más adecuado para la mayor parte de los sistemas.</span><span class="sxs-lookup"><span data-stu-id="33a2a-108">The default setting is best for most systems.</span></span> <span data-ttu-id="33a2a-109">No obstante, dependiendo de la configuración del sistema, el uso de un valor concreto para **máximo de subprocesos de trabajo** en ocasiones puede mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="33a2a-109">However, depending on your system configuration, setting **max worker threads** to a specific value sometimes improves performance.</span></span>  
  
 <span data-ttu-id="33a2a-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="33a2a-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="33a2a-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="33a2a-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="33a2a-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="33a2a-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="33a2a-113">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="33a2a-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="33a2a-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="33a2a-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="33a2a-115">**Para configurar la opción de máximo de subprocesos de trabajo, use:**</span><span class="sxs-lookup"><span data-stu-id="33a2a-115">**To configure the max worker threads option, using:**</span></span>  
  
     [<span data-ttu-id="33a2a-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33a2a-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="33a2a-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33a2a-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="33a2a-118">**Seguimiento:**  [Después de configurar la opción de máximo de subprocesos de trabajo](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="33a2a-118">**Follow Up:**  [After you configure the max worker threads option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="33a2a-119">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="33a2a-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="33a2a-120">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="33a2a-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="33a2a-121">Si el número real de solicitudes de consulta es inferior al número establecido en la opción de **máximo de subprocesos de trabajo**, un subproceso controla cada solicitud de consulta.</span><span class="sxs-lookup"><span data-stu-id="33a2a-121">When the actual number of query requests is less than the amount set in **max worker threads**, one thread handles each query request.</span></span> <span data-ttu-id="33a2a-122">Sin embargo, si el número real de solicitudes de consulta supera la cantidad establecida en **máximo de subprocesos de trabajo**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agrupa los subprocesos de trabajo para que el siguiente subproceso de trabajo disponible pueda controlar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="33a2a-122">However, if the actual number of query request exceeds the amount set in **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pools the worker threads so that the next available worker thread can handle the request.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="33a2a-123">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="33a2a-123">Recommendations</span></span>  
  
-   <span data-ttu-id="33a2a-124">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="33a2a-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="33a2a-125">La agrupación de subprocesos permite optimizar el rendimiento cuando un gran número de clientes se conecta al servidor.</span><span class="sxs-lookup"><span data-stu-id="33a2a-125">Thread pooling helps optimize performance when large numbers of clients are connected to the server.</span></span> <span data-ttu-id="33a2a-126">Normalmente, se crea un subproceso del sistema operativo independiente para cada solicitud de la consulta.</span><span class="sxs-lookup"><span data-stu-id="33a2a-126">Usually, a separate operating system thread is created for each query request.</span></span> <span data-ttu-id="33a2a-127">Sin embargo, cuando hay cientos de conexiones al servidor, el uso de un subproceso por solicitud de consulta puede consumir grandes cantidades de recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="33a2a-127">However, with hundreds of connections to the server, using one thread per query request can consume large amounts of system resources.</span></span> <span data-ttu-id="33a2a-128">La opción de **máximo de subprocesos de trabajo** permite que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cree un grupo de subprocesos de trabajo para atender un gran número de solicitudes de consulta, lo que mejora el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="33a2a-128">The **max worker threads** option enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to create a pool of worker threads to service a larger number of query requests, which improves performance.</span></span>  
  
-   <span data-ttu-id="33a2a-129">En la siguiente tabla se muestra el número configurado automáticamente de máximo de subprocesos de trabajo para diferentes combinaciones de CPU y versiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a2a-129">The following table shows the automatically configured number of max worker threads for various combinations of CPUs and versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    |<span data-ttu-id="33a2a-130">Número de CPU</span><span class="sxs-lookup"><span data-stu-id="33a2a-130">Number of CPUs</span></span>|<span data-ttu-id="33a2a-131">Equipo de 32 bits</span><span class="sxs-lookup"><span data-stu-id="33a2a-131">32-bit computer</span></span>|<span data-ttu-id="33a2a-132">Equipo de 64 bits</span><span class="sxs-lookup"><span data-stu-id="33a2a-132">64-bit computer</span></span>|  
    |--------------------|----------------------|----------------------|  
    |<span data-ttu-id="33a2a-133">\<= 4 procesadores</span><span class="sxs-lookup"><span data-stu-id="33a2a-133">\<= 4 processors</span></span>|<span data-ttu-id="33a2a-134">256</span><span class="sxs-lookup"><span data-stu-id="33a2a-134">256</span></span>|<span data-ttu-id="33a2a-135">512</span><span class="sxs-lookup"><span data-stu-id="33a2a-135">512</span></span>|  
    |<span data-ttu-id="33a2a-136">8 procesadores</span><span class="sxs-lookup"><span data-stu-id="33a2a-136">8 processors</span></span>|<span data-ttu-id="33a2a-137">288</span><span class="sxs-lookup"><span data-stu-id="33a2a-137">288</span></span>|<span data-ttu-id="33a2a-138">576</span><span class="sxs-lookup"><span data-stu-id="33a2a-138">576</span></span>|  
    |<span data-ttu-id="33a2a-139">16 procesadores</span><span class="sxs-lookup"><span data-stu-id="33a2a-139">16 processors</span></span>|<span data-ttu-id="33a2a-140">352</span><span class="sxs-lookup"><span data-stu-id="33a2a-140">352</span></span>|<span data-ttu-id="33a2a-141">704</span><span class="sxs-lookup"><span data-stu-id="33a2a-141">704</span></span>|  
    |<span data-ttu-id="33a2a-142">32 procesadores</span><span class="sxs-lookup"><span data-stu-id="33a2a-142">32 processors</span></span>|<span data-ttu-id="33a2a-143">480</span><span class="sxs-lookup"><span data-stu-id="33a2a-143">480</span></span>|<span data-ttu-id="33a2a-144">960</span><span class="sxs-lookup"><span data-stu-id="33a2a-144">960</span></span>|  
    |<span data-ttu-id="33a2a-145">64 procesadores</span><span class="sxs-lookup"><span data-stu-id="33a2a-145">64 processors</span></span>|<span data-ttu-id="33a2a-146">736</span><span class="sxs-lookup"><span data-stu-id="33a2a-146">736</span></span>|<span data-ttu-id="33a2a-147">1472</span><span class="sxs-lookup"><span data-stu-id="33a2a-147">1472</span></span>|  
    |<span data-ttu-id="33a2a-148">128 procesadores</span><span class="sxs-lookup"><span data-stu-id="33a2a-148">128 processors</span></span>|<span data-ttu-id="33a2a-149">4224</span><span class="sxs-lookup"><span data-stu-id="33a2a-149">4224</span></span>|<span data-ttu-id="33a2a-150">4480</span><span class="sxs-lookup"><span data-stu-id="33a2a-150">4480</span></span>|  
    |<span data-ttu-id="33a2a-151">256 procesadores</span><span class="sxs-lookup"><span data-stu-id="33a2a-151">256 processors</span></span>|<span data-ttu-id="33a2a-152">8320</span><span class="sxs-lookup"><span data-stu-id="33a2a-152">8320</span></span>|<span data-ttu-id="33a2a-153">8576</span><span class="sxs-lookup"><span data-stu-id="33a2a-153">8576</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="33a2a-154">Para obtener recomendaciones sobre el uso de más de 64 CPU, vea [Prácticas recomendadas para ejecutar SQL Server en equipos que tienen más de 64 CPU](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="33a2a-154">For recommendations on using more than 64 CPUs, refer to [Best Practices for Running SQL Server on Computers That Have More Than 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="33a2a-155">Se recomienda 1024 como número máximo de subprocesos de trabajo para una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecuta en un equipo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="33a2a-155">We recommend 1024 as the maximum number of worker threads for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on a 32-bit computer.</span></span>  
  
-   <span data-ttu-id="33a2a-156">Si todos los subprocesos de trabajo están activos con consultas de ejecución prolongada, puede parecer que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no responde hasta que finaliza un subproceso de trabajo y vuelve a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="33a2a-156">When all worker threads are active with long running queries, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might appear unresponsive until a worker thread completes and becomes available.</span></span> <span data-ttu-id="33a2a-157">Aunque no se trata de un defecto, puede que a veces este comportamiento no sea deseable.</span><span class="sxs-lookup"><span data-stu-id="33a2a-157">Although this is not a defect, it can sometimes be undesirable.</span></span> <span data-ttu-id="33a2a-158">Si un proceso parece no responder y no se pueden procesar nuevas consultas, conéctese a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la conexión de administrador dedicada (DAC) y finalice el proceso.</span><span class="sxs-lookup"><span data-stu-id="33a2a-158">If a process appears to be unresponsive and no new queries can be processed, then connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the dedicated administrator connection (DAC), and kill the process.</span></span> <span data-ttu-id="33a2a-159">Para impedir este comportamiento, aumente el número máximo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="33a2a-159">To prevent this, increase the number of max worker threads.</span></span>  
  
 <span data-ttu-id="33a2a-160">La opción de configuración del servidor **max worker threads** no tiene en cuenta los subprocesos necesarios para todas las tareas del sistema como grupos de disponibilidad, Service Broker, administrador de bloqueos y otros.</span><span class="sxs-lookup"><span data-stu-id="33a2a-160">The **max worker threads** server configuration option does not take into account threads that are required for all the system tasks such as Availibility Groups, Service Broker, Lock Manager, and others.</span></span>  <span data-ttu-id="33a2a-161">Si se supera el número de subprocesos configurados, la siguiente consulta proporcionará información sobre las tareas del sistema que han creado los subprocesos adicionales.</span><span class="sxs-lookup"><span data-stu-id="33a2a-161">If the number of threads configured are being exceeded, the following query will provide information about the system tasks that have spawned the additional threads.</span></span>  
  
```  
SELECT  
s.session_id,  
r.command,  
r.status,  
r.wait_type,  
r.scheduler_id,  
w.worker_address,  
w.is_preemptive,  
w.state,  
t.task_state,  
t.session_id,  
t.exec_context_id,  
t.request_id  
FROM sys.dm_exec_sessions AS s  
INNERJOIN sys.dm_exec_requests AS r  
    ON s.session_id = r.session_id  
INNER JOIN sys.dm_os_tasks AS t  
    ON r.task_address = t.task_address  
INNER JOIN sys.dm_os_workers AS w  
    ON t.worker_address = w.worker_address  
WHERE s.is_user_process = 0;  
  
```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="33a2a-162">Seguridad</span><span class="sxs-lookup"><span data-stu-id="33a2a-162">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="33a2a-163">Permisos</span><span class="sxs-lookup"><span data-stu-id="33a2a-163">Permissions</span></span>  
 <span data-ttu-id="33a2a-164">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="33a2a-164">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="33a2a-165">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="33a2a-165">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="33a2a-166">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="33a2a-166">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="33a2a-167">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="33a2a-167">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="33a2a-168">Para configurar la opción de máximo de subprocesos de trabajo</span><span class="sxs-lookup"><span data-stu-id="33a2a-168">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="33a2a-169">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="33a2a-169">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="33a2a-170">Haga clic en el nodo **Procesadores** .</span><span class="sxs-lookup"><span data-stu-id="33a2a-170">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="33a2a-171">En el cuadro **máximo de subprocesos de trabajo** , escriba o seleccione un valor entre 128 y 32767.</span><span class="sxs-lookup"><span data-stu-id="33a2a-171">In the **Max worker threads** box, type or select a value from 128 through 32767.</span></span>  
  
     <span data-ttu-id="33a2a-172">Utilice la opción **max worker threads** para configurar el número de subprocesos de trabajo disponibles para procesos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33a2a-172">Use the **max worker threads** option to configure the number of worker threads available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> <span data-ttu-id="33a2a-173">El valor predeterminado de la opción **max worker threads** es el óptimo para la mayor parte de los sistemas.</span><span class="sxs-lookup"><span data-stu-id="33a2a-173">The default setting for **max worker threads** is best for most systems.</span></span> <span data-ttu-id="33a2a-174">No obstante, dependiendo de la configuración del sistema, el uso de un valor inferior para el **máximo de subprocesos de trabajo** puede mejorar el rendimiento a veces.</span><span class="sxs-lookup"><span data-stu-id="33a2a-174">However, depending on your system configuration, setting **max worker threads** to a smaller value sometimes improves performance.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="33a2a-175">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33a2a-175">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="33a2a-176">Para configurar la opción de máximo de subprocesos de trabajo</span><span class="sxs-lookup"><span data-stu-id="33a2a-176">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="33a2a-177">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a2a-177">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="33a2a-178">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="33a2a-178">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="33a2a-179">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="33a2a-179">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="33a2a-180">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar la opción `max worker threads` en `900`.</span><span class="sxs-lookup"><span data-stu-id="33a2a-180">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max worker threads` option to `900`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'max worker threads', 900 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="33a2a-181">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33a2a-181">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-worker-threads-option"></a><a name="FollowUp"></a> <span data-ttu-id="33a2a-182">Seguimiento: Después de configurar la opción de máximo de subprocesos de trabajo</span><span class="sxs-lookup"><span data-stu-id="33a2a-182">Follow Up: After you configure the max worker threads option</span></span>  
 <span data-ttu-id="33a2a-183">El cambio tendrá efecto inmediatamente sin necesidad de reiniciar el [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33a2a-183">The change will take effect immediately without requiring the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a2a-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33a2a-184">See Also</span></span>  
 <span data-ttu-id="33a2a-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="33a2a-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="33a2a-186">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="33a2a-186">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="33a2a-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="33a2a-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="33a2a-188">Conexión de diagnóstico para administradores de bases de datos</span><span class="sxs-lookup"><span data-stu-id="33a2a-188">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
