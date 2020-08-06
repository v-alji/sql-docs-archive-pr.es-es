---
title: Establecer la opción de configuración del servidor Grado máximo de paralelismo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parallel queries [SQL Server]
- processors [SQL Server], parallel queries
- number of processors for parallel queries
- max degree of parallelism option
ms.assetid: 86b65bf1-a6a1-4670-afc0-cdfad1558032
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 824dc837142acc4a0898cb04b4a8687bc5be4043
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674340"
---
# <a name="configure-the-max-degree-of-parallelism-server-configuration-option"></a><span data-ttu-id="c9b1f-102">Establecer la opción de configuración del servidor Grado máximo de paralelismo</span><span class="sxs-lookup"><span data-stu-id="c9b1f-102">Configure the max degree of parallelism Server Configuration Option</span></span>
  <span data-ttu-id="c9b1f-103">En este tema se describe cómo configurar la `max degree of parallelism` opción de configuración del servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9b1f-103">This topic describes how to configure the `max degree of parallelism` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c9b1f-104">Cuando una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecuta en un equipo con más de un microprocesador o CPU, detecta el mejor grado de paralelismo, es decir, el número de procesadores que se emplea para ejecutar una única instrucción en cada ejecución de planes en paralelo.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-104">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on a computer that has more than one microprocessor or CPU, it detects the best degree of parallelism, that is, the number of processors employed to run a single statement, for each parallel plan execution.</span></span> <span data-ttu-id="c9b1f-105">Puede utilizar la opción `max degree of parallelism` para limitar el número de procesadores utilizados en la ejecución de planes paralelos.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-105">You can use the `max degree of parallelism` option to limit the number of processors to use in parallel plan execution.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c9b1f-106">considera los planes de ejecución en paralelo para las consultas, las operaciones de lenguaje de definición de datos (DDL) de índice y el rellenado de cursor estático y controlado por conjunto de claves.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-106">considers parallel execution plans for queries, index data definition language (DDL) operations, and static and keyset-driven cursor population.</span></span>  
  
 <span data-ttu-id="c9b1f-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c9b1f-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c9b1f-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="c9b1f-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c9b1f-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c9b1f-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c9b1f-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="c9b1f-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c9b1f-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c9b1f-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c9b1f-112">**Para configurar la opción de grado máximo de paralelismo, use:**</span><span class="sxs-lookup"><span data-stu-id="c9b1f-112">**To configure the max degree of parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="c9b1f-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9b1f-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c9b1f-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9b1f-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c9b1f-115">**Seguimiento:**  [Después de configurar la opción de grado máximo de paralelismo](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c9b1f-115">**Follow Up:**  [After you configure the max degree of parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9b1f-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c9b1f-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c9b1f-117">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c9b1f-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c9b1f-118">Si el valor de la opción affinity mask no es el predeterminado, es posible que se limite el número de procesadores disponibles para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en sistemas de multiproceso simétrico (SMP).</span><span class="sxs-lookup"><span data-stu-id="c9b1f-118">If the affinity mask option is not set to the default, it may restrict the number of processors available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on symmetric multiprocessing (SMP) systems.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c9b1f-119">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="c9b1f-119">Recommendations</span></span>  
  
-   <span data-ttu-id="c9b1f-120">Esta opción es avanzada y solo debe cambiarla un administrador de base de datos con experiencia o un técnico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la titulación apropiada.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-120">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="c9b1f-121">Para que el servidor pueda determinar el Grado máximo de paralelismo, establezca esta opción en 0, que es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-121">To enable the server to determine the maximum degree of parallelism, set this option to 0, the default value.</span></span> <span data-ttu-id="c9b1f-122">Si se establece el grado máximo de paralelismo en 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede usar todos los procesadores disponibles hasta un número de 64.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-122">Setting maximum degree of parallelism to 0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use all the available processors up to 64 processors.</span></span> <span data-ttu-id="c9b1f-123">Para suprimir la generación del plan paralelo, establezca `max degree of parallelism` en 1.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-123">To suppress parallel plan generation, set `max degree of parallelism` to 1.</span></span> <span data-ttu-id="c9b1f-124">Establezca el valor en un número de 1 a 32.767 para especificar el número máximo de núcleos de procesador que puede usar una única ejecución de consulta.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-124">Set the value to a number from 1 to 32,767 to specify the maximum number of processor cores that can be used by a single query execution.</span></span> <span data-ttu-id="c9b1f-125">Si se especifica un valor superior al número de procesadores disponibles, se utilizará el número real de procesadores disponibles.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-125">If a value greater than the number of available processors is specified, the actual number of available processors is used.</span></span> <span data-ttu-id="c9b1f-126">Si el equipo tiene solo un procesador, se omite el valor de `max degree of parallelism`.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-126">If the computer has only one processor, the `max degree of parallelism` value is ignored.</span></span>  
  
-   <span data-ttu-id="c9b1f-127">Puede omitir el valor de la opción max degree of parallelism especificando la sugerencia de consulta MAXDOP en la instrucción de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-127">You can override the max degree of parallelism value in queries by specifying the MAXDOP query hint in the query statement.</span></span> <span data-ttu-id="c9b1f-128">Para obtener más información, vea [Sugerencias de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="c9b1f-128">For more information, see [Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
-   <span data-ttu-id="c9b1f-129">Las operaciones de índice que crean o vuelven a generar un índice, o que eliminan un índice clúster, pueden consumir recursos de forma intensiva.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-129">Index operations that create or rebuild an index, or that drop a clustered index, can be resource intensive.</span></span> <span data-ttu-id="c9b1f-130">Puede omitir el valor de la opción max degree of parallelism para operaciones de índice especificando la opción de índice MAXDOP en la instrucción del índice.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-130">You can override the max degree of parallelism value for index operations by specifying the MAXDOP index option in the index statement.</span></span> <span data-ttu-id="c9b1f-131">El valor de MAXDOP se aplica a la instrucción en tiempo de ejecución y no se almacena en los metadatos del índice.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-131">The MAXDOP value is applied to the statement at execution time and is not stored in the index metadata.</span></span> <span data-ttu-id="c9b1f-132">Para obtener más información, vea [Configurar operaciones de índice en paralelo](../../relational-databases/indexes/configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c9b1f-132">For more information, see [Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md).</span></span>  
  
-   <span data-ttu-id="c9b1f-133">Además de las operaciones de consultas e índices, esta opción también controla el paralelismo de DBCC CHECKTABLE, DBCC CHECKDB y DBCC CHECKFILEGROUP.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-133">In addition to queries and index operations, this option also controls the parallelism of DBCC CHECKTABLE, DBCC CHECKDB, and DBCC CHECKFILEGROUP.</span></span> <span data-ttu-id="c9b1f-134">Puede deshabilitar los planes de ejecución en paralelo de estas instrucciones mediante el uso de la marca de seguimiento 2528.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-134">You can disable parallel execution plans for these statements by using trace flag 2528.</span></span> <span data-ttu-id="c9b1f-135">Para obtener más información, vea [Marcas de seguimiento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9b1f-135">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c9b1f-136">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c9b1f-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c9b1f-137">Permisos</span><span class="sxs-lookup"><span data-stu-id="c9b1f-137">Permissions</span></span>  
 <span data-ttu-id="c9b1f-138">De forma predeterminada, todos los usuarios tienen permisos de ejecución en **sp_configure** sin ningún parámetro o solo con el primero.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-138">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c9b1f-139">Para ejecutar **sp_configure** con ambos parámetros y cambiar una opción de configuración, o para ejecutar la instrucción RECONFIGURE, un usuario debe tener el permiso ALTER SETTINGS en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-139">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c9b1f-140">Los roles fijos de servidor **sysadmin** y **serveradmin** tienen el permiso ALTER SETTINGS de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-140">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c9b1f-141">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9b1f-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="c9b1f-142">Para configurar la opción de grado máximo de paralelismo</span><span class="sxs-lookup"><span data-stu-id="c9b1f-142">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="c9b1f-143">En el **Explorador de objetos**, haga clic con el botón derecho en un servidor y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-143">In **Object Explorer**, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c9b1f-144">Haga clic en el nodo **Avanzado** .</span><span class="sxs-lookup"><span data-stu-id="c9b1f-144">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="c9b1f-145">En el cuadro **Grado máximo de paralelismo** , seleccione el número máximo de procesadores que se usarán en la ejecución de planes paralelos.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-145">In the **Max Degree of Parallelism** box, select the maximum number of processors to use in parallel plan execution.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c9b1f-146">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9b1f-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="c9b1f-147">Para configurar la opción de grado máximo de paralelismo</span><span class="sxs-lookup"><span data-stu-id="c9b1f-147">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="c9b1f-148">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9b1f-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c9b1f-149">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c9b1f-150">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c9b1f-151">En este ejemplo se muestra cómo usar [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) para configurar la opción `max degree of parallelism` en `8`.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max degree of parallelism` option to `8`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO   
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
EXEC sp_configure 'max degree of parallelism', 8;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
```  
  
 <span data-ttu-id="c9b1f-152">Para obtener más información, vea [Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c9b1f-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-degree-of-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="c9b1f-153">Seguimiento: Después de configurar la opción de grado máximo de paralelismo</span><span class="sxs-lookup"><span data-stu-id="c9b1f-153">Follow Up: After you configure the max degree of parallelism option</span></span>  
 <span data-ttu-id="c9b1f-154">La configuración surte efecto inmediatamente, sin necesidad de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="c9b1f-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b1f-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9b1f-155">See Also</span></span>  
 <span data-ttu-id="c9b1f-156">[affinity mask (opción de configuración del servidor)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-156">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="c9b1f-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-158">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="c9b1f-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="c9b1f-166">[Configurar operaciones de índice en paralelo](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-166">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="c9b1f-167">[Sugerencias de consulta &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="c9b1f-167">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="c9b1f-168">Establecer opciones de índice</span><span class="sxs-lookup"><span data-stu-id="c9b1f-168">Set Index Options</span></span>](../../relational-databases/indexes/set-index-options.md)  
  
  
