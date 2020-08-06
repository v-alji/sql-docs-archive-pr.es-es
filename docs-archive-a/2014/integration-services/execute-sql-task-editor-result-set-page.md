---
title: Editor de la tarea ejecutar SQL (página conjunto de resultados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.resultset.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: d27000c8-8d91-4e1c-b45e-bca9a3c12f6d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 027f3c77e84b47958e9fb6567acdb308c14eb1e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671117"
---
# <a name="execute-sql-task-editor-result-set-page"></a><span data-ttu-id="de36c-102">Editor de la tarea Ejecutar SQL (página Conjunto de resultados)</span><span class="sxs-lookup"><span data-stu-id="de36c-102">Execute SQL Task Editor (Result Set Page)</span></span>
  <span data-ttu-id="de36c-103">Utilice la página **Conjunto de resultados** del cuadro de diálogo **Editor de la tarea Ejecutar SQL** para asignar el resultado de la instrucción SQL a variables nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="de36c-103">Use the **Result Set** page of the **Execute SQL Task Editor** dialog to map the result of the SQL statement to new or existing variables.</span></span> <span data-ttu-id="de36c-104">Las opciones de este cuadro de diálogo están deshabilitadas si se define **Conjunto de resultados** de la página General como **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="de36c-104">The options in this dialog box are disabled if **ResultSet** on the General page is set to **None**.</span></span>  
  
 <span data-ttu-id="de36c-105">Para más información sobre esta tarea, vea [Tarea Ejecutar SQL](control-flow/execute-sql-task.md) y [Conjuntos de resultados en la tarea Ejecutar SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="de36c-105">For more information about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="de36c-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="de36c-106">Options</span></span>  
 <span data-ttu-id="de36c-107">**Nombre del resultado**</span><span class="sxs-lookup"><span data-stu-id="de36c-107">**Result Name**</span></span>  
 <span data-ttu-id="de36c-108">Después de hacer clic en **Agregar**y de agregar un conjunto de asignaciones de conjuntos de resultados, asigne un nombre al resultado.</span><span class="sxs-lookup"><span data-stu-id="de36c-108">After you have added a result set mapping set by clicking **Add**, provide a name for the result.</span></span> <span data-ttu-id="de36c-109">Deberá utilizar nombres de resultados específicos dependiendo del tipo de conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="de36c-109">Depending on the result set type, you must use specific result names.</span></span>  
  
 <span data-ttu-id="de36c-110">Si el tipo de conjunto de resultados es **Fila única**, puede utilizar el nombre de una columna devuelta por la consulta o el número que representa la posición de una columna en la lista de columnas de una de las columnas devueltas por la consulta.</span><span class="sxs-lookup"><span data-stu-id="de36c-110">If the result set type is **Single row**, you can use either the name of a column returned by the query or the number that represents the position of a column in the column list of a column returned by the query.</span></span>  
  
 <span data-ttu-id="de36c-111">Si el tipo de conjunto de resultados es **Conjunto de resultados completo** o **XML**, debe utilizar 0 como nombre del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="de36c-111">If the result set type is **Full result set** or **XML**, you must use 0 as the result set name.</span></span>  
  
 <span data-ttu-id="de36c-112">**Temas relacionados**: [Conjuntos de resultados en la tarea Ejecutar SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="de36c-112">**Related Topics**: [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="de36c-113">**Nombre de variable**</span><span class="sxs-lookup"><span data-stu-id="de36c-113">**Variable Name**</span></span>  
 <span data-ttu-id="de36c-114">Para asignar el conjunto de resultados a una variable, seleccione una variable o haga clic en \<**New variable...**> para agregar una variable nueva con el cuadro de diálogo **Agregar variable**.</span><span class="sxs-lookup"><span data-stu-id="de36c-114">Map the result set to a variable by selecting a variable or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="de36c-115">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="de36c-115">**Add**</span></span>  
 <span data-ttu-id="de36c-116">Haga clic para agregar una asignación de conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="de36c-116">Click to add a result set mapping.</span></span>  
  
 <span data-ttu-id="de36c-117">**Remove**</span><span class="sxs-lookup"><span data-stu-id="de36c-117">**Remove**</span></span>  
 <span data-ttu-id="de36c-118">Seleccione de la lista una asignación de conjuntos de resultados y, después, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="de36c-118">Select a result set mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de36c-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de36c-119">See Also</span></span>  
 <span data-ttu-id="de36c-120">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="de36c-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="de36c-121">[Editor de la tarea ejecutar SQL &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="de36c-121">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="de36c-122">[&#40;página de asignación de parámetros del editor de la tarea ejecutar SQL&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span><span class="sxs-lookup"><span data-stu-id="de36c-122">[Execute SQL Task Editor &#40;Parameter Mapping Page&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span></span>  
 [<span data-ttu-id="de36c-123">Referencia de Transact-SQL &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="de36c-123">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
