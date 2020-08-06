---
title: Agregar un elemento de recopilación a un conjunto de recopilación (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection items [SQL Server]
- collection sets [SQL Server], adding items
ms.assetid: 9fe6454e-8c0e-4b50-937b-d9871b20fd13
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0b21508761bdfbaf8918242b074f78203c1bcaed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677680"
---
# <a name="add-a-collection-item-to-a-collection-set-transact-sql"></a><span data-ttu-id="98d0c-102">Agregar un elemento de recopilación a un conjunto de recopilación (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="98d0c-102">Add a Collection Item to a Collection Set (Transact-SQL)</span></span>
  <span data-ttu-id="98d0c-103">Puede agregar un elemento de recopilación a una conjunto de recopilación existente mediante los procedimientos almacenados que se proporcionan con el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="98d0c-103">You can add a collection item to an existing collection set using the stored procedures that are provided with the data collector.</span></span>  
  
 <span data-ttu-id="98d0c-104">Lleve a cabo los pasos siguientes utilizando Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98d0c-104">Carry out the following steps using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="add-a-collection-item-to-a-collection-set"></a><span data-ttu-id="98d0c-105">Agregar un elemento de recopilación a un conjunto de recopilación</span><span class="sxs-lookup"><span data-stu-id="98d0c-105">Add a collection item to a collection set</span></span>  
  
1.  <span data-ttu-id="98d0c-106">Detenga el conjunto de recopilación al que quiere agregar el elemento; para ello, ejecute el procedimiento almacenado **sp_syscollector_stop_collection_set** .</span><span class="sxs-lookup"><span data-stu-id="98d0c-106">Stop the collection set that you want to add the item to by running the **sp_syscollector_stop_collection_set** stored procedure.</span></span> <span data-ttu-id="98d0c-107">Por ejemplo, para detener un conjunto de recopilación denominado "Test Collection Set", ejecute las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="98d0c-107">For example, to stop a collection set that is named "Test Collection Set", run the following statements:</span></span>  
  
    ```sql  
    USE msdb  
    DECLARE @csid int  
    SELECT @csid = collection_set_id  
    FROM syscollector_collection_sets  
    WHERE name = 'Test Collection Set'  
    SELECT @csid  
    EXEC dbo.sp_syscollector_stop_collection_set @collection_set_id = @csid  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="98d0c-108">Para detener el conjunto de recopilación, también puede usar el Explorador de objetos en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98d0c-108">You can also stop the collection set by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="98d0c-109">Para obtener más información, vea [Iniciar o detener un conjunto de recopilación](start-or-stop-a-collection-set.md).</span><span class="sxs-lookup"><span data-stu-id="98d0c-109">For more information, see [Start or Stop a Collection Set](start-or-stop-a-collection-set.md).</span></span>  
  
2.  <span data-ttu-id="98d0c-110">Declare el conjunto de recopilación al que desea agregar el elemento de recopilación.</span><span class="sxs-lookup"><span data-stu-id="98d0c-110">Declare the collection set that you want to add the collection item to.</span></span> <span data-ttu-id="98d0c-111">El código siguiente es un ejemplo de cómo se declara el identificador del conjunto de recopilación.</span><span class="sxs-lookup"><span data-stu-id="98d0c-111">The following code provides an example of how to declare the collection set ID.</span></span>  
  
    ```sql  
    DECLARE @collection_set_id_1 int  
    SELECT @collection_set_id_1 = collection_set_id FROM [msdb].[dbo].[syscollector_collection_sets]  
    WHERE name = N'Test Collection Set'; -- name of collection set  
    ```  
  
3.  <span data-ttu-id="98d0c-112">Declare el tipo de recopilador.</span><span class="sxs-lookup"><span data-stu-id="98d0c-112">Declare the collector type.</span></span> <span data-ttu-id="98d0c-113">El código siguiente es un ejemplo de cómo se declara el tipo de recopilador de consultas T-SQL genérico.</span><span class="sxs-lookup"><span data-stu-id="98d0c-113">The following code provides an example of how to declare the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid_1 uniqueidentifier  
    SELECT @collector_type_uid_1 = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
       WHERE name = N'Generic T-SQL Query Collector Type';  
    ```  
  
     <span data-ttu-id="98d0c-114">Puede ejecutar el código siguiente para obtener una lista de los tipos de recopilador instalados:</span><span class="sxs-lookup"><span data-stu-id="98d0c-114">You can run the following code to obtain a list of the installed collector types:</span></span>  
  
    ```sql  
    USE msdb  
    SELECT * from syscollector_collector_types  
    GO  
    ```  
  
4.  <span data-ttu-id="98d0c-115">Ejecute el procedimiento almacenado **sp_syscollector_create_collection_item** para crear el elemento de recopilación.</span><span class="sxs-lookup"><span data-stu-id="98d0c-115">Run the **sp_syscollector_create_collection_item** stored procedure to create the collection item.</span></span> <span data-ttu-id="98d0c-116">Debe declarar el esquema del elemento de recopilación para que se asigne al esquema que corresponde al tipo de recopilador deseado.</span><span class="sxs-lookup"><span data-stu-id="98d0c-116">You must declare the schema for the collection item so that it maps to the required schema for the desired collector type.</span></span> <span data-ttu-id="98d0c-117">En el ejemplo siguiente se usa el esquema de entrada de consultas T-SQL genérico.</span><span class="sxs-lookup"><span data-stu-id="98d0c-117">The following example uses the Generic T-SQL Query input schema.</span></span>  
  
    ```sql  
    DECLARE @collection_item_id int;  
    EXEC [msdb].[dbo].[sp_syscollector_create_collection_item]   
    @name=N'OS Wait Stats', --name of collection item  
    @parameters=N'  
    <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
     <Query>  
      <Value>select * from sys.dm_os_wait_stats</Value>  
      <OutputTable>os_wait_stats</OutputTable>  
    </Query>  
    </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 60,  
    @collection_set_id = @collection_set_id_1, --- Provides the collection set ID number  
    @collector_type_uid = @collector_type_uid_1 -- Provides the collector type UID  
    SELECT @collection_item_id     
    ```  
  
5.  <span data-ttu-id="98d0c-118">Antes de iniciar el conjunto de recopilación actualizado, ejecute la consulta siguiente para comprobar que se ha creado el nuevo elemento de recopilación:</span><span class="sxs-lookup"><span data-stu-id="98d0c-118">Before starting the updated collection set, run the following query to verify that the new collection item has been created:</span></span>  
  
    ```xaml  
    USE msdb  
    SELECT * from syscollector_collection_sets  
    SELECT * from syscollector_collection_items  
    GO  
    ```  
  
     <span data-ttu-id="98d0c-119">Los conjuntos de recopilación y sus elementos de recopilación se muestran en la pestaña **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="98d0c-119">The collection sets and their collection items are displayed in the **Results** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d0c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98d0c-120">See Also</span></span>  
 <span data-ttu-id="98d0c-121">[Crear un conjunto de recopilación personalizado que use el tipo de recopilador de consultas T-SQL genérico &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span><span class="sxs-lookup"><span data-stu-id="98d0c-121">[Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span></span>  
 [<span data-ttu-id="98d0c-122">Procedimientos almacenados del recopilador de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98d0c-122">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
