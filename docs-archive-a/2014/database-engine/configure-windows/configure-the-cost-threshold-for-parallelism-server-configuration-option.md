---
title: Establecer la opción de configuración del servidor Umbral de costo para paralelismo | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cost threshold for parallelism option
ms.assetid: dad21bee-fe28-41f6-9d2f-e6ababfaf9db
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 675055a753e84ace3a4fcb44b41b8c914326c5c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663709"
---
# <a name="configure-the-cost-threshold-for-parallelism-server-configuration-option"></a><span data-ttu-id="cfeec-102">Establecer la opción de configuración del servidor Umbral de costo para paralelismo</span><span class="sxs-lookup"><span data-stu-id="cfeec-102">Configure the cost threshold for parallelism Server Configuration Option</span></span>
  <span data-ttu-id="cfeec-103">En este tema se describe cómo establecer la opción de configuración del servidor **umbral de costo para paralelismo** en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfeec-103">This topic describes how to configure the **cost threshold for parallelism** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cfeec-104">La opción **Umbral de costo para paralelismo** permite especificar el umbral en el que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea y ejecuta planes paralelos para consultas.</span><span class="sxs-lookup"><span data-stu-id="cfeec-104">The **cost threshold for parallelism** option specifies the threshold at which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates and runs parallel plans for queries.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cfeec-105">crea y ejecuta un plan paralelo para una consulta solo cuando el costo estimado para ejecutar un plan serie para la misma consulta es superior al valor establecido en **umbral de costo para paralelismo**.</span><span class="sxs-lookup"><span data-stu-id="cfeec-105">creates and runs a parallel plan for a query only when the estimated cost to run a serial plan for the same query is higher than the value set in **cost threshold for parallelism**.</span></span> <span data-ttu-id="cfeec-106">Este costo hace referencia al tiempo transcurrido estimado en segundos que es necesario para ejecutar el plan serie en una configuración de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="cfeec-106">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="cfeec-107">Puede establecer cualquier valor entre 0 y 32767 para la opción **umbral de costo para paralelismo** .</span><span class="sxs-lookup"><span data-stu-id="cfeec-107">The **cost threshold for parallelism** option can be set to any value from 0 through 32767.</span></span> <span data-ttu-id="cfeec-108">El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="cfeec-108">The default value is 5.</span></span>  
  
 <span data-ttu-id="cfeec-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="cfeec-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cfeec-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="cfeec-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cfeec-111">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="cfeec-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cfeec-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="cfeec-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="cfeec-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cfeec-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cfeec-114">**Para configurar la opción de umbral de costo para paralelismo, use:**</span><span class="sxs-lookup"><span data-stu-id="cfeec-114">**To configure the cost threshold for parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="cfeec-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfeec-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cfeec-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cfeec-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="cfeec-117">**Seguimiento:**  [Después de configurar la opción de umbral de costo para paralelismo](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="cfeec-117">**Follow Up:**  [After you configure the cost threshold for parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cfeec-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="cfeec-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cfeec-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="cfeec-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cfeec-120">Este costo hace referencia al tiempo transcurrido estimado en segundos que es necesario para ejecutar el plan serie en una configuración de hardware específica.</span><span class="sxs-lookup"><span data-stu-id="cfeec-120">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="cfeec-121">**cost threshold for parallelism** solo debe establecerse en multiprocesadores simétricos.</span><span class="sxs-lookup"><span data-stu-id="cfeec-121">Only set **cost threshold for parallelism** on symmetric multiprocessors.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cfeec-122">omite el valor de **umbral de costo para paralelismo** en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="cfeec-122">ignores the **cost threshold for parallelism** value under the following conditions:</span></span>  
  
    -   <span data-ttu-id="cfeec-123">El equipo tiene solo un procesador lógico.</span><span class="sxs-lookup"><span data-stu-id="cfeec-123">Your computer has only one logical processor.</span></span>  
  
    -   <span data-ttu-id="cfeec-124">Solo hay disponible un procesador lógico para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debido a la opción de configuración de la **máscara de afinidad** .</span><span class="sxs-lookup"><span data-stu-id="cfeec-124">Only a single logical processor is available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because of the **affinity mask** configuration option.</span></span>  
  
    -   <span data-ttu-id="cfeec-125">La opción **grado máximo de paralelismo** está establecida en 1.</span><span class="sxs-lookup"><span data-stu-id="cfeec-125">The **max degree of parallelism** option is set to 1.</span></span>  
  
 <span data-ttu-id="cfeec-126">Un procesador lógico es la unidad básica de hardware de procesador que permite al sistema operativo enviar una tarea o ejecutar un contexto de subproceso.</span><span class="sxs-lookup"><span data-stu-id="cfeec-126">A logical processor is the basic unit of processor hardware that allows the operating system to dispatch a task or execute a thread context.</span></span> <span data-ttu-id="cfeec-127">Cada procesador lógico puede ejecutar solo un contexto de subproceso a la vez.</span><span class="sxs-lookup"><span data-stu-id="cfeec-127">Each logical processor can execute only one thread context at a time.</span></span> <span data-ttu-id="cfeec-128">El núcleo del procesador es el conjunto de circuitos que proporciona capacidad para descodificar y ejecutar instrucciones.</span><span class="sxs-lookup"><span data-stu-id="cfeec-128">The processor core is the circuitry that provides ability to decode and execute instructions.</span></span> <span data-ttu-id="cfeec-129">El núcleo de un procesador puede contener uno o varios procesadores lógicos.</span><span class="sxs-lookup"><span data-stu-id="cfeec-129">A processor core may contain one or more logical processors.</span></span> <span data-ttu-id="cfeec-130">La siguiente consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] se puede utilizar para obtener información de CPU para el sistema.</span><span class="sxs-lookup"><span data-stu-id="cfeec-130">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] query can be used for obtaining CPU information for the system.</span></span>  
  
```  
SELECT (cpu_count / hyperthread_ratio) AS PhysicalCPUs,   
cpu_count AS logicalCPUs   
FROM sys.dm_os_sys_info  
```  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="cfeec-131">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="cfeec-131">Recommendations</span></span>  
  
-   <span data-ttu-id="cfeec-132">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="cfeec-132">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="cfeec-133">En determinados casos, puede elegirse un plan paralelo aunque el costo del plan de la consulta sea inferior al valor actual de **umbral de costo para paralelismo** .</span><span class="sxs-lookup"><span data-stu-id="cfeec-133">In certain cases, a parallel plan may be chosen even though the query's cost plan is less than the current **cost threshold for parallelism** value.</span></span> <span data-ttu-id="cfeec-134">Esto se debe a que la decisión de utilizar un plan serie o un plan paralelo se basa en un costo estimado proporcionado antes de finalizar la optimización completa.</span><span class="sxs-lookup"><span data-stu-id="cfeec-134">This can happen because the decision to use a parallel or serial plan is based on a cost estimate provided before the full optimization is complete.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cfeec-135">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cfeec-135">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cfeec-136">Permisos</span><span class="sxs-lookup"><span data-stu-id="cfeec-136">Permissions</span></span>  
 <span data-ttu-id="cfeec-137">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="cfeec-137">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="cfeec-138">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="cfeec-138">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="cfeec-139">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="cfeec-139">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cfeec-140">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfeec-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="cfeec-141">Para configurar la opción de umbral de costo para paralelismo</span><span class="sxs-lookup"><span data-stu-id="cfeec-141">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="cfeec-142">En el Explorador de objetos, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cfeec-142">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="cfeec-143">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="cfeec-143">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="cfeec-144">En **Paralelismo**, cambie la opción **CostThresholdForParallelism** al valor que desee.</span><span class="sxs-lookup"><span data-stu-id="cfeec-144">Under **Parallelism**, change the **CostThresholdForParallelism** option to the value you want.</span></span> <span data-ttu-id="cfeec-145">Escriba o seleccione un valor entre 0 y 32767.</span><span class="sxs-lookup"><span data-stu-id="cfeec-145">Type or select a value from 0 to 32767.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cfeec-146">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cfeec-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="cfeec-147">Para configurar la opción de umbral de costo para paralelismo</span><span class="sxs-lookup"><span data-stu-id="cfeec-147">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="cfeec-148">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfeec-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cfeec-149">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cfeec-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cfeec-150">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cfeec-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cfeec-151">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para establecer el valor de la opción de `cost threshold for parallelism` en `10`.</span><span class="sxs-lookup"><span data-stu-id="cfeec-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `cost threshold for parallelism` option to `10`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cost threshold for parallelism', 10 ;  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="cfeec-152">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cfeec-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cost-threshold-for-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="cfeec-153">Seguimiento: Después de configurar la opción de umbral de costo para paralelismo</span><span class="sxs-lookup"><span data-stu-id="cfeec-153">Follow Up: After you configure the cost threshold for parallelism option</span></span>  
 <span data-ttu-id="cfeec-154">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="cfeec-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfeec-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfeec-155">See Also</span></span>  
 <span data-ttu-id="cfeec-156">[Configurar operaciones de índice en paralelo](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="cfeec-156">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="cfeec-157">[Sugerencias de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="cfeec-157">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 <span data-ttu-id="cfeec-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfeec-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="cfeec-159">[affinity mask (opción de configuración del servidor)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="cfeec-159">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="cfeec-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfeec-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cfeec-161">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cfeec-161">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cfeec-162">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cfeec-162">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
