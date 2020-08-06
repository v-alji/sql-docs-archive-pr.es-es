---
title: Tarea Volver a generar índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rebuildindextask.f1
helpviewer_keywords:
- rebuilding indexes
- indexes [Integration Services]
- Rebuild Index task
ms.assetid: 021884dd-e72d-47b2-99e8-b741410509c3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33bbe25bc8c47f4f749f95dbb7096c3a76c25297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674254"
---
# <a name="rebuild-index-task"></a><span data-ttu-id="c63c4-102">Volver a generar índice, tarea</span><span class="sxs-lookup"><span data-stu-id="c63c4-102">Rebuild Index Task</span></span>
  <span data-ttu-id="c63c4-103">La tarea Volver a generar índice vuelve a generar los índices de las tablas y vistas de bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c63c4-103">The Rebuild Index task rebuilds indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="c63c4-104">Para más información sobre la administración de índices, vea [Reorganizar y volver a generar índices](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c63c4-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="c63c4-105">Un paquete puede usar la tarea Volver a generar índice para volver a generar los índices de una base de datos individual o de varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c63c4-105">By using the Rebuild Index task, a package can rebuild indexes in a single database or multiple databases.</span></span> <span data-ttu-id="c63c4-106">Si la tarea solo vuelve a generar los índices de una base de datos individual, puede elegir las vistas y las tablas cuyos índices vuelve a generar la tarea.</span><span class="sxs-lookup"><span data-stu-id="c63c4-106">If the task rebuilds only the indexes in a single database, you can choose the views and tables whose indexes the task rebuilds.</span></span>  
  
 <span data-ttu-id="c63c4-107">Esta tarea encapsula una instrucción ALTER INDEX REBUILD con las siguientes opciones para volver a generar el índice:</span><span class="sxs-lookup"><span data-stu-id="c63c4-107">This task encapsulates an ALTER INDEX REBUILD statement with the following index rebuild options:</span></span>  
  
-   <span data-ttu-id="c63c4-108">Especifique un porcentaje de FILLFACTOR o use el valor original de FILLFACTOR.</span><span class="sxs-lookup"><span data-stu-id="c63c4-108">Specify a FILLFACTOR percentage or use the original FILLFACTOR amount.</span></span>  
  
-   <span data-ttu-id="c63c4-109">Establezca PAD_INDEX = ON para asignar el espacio disponible especificado por FILLFACTOR a las páginas de nivel intermedio del índice.</span><span class="sxs-lookup"><span data-stu-id="c63c4-109">Set PAD_INDEX = ON to allocate the free space specified by FILLFACTOR to the intermediate-level pages of the index.</span></span>  
  
-   <span data-ttu-id="c63c4-110">Establezca SORT_IN_TEMPDB = ON para almacenar el resultado intermedio de ordenación utilizado para volver a generar el índice en tempdb.</span><span class="sxs-lookup"><span data-stu-id="c63c4-110">Set SORT_IN_TEMPDB = ON to store the intermediate sort result used to rebuild the index in tempdb.</span></span> <span data-ttu-id="c63c4-111">Si se establece el resultado intermedio de ordenación en OFF, el resultado se almacena en la misma base de datos que el índice.</span><span class="sxs-lookup"><span data-stu-id="c63c4-111">When the intermediate sort result is set to OFF, the result is stored in the same database as the index.</span></span>  
  
-   <span data-ttu-id="c63c4-112">Establezca IGNORE_DUP_KEY = ON para permitir una operación de inserción de múltiples filas con registros que infringen restricciones UNIQUE para insertar los registros que no infringen las restricciones UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="c63c4-112">Set IGNORE_DUP_KEY = ON to allow a multirow insert operation that includes records that violate unique constraints to insert the records that do not violate the unique constraints.</span></span>  
  
-   <span data-ttu-id="c63c4-113">Establezca ONLINE = ON para que no se mantengan los bloqueos de tabla, de forma que las consultas o actualizaciones de la tabla subyacente puedan continuar mientras se vuelve a generar el índice.</span><span class="sxs-lookup"><span data-stu-id="c63c4-113">Set ONLINE = ON to not hold table locks so that queries or updates to the underlying table can proceed during re-indexing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c63c4-114">Las operaciones de índices en línea no están disponibles en todas las ediciones de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c63c4-114">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c63c4-115">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="c63c4-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="c63c4-116">Para más información sobre la instrucción ALTER INDEX y las opciones para volver a generar el índice, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c63c4-116">For more information about the ALTER INDEX statement and index rebuild options, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c63c4-117">El tiempo que tarda la tarea en crear la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] que va a ejecutar es proporcional al número de índices que se vuelven a generar.</span><span class="sxs-lookup"><span data-stu-id="c63c4-117">The time the task takes to create the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that the task runs is proportionate to the number of indexes the task rebuilds.</span></span> <span data-ttu-id="c63c4-118">Si se configura la tarea para volver a generar los índices de todas las tablas y vistas de una base de datos que contiene una gran cantidad de índices, o para volver a generar los índices de varias bases de datos, la tarea puede tardar mucho tiempo en generar la instrucción Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c63c4-118">If the task is configured to rebuild indexes in all the tables and views in a database with a large number of indexes, or to rebuild indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-rebuild-index-task"></a><span data-ttu-id="c63c4-119">Configuración de la tarea Volver a generar índice</span><span class="sxs-lookup"><span data-stu-id="c63c4-119">Configuration of the Rebuild Index Task</span></span>  
 <span data-ttu-id="c63c4-120">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c63c4-120">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="c63c4-121">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c63c4-121">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="c63c4-122">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="c63c4-122">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
 [<span data-ttu-id="c63c4-123">Tarea Volver a generar índice &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="c63c4-123">Rebuild Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/rebuild-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="c63c4-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c63c4-124">Related Tasks</span></span>  
 <span data-ttu-id="c63c4-125">Para más información sobre cómo establecer estas propiedades en el Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , vea [Establecer las propiedades de tareas o contenedores](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="c63c4-125">For more about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63c4-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c63c4-126">See Also</span></span>  
 <span data-ttu-id="c63c4-127">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="c63c4-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="c63c4-128">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="c63c4-128">Control Flow</span></span>](control-flow.md)  
  
  
