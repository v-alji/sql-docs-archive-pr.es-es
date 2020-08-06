---
title: Tarea Actualizar estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.updatestatisticstask.f1
helpviewer_keywords:
- updating statistics
- Update Statistics task [Integration Services]
ms.assetid: 0247483b-f092-4511-8fa8-3610108bd1bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1507ada1e4fa087901383930fce4996c191fb553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662177"
---
# <a name="update-statistics-task"></a><span data-ttu-id="8dba1-102">Tarea Actualizar estadísticas</span><span class="sxs-lookup"><span data-stu-id="8dba1-102">Update Statistics Task</span></span>
  <span data-ttu-id="8dba1-103">La tarea Actualizar estadísticas actualiza información sobre la distribución de valores clave para uno o varios grupos de estadísticas (colecciones) de la tabla o vista indizada especificada.</span><span class="sxs-lookup"><span data-stu-id="8dba1-103">The Update Statistics task updates information about the distribution of key values for one or more statistics groups (collections) in the specified table or indexed view.</span></span> <span data-ttu-id="8dba1-104">Para más información, consulte [Estadísticas](../../relational-databases/statistics/statistics.md).</span><span class="sxs-lookup"><span data-stu-id="8dba1-104">For more information, see [Statistics](../../relational-databases/statistics/statistics.md).</span></span>  
  
 <span data-ttu-id="8dba1-105">Si utiliza la tarea Actualizar estadísticas, un paquete puede actualizar estadísticas para una o varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="8dba1-105">By using the Update Statistics task, a package can update statistics for a single database or multiple databases.</span></span> <span data-ttu-id="8dba1-106">Si la tarea solo actualiza las estadísticas de una base de datos individual, puede elegir las vistas o las tablas para las que se van a actualizar las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="8dba1-106">If the task updates only the statistics in a single database, you can choose the views or the tables whose statistics the task updates.</span></span> <span data-ttu-id="8dba1-107">Puede configurar la actualización para que actualice todas las estadísticas, solo estadísticas de columnas o solo estadísticas de índices.</span><span class="sxs-lookup"><span data-stu-id="8dba1-107">You can configure the update to update all statistics, column statistics only, or index statistics only.</span></span>  
  
 <span data-ttu-id="8dba1-108">Esta tarea encapsula una instrucción UPDATE STATISTICS con los siguientes argumentos y cláusulas:</span><span class="sxs-lookup"><span data-stu-id="8dba1-108">This task encapsulates an UPDATE STATISTICS statement, including the following arguments and clauses:</span></span>  
  
-   <span data-ttu-id="8dba1-109">El argumento *table_name* o *view_name* .</span><span class="sxs-lookup"><span data-stu-id="8dba1-109">The *table_name* or *view_name* argument.</span></span>  
  
-   <span data-ttu-id="8dba1-110">Si se aplica la actualización a todas las estadísticas, la cláusula WITH ALL está implícita.</span><span class="sxs-lookup"><span data-stu-id="8dba1-110">If the update applies to all statistics, the WITH ALL clause is implied.</span></span>  
  
-   <span data-ttu-id="8dba1-111">Si la actualización solo se aplica a columnas, se incluye la cláusula WITH COLUMN.</span><span class="sxs-lookup"><span data-stu-id="8dba1-111">If the update applies only to columns, the WITH COLUMN clause is included.</span></span>  
  
-   <span data-ttu-id="8dba1-112">Si la actualización solo se aplica a índices, se incluye la cláusula WITH INDEX.</span><span class="sxs-lookup"><span data-stu-id="8dba1-112">If the update applies only to indexes, the WITH INDEX clause is included.</span></span>  
  
 <span data-ttu-id="8dba1-113">Si la tarea Actualizar estadísticas actualiza las estadísticas en varias bases de datos, la tarea ejecuta múltiples instrucciones UPDATE STATISTICS, una para cada tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="8dba1-113">If the Update Statistics task updates statistics in multiple databases, the task runs multiple UPDATE STATISTICS statements, one for each table or view.</span></span> <span data-ttu-id="8dba1-114">Todas las instancias de UPDATE STATISTICS usan la misma cláusula, pero con distintos valores de *table_name* o *view_name* .</span><span class="sxs-lookup"><span data-stu-id="8dba1-114">All instances of UPDATE STATISTICS use the same clause, but different *table_name* or *view_name* values.</span></span> <span data-ttu-id="8dba1-115">Para más información, vea [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) y [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8dba1-115">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) and [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8dba1-116">El tiempo que tarda la tarea en crear la instrucción Transact-SQL que va a ejecutar es proporcional al número de estadísticas actualizadas por la tarea.</span><span class="sxs-lookup"><span data-stu-id="8dba1-116">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of statistics the task updates.</span></span> <span data-ttu-id="8dba1-117">Si se configura la tarea para actualizar estadísticas de todas las tablas y vistas de una base de datos que contiene una gran cantidad de índices, o para actualizar las estadísticas de varias bases de datos, la tarea puede tardar mucho tiempo en generar la instrucción Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8dba1-117">If the task is configured to update statistics in all the tables and views in a database with a large number of indexes, or to update statistics in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-update-statistics-task"></a><span data-ttu-id="8dba1-118">Configuración de la tarea Actualizar estadísticas</span><span class="sxs-lookup"><span data-stu-id="8dba1-118">Configuration of the Update Statistics Task</span></span>  
 <span data-ttu-id="8dba1-119">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8dba1-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="8dba1-120">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8dba1-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="8dba1-121">Para obtener información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="8dba1-121">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="8dba1-122">Tarea Actualizar estadísticas &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="8dba1-122">Update Statistics Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/update-statistics-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="8dba1-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8dba1-123">Related Tasks</span></span>  
 <span data-ttu-id="8dba1-124">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="8dba1-124">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="8dba1-125">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="8dba1-125">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="8dba1-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8dba1-126">See Also</span></span>  
 <span data-ttu-id="8dba1-127">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="8dba1-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="8dba1-128">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="8dba1-128">Control Flow</span></span>](control-flow.md)  
  
  
