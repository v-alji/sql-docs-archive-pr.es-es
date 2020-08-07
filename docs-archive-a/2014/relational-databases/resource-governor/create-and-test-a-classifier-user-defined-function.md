---
title: Creación y prueba de una función clasificadora definida por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function create
- classifier function [SQL Server], test
- classifier function [SQL Server], create
- Resource Governor, classifier function test
ms.assetid: 7866b3c9-385b-40c6-aca5-32d3337032be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1b8e5371762e38cf2b3ac8c1d506b467dcfa7e3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745700"
---
# <a name="create-and-test-a-classifier-user-defined-function"></a><span data-ttu-id="88fa9-102">Crear y probar una función clasificadora definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="88fa9-102">Create and Test a Classifier User-Defined Function</span></span>
  <span data-ttu-id="88fa9-103">En este tema se muestra cómo crear y probar una función clasificadora definida por el usuario (UDF).</span><span class="sxs-lookup"><span data-stu-id="88fa9-103">This topic shows how to create and test a classifier user-defined function (UDF).</span></span> <span data-ttu-id="88fa9-104">Los pasos implican ejecutar instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88fa9-104">The steps involve executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="88fa9-105">El ejemplo mostrado en el procedimiento siguiente ilustra las posibilidades para crear una función clasificadora definida por el usuario bastante compleja.</span><span class="sxs-lookup"><span data-stu-id="88fa9-105">The example shown in the following procedure illustrates the possibilities for creating a fairly complex classifier user-defined function.</span></span>  
  
 <span data-ttu-id="88fa9-106">En el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="88fa9-106">In our example:</span></span>  
  
-   <span data-ttu-id="88fa9-107">Se crean un grupo de recursos de servidor (pProductionProcessing) y un grupo de cargas de trabajo (gProductionProcessing) para el procesamiento de producción durante un intervalo de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="88fa9-107">A resource pool (pProductionProcessing) and workload group (gProductionProcessing) are created for production processing during a specified time range.</span></span>  
  
-   <span data-ttu-id="88fa9-108">Se crean un grupo de recursos de servidor (pOffHoursProcessing) y un grupo de cargas de trabajo (gOffHoursProcessing) para administrar las conexiones que no cumplen los requisitos del procesamiento de producción.</span><span class="sxs-lookup"><span data-stu-id="88fa9-108">A resource pool (pOffHoursProcessing) and workload group (gOffHoursProcessing) are created for handling connections that do not meet the requirements for production processing.</span></span>  
  
-   <span data-ttu-id="88fa9-109">Se crea una tabla (TblClassificationTimeTable) en la base de datos maestra para contener la hora de inicio y de finalización que se puede evaluar con una hora de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="88fa9-109">A table (TblClassificationTimeTable) is created in master to hold start and end times that can be evaluated against a login time.</span></span> <span data-ttu-id="88fa9-110">Esto se debe crear en la base de datos maestra porque el regulador de recursos utiliza el enlace de esquemas para las funciones clasificadoras.</span><span class="sxs-lookup"><span data-stu-id="88fa9-110">This must be created in master because Resource Governor uses schema binding for classifier functions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="88fa9-111">Como práctica recomendada, no debería almacenar en la base de datos maestra las tablas grandes que se actualicen con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="88fa9-111">As a best practice, you should not store large, frequently updated tables in master.</span></span>  
  
 <span data-ttu-id="88fa9-112">La función clasificadora extiende el tiempo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="88fa9-112">The classifier function extends the login time.</span></span> <span data-ttu-id="88fa9-113">Una función demasiado compleja puede hacer que los inicios de sesión agoten el tiempo de espera o ralenticen las conexiones rápidas.</span><span class="sxs-lookup"><span data-stu-id="88fa9-113">An overly complex function can cause logins to time out or slow down fast connections.</span></span>  
  
### <a name="to-create-the-classifier-user-defined-function"></a><span data-ttu-id="88fa9-114">Para crear la función clasificadora definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="88fa9-114">To create the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="88fa9-115">Cree y configure los grupos de recursos y grupos de cargas de trabajo nuevos.</span><span class="sxs-lookup"><span data-stu-id="88fa9-115">Create and configure the new resource pools and workload groups.</span></span> <span data-ttu-id="88fa9-116">Asigne cada grupo de cargas de trabajo al grupo de recursos de servidor adecuado.</span><span class="sxs-lookup"><span data-stu-id="88fa9-116">Assign each workload group to the appropriate resource pool.</span></span>  
  
    ```  
    --- Create a resource pool for production processing  
    --- and set limits.  
    USE master  
    GO  
    CREATE RESOURCE POOL pProductionProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 100,  
         MIN_CPU_PERCENT = 50  
    )  
    GO  
    --- Create a workload group for production processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gProductionProcessing  
    WITH  
    (  
         IMPORTANCE = MEDIUM  
    )  
    --- Assign the workload group to the production processing  
    --- resource pool.  
    USING pProductionProcessing  
    GO  
    --- Create a resource pool for off-hours processing  
    --- and set limits.  
  
    CREATE RESOURCE POOL pOffHoursProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 50,  
         MIN_CPU_PERCENT = 0  
    )  
    GO  
    --- Create a workload group for off-hours processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gOffHoursProcessing  
    WITH  
    (  
         IMPORTANCE = LOW  
    )  
    --- Assign the workload group to the off-hours processing  
    --- resource pool.  
    USING pOffHoursProcessing  
    GO  
    ```  
  
2.  <span data-ttu-id="88fa9-117">Actualice la configuración en la memoria.</span><span class="sxs-lookup"><span data-stu-id="88fa9-117">Update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
3.  <span data-ttu-id="88fa9-118">Cree una tabla y defina las horas de finalización e inicio para el intervalo de tiempo de proceso de producción.</span><span class="sxs-lookup"><span data-stu-id="88fa9-118">Create a table and define the start and end times for the production processing time range.</span></span>  
  
    ```  
    USE master  
    GO  
    CREATE TABLE tblClassificationTimeTable  
    (  
         strGroupName     sysname          not null,  
         tStartTime       time              not null,  
         tEndTime         time              not null  
    )  
    GO  
    --- Add time values that the classifier will use to  
    --- determine the workload group for a session.  
    INSERT into tblClassificationTimeTable VALUES('gProductionProcessing', '6:35 AM', '6:15 PM')  
    go  
    ```  
  
4.  <span data-ttu-id="88fa9-119">Cree la función clasificadora que utiliza las funciones de hora y los valores que se pueden evaluar con las horas en la tabla de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="88fa9-119">Create the classifier function that uses time functions and values that can be evaluated against the times in the lookup table.</span></span> <span data-ttu-id="88fa9-120">Para obtener información sobre cómo usar tablas de búsqueda en una función clasificadora, vea "Procedimientos recomendados para usar tablas de búsqueda en una función clasificadora" en este tema.</span><span class="sxs-lookup"><span data-stu-id="88fa9-120">For information about using Lookup Tables in a classifier function, see "Best practices for using Lookup Tables in a classifier function" in this topic.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="88fa9-121">incluía un conjunto expandido de funciones y tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="88fa9-121">introduced an expanded set of date and time data types and functions.</span></span> <span data-ttu-id="88fa9-122">Para obtener más información, vea [Tipos de datos y funciones de fecha y hora &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="88fa9-122">For more information, see [Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
    ```  
    CREATE FUNCTION fnTimeClassifier()  
    RETURNS sysname  
    WITH SCHEMABINDING  
    AS  
    BEGIN  
         DECLARE @strGroup sysname  
         DECLARE @loginTime time  
         SET @loginTime = CONVERT(time,GETDATE())  
         SELECT TOP 1 @strGroup = strGroupName  
              FROM dbo.tblClassificationTimeTable  
              WHERE tStartTime <= @loginTime and tEndTime >= @loginTime  
         IF(@strGroup is not null)  
         BEGIN  
              RETURN @strGroup  
         END  
    --- Use the default workload group if there is no match  
    --- on the lookup.  
         RETURN N'gOffHoursProcessing'  
    END  
    GO  
    ```  
  
5.  <span data-ttu-id="88fa9-123">Registre la función clasificadora y actualice la configuración en memoria.</span><span class="sxs-lookup"><span data-stu-id="88fa9-123">Register the classifier function and update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR with (CLASSIFIER_FUNCTION = dbo.fnTimeClassifier)  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
### <a name="to-verify-the-resource-pools-workload-groups-and-the-classifier-user-defined-function"></a><span data-ttu-id="88fa9-124">Para comprobar los grupos de recursos, los grupos de cargas de trabajo y la función clasificadora definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="88fa9-124">To verify the resource pools, workload groups, and the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="88fa9-125">Obtenga la configuración del grupo de cargas de trabajo y del grupo de recursos de servidor con la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="88fa9-125">Obtain the resource pool and workload group configuration by using the following query.</span></span>  
  
    ```  
    USE master  
    SELECT * FROM sys.resource_governor_resource_pools  
    SELECT * FROM sys.resource_governor_workload_groups  
    GO  
    ```  
  
2.  <span data-ttu-id="88fa9-126">Compruebe que la función clasificadora existe y está habilitada con las consultas siguientes.</span><span class="sxs-lookup"><span data-stu-id="88fa9-126">Verify that the classifier function exists and is enabled by using the following queries.</span></span>  
  
    ```  
    --- Get the classifier function Id and state (enabled).  
    SELECT * FROM sys.resource_governor_configuration  
    GO  
    --- Get the classifer function name and the name of the schema  
    --- that it is bound to.  
    SELECT   
          object_schema_name(classifier_function_id) AS [schema_name],  
          object_name(classifier_function_id) AS [function_name]  
    FROM sys.dm_resource_governor_configuration  
  
    ```  
  
3.  <span data-ttu-id="88fa9-127">Obtenga los datos de tiempo de ejecución actuales para los grupos de recursos y de cargas de trabajo con la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="88fa9-127">Obtain the current runtime data for the resource pools and workload groups by using the following query.</span></span>  
  
    ```  
    SELECT * FROM sys.dm_resource_governor_resource_pools  
    SELECT * FROM sys.dm_resource_governor_workload_groups  
    GO  
    ```  
  
4.  <span data-ttu-id="88fa9-128">Averigüe qué sesiones están en cada grupo con la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="88fa9-128">Find out what sessions are in each group by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, CAST(g.name as nvarchar(20)), s.session_id, s.login_time, CAST(s.host_name as nvarchar(20)), CAST(s.program_name AS nvarchar(20))  
              FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
              ON g.group_id = s.group_id  
    ORDER BY g.name  
    GO  
    ```  
  
5.  <span data-ttu-id="88fa9-129">Averigüe qué solicitudes están en cada grupo con la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="88fa9-129">Find out which requests are in each group by using the following query.</span></span>  
  
    ```  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
                ON g.group_id = r.group_id  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
6.  <span data-ttu-id="88fa9-130">Averigüe qué solicitudes está ejecutándose en la función clasificadora con la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="88fa9-130">Find out what requests are running in the classifier by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, g.name, s.session_id, s.login_time, s.host_name, s.program_name   
               FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = s.group_id  
                     AND 'preconnect' = s.status  
    ORDER BY g.name  
    GO  
  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = r.group_id  
                     AND 'preconnect' = r.status  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
### <a name="best-practices-for-using-lookup-tables-in-a-classifier-function"></a><span data-ttu-id="88fa9-131">Prácticas recomendadas para utilizar tablas de búsqueda en una función clasificadora</span><span class="sxs-lookup"><span data-stu-id="88fa9-131">Best practices for using Lookup Tables in a classifier function</span></span>  
  
1.  <span data-ttu-id="88fa9-132">No utilice una tabla de búsqueda a menos que sea absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="88fa9-132">Do not use a lookup table unless it is absolutely necessary.</span></span> <span data-ttu-id="88fa9-133">Si necesita utilizar una tabla de búsqueda, puede estar codificada de forma rígida en la propia función; sin embargo, es necesario que esté en equilibrio con la complejidad y los cambios dinámicos de la función clasificadora.</span><span class="sxs-lookup"><span data-stu-id="88fa9-133">If you need to use a lookup table, it can be hard coded into the function itself; however, this needs to be balanced with the complexity and dynamic changes of the classifier function.</span></span>  
  
2.  <span data-ttu-id="88fa9-134">Limite la E/S realizada para las tablas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="88fa9-134">Limit the I/O performed for lookup tables.</span></span>  
  
    1.  <span data-ttu-id="88fa9-135">Utilice TOP 1 para que se devuelva solo una fila.</span><span class="sxs-lookup"><span data-stu-id="88fa9-135">Use the TOP 1 to return only one row.</span></span>  
  
    2.  <span data-ttu-id="88fa9-136">Minimice el número de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="88fa9-136">Minimize the number of rows in the table.</span></span>  
  
    3.  <span data-ttu-id="88fa9-137">Haga que todas las filas de la tabla estén en una sola página o en un número reducido de páginas.</span><span class="sxs-lookup"><span data-stu-id="88fa9-137">Make all rows of the table exist on a single page, or a small number of pages.</span></span>  
  
    4.  <span data-ttu-id="88fa9-138">Confirme que las filas encontradas utilizando las operaciones de Index Seek usan tantas columnas de búsqueda como sea posible.</span><span class="sxs-lookup"><span data-stu-id="88fa9-138">Confirm that rows found using the Index Seek operations use as many seeking columns as possible.</span></span>  
  
    5.  <span data-ttu-id="88fa9-139">Desnormalice a una sola tabla si está pensando en utilizar varias tablas con combinaciones.</span><span class="sxs-lookup"><span data-stu-id="88fa9-139">De-normalize to a single table if you are considering using multiple tables with joins.</span></span>  
  
3.  <span data-ttu-id="88fa9-140">Evite el bloqueo en la tabla de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="88fa9-140">Prevent blocking on the lookup table.</span></span>  
  
    1.  <span data-ttu-id="88fa9-141">Utilice la sugerencia `NOLOCK` para evitar el bloqueo o utilice `SET LOCK_TIMEOUT` en la función con un valor máximo de 1000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="88fa9-141">Use the `NOLOCK` hint to prevent blocking or use `SET LOCK_TIMEOUT` in the function with a maximum value of 1000 milliseconds.</span></span>  
  
    2.  <span data-ttu-id="88fa9-142">Debe haber tablas en la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="88fa9-142">Table(s) must exist in the master database.</span></span> <span data-ttu-id="88fa9-143">(La base de datos maestra es la única base de datos cuya recuperación está asegurada cuando los equipos clientes intentan la conexión).</span><span class="sxs-lookup"><span data-stu-id="88fa9-143">(The master database is the only database that is guaranteed to be recovered when the client computers attempt to connect).</span></span>  
  
    3.  <span data-ttu-id="88fa9-144">Utilice siempre el nombre completo de la tabla con el esquema.</span><span class="sxs-lookup"><span data-stu-id="88fa9-144">Always fully-qualify the table name with the schema.</span></span> <span data-ttu-id="88fa9-145">El nombre de la base de datos no es necesario porque tiene que ser la base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="88fa9-145">The database name is not necessary since it has to be the master database.</span></span>  
  
    4.  <span data-ttu-id="88fa9-146">No debe haber desencadenadores en la tabla.</span><span class="sxs-lookup"><span data-stu-id="88fa9-146">No triggers on the table.</span></span>  
  
    5.  <span data-ttu-id="88fa9-147">Si está actualizando el contenido de la tabla, asegúrese de utilizar una transacción de nivel de aislamiento de instantáneas para que los escritores no bloqueen los lectores.</span><span class="sxs-lookup"><span data-stu-id="88fa9-147">If you are updating the table contents, make sure to use a snapshot isolation level transaction to prevent Writer blocking Readers.</span></span> <span data-ttu-id="88fa9-148">Observe que el uso de la sugerencia `NOLOCK` también debe mitigar este riesgo.</span><span class="sxs-lookup"><span data-stu-id="88fa9-148">Note that using the `NOLOCK` hint should also mitigate this.</span></span>  
  
    6.  <span data-ttu-id="88fa9-149">Si es posible, deshabilite la función clasificadora al cambiar el contenido de la tabla.</span><span class="sxs-lookup"><span data-stu-id="88fa9-149">If possible, disable the classifier function when changing the table contents.</span></span>  
  
        > [!WARNING]  
        >  <span data-ttu-id="88fa9-150">Se aconseja encarecidamente seguir estas prácticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="88fa9-150">We highly recommend following these best practices.</span></span> <span data-ttu-id="88fa9-151">Si hay problemas que impiden seguir las prácticas recomendadas, conviene ponerse en contacto con el servicio de soporte técnico de Microsoft para poder evitar de forma proactiva cualquier problema futuro.</span><span class="sxs-lookup"><span data-stu-id="88fa9-151">If there are issues that prevent you from following the best practices, we recommend that you contact Microsoft Support so that you can proactively prevent any future problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fa9-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88fa9-152">See Also</span></span>  
 <span data-ttu-id="88fa9-153">[Regulador de recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="88fa9-153">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="88fa9-154">[Habilitar el regulador de recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="88fa9-154">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="88fa9-155">[Grupo de recursos de servidor del regulador de recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="88fa9-155">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="88fa9-156">[Grupos de cargas de trabajo del regulador de recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="88fa9-156">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="88fa9-157">[Configurar el regulador de recursos utilizando una plantilla](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="88fa9-157">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="88fa9-158">[Ver las propiedades del regulador de recursos](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="88fa9-158">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="88fa9-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="88fa9-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span></span>  
 <span data-ttu-id="88fa9-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="88fa9-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="88fa9-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="88fa9-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="88fa9-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="88fa9-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="88fa9-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="88fa9-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
