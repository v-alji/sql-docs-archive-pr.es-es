---
title: Almacén de administración de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], management data warehouse
- data warehouse
- management data warehouse
ms.assetid: 9874a8b2-7ccd-494a-944c-ad33b30b5499
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 96eb26c3e273832aead4aa0421304df17dc5b8ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671097"
---
# <a name="management-data-warehouse"></a><span data-ttu-id="f25bf-102">almacén de administración de datos</span><span class="sxs-lookup"><span data-stu-id="f25bf-102">Management Data Warehouse</span></span>
  <span data-ttu-id="f25bf-103">El almacén de administración de datos es una base de datos relacional que contiene los datos recopilados de un servidor que es el destino de la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-103">The management data warehouse is a relational database that contains the data that is collected from a server that is a data collection target.</span></span> <span data-ttu-id="f25bf-104">Estos datos se utilizan para generar informes para los conjuntos de recopilación de datos del sistema y también pueden utilizarse para crear informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="f25bf-104">This data is used to generate the reports for the System Data collection sets, and can also be used to create custom reports.</span></span>  
  
 <span data-ttu-id="f25bf-105">La infraestructura del recopilador de datos define los trabajos y los planes de mantenimiento que se necesitan para implementar las directivas de retención definidas por el administrador de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-105">The data collector infrastructure defines the jobs and maintenance plans that are needed to implement the retention policies defined by the database administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f25bf-106">Para esta versión del recopilador de datos, el almacén de datos de administración se crea utilizando el modelo de recuperación simple, para minimizar el registro.</span><span class="sxs-lookup"><span data-stu-id="f25bf-106">For this release of the data collector, the management data warehouse is created using the Simple recovery model, to minimize logging.</span></span> <span data-ttu-id="f25bf-107">Debe implementar el modelo de recuperación adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="f25bf-107">You should implement the appropriate recovery model for your organization.</span></span>  
  
## <a name="deploying-and-using-the-data-warehouse"></a><span data-ttu-id="f25bf-108">Implementar y usar el almacenamiento de datos</span><span class="sxs-lookup"><span data-stu-id="f25bf-108">Deploying and Using the Data Warehouse</span></span>  
 <span data-ttu-id="f25bf-109">Puede instalar el almacén de administración de datos en la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ejecuta el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-109">You can install the management data warehouse on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that runs the data collector.</span></span> <span data-ttu-id="f25bf-110">Sin embargo, si los recursos o el rendimiento del servidor suponen un problema en el servidor que se está supervisando, puede instalar el almacén de administración de datos en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="f25bf-110">However, if server resources or performance is an issue on the server being monitored, you can install the management data warehouse on a different computer.</span></span>  
  
 <span data-ttu-id="f25bf-111">Al crear el almacén de administración de datos, se crean los esquemas necesarios y sus objetos para los conjuntos de recopilación del sistema predefinidos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-111">The required schemas and their objects for the predefined system collection sets are created when you create the management data warehouse.</span></span> <span data-ttu-id="f25bf-112">Se crean dos esquemas, el de núcleo y el de instantáneas. Se crea un tercer esquema, custom_snapshots, cuando se crean conjuntos de recopilación definidos por el usuario que incluyen elementos de recopilación que usan el tipo de recopilador de consultas T-SQL genérico.</span><span class="sxs-lookup"><span data-stu-id="f25bf-112">The schemas that are created are core and snapshots.A third schema, custom_snapshots, is created when user-defined collection sets are created that include collection items that use the Generic T-SQL Query collector type.</span></span>  
  
###### <a name="core-schema"></a><span data-ttu-id="f25bf-113">Esquema de núcleo</span><span class="sxs-lookup"><span data-stu-id="f25bf-113">Core schema</span></span>  
 <span data-ttu-id="f25bf-114">El esquema de núcleo define las tablas, los procedimientos almacenados y las vistas que se usan para organizar e identificar los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="f25bf-114">The core schema describes the tables, stored procedures, and views that are used to organize and to identify collected data.</span></span> <span data-ttu-id="f25bf-115">Estas tablas se comparten entre todas las tablas de datos creadas para los tipos de recopilador individuales.</span><span class="sxs-lookup"><span data-stu-id="f25bf-115">These tables are shared among all the data tables created for individual collector types.</span></span> <span data-ttu-id="f25bf-116">Este esquema está bloqueado y solamente lo puede modificar el propietario de la base de datos del almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-116">This schema is locked and can only be modified by the owner of the management data warehouse database.</span></span> <span data-ttu-id="f25bf-117">Los nombres de las tablas de este esquema llevan el prefijo "core".</span><span class="sxs-lookup"><span data-stu-id="f25bf-117">The names of the tables in this schema are prefixed by "core".</span></span>  
  
 <span data-ttu-id="f25bf-118">En la tabla siguiente se describen las tablas de base de datos del esquema de núcleo.</span><span class="sxs-lookup"><span data-stu-id="f25bf-118">The following table describes the database tables in the core schema.</span></span> <span data-ttu-id="f25bf-119">Estas tablas de base de datos permiten al recopilador de datos realizar el seguimiento de la procedencia de los datos y saber quién los insertó y cuándo se cargaron en el almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-119">These database tables enable the data collector to track where the data came from, who inserted it, and when it was uploaded to the data warehouse.</span></span>  
  
|<span data-ttu-id="f25bf-120">Nombre de la tabla</span><span class="sxs-lookup"><span data-stu-id="f25bf-120">Table name</span></span>|<span data-ttu-id="f25bf-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f25bf-121">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="f25bf-122">core.performance_counter_report_group_items</span><span class="sxs-lookup"><span data-stu-id="f25bf-122">core.performance_counter_report_group_items</span></span>|<span data-ttu-id="f25bf-123">Almacena información sobre la forma en que se deben agrupar y agregar los contadores de rendimiento en los informes del almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-123">Stores information about how the management data warehouse reports should group and aggregate performance counters.</span></span>|  
|<span data-ttu-id="f25bf-124">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="f25bf-124">core.snapshots_internal</span></span>|<span data-ttu-id="f25bf-125">Identifica cada nueva instantánea.</span><span class="sxs-lookup"><span data-stu-id="f25bf-125">Identifies each new snapshot.</span></span> <span data-ttu-id="f25bf-126">En esta tabla se inserta una nueva fila cada vez que un paquete de carga inicia la carga de un nuevo lote de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-126">A new row is inserted into this table whenever an upload package starts uploading a new batch of data.</span></span>|  
|<span data-ttu-id="f25bf-127">core.snapshot_timetable_internal</span><span class="sxs-lookup"><span data-stu-id="f25bf-127">core.snapshot_timetable_internal</span></span>|<span data-ttu-id="f25bf-128">Almacena información sobre la hora de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="f25bf-128">Stores information about the snapshot times.</span></span> <span data-ttu-id="f25bf-129">La hora de la instantánea se almacena en una tabla independiente, porque pueden producirse muchas instantáneas prácticamente a la vez.</span><span class="sxs-lookup"><span data-stu-id="f25bf-129">The snapshot time is stored in a separate table because many snapshots can happen at nearly the same time.</span></span>|  
|<span data-ttu-id="f25bf-130">core.source.info_internal</span><span class="sxs-lookup"><span data-stu-id="f25bf-130">core.source.info_internal</span></span>|<span data-ttu-id="f25bf-131">Esta tabla almacena información sobre el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-131">This table stores information about the data source.</span></span> <span data-ttu-id="f25bf-132">Se actualiza esta tabla cuando un nuevo conjunto de recopilación empieza a cargar los datos en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-132">This table is updated whenever a new collection set starts uploading data to the data warehouse.</span></span>|  
|<span data-ttu-id="f25bf-133">core.supported_collector_types_internal</span><span class="sxs-lookup"><span data-stu-id="f25bf-133">core.supported_collector_types_internal</span></span>|<span data-ttu-id="f25bf-134">Contiene los identificadores de los tipos de recopilador registrados que pueden cargar datos en el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-134">Contains the IDs of registered collector types that can upload data to the management data warehouse.</span></span> <span data-ttu-id="f25bf-135">Esta tabla solo se actualiza cuando el esquema del almacén de datos se actualiza para admitir un nuevo tipo de recopilador.</span><span class="sxs-lookup"><span data-stu-id="f25bf-135">This table is only updated when the schema of the warehouse is updated to support a new collector type.</span></span> <span data-ttu-id="f25bf-136">Cuando se crea el almacén de administración de datos, esta tabla se rellena con los identificadores de los tipos de recopilador proporcionados por el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-136">When the management data warehouse is created, this table is populated with the IDs of the collector types provided by the data collector.</span></span>|  
|<span data-ttu-id="f25bf-137">core.wait_categories</span><span class="sxs-lookup"><span data-stu-id="f25bf-137">core.wait_categories</span></span>|<span data-ttu-id="f25bf-138">Contiene las categorías utilizadas para agrupar los tipos de espera de acuerdo con la característica wait_type.</span><span class="sxs-lookup"><span data-stu-id="f25bf-138">Contains the categories used to group wait types according to wait_type characteristic.</span></span>|  
|<span data-ttu-id="f25bf-139">core.wait_types</span><span class="sxs-lookup"><span data-stu-id="f25bf-139">core.wait_types</span></span>|<span data-ttu-id="f25bf-140">Contiene los tipos de espera reconocidos por el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-140">Contains the wait types recognized by the data collector.</span></span>|  
|<span data-ttu-id="f25bf-141">core.purge_info_internal</span><span class="sxs-lookup"><span data-stu-id="f25bf-141">core.purge_info_internal</span></span>|<span data-ttu-id="f25bf-142">Indica que se ha realizado una solicitud para detener la eliminación de datos en el almacén de administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f25bf-142">Indicates that a request has been made to stop the removal of data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="f25bf-143">Las tablas anteriores se utilizan con tablas de tipo de recopilador para almacenar información.</span><span class="sxs-lookup"><span data-stu-id="f25bf-143">The preceding tables are used with collector type tables to store information.</span></span> <span data-ttu-id="f25bf-144">Por ejemplo, el tipo de recopilador genérico de Seguimiento de SQL usa las tablas siguientes para almacenar los datos de seguimiento:</span><span class="sxs-lookup"><span data-stu-id="f25bf-144">For example, the Generic SQL Trace collector type uses the following tables to store trace data:</span></span>  
  
-   <span data-ttu-id="f25bf-145">core.source_info_internal</span><span class="sxs-lookup"><span data-stu-id="f25bf-145">core.source_info_internal</span></span>  
  
-   <span data-ttu-id="f25bf-146">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="f25bf-146">core.snapshots_internal</span></span>  
  
-   <span data-ttu-id="f25bf-147">snapshots.trace_info</span><span class="sxs-lookup"><span data-stu-id="f25bf-147">snapshots.trace_info</span></span>  
  
-   <span data-ttu-id="f25bf-148">snapshots.trace_data</span><span class="sxs-lookup"><span data-stu-id="f25bf-148">snapshots.trace_data</span></span>  
  
###### <a name="snapshots-schema"></a><span data-ttu-id="f25bf-149">Esquema de instantáneas</span><span class="sxs-lookup"><span data-stu-id="f25bf-149">Snapshots schema</span></span>  
 <span data-ttu-id="f25bf-150">El esquema de instantáneas describe los objetos necesarios para almacenar y mantener los datos recopilados por los tipos de recopilador que se proporcionan.</span><span class="sxs-lookup"><span data-stu-id="f25bf-150">The snapshots schema describes the objects needed to store and maintain the data collected by the collector types that are provided.</span></span> <span data-ttu-id="f25bf-151">Las tablas de este esquema son fijas y no necesitan cambiarse durante la vigencia del tipo de recopilador.</span><span class="sxs-lookup"><span data-stu-id="f25bf-151">The tables in this schema are fixed and do not need to be changed during the lifetime of the collector type.</span></span> <span data-ttu-id="f25bf-152">Si se necesitan cambios, solo los miembros del rol mdw_admin pueden cambiar el esquema.</span><span class="sxs-lookup"><span data-stu-id="f25bf-152">If changes are needed, the schema can only be changed by members of the mdw_admin role.</span></span> <span data-ttu-id="f25bf-153">Estas tablas se crean para almacenar los datos recopilados por los conjuntos de recopilación de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="f25bf-153">These tables are created to store the data collected by the System Data collection sets.</span></span>  
  
 <span data-ttu-id="f25bf-154">En las tablas siguientes se muestra una parte del esquema del almacén de administración de datos que se requiere para los conjuntos de recopilación de actividad del servidor y de estadísticas de consultas.</span><span class="sxs-lookup"><span data-stu-id="f25bf-154">The following tables illustrate a portion of the management data warehouse schema that is required for the Server Activity and Query Statistics collection sets.</span></span>  
  
-   <span data-ttu-id="f25bf-155">Tablas de recursos de nivel del sistema</span><span class="sxs-lookup"><span data-stu-id="f25bf-155">System-level resource tables</span></span>  
  
    -   <span data-ttu-id="f25bf-156">**snapshots.os_wait_stats**</span><span class="sxs-lookup"><span data-stu-id="f25bf-156">**snapshots.os_wait_stats**</span></span>  
  
    -   <span data-ttu-id="f25bf-157">**snapshots.os_latch_stats**</span><span class="sxs-lookup"><span data-stu-id="f25bf-157">**snapshots.os_latch_stats**</span></span>  
  
    -   <span data-ttu-id="f25bf-158">**snapshots.os_schedulers**</span><span class="sxs-lookup"><span data-stu-id="f25bf-158">**snapshots.os_schedulers**</span></span>  
  
    -   `snapshots.os_memory_clerks`  
  
    -   <span data-ttu-id="f25bf-159">**snapshots.os_memory_nodes**</span><span class="sxs-lookup"><span data-stu-id="f25bf-159">**snapshots.os_memory_nodes**</span></span>  
  
    -   <span data-ttu-id="f25bf-160">snapshots.sql_process_and_system_memory</span><span class="sxs-lookup"><span data-stu-id="f25bf-160">snapshots.sql_process_and_system_memory</span></span>  
  
-   <span data-ttu-id="f25bf-161">Actividad del sistema</span><span class="sxs-lookup"><span data-stu-id="f25bf-161">System activity</span></span>  
  
    -   <span data-ttu-id="f25bf-162">snapshots.active_sessions_and_requests</span><span class="sxs-lookup"><span data-stu-id="f25bf-162">snapshots.active_sessions_and_requests</span></span>  
  
-   <span data-ttu-id="f25bf-163">Estadísticas de consultas</span><span class="sxs-lookup"><span data-stu-id="f25bf-163">Query statistics</span></span>  
  
    -   <span data-ttu-id="f25bf-164">snapshots.query_stats</span><span class="sxs-lookup"><span data-stu-id="f25bf-164">snapshots.query_stats</span></span>  
  
-   <span data-ttu-id="f25bf-165">Estadísticas de E/S</span><span class="sxs-lookup"><span data-stu-id="f25bf-165">I/O statistics</span></span>  
  
    -   `snapshots.io_virtual_file_stats`  
  
-   <span data-ttu-id="f25bf-166">Texto y plan de consulta</span><span class="sxs-lookup"><span data-stu-id="f25bf-166">Query text and plan</span></span>  
  
    -   <span data-ttu-id="f25bf-167">snapshots.notable_query_text</span><span class="sxs-lookup"><span data-stu-id="f25bf-167">snapshots.notable_query_text</span></span>  
  
    -   <span data-ttu-id="f25bf-168">snapshots.notable_query_plan</span><span class="sxs-lookup"><span data-stu-id="f25bf-168">snapshots.notable_query_plan</span></span>  
  
-   <span data-ttu-id="f25bf-169">Estadísticas de consultas normalizadas</span><span class="sxs-lookup"><span data-stu-id="f25bf-169">Normalized query statistics</span></span>  
  
    -   <span data-ttu-id="f25bf-170">snapshots.distinct_queries</span><span class="sxs-lookup"><span data-stu-id="f25bf-170">snapshots.distinct_queries</span></span>  
  
    -   <span data-ttu-id="f25bf-171">snapshots.distinct_query_to_handle</span><span class="sxs-lookup"><span data-stu-id="f25bf-171">snapshots.distinct_query_to_handle</span></span>  
  
 <span data-ttu-id="f25bf-172">**Esquema custom_snapshots**</span><span class="sxs-lookup"><span data-stu-id="f25bf-172">**Custom_snapshots schema**</span></span>  
  
 <span data-ttu-id="f25bf-173">El esquema custom_snapshots describe las tablas y las vistas nuevas que se crean cuando se utilizan tipos de recopilador estándar o de otros fabricantes para crear los conjuntos de recopilación definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f25bf-173">The custom_snapshots schema describes new tables and views that are created when standard or third-party collector types are used to create user-defined collection sets.</span></span> <span data-ttu-id="f25bf-174">Cualquier tipo de recopilador que requiera una nueva tabla de datos para un elemento de recopilación puede crear esa tabla en este esquema.</span><span class="sxs-lookup"><span data-stu-id="f25bf-174">Any collector type that requires a new data table for a collection item can create that table in this schema.</span></span> <span data-ttu-id="f25bf-175">Los miembros del rol mdw_writer pueden agregar nuevas tablas a este esquema.</span><span class="sxs-lookup"><span data-stu-id="f25bf-175">New tables can be added in this schema by members of the mdw_writer role.</span></span> <span data-ttu-id="f25bf-176">Cualquier otro cambio en el esquema solo lo pueden realizar los miembros del rol mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="f25bf-176">Any other changes to the schema can only be made by members of the mdw_admin role.</span></span>  
  
 <span data-ttu-id="f25bf-177">Para obtener información detallada sobre el tipo de datos y el contenido de las columnas de tabla de base de datos, lea la documentación del procedimiento almacenado del recopilador de datos correspondiente de cada una de las tablas.</span><span class="sxs-lookup"><span data-stu-id="f25bf-177">You can get detailed data type and content information for the database table columns by reading the documentation for the appropriate data collector stored procedure for each of the tables.</span></span>  
  
### <a name="best-practices"></a><span data-ttu-id="f25bf-178">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="f25bf-178">Best Practices</span></span>  
 <span data-ttu-id="f25bf-179">Al trabajar con el almacén de datos de administración, recomendamos seguir estas prácticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="f25bf-179">When working with the management data warehouse, we recommend following these best practices:</span></span>  
  
-   <span data-ttu-id="f25bf-180">No modifique los metadatos de tablas de almacén de datos de administración a menos que esté agregando un nuevo tipo de recopilador.</span><span class="sxs-lookup"><span data-stu-id="f25bf-180">Do not modify the metadata of management data warehouse tables unless you are adding a new collector type.</span></span>  
  
-   <span data-ttu-id="f25bf-181">No modifique directamente los datos del almacén de datos de administración.</span><span class="sxs-lookup"><span data-stu-id="f25bf-181">Do not directly modify the data in the management data warehouse.</span></span> <span data-ttu-id="f25bf-182">Al cambiar los datos que ha recopilado, se invalida la legitimidad de los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="f25bf-182">Changing the data that you have collected invalidates the legitimacy of the collected data.</span></span>  
  
-   <span data-ttu-id="f25bf-183">En lugar de usar las tablas directamente, use los procedimientos almacenados y las funciones que se proporcionan con el recopilador de datos para obtener acceso a los datos de instancia y aplicación.</span><span class="sxs-lookup"><span data-stu-id="f25bf-183">Instead of directly using the tables, use the documented stored procedures and functions that are provided with the data collector to access instance and application data.</span></span> <span data-ttu-id="f25bf-184">Los nombres y las definiciones de las tablas se pueden cambiar, cambian al actualizar la aplicación y pueden cambiar en versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="f25bf-184">The table names and definitions can change, do change when you update the application, and might change in future releases.</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="f25bf-185">Historial de cambios</span><span class="sxs-lookup"><span data-stu-id="f25bf-185">Change History</span></span>  
  
|<span data-ttu-id="f25bf-186">Contenido actualizado</span><span class="sxs-lookup"><span data-stu-id="f25bf-186">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="f25bf-187">Se ha agregado la tabla core.performance_counter_report_group_items a la sección "Esquema de núcleo".</span><span class="sxs-lookup"><span data-stu-id="f25bf-187">Added the core.performance_counter_report_group_items table to the "Core schema" section.</span></span>|  
|<span data-ttu-id="f25bf-188">Se ha actualizado la lista de tablas de la sección "Esquema de instantáneas".</span><span class="sxs-lookup"><span data-stu-id="f25bf-188">Updated the list of tables in the "Snapshots schema" section.</span></span> <span data-ttu-id="f25bf-189">Se ha agregado snapshots.os_memory_clerks, snapshots.sql_process_and_system_memory y snapshots.io_virtual_file_stats.</span><span class="sxs-lookup"><span data-stu-id="f25bf-189">Added snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory, and snapshots.io_virtual_file_stats.</span></span> <span data-ttu-id="f25bf-190">Se ha quitado snapshots.os_process_memory y snapshots.distinct_query_stats.</span><span class="sxs-lookup"><span data-stu-id="f25bf-190">Removedsnapshots.os_process_memory and snapshots.distinct_query_stats.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f25bf-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f25bf-191">See Also</span></span>  
 <span data-ttu-id="f25bf-192">[Procedimientos almacenados de almacén de administración de datos &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f25bf-192">[Management Data Warehouse Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="f25bf-193">[Procedimientos almacenados del recopilador de datos &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f25bf-193">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="f25bf-194">[Recopilación de datos](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="f25bf-194">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="f25bf-195">Ver un informe de conjunto de recopilación &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f25bf-195">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
  
