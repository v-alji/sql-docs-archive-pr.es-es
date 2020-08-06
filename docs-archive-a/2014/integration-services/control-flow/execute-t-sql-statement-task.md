---
title: Tarea Ejecutar instrucción T-SQL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executetsqlstatementtask.f1
helpviewer_keywords:
- Transact-SQL statements, SSIS
- statements [Integration Services]
- Execute T-SQL Statement task [Integration Services]
ms.assetid: 7e9086ca-d27e-46c0-bfad-d61333ebd55e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7ebc73ad843ac7fcf1dfbe7699ecd8ea53edcdad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744810"
---
# <a name="execute-t-sql-statement-task"></a><span data-ttu-id="088cc-102">Tarea Ejecutar instrucción T-SQL</span><span class="sxs-lookup"><span data-stu-id="088cc-102">Execute T-SQL Statement Task</span></span>
  <span data-ttu-id="088cc-103">La tarea Ejecutar instrucción T-SQL ejecuta instrucciones Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="088cc-103">The Execute T-SQL Statement task runs Transact-SQL statements.</span></span> <span data-ttu-id="088cc-104">Para más información, vea [Referencia de Transact-SQL &#40;motor de base de datos&#41;](/sql/t-sql/language-reference) y [Consultas de Integration Services &#40;SSIS&#41;](../integration-services-ssis-queries.md).</span><span class="sxs-lookup"><span data-stu-id="088cc-104">For more information, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference) and [Integration Services &#40;SSIS&#41; Queries](../integration-services-ssis-queries.md).</span></span>  
  
 <span data-ttu-id="088cc-105">Esta tarea es similar a la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="088cc-105">This task is similar to the Execute SQL task.</span></span> <span data-ttu-id="088cc-106">Sin embargo, la tarea Ejecutar instrucción T-SQL solo admite la versión Transact-SQL del lenguaje SQL, por lo que no se puede usar esta tarea para ejecutar instrucciones en servidores que usen otros dialectos del lenguaje SQL.</span><span class="sxs-lookup"><span data-stu-id="088cc-106">However, the Execute T-SQL Statement task supports only the Transact-SQL version of the SQL language and you cannot use this task to run statements on servers that use other dialects of the SQL language.</span></span> <span data-ttu-id="088cc-107">Si necesita ejecutar consultas con parámetros, guardar los resultados de la consulta en variables o usar expresiones de propiedades, debe usar la tarea Ejecutar SQL en lugar de la tarea Ejecutar instrucción T-SQL.</span><span class="sxs-lookup"><span data-stu-id="088cc-107">If you need to run parameterized queries, save the query results to variables, or use property expressions, you should use the Execute SQL task instead of the Execute T-SQL Statement task.</span></span> <span data-ttu-id="088cc-108">Para más información, consulte [Execute SQL Task](execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="088cc-108">For more information, see [Execute SQL Task](execute-sql-task.md).</span></span>  
  
## <a name="configuration-of-the-execute-t-sql-task"></a><span data-ttu-id="088cc-109">Configuración de la tarea Ejecutar T-SQL</span><span class="sxs-lookup"><span data-stu-id="088cc-109">Configuration of the Execute T-SQL Task</span></span>  
 <span data-ttu-id="088cc-110">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="088cc-110">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="088cc-111">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="088cc-111">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="088cc-112">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="088cc-112">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="088cc-113">Tarea Ejecutar instrucción T-SQL &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="088cc-113">Execute T-SQL Statement Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/execute-t-sql-statement-task-maintenance-plan.md)  
  
 <span data-ttu-id="088cc-114">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="088cc-114">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="088cc-115">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="088cc-115">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="088cc-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="088cc-116">See Also</span></span>  
 <span data-ttu-id="088cc-117">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="088cc-117">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="088cc-118">[Flujo de control](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="088cc-118">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="088cc-119">MERGE en paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="088cc-119">MERGE in Integration Services Packages</span></span>](merge-in-integration-services-packages.md)  
  
  
