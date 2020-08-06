---
title: Tarea Reorganizar índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.reorganizeindextask.f1
helpviewer_keywords:
- reorganizing indexes
- Reorganize Index task [Integration Services]
- indexes [Integration Services]
ms.assetid: 9ed87861-e5c3-4fcd-8760-d112f4c0af0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3f910391bd3a5a35770bb677bc17c91a00ace457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674252"
---
# <a name="reorganize-index-task"></a><span data-ttu-id="1abf3-102">Tarea Reorganizar índice</span><span class="sxs-lookup"><span data-stu-id="1abf3-102">Reorganize Index Task</span></span>
  <span data-ttu-id="1abf3-103">La tarea Reorganizar índice reorganiza los índices de las tablas y vistas de bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1abf3-103">The Reorganize Index task reorganizes indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="1abf3-104">Para más información sobre la administración de índices, vea [Reorganizar y volver a generar índices](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="1abf3-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="1abf3-105">Un paquete puede usar la tarea Reorganizar índice para reorganizar los índices de una base de datos individual o de varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1abf3-105">By using the Reorganize Index task, a package can reorganize indexes in a single database or multiple databases.</span></span> <span data-ttu-id="1abf3-106">Si la tarea solo reorganiza los índices de una base de datos individual, puede elegir las vistas o las tablas cuyos índices reorganiza la tarea.</span><span class="sxs-lookup"><span data-stu-id="1abf3-106">If the task reorganizes only the indexes in a single database, you can choose the views or the tables whose indexes the task reorganizes.</span></span> <span data-ttu-id="1abf3-107">La tarea Reorganizar índice también incluye la opción de compactar datos de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="1abf3-107">The Reorganize Index task also includes an option to compact large object data.</span></span> <span data-ttu-id="1abf3-108">Los datos de objetos grandes son datos de tipo `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` o `xml`.</span><span class="sxs-lookup"><span data-stu-id="1abf3-108">Large object data is data with the `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, or `xml` data type.</span></span> <span data-ttu-id="1abf3-109">Para obtener más información, vea [Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1abf3-109">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="1abf3-110">La tarea Reorganizar índice encapsula la instrucción ALTER INDEX de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1abf3-110">The Reorganize Index task encapsulates the Transact-SQL ALTER INDEX statement.</span></span> <span data-ttu-id="1abf3-111">Si elige compactar datos de objetos grandes, la instrucción utiliza la cláusula REORGANIZE WITH (LOB_COMPACTION = ON); en caso contrario, se establece LOB_COMPACTION en OFF.</span><span class="sxs-lookup"><span data-stu-id="1abf3-111">If you choose to compact large object data, the statement uses the REORGANIZE WITH (LOB_COMPACTION = ON) clause, otherwise LOB_COMPACTION is set to OFF.</span></span> <span data-ttu-id="1abf3-112">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1abf3-112">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1abf3-113">El tiempo que tarda la tarea en crear la instrucción Transact-SQL que va a ejecutar es proporcional al número de índices reorganizados por la tarea.</span><span class="sxs-lookup"><span data-stu-id="1abf3-113">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of indexes the task reorganizes.</span></span> <span data-ttu-id="1abf3-114">Si se configura la tarea para reorganizar los índices de todas las tablas y vistas de una base de datos que contiene una gran cantidad de índices, o para reorganizar índices de varias bases de datos, la tarea puede tardar mucho tiempo en generar la instrucción Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1abf3-114">If the task is configured to reorganize indexes in all the tables and views in a database that holds a large number of indexes, or to reorganize indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-reorganize-index-task"></a><span data-ttu-id="1abf3-115">Configuración de la tarea Reorganizar índice</span><span class="sxs-lookup"><span data-stu-id="1abf3-115">Configuration of the Reorganize Index Task</span></span>  
 <span data-ttu-id="1abf3-116">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1abf3-116">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="1abf3-117">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1abf3-117">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="1abf3-118">Para obtener información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="1abf3-118">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="1abf3-119">Tarea Reorganizar índice &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="1abf3-119">Reorganize Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/reorganize-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="1abf3-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1abf3-120">Related Tasks</span></span>  
 <span data-ttu-id="1abf3-121">Para más información sobre cómo establecer estas propiedades en el Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , vea [Establecer las propiedades de tareas o contenedores](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="1abf3-121">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abf3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1abf3-122">See Also</span></span>  
 <span data-ttu-id="1abf3-123">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="1abf3-123">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="1abf3-124">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="1abf3-124">Control Flow</span></span>](control-flow.md)  
  
  
