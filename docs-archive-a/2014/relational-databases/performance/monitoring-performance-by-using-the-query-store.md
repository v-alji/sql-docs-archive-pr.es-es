---
title: Supervisión del rendimiento mediante el Almacén de consultas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: e06344a4-22a5-4c67-b6c6-a7060deb5de6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e5d74b9c4def9c0314569a8d0bd87939cdcb11b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677034"
---
# <a name="monitoring-performance-by-using-the-query-store"></a><span data-ttu-id="d8b6f-102">Supervisar el rendimiento mediante el almacén de consultas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-102">Monitoring Performance By Using the Query Store</span></span>
  <span data-ttu-id="d8b6f-103">La característica del almacén de consultas ofrece a los DBA conocimientos sobre el rendimiento y la elección del plan de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-103">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="d8b6f-104">Esta característica simplifica la solución de problemas de rendimiento al permitirle encontrar rápidamente diferencias de rendimiento provocadas por cambios en los planes de consulta.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-104">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="d8b6f-105">Captura automáticamente un historial de consultas, planes y estadísticas en tiempo de ejecución, y los conserva para su revisión.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-105">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="d8b6f-106">Separa los datos por ventanas de tiempo, lo que permite ver patrones de uso la base de datos y comprender cuándo se produjeron cambios del plan de consultas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-106">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="d8b6f-107">El almacén de consultas se puede configurar mediante la opción [ALTER DATABASE Set](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="d8b6f-107">The query store can be configured by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span>

||
|-|
|<span data-ttu-id="d8b6f-108">**Se aplica a**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([obtenerlo](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="d8b6f-108">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)] ([Get it](http://azure.micosoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="d8b6f-109">Actualmente, se trata de una característica de vista previa.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-109">This is currently a preview feature.</span></span> <span data-ttu-id="d8b6f-110">Para usar el Almacén de consultas debe confirmar y aceptar que la implementación de Almacén de consultas está sujeta a los términos de vista previa del contrato de licencia (por ejemplo, el Contrato Enterprise, Contrato de Microsoft Azure o Contrato Microsoft Online Subscription), así como cualquier [término de uso complementario aplicable para Microsoft Azure vista previa](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span><span class="sxs-lookup"><span data-stu-id="d8b6f-110">To use the Query Store you must acknowledge and agree that implementation of Query Store is subject to the preview terms in your license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

##  <a name="enabling-the-query-store"></a><a name="Enabling"></a> <span data-ttu-id="d8b6f-111">Habilitar el Almacén de consultas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-111">Enabling the Query Store</span></span>
 <span data-ttu-id="d8b6f-112">El Almacén de consultas no está activo para nuevas bases de datos de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-112">Query Store is not active for new databases by default.</span></span>

#### <a name="by-using-the-query-store-page-in-management-studio"></a><span data-ttu-id="d8b6f-113">Mediante el uso de la página del Almacén de consultas en Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8b6f-113">By Using the Query Store Page in Management Studio</span></span>

1.  <span data-ttu-id="d8b6f-114">En el Explorador de objetos, haga clic con el botón derecho en una base de datos y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-114">In Object Explorer, right-click a database, and then click **Properties**.</span></span> <span data-ttu-id="d8b6f-115">(Requiere la versión [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 de [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="d8b6f-115">(Requires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2016 version of [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].)</span></span>

2.  <span data-ttu-id="d8b6f-116">En el cuadro de diálogo **Propiedades de la base de datos** , seleccione la página **Almacén de consultas** .</span><span class="sxs-lookup"><span data-stu-id="d8b6f-116">In the **Database Properties** dialog box, select the **Query Store** page.</span></span>

3.  <span data-ttu-id="d8b6f-117">En el cuadro **Habilitar** , seleccione **true**.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-117">In the **Enable** box, select **True**.</span></span>

#### <a name="by-using-transact-sql-statements"></a><span data-ttu-id="d8b6f-118">Mediante instrucciones Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8b6f-118">By Using Transact-SQL Statements</span></span>

1.  <span data-ttu-id="d8b6f-119">Use la instrucción `ALTER DATABASE` para habilitar el almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-119">Use the `ALTER DATABASE` statement to enable the query store.</span></span> <span data-ttu-id="d8b6f-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d8b6f-120">For example:</span></span>

    ```
    ALTER DATABASE AdventureWorks2012 SET QUERY_STORE = ON;
    ```

     <span data-ttu-id="d8b6f-121">Para obtener más opciones de sintaxis relacionadas con el almacén de consultas, vea [Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="d8b6f-121">For more syntax options related to the query store, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>

> [!NOTE]
>  <span data-ttu-id="d8b6f-122">No se puede habilitar el almacén de consultas para la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-122">You cannot enable the query store for the master database.</span></span>



##  <a name="information-in-the-query-store"></a><a name="About"></a> <span data-ttu-id="d8b6f-123">Información del Almacén de consultas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-123">Information in the Query Store</span></span>
 <span data-ttu-id="d8b6f-124">Los planes de ejecución para cualquier consulta específica en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] suelen evolucionar con el tiempo debido a una serie de motivos diferentes, como cambios en las estadísticas, cambios de esquema, creación o eliminación de los índices, etc. La caché de procedimientos (donde se almacenan los planes de consulta almacenados en caché) solo almacena el plan de ejecución más reciente.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-124">Execution plans for any specific query in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] typically evolve over time due to a number of different reasons such as statistics changes, schema changes, creation/deletion of indexes, etc. The procedure cache (where cached query plans are stored) only stores the latest execution plan.</span></span> <span data-ttu-id="d8b6f-125">Los planes también se eliminan de la caché de planes debido a la presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-125">Plans also get evicted from the plan cache due to memory pressure.</span></span> <span data-ttu-id="d8b6f-126">Como resultado, es posible que las regresiones de rendimiento de consultas provocadas por los cambios de planes de ejecución no sean triviales y que su resolución lleve mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-126">As a result, query performance regressions caused by execution plan changes can be non-trivial and time consuming to resolve.</span></span>

 <span data-ttu-id="d8b6f-127">Como el almacén de consultas conserva varios planes de ejecución por consulta, puede aplicar directivas para dirigir el procesador de consultas para que use un plan de ejecución concreto para una consulta.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-127">Since the query store retains multiple execution plans per query, it can enforce policies to direct the query processor to use a specific execution plan for a query.</span></span> <span data-ttu-id="d8b6f-128">Esto se conoce como forzado de plan.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-128">This is referred to as plan forcing.</span></span> <span data-ttu-id="d8b6f-129">El forzado de plan en la consulta de almacenes se ofrece mediante un mecanismo similar al de la sugerencia de consulta [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) , pero no requiere ningún cambio en las aplicaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-129">Plan forcing in Query Store is provided by using a mechanism similar to the [USE PLAN](/sql/t-sql/queries/hints-transact-sql-query) query hint, but it does not require any change in user applications.</span></span> <span data-ttu-id="d8b6f-130">El plan de forzado puede resolver una regresión del rendimiento de consultas provocado por un cambio de plan en un período de tiempo muy breve.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-130">Plan forcing can resolve a query performance regression caused by a plan change in a very short period of time.</span></span>

 <span data-ttu-id="d8b6f-131">Entre los escenarios comunes para usar la característica Almacén de consultas se encuentran:</span><span class="sxs-lookup"><span data-stu-id="d8b6f-131">Common scenarios for using the Query Store feature are:</span></span>

-   <span data-ttu-id="d8b6f-132">Buscar y corregir rápidamente una regresión de rendimiento de plan forzando el plan de consulta anterior.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-132">Quickly find and fix a plan performance regression by forcing the previous query plan.</span></span> <span data-ttu-id="d8b6f-133">Corregir las consultas de las que se ha realizado regresión recientemente en el rendimiento debido a cambios del plan de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-133">Fix queries that have recently regressed in performance due to execution plan changes.</span></span>

-   <span data-ttu-id="d8b6f-134">Determinar el número de veces en que se ha ejecutado una consulta en una ventana de tiempo determinado, ayudando a un DBA en la solución de problemas de rendimiento de recursos.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-134">Determine the number of times a query was executed in a given time window, assisting a DBA in troubleshooting performance resource problems.</span></span>

-   <span data-ttu-id="d8b6f-135">Identificar las principales *n* consultas (por tiempo de ejecución, consumo de memoria, etc.) en las últimas *x* horas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-135">Identify top *n* queries (by execution time, memory consumption, etc.) in the past *x* hours.</span></span>

-   <span data-ttu-id="d8b6f-136">Auditar el historial de planes de consulta para una consulta determinada.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-136">Audit the history of query plans for a given query.</span></span>

-   <span data-ttu-id="d8b6f-137">Analizar los patrones de uso (CPU, E/S y memoria) de recursos para una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-137">Analyze the resource (CPU, I/O, and Memory) usage patterns for a particular database.</span></span>

 <span data-ttu-id="d8b6f-138">El almacén de consultas contiene dos almacenes: un **almacén de planes** para conservar la información del plan de ejecución y un **almacén de estadísticas de tiempo de ejecución** para conservar la información de estadísticas de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-138">The query store contains two stores; a **plan store** for persisting the execution plan information, and a **runtime stats store** for persisting the execution statistics information.</span></span> <span data-ttu-id="d8b6f-139">El número de planes únicos que se pueden almacenar para una consulta en el almacén de planes se limita por la opción de configuración `max_plans_per_query`.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-139">The number of unique plans that can be stored for a query in the plan store is limited by the `max_plans_per_query` configuration option.</span></span> <span data-ttu-id="d8b6f-140">Para mejorar el rendimiento, la información se escribe en los dos almacenes de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-140">To enhance performance, the information is written to the two stores asynchronously.</span></span> <span data-ttu-id="d8b6f-141">Para minimizar el uso del espacio, se agregan las estadísticas de ejecución en tiempo de ejecución en el almacén de estadísticas de tiempo de ejecución en una ventana de tiempo fijo.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-141">To minimize space usage, the runtime execution statistics in the runtime stats store are aggregated over a fixed time window.</span></span> <span data-ttu-id="d8b6f-142">La información de estos almacenes se puede ver al consultar las vistas del catálogo del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-142">The information in these stores is visible by querying the query store catalog views.</span></span>

 <span data-ttu-id="d8b6f-143">La siguiente consulta devuelve información sobre las consultas y los planes del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-143">The following query returns information about queries and plans in the query store.</span></span>

```
SELECT Txt.query_text_id, Txt.query_sql_text, Pl.plan_id, Qry.*
FROM sys.query_store_plan AS Pl
JOIN sys.query_store_query AS Qry
    ON Pl.query_id = Qry.query_id
JOIN sys.query_store_query_text AS Txt
    ON Qry.query_text_id = Txt.query_text_id ;
```



## <a name="using-the-regressed-queries-feature"></a><span data-ttu-id="d8b6f-144">Mediante la característica de consultas devueltas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-144">Using the Regressed Queries Feature</span></span>
 <span data-ttu-id="d8b6f-145">Después de habilitar el almacén de consultas, actualice la parte de la base de datos del panel Explorador de objetos para agregar la sección **almacén de consultas** .</span><span class="sxs-lookup"><span data-stu-id="d8b6f-145">After enabling the query store, refresh the database portion of the Object Explorer pane to add the **Query Store** section.</span></span>

 <span data-ttu-id="d8b6f-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span><span class="sxs-lookup"><span data-stu-id="d8b6f-146">![QueryStore](../../database-engine/media/querystore.PNG "QueryStore")</span></span>

 <span data-ttu-id="d8b6f-147">Al seleccionar **consultas con regresión**, se abre el panel de **consultas** devueltas en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8b6f-147">Selecting **Regressed Queries**, opens the **Regressed Queries** pane in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="d8b6f-148">En el panel Consultas devueltas se muestran las consultas y los planes del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-148">The Regressed Queries pane shows you the queries, and plans in the query store.</span></span> <span data-ttu-id="d8b6f-149">Los cuadros desplegables de la parte superior le permiten seleccionar consultas en función de varios criterios.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-149">Drop down boxes at the top allow you to select queries based on various criteria.</span></span> <span data-ttu-id="d8b6f-150">Seleccione un plan para ver el plan de consulta gráfica.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-150">Select a plan to see the graphical query plan.</span></span> <span data-ttu-id="d8b6f-151">Los botones están disponibles para ver la consulta de origen, aplicar y eliminar la aplicación de un plan de consulta, y actualizar la pantalla.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-151">Buttons are available to view the source query, force, and unforce a query plan, and refresh the display.</span></span>

 <span data-ttu-id="d8b6f-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span><span class="sxs-lookup"><span data-stu-id="d8b6f-152">![RegressedQueries](../../database-engine/media/regressedqueries.PNG "RegressedQueries")</span></span>

 <span data-ttu-id="d8b6f-153">Para forzar un plan, seleccione una consulta y un plan y, a continuación, haga clic en **forzar plan.**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-153">To force a plan, select a query and plan, and then click **Force Plan.**</span></span> <span data-ttu-id="d8b6f-154">Solo puede forzar planes que se guardaron mediante la característica del plan de consulta y que todavía se conservan en la caché del plan de consulta.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-154">You can only force plans that were saved by the query plan feature and are still retained in the query plan cache.</span></span>



##  <a name="configuration-options"></a><a name="Options"></a> <span data-ttu-id="d8b6f-155">Opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="d8b6f-155">Configuration Options</span></span>
 <span data-ttu-id="d8b6f-156">OPERATION_MODE puede ser READ_WRITE o READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-156">OPERATION_MODE Can be READ_WRITE or READ_ONLY.</span></span>

 <span data-ttu-id="d8b6f-157">CLEANUP_POLICY configurar el argumento STALE_QUERY_THRESHOLD_DAYS para especificar el número de días que se conservarán los datos en el almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-157">CLEANUP_POLICY Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>

 <span data-ttu-id="d8b6f-158">DATA_FLUSH_INTERVAL_SECONDS Determina la frecuencia con la que los datos escritos en el almacén de consultas se conservan en el disco.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-158">DATA_FLUSH_INTERVAL_SECONDS Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="d8b6f-159">Para optimizar el rendimiento, los datos recopilados por el almacén de consultas se escriben de manera asincrónica en el disco.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-159">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="d8b6f-160">La frecuencia con la que se produce esta transferencia asincrónica se configura mediante DATA_FLUSH_INTERVAL_SECONDS.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-160">The frequency at which this asynchronous transfer occurs is configured via DATA_FLUSH_INTERVAL_SECONDS.</span></span>

 <span data-ttu-id="d8b6f-161">MAX_SIZE_MB configura el tamaño máximo del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-161">MAX_SIZE_MB Configures the maximum size of the query store.</span></span> <span data-ttu-id="d8b6f-162">Si los datos del almacén de consultas alcanzan el límite de MAX_SIZE_MB, el almacén de consultas cambia automáticamente el estado de lectura-escritura a solo lectura y deja de recopilar datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-162">If the data in the query store hits the MAX_SIZE_MB limit, the query store automatically changes the state from read-write to read-only and stops collecting new data.</span></span>

 <span data-ttu-id="d8b6f-163">INTERVAL_LENGTH_MINUTES Determina el intervalo de tiempo en el que se agregan los datos de estadísticas de ejecución en tiempo de ejecución al almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-163">INTERVAL_LENGTH_MINUTES Determines the time interval at which runtime execution statistics data is aggregated into the query store.</span></span> <span data-ttu-id="d8b6f-164">Para optimizar el uso del espacio, se agregan las estadísticas de ejecución en tiempo de ejecución en el almacén de estadísticas de tiempo de ejecución en una ventana de tiempo fijo.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-164">To optimize for space usage, the runtime execution statistics in the Runtime Stats Store are aggregated over a fixed time window.</span></span> <span data-ttu-id="d8b6f-165">Esta ventana de tiempo fijo se configura mediante INTERVAL_LENGTH_MINUTES.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-165">This fixed time window is configured via INTERVAL_LENGTH_MINUTES.</span></span>

 <span data-ttu-id="d8b6f-166">Consulte la vista `sys.database_query_store_options` para determinar las opciones actuales del almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-166">Query the `sys.database_query_store_options` view to determine the current options of the query store.</span></span>

 <span data-ttu-id="d8b6f-167">Para obtener más información sobre el establecimiento de opciones mediante instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] , vea [Administración de opciones](#OptionMgmt).</span><span class="sxs-lookup"><span data-stu-id="d8b6f-167">For more information about setting options by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, see [Option Management](#OptionMgmt).</span></span>

 

##  <a name="related-views-functions-and-procedures"></a><a name="Related"></a> <span data-ttu-id="d8b6f-168">Vistas, funciones y procedimientos relacionados</span><span class="sxs-lookup"><span data-stu-id="d8b6f-168">Related Views, Functions, and Procedures</span></span>
 <span data-ttu-id="d8b6f-169">El Almacén de consultas se puede ver y administrar a través de [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] o usando las siguientes vistas y procedimientos.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-169">The Query Store can be viewed and managed through [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] or by using the following views and procedures.</span></span>

-   [<span data-ttu-id="d8b6f-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-170">sys.fn_stmt_sql_handle_from_sql_stmt &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-stmt-sql-handle-from-sql-stmt-transact-sql)

### <a name="query-store-catalog-views"></a><span data-ttu-id="d8b6f-171">Vistas de catálogo del almacén de consultas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-171">Query Store Catalog Views</span></span>
 <span data-ttu-id="d8b6f-172">Las siete vistas de catálogo presentan información sobre el Almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-172">Seven catalog views present information about the Query Store.</span></span>

-   [<span data-ttu-id="d8b6f-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-173">sys.database_query_store_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-query-store-options-transact-sql)

-   [<span data-ttu-id="d8b6f-174">sys.query_context_settings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-174">sys.query_context_settings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-context-settings-transact-sql)

-   [<span data-ttu-id="d8b6f-175">sys.query_store_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-175">sys.query_store_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-plan-transact-sql)

-   [<span data-ttu-id="d8b6f-176">sys.query_store_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-176">sys.query_store_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-transact-sql)

-   [<span data-ttu-id="d8b6f-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-177">sys.query_store_query_text &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-query-text-transact-sql)

-   [<span data-ttu-id="d8b6f-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-178">sys.query_store_runtime_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-transact-sql)

-   [<span data-ttu-id="d8b6f-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-179">sys.query_store_runtime_stats_interval &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-query-store-runtime-stats-interval-transact-sql)

### <a name="query-store-stored-procedures"></a><span data-ttu-id="d8b6f-180">Procedimientos almacenados del almacén de consultas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-180">Query Store Stored Procedures</span></span>
 <span data-ttu-id="d8b6f-181">Los seis procedimientos almacenados configuran el Almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-181">Six stored procedures configure the Query Store.</span></span>

-   [<span data-ttu-id="d8b6f-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-182">sp_query_store_flush_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-flush-db-transact-sql)

-   [<span data-ttu-id="d8b6f-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-183">sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql)

-   [<span data-ttu-id="d8b6f-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-184">sp_query_store_force_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql)

-   [<span data-ttu-id="d8b6f-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-185">sp_query_store_unforce_plan &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql)

-   [<span data-ttu-id="d8b6f-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-186">sp_query_store_remove_plan &#40;Transct-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql)

-   [<span data-ttu-id="d8b6f-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-187">sp_query_store_remove_query &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql)



##  <a name="key-usage-scenarios"></a><a name="Scenarios"></a> <span data-ttu-id="d8b6f-188">Escenarios de uso clave</span><span class="sxs-lookup"><span data-stu-id="d8b6f-188">Key Usage Scenarios</span></span>

###  <a name="option-management"></a><a name="OptionMgmt"></a> <span data-ttu-id="d8b6f-189">Administración de opciones</span><span class="sxs-lookup"><span data-stu-id="d8b6f-189">Option Management</span></span>
 <span data-ttu-id="d8b6f-190">En esta sección se ofrecen algunas directrices sobre la administración de la propia característica Almacén de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-190">This section provides some guidelines on managing Query Store feature itself.</span></span>

 <span data-ttu-id="d8b6f-191">**¿Está el Almacén de consultas activo actualmente?**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-191">**Is Query Store currently active?**</span></span>

 <span data-ttu-id="d8b6f-192">El Almacén de consultas almacena sus datos dentro de la base de datos del usuario y ese es el motivo por el que tiene limitado el tamaño (configurado con `MAX_STORAGE_SIZE_MB`).</span><span class="sxs-lookup"><span data-stu-id="d8b6f-192">Query Store stores its data inside the user database and that is why it has size limit (configured  with `MAX_STORAGE_SIZE_MB`).</span></span> <span data-ttu-id="d8b6f-193">Si los datos del Almacén de consultas alcanzan ese límite, el Almacén de consultas cambiará automáticamente el estado de lectura-escritura a solo lectura y dejará de recopilar datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-193">If data in Query Store hits that limit Query Store will automatically change state from read-write to read-only and stop collecting new data.</span></span>

 <span data-ttu-id="d8b6f-194">Ejecute el script siguiente para determinar si el almacén de consultas está activo actualmente y si recopila actualmente estadísticas en tiempo de ejecución o no.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-194">Execute the following script to determine if Query Store is currently active, and whether it is currently collects runtime stats or not.</span></span>

```
DECLARE @x nvarchar(100) = CAST(newid() AS nvarchar(100));
DECLARE @query nvarchar(max) = 
N'IF EXISTS
(
    SELECT * 
    FROM sys.query_store_query_text 
    WHERE query_sql_text LIKE ''%' + @x + N'%''
)
SELECT ''Query Store is active'' ;
ELSE SELECT ''Query Store is NOT active''' ;
EXEC sp_executesql @query;
```

 <span data-ttu-id="d8b6f-195">**Obtener opciones del Almacén de consultas**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-195">**Get Query Store options**</span></span>

 <span data-ttu-id="d8b6f-196">Para averiguar información detallada sobre el estado del Almacén de consultas, ejecute lo siguiente en una base de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-196">To find out detailed information about Query Store status, execute following in a user database.</span></span>

```
SELECT * FROM sys.database_query_store_options;
```

 <span data-ttu-id="d8b6f-197">**Establecimiento del intervalo del Almacén de consultas**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-197">**Setting Query Store interval**</span></span>

 <span data-ttu-id="d8b6f-198">Puede invalidar el intervalo para agregar estadísticas de tiempo de ejecución de consultas (el valor predeterminado es 60 minutos).</span><span class="sxs-lookup"><span data-stu-id="d8b6f-198">You can override interval for aggregating query runtime statistics (default is 60 minutes).</span></span>

```

      USE master;
GO

ALTER DATABASE <database_name> 
SET QUERY_STORE (INTERVAL_LENGTH_MINUTES = 15);
```

 <span data-ttu-id="d8b6f-199">Tenga en cuenta que no se permiten valores arbitrarios; debería usar uno de los siguientes valores: 1, 5, 10, 15, 30 y 60.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-199">Note that arbitrary values are not allowed - you should use one of the following: 1, 5, 10, 15, 30 and 60.</span></span>

 <span data-ttu-id="d8b6f-200">El nuevo valor de intervalo se expone a través de la vista `sys.database_query_store_options`.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-200">New value for interval is exposed through `sys.database_query_store_options` view.</span></span>

 <span data-ttu-id="d8b6f-201">Si el almacenamiento del Almacén de consultas está completamente lleno, use la siguiente instrucción para ampliar el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-201">If the Query Store storage is full use the following statement to extend the storage.</span></span>

```
ALTER DATABASE <database_name> 
SET QUERY_STORE (MAX_STORAGE_SIZE_MB = <new_size>);
```

 <span data-ttu-id="d8b6f-202">**Establecer todas las opciones del Almacén de consultas**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-202">**Set all Query Store options**</span></span>

 <span data-ttu-id="d8b6f-203">Puede establecer varias opciones del Almacén de consultas a la vez con una sola instrucción ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-203">You can set multiple Query Store options at once with a single ALTER DATABASE statement.</span></span>

```
ALTER DATABASE <database name> 
SET QUERY_STORE (
    OPERATION_MODE = READ_WRITE,
    CLEANUP_POLICY = 
    (STALE_QUERY_THRESHOLD_DAYS = 30),
    DATA_FLUSH_INTERVAL_SECONDS = 3000,
    MAX_STORAGE_SIZE_MB = 500,
    INTERVAL_LENGTH_MINUTES = 15
);
```

 <span data-ttu-id="d8b6f-204">**Limpieza del espacio**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-204">**Cleaning up the space**</span></span>

 <span data-ttu-id="d8b6f-205">Las tablas internas del Almacén de consultas se crean en el grupo de archivos PRIMARY durante la creación de la base de datos y esa configuración no se podrá cambiar más adelante.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-205">Query Store internal tables are created in the PRIMARY filegroup during database creation and that configuration cannot be changed later.</span></span> <span data-ttu-id="d8b6f-206">Si se está quedando sin espacio, puede que quiera borrar los datos más antiguos del Almacén de consultas con la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-206">If you are running out of space you might want to clear older Query Store data by using the following statement.</span></span>

```
ALTER DATABASE <db_name> SET QUERY_STORE CLEAR;
```

 <span data-ttu-id="d8b6f-207">Como alternativa, puede que quiera borrar solo datos de consultas ad hoc, porque resulta menos relevantes para optimizaciones de consultas y análisis de plan, pero ocupa el mismo espacio.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-207">Alternatively, you might want to clear up only ad-hoc query data, since it is less relevant for query optimizations and plan analysis but takes up just as much space.</span></span>

 <span data-ttu-id="d8b6f-208">**Eliminar consultas ad hoc** Se eliminan las consultas que solo se ejecutaron una vez y que tienen más de 24 horas de antigüedad.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-208">**Delete ad-hoc queries** This deletes the queries that were only executed only once and that are more than 24 hours old.</span></span>

```
DECLARE @id int
DECLARE adhoc_queries_cursor CURSOR 
FOR 
SELECT q.query_id
FROM sys.query_store_query_text AS qt
JOIN sys.query_store_query AS q 
    ON q.query_text_id = qt.query_text_id
JOIN sys.query_store_plan AS p 
    ON p.query_id = q.query_id
JOIN sys.query_store_runtime_stats AS rs 
    ON rs.plan_id = p.plan_id
GROUP BY q.query_id
HAVING SUM(rs.count_executions) < 2 
AND MAX(rs.last_execution_time) < DATEADD (hour, -24, GETUTCDATE())
ORDER BY q.query_id ;

OPEN adhoc_queries_cursor ;
FETCH NEXT FROM adhoc_queries_cursor INTO @id;
WHILE @@fetch_status = 0
    BEGIN 
        PRINT @id
        EXEC sp_query_store_remove_query @id
        FETCH NEXT FROM adhoc_queries_cursor INTO @id
    END 
CLOSE adhoc_queries_cursor ;
DEALLOCATE adhoc_queries_cursor;
```

 <span data-ttu-id="d8b6f-209">Puede definir su propio procedimiento con una lógica diferente para borrar los datos que ya no son importantes para usted.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-209">You can define your own procedure with different logic for clearing up the data that is no longer important for you.</span></span>

 <span data-ttu-id="d8b6f-210">En el ejemplo anterior se usa el procedimiento almacenado extendido `sp_query_store_remove_query` para quitar datos innecesarios.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-210">The example above uses the `sp_query_store_remove_query` extended stored procedure for removing unnecessary data.</span></span> <span data-ttu-id="d8b6f-211">También puede usar otros dos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-211">You can also use two other procedures.</span></span>

-   <span data-ttu-id="d8b6f-212">`sp_query_store_reset_exec_stats`-borrar las estadísticas de tiempo de ejecución de un plan determinado.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-212">`sp_query_store_reset_exec_stats` - clear runtime statistics for a given plan.</span></span>

-   <span data-ttu-id="d8b6f-213">`sp_query_store_remove_plan`: quita un plan único.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-213">`sp_query_store_remove_plan` - removes a single plan.</span></span>



###  <a name="performance-auditing-and-troubleshooting"></a><a name="Peformance"></a> <span data-ttu-id="d8b6f-214">Auditoría del rendimiento y solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-214">Performance Auditing and Troubleshooting</span></span>
 <span data-ttu-id="d8b6f-215">Como el almacén de consultas conserva el historial de métricas de tiempo de ejecución y compilación a lo largo de las ejecuciones de consulta, hay muchas preguntas diferentes que puede responder con facilidad con respecto a la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-215">Because Query Store keeps history of compilation and runtime metrics throughout query executions there are many different questions you can easily answer with regards to your workload.</span></span>

 <span data-ttu-id="d8b6f-216">**Últimas *n* consultas ejecutadas en la base de datos.**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-216">**Last *n* queries executed on the database.**</span></span>

```
SELECT TOP 10 qt.query_sql_text, q.query_id, 
    qt.query_text_id, p.plan_id, rs.last_execution_time
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
ORDER BY rs.last_execution_time DESC;
```

 <span data-ttu-id="d8b6f-217">**Número de ejecuciones para cada consulta.**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-217">**Number of executions for each query.**</span></span>

```
SELECT q.query_id, qt.query_text_id, qt.query_sql_text, 
    SUM(rs.count_executions) AS total_execution_count
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
GROUP BY q.query_id, qt.query_text_id, qt.query_sql_text
ORDER BY total_execution_count DESC;
```

 <span data-ttu-id="d8b6f-218">**El número de consultas con el mayor promedio de tiempo de ejecución en la última hora.**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-218">**The number of queries with the longest average execution time within last hour.**</span></span>

```
SELECT TOP 10 rs.avg_duration, qt.query_sql_text, q.query_id,
    qt.query_text_id, p.plan_id, GETUTCDATE() AS CurrentUTCTime, 
    rs.last_execution_time 
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id
WHERE rs.last_execution_time > DATEADD(hour, -1, GETUTCDATE())
ORDER BY rs.avg_duration DESC;
```

 <span data-ttu-id="d8b6f-219">**El número de consultas que tenían el mayor promedio de lecturas de e/s físicas en las últimas 24 horas, con el recuento medio de filas y el recuento de ejecuciones correspondientes.**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-219">**The number of queries that had the biggest average physical IO reads in last 24 hours, with corresponding average row count and execution count.**</span></span>

```
SELECT TOP 10 rs.avg_physical_io_reads, qt.query_sql_text, 
    q.query_id, qt.query_text_id, p.plan_id, rs.runtime_stats_id, 
    rsi.start_time, rsi.end_time, rs.avg_rowcount, rs.count_executions
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p 
    ON q.query_id = p.query_id 
JOIN sys.query_store_runtime_stats AS rs 
    ON p.plan_id = rs.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi 
    ON rsi.runtime_stats_interval_id = rs.runtime_stats_interval_id
WHERE rsi.start_time >= DATEADD(hour, -24, GETUTCDATE()) 
ORDER BY rs.avg_physical_io_reads DESC;
```

 <span data-ttu-id="d8b6f-220">**Consultas con varios planes.**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-220">**Queries with multiple plans.**</span></span> <span data-ttu-id="d8b6f-221">Estas consultas son especialmente interesantes porque son candidatas para las regresiones debido al cambio de elección del plan.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-221">These queries are especially interesting because they are candidates for regressions due to plan choice change.</span></span> <span data-ttu-id="d8b6f-222">La siguiente consulta identifica estas consultas junto con todos los planes:</span><span class="sxs-lookup"><span data-stu-id="d8b6f-222">The following query identifies these queries along with all plans:</span></span>

```
WITH Query_MultPlans
AS
(
    SELECT COUNT(*) AS cnt, q.query_id 
    FROM sys.query_store_query_text AS qt
    JOIN sys.query_store_query AS q
        ON qt.query_text_id = q.query_text_id
    JOIN sys.query_store_plan AS p
        ON p.query_id = q.query_id
    GROUP BY q.query_id
    HAVING COUNT(distinct plan_id) > 1
)

SELECT q.query_id, object_name(object_id) AS ContainingObject, query_sql_text,
plan_id, p.query_plan AS plan_xml,
p.last_compile_start_time, p.last_execution_time
FROM Query_MultPlans AS qm
JOIN sys.query_store_query AS q
    ON qm.query_id = q.query_id
JOIN sys.query_store_plan AS p
    ON q.query_id = p.query_id
JOIN sys.query_store_query_text qt 
    ON qt.query_text_id = q.query_text_id
ORDER BY query_id, plan_id;
```

 <span data-ttu-id="d8b6f-223">**Consultas que se devolvieron recientemente en rendimiento (comparando un momento dado diferente).**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-223">**Queries that recently regressed in performance (comparing different point in time).**</span></span> <span data-ttu-id="d8b6f-224">El siguiente ejemplo de consulta devuelve todas las consultas para las que se duplicó el tiempo de ejecución en las últimas 48 horas debido a un cambio de elección del plan.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-224">The following query example returns all queries for which execution time doubled in last 48 hours due to a plan choice change.</span></span> <span data-ttu-id="d8b6f-225">La consulta compara todos los intervalos de estadísticas en tiempo de ejecución en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-225">Query compares all runtime stat intervals side by side.</span></span>

```
SELECT 
    qt.query_sql_text, 
    q.query_id, 
    qt.query_text_id, 
    rs1.runtime_stats_id AS runtime_stats_id_1,
    rsi1.start_time AS interval_1, 
    p1.plan_id AS plan_1, 
    rs1.avg_duration AS avg_duration_1, 
    rs2.avg_duration AS avg_duration_2,
    p2.plan_id AS plan_2, 
    rsi2.start_time AS interval_2, 
    rs2.runtime_stats_id AS runtime_stats_id_2
FROM sys.query_store_query_text AS qt 
JOIN sys.query_store_query AS q 
    ON qt.query_text_id = q.query_text_id 
JOIN sys.query_store_plan AS p1 
    ON q.query_id = p1.query_id 
JOIN sys.query_store_runtime_stats AS rs1 
    ON p1.plan_id = rs1.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi1 
    ON rsi1.runtime_stats_interval_id = rs1.runtime_stats_interval_id 
JOIN sys.query_store_plan AS p2 
    ON q.query_id = p2.query_id 
JOIN sys.query_store_runtime_stats AS rs2 
    ON p2.plan_id = rs2.plan_id 
JOIN sys.query_store_runtime_stats_interval AS rsi2 
    ON rsi2.runtime_stats_interval_id = rs2.runtime_stats_interval_id
WHERE rsi1.start_time > DATEADD(hour, -48, GETUTCDATE()) 
    AND rsi2.start_time > rsi1.start_time 
    AND p1.plan_id <> p2.plan_id
    AND rs2.avg_duration > 2*rs1.avg_duration
ORDER BY q.query_id, rsi1.start_time, rsi2.start_time;
```

 <span data-ttu-id="d8b6f-226">Si quiere ver el rendimiento de todas las regresiones (no solo de aquellas relacionadas con el cambio de elección de plan), solo tiene que eliminar la condición `AND p1.plan_id <> p2.plan_id` de la consulta anterior.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-226">If you want to see performance all regressions (not only those related to plan choice change) than just remove condition `AND p1.plan_id <> p2.plan_id` from the previous query.</span></span>

 <span data-ttu-id="d8b6f-227">**Consultas que se devolvieron recientemente en rendimiento (comparando la ejecución reciente frente al historial).**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-227">**Queries that recently regressed in performance (comparing recent vs. history execution).**</span></span> <span data-ttu-id="d8b6f-228">La siguiente consulta compara períodos de ejecución basados en ejecución de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-228">The next query compares query execution based periods of execution.</span></span> <span data-ttu-id="d8b6f-229">En este ejemplo concreto, la consulta compara la ejecución en el período reciente (1 hora) con el período del historial (última día) e identifica las que introdujeron additional_duration_workload.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-229">In this particular example the query compares execution in recent period (1 hour) vs. history period (last day) and identifies those that introduced additional_duration_workload.</span></span> <span data-ttu-id="d8b6f-230">Esta métrica se calcula como una diferencia entre la media de las ejecuciones recientes y la media de las ejecuciones del historial multiplicada por el número de ejecuciones recientes.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-230">This metrics is calculated as a difference between recent average execution and history average execution multiplied by the number of recent executions.</span></span> <span data-ttu-id="d8b6f-231">En realidad representa la cantidad de ejecuciones recientes de duración adicional introducidas en comparación con el historial:</span><span class="sxs-lookup"><span data-stu-id="d8b6f-231">It actually represents how much of additional duration recent executions introduced compared to history:</span></span>

```
--- "Recent" workload - last 1 hour
DECLARE @recent_start_time datetimeoffset;
DECLARE @recent_end_time datetimeoffset;
SET @recent_start_time = DATEADD(hour, -1, SYSUTCDATETIME());
SET @recent_end_time = SYSUTCDATETIME();

--- "History" workload
DECLARE @history_start_time datetimeoffset;
DECLARE @history_end_time datetimeoffset;
SET @history_start_time = DATEADD(hour, -24, SYSUTCDATETIME());
SET @history_end_time = SYSUTCDATETIME();

WITH
hist AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
     FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @history_start_time AND rs.last_execution_time < @history_end_time)
        OR (rs.first_execution_time <= @history_start_time AND rs.last_execution_time > @history_start_time)
        OR (rs.first_execution_time <= @history_end_time AND rs.last_execution_time > @history_end_time)
    GROUP BY p.query_id
),
recent AS
(
    SELECT 
        p.query_id query_id, 
        CONVERT(float, SUM(rs.avg_duration*rs.count_executions)) total_duration, 
        SUM(rs.count_executions) count_executions,
        COUNT(distinct p.plan_id) num_plans 
    FROM sys.query_store_runtime_stats AS rs
        JOIN sys.query_store_plan p ON p.plan_id = rs.plan_id
    WHERE  (rs.first_execution_time >= @recent_start_time AND rs.last_execution_time < @recent_end_time)
        OR (rs.first_execution_time <= @recent_start_time AND rs.last_execution_time > @recent_start_time)
        OR (rs.first_execution_time <= @recent_end_time AND rs.last_execution_time > @recent_end_time)
    GROUP BY p.query_id
)
SELECT 
    results.query_id query_id,
    results.query_text query_text,
    results.additional_duration_workload additional_duration_workload,
    results.total_duration_recent total_duration_recent,
    results.total_duration_hist total_duration_hist,
    ISNULL(results.count_executions_recent, 0) count_executions_recent,
    ISNULL(results.count_executions_hist, 0) count_executions_hist 
FROM
(
    SELECT
        hist.query_id query_id,
        qt.query_sql_text query_text,
        ROUND(CONVERT(float, recent.total_duration/recent.count_executions-hist.total_duration/hist.count_executions)*(recent.count_executions), 2) AS additional_duration_workload,
        ROUND(recent.total_duration, 2) total_duration_recent, 
        ROUND(hist.total_duration, 2) total_duration_hist,
        recent.count_executions count_executions_recent,
        hist.count_executions count_executions_hist   
    FROM hist 
        JOIN recent 
            ON hist.query_id = recent.query_id 
        JOIN sys.query_store_query AS q 
            ON q.query_id = hist.query_id
        JOIN sys.query_store_query_text AS qt 
            ON q.query_text_id = qt.query_text_id    
) AS results
WHERE additional_duration_workload > 0
ORDER BY additional_duration_workload DESC
OPTION (MERGE JOIN);
```



###  <a name="maintaining-query-performance-stability"></a><a name="Stability"></a><span data-ttu-id="d8b6f-232">Mantener la estabilidad del rendimiento de las consultas</span><span class="sxs-lookup"><span data-stu-id="d8b6f-232">Maintaining Query Performance Stability</span></span>
 <span data-ttu-id="d8b6f-233">Para las consultas ejecutadas varias veces puede observar que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ha usado diferentes planes que han generado diferente duración y uso de los recursos.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-233">For queries that are executed multiple times you may notice that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] used different plans which resulted in different resource utilization and duration.</span></span> <span data-ttu-id="d8b6f-234">Con el Almacén de consultas puede detectar con facilidad cuándo se devolvió el rendimiento de las consultas y determinar el plan óptimo en un período de interés.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-234">With Query Store you can easily detect when the query performance regressed and determine the optimal plan within a period of interest.</span></span> <span data-ttu-id="d8b6f-235">Luego puede forzar ese plan óptimo para futuras ejecuciones de consultas.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-235">Then you can force that optimal plan for future query execution.</span></span>

 <span data-ttu-id="d8b6f-236">También puede identificar el rendimiento incoherente de las consultas para una consulta con parámetros (ya sea con parámetros automáticos o con parámetros manuales).</span><span class="sxs-lookup"><span data-stu-id="d8b6f-236">You can also identify inconsistent query performance for a query with parameters (either auto- parameterized or manually parameterized).</span></span> <span data-ttu-id="d8b6f-237">Entre los distintos planes puede identificar el plan que es rápido y lo suficientemente óptimo para todos o la mayoría de los valores de parámetros y forzar ese plan, manteniendo un rendimiento predecible para el conjunto más amplio de escenarios de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-237">Among different plans you can identify plan which is fast and optimal enough for all or most of the parameter values and force that plan; keeping predictable performance for the wider set of user scenarios.</span></span>

 <span data-ttu-id="d8b6f-238">**Forzar o planear una consulta (aplicar directiva de forzado).**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-238">**Force or a plan for a query (apply forcing policy).**</span></span> <span data-ttu-id="d8b6f-239">Cuando se fuerza un plan para una determinada consulta, cada vez que una consulta entra en ejecución, se ejecutará con el plan que se fuerza.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-239">When a plan is forced for a certain query, every time a query comes to execution it will be executed with the plan that is forced.</span></span>

```
EXEC sp_query_store_force_plan @query_id = 48, @plan_id = 49;
```

 <span data-ttu-id="d8b6f-240">Al usar `sp_query_store_force_plan` solo puede forzar los planes que se grabaron por el Almacén de consultas como un plan para esa consulta.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-240">When using `sp_query_store_force_plan` you can only force plans that were recorded by Query Store as a plan for that query.</span></span> <span data-ttu-id="d8b6f-241">Es decir, los únicos planes disponibles para una consulta son aquellos que ya se usaron para ejecutar la Q1 mientras el Almacén de consultas estaba activo.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-241">In other words, the only plans available for a query are those that were already used to execute Q1 while Query Store was active.</span></span>

 <span data-ttu-id="d8b6f-242">**Quitar el forzado de un plan para una consulta.**</span><span class="sxs-lookup"><span data-stu-id="d8b6f-242">**Remove plan forcing for a query.**</span></span> <span data-ttu-id="d8b6f-243">Para confiar de nuevo en el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] optimizador de consultas para calcular el plan de consulta óptimo, use `sp_query_store_unforce_plan` para no aplicar el plan seleccionado para la consulta.</span><span class="sxs-lookup"><span data-stu-id="d8b6f-243">To rely again on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] query optimizer to calculate the optimal query plan, use `sp_query_store_unforce_plan` to unforce the plan that was selected for the query.</span></span>

```
EXEC sp_query_store_unforce_plan @query_id = 48, @plan_id = 49;
```



## <a name="see-also"></a><span data-ttu-id="d8b6f-244">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8b6f-244">See Also</span></span>
 <span data-ttu-id="d8b6f-245">[Supervisar y ajustar](../performance/monitor-and-tune-for-performance.md) [las herramientas de supervisión y optimización del rendimiento](../performance/performance-monitoring-and-tuning-tools.md) de rendimiento [abrir el monitor de actividad &#40;SQL Server Management Studio](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [monitor de actividad](../performance-monitor/activity-monitor.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b6f-245">[Monitor and Tune for Performance](../performance/monitor-and-tune-for-performance.md) [Performance Monitoring and Tuning Tools](../performance/performance-monitoring-and-tuning-tools.md) [Open Activity Monitor &#40;SQL Server Management Studio&#41;](../performance-monitor/open-activity-monitor-sql-server-management-studio.md) [Activity Monitor](../performance-monitor/activity-monitor.md)</span></span>


