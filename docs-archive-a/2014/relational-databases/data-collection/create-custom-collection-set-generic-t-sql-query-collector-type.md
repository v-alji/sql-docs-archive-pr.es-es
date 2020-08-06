---
title: Crear un conjunto de recopilación personalizado que use el tipo de recopilador de consultas T-SQL genérico (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- T-SQL Query collector type
- collection sets [SQL Server], creating custom
ms.assetid: 6b06db5b-cfdc-4ce0-addd-ec643460605b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab21ad5fd65556dec639fd5ca6999d23e2de673b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674869"
---
# <a name="create-a-custom-collection-set-that-uses-the-generic-t-sql-query-collector-type-transact-sql"></a><span data-ttu-id="f90ff-102">Crear un conjunto de recopilación personalizado que utilice el tipo de recopilador de consultas T-SQL genérico (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f90ff-102">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type (Transact-SQL)</span></span>
  <span data-ttu-id="f90ff-103">Puede crear un conjunto de recopilación personalizado con elementos de recopilación que utilicen el tipo de recopilador de consultas T-SQL genérico mediante los procedimientos almacenados que se proporcionan con el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="f90ff-103">You can create a custom collection set with collection items that use the Generic T-SQL Query collector type by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="f90ff-104">Para realizar esta tarea debe usar el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para llevar a cabo los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="f90ff-104">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedures:</span></span>  
  
-   <span data-ttu-id="f90ff-105">Configurar programaciones de carga.</span><span class="sxs-lookup"><span data-stu-id="f90ff-105">Configure upload schedules.</span></span>  
  
-   <span data-ttu-id="f90ff-106">Definir y crear el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-106">Define and create the collection set.</span></span>  
  
-   <span data-ttu-id="f90ff-107">Definir y crear un elemento de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-107">Define and create a collection item.</span></span>  
  
-   <span data-ttu-id="f90ff-108">Comprobar la existencia del conjunto de recopilación y de los elementos de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-108">Verify that the collection set and collection items exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f90ff-109">Antes de crear un conjunto de recopilación personalizada, debe configurar los parámetros de recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="f90ff-109">Before you create a custom collection set, you must configure data collection parameters.</span></span> <span data-ttu-id="f90ff-110">Para obtener más información, vea [Configurar parámetros para la recopilación de datos &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f90ff-110">For more information, see [Configure Data Collection Parameters &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span></span>  
  
### <a name="define-and-create-the-collection-set"></a><span data-ttu-id="f90ff-111">Definir y crear el conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="f90ff-111">Define and create the collection set</span></span>  
  
1.  <span data-ttu-id="f90ff-112">Defina un nuevo conjunto de recopilación mediante el procedimiento almacenado sp_syscollector_create_collection_set.</span><span class="sxs-lookup"><span data-stu-id="f90ff-112">Define a new collection set using the sp_syscollector_create_collection_set stored procedure.</span></span>  
  
    ```  
    USE msdb;  
    DECLARE @collection_set_id int;  
    DECLARE @collection_set_uid uniqueidentifier;  
    EXEC sp_syscollector_create_collection_set   
        @name=N'DMV Test 1',   
        @collection_mode=0,   
        @description=N'This is a test collection set',   
        @logging_level=1,   
        @days_until_expiration=14,   
        @schedule_name=N'CollectorSchedule_Every_15min',   
        @collection_set_id=@collection_set_id OUTPUT,   
        @collection_set_uid=@collection_set_uid OUTPUT;  
    SELECT @collection_set_id, @collection_set_uid;  
    ```  
  
     <span data-ttu-id="f90ff-113">El modo de recopilación se puede establecer en 0 (almacenamiento en caché) o en 1 (sin almacenamiento en caché).</span><span class="sxs-lookup"><span data-stu-id="f90ff-113">The collection mode can be set to either 0 (cached) or to 1 (non-cached).</span></span>  
  
     <span data-ttu-id="f90ff-114">El nivel de registro se puede establecer en 0, 1 o 2.</span><span class="sxs-lookup"><span data-stu-id="f90ff-114">The logging level can be set to 0, 1 or 2.</span></span>  
  
     <span data-ttu-id="f90ff-115">Se proporcionan las siguientes programaciones preconfiguradas con el recopilador de datos:</span><span class="sxs-lookup"><span data-stu-id="f90ff-115">The following preconfigured schedules are provided with the data collector:</span></span>  
  
    -   <span data-ttu-id="f90ff-116">CollectorSchedule_Every_5min</span><span class="sxs-lookup"><span data-stu-id="f90ff-116">CollectorSchedule_Every_5min</span></span>  
  
    -   <span data-ttu-id="f90ff-117">CollectorSchedule_Every_10min</span><span class="sxs-lookup"><span data-stu-id="f90ff-117">CollectorSchedule_Every_10min</span></span>  
  
    -   <span data-ttu-id="f90ff-118">CollectorSchedule_Every_15min</span><span class="sxs-lookup"><span data-stu-id="f90ff-118">CollectorSchedule_Every_15min</span></span>  
  
    -   <span data-ttu-id="f90ff-119">CollectorSchedule_Every_30min</span><span class="sxs-lookup"><span data-stu-id="f90ff-119">CollectorSchedule_Every_30min</span></span>  
  
    -   <span data-ttu-id="f90ff-120">CollectorSchedule_Every_60min</span><span class="sxs-lookup"><span data-stu-id="f90ff-120">CollectorSchedule_Every_60min</span></span>  
  
    -   <span data-ttu-id="f90ff-121">CollectorSchedule_Every_6h</span><span class="sxs-lookup"><span data-stu-id="f90ff-121">CollectorSchedule_Every_6h</span></span>  
  
     <span data-ttu-id="f90ff-122">Si no desea usar una de las programaciones que se proporcionan, puede crear una nueva programación y usarla para el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-122">If you do not want to use one of the schedules that are provided, you can create a new schedule and use it for the collection set.</span></span> <span data-ttu-id="f90ff-123">Para obtener más información, vea [Crear y adjuntar programaciones a trabajos](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f90ff-123">For more information, see [Create and Attach Schedules to Jobs](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span></span>  
  
### <a name="define-and-create-a-collection-item"></a><span data-ttu-id="f90ff-124">Definir y crear un elemento de recopilación</span><span class="sxs-lookup"><span data-stu-id="f90ff-124">Define and create a collection item</span></span>  
  
1.  <span data-ttu-id="f90ff-125">Dado que el nuevo elemento de recopilación está basado en un tipo de recopilador genérico que ya se ha instalado, puede ejecutar el siguiente código para establecer el GUID de forma que corresponda al tipo de recopilador de consultas T-SQL genérico.</span><span class="sxs-lookup"><span data-stu-id="f90ff-125">Because the new collection item is based on a generic collector type that is already installed, you can run the following code to set the GUID to correspond to the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid uniqueidentifier;  
    SELECT @collector_type_uid = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
    WHERE name = N'Generic T-SQL Query Collector Type';  
    DECLARE @collection_item_id int;  
    ```  
  
2.  <span data-ttu-id="f90ff-126">Use el procedimiento almacenado sp_syscollector_create_collection_item para crear el elemento de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-126">Use the sp_syscollector_create_collection_item stored procedure to create the collection item.</span></span> <span data-ttu-id="f90ff-127">Declare el esquema para el elemento de recopilación para que se asigne al esquema necesario para el tipo de recopilador de consultas T-SQL genérico.</span><span class="sxs-lookup"><span data-stu-id="f90ff-127">Declare the schema for the collection item so it maps to the schema that is required for the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    EXEC sp_syscollector_create_collection_item   
        @name=N'Query Stats - Test 1',   
        @parameters=N'  
            <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
            <Query>  
            <Value>SELECT * FROM sys.dm_exec_query_stats</Value>  
            <OutputTable>dm_exec_query_stats</OutputTable>  
            </Query>  
            </ns:TSQLQueryCollector>',   
        @collection_item_id=@collection_item_id OUTPUT,   
        @frequency=5,   
        @collection_set_id=@collection_set_id,   
        @collector_type_uid=@collector_type_uid;  
    SELECT @collection_item_id;  
    ```  
  
### <a name="verify-that-the-new-collection-set-and-collection-item-exist"></a><span data-ttu-id="f90ff-128">Compruebe que el nuevo conjunto de recopilación y el elemento de recopilación existan.</span><span class="sxs-lookup"><span data-stu-id="f90ff-128">Verify that the new collection set and collection item exist</span></span>  
  
1.  <span data-ttu-id="f90ff-129">Antes de iniciar el nuevo conjunto de recopilación, ejecute la consulta siguiente para comprobar que se han creado el nuevo conjunto de recopilación y su elemento de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-129">Before starting the new collection set, run the following query to verify that the new collection set and its collection item have been created.</span></span>  
  
    ```sql  
    USE msdb;  
    SELECT * FROM syscollector_collection_sets;  
    SELECT * FROM syscollector_collection_items;  
    GO  
    ```  
  
     <span data-ttu-id="f90ff-130">También puede hacer una comprobación visual en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f90ff-130">You can also do a visual check in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f90ff-131">En el Explorador de objetos, expanda el nodo **Administración** y, a continuación, expanda **Recopilación de datos**.</span><span class="sxs-lookup"><span data-stu-id="f90ff-131">In Object Explorer, expand the **Management** node, and then expand **Data Collection**.</span></span> <span data-ttu-id="f90ff-132">Se mostrará el nuevo conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-132">The new collection set will be displayed.</span></span> <span data-ttu-id="f90ff-133">El icono de círculo rojo para el conjunto de recopilación indica que se ha detenido el conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="f90ff-133">The red circle icon for the collection set indicates that the collection set is stopped.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f90ff-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f90ff-134">Example</span></span>  
 <span data-ttu-id="f90ff-135">El ejemplo de código siguiente combina los ejemplos documentados en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="f90ff-135">The following code sample combines the examples that are documented in the previous steps.</span></span> <span data-ttu-id="f90ff-136">Tenga en cuenta que la frecuencia de recopilación establecida para el elemento de recopilación (5 segundos) se omite porque el modo recopilación del conjunto de recopilación se ha establecido en 0, que es el modo de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="f90ff-136">Note that the collection frequency that is set for the collection item (5 seconds) is ignored because the collection set collection mode is set to 0, which is cached mode.</span></span> <span data-ttu-id="f90ff-137">Para obtener más información, consulte [Data Collection](data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="f90ff-137">For more information, see [Data Collection](data-collection.md).</span></span>  
  
```sql  
USE msdb;  
  
DECLARE @collection_set_id int;  
DECLARE @collection_set_uid uniqueidentifier  
  
EXEC dbo.sp_syscollector_create_collection_set  
    @name = N'DMV Stats Test 1',  
    @collection_mode = 0,  
    @description = N'This is a test collection set',  
    @logging_level=1,  
    @days_until_expiration = 14,  
    @schedule_name=N'CollectorSchedule_Every_15min',  
    @collection_set_id = @collection_set_id OUTPUT,  
    @collection_set_uid = @collection_set_uid OUTPUT;  
SELECT @collection_set_id,@collection_set_uid;  
  
DECLARE @collector_type_uid uniqueidentifier;  
SELECT @collector_type_uid = collector_type_uid FROM syscollector_collector_types   
WHERE name = N'Generic T-SQL Query Collector Type';  
  
DECLARE @collection_item_id int;  
EXEC sp_syscollector_create_collection_item  
@name= N'Query Stats - Test 1',  
@parameters=N'  
<ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
<Query>  
  <Value>select * from sys.dm_exec_query_stats</Value>  
  <OutputTable>dm_exec_query_stats</OutputTable>  
</Query>  
 </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 5, -- This parameter is ignored in cached mode  
    @collection_set_id = @collection_set_id,  
    @collector_type_uid = @collector_type_uid;  
SELECT @collection_item_id;  
  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f90ff-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f90ff-138">See Also</span></span>  
 <span data-ttu-id="f90ff-139">[Procedimientos almacenados del recopilador de datos &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f90ff-139">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="f90ff-140">[Administrar programaciones](../../ssms/agent/manage-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="f90ff-140">[Manage Schedules](../../ssms/agent/manage-schedules.md) </span></span>  
 [<span data-ttu-id="f90ff-141">Iniciar o detener un conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="f90ff-141">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
  
