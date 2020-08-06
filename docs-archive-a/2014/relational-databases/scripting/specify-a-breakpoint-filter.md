---
title: Especificar un filtro del punto de interrupción
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint filter
ms.assetid: 7bf1dddd-7b0b-4c47-8a7b-28a5569b4fa5
author: rothja
ms.author: jroth
ms.openlocfilehash: 9fc320397da1bddc0d28191c359c4d311b23e044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673615"
---
# <a name="specify-a-breakpoint-filter"></a><span data-ttu-id="55790-102">Especificar un filtro del punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="55790-102">Specify a Breakpoint Filter</span></span>
  <span data-ttu-id="55790-103">Un filtro del punto de interrupción limita el punto de interrupción de manera que solo actúe en los equipos, procesos del sistema operativo y subprocesos especificados.</span><span class="sxs-lookup"><span data-stu-id="55790-103">A breakpoint filter limits the breakpoint to acting only on specified computers, operating system processes, and threads.</span></span> <span data-ttu-id="55790-104">Los filtros del punto de interrupción suelen utilizarse al depurar aplicaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="55790-104">Breakpoint filters are typically used when debugging parallel applications.</span></span>  
  
##  <a name="filter-considerations"></a><a name="BKMK_ActionConsiderations"></a> <span data-ttu-id="55790-105">Consideraciones de filtrado</span><span class="sxs-lookup"><span data-stu-id="55790-105">Filter Considerations</span></span>  
 <span data-ttu-id="55790-106">Los filtros del punto de interrupción no suelen utilizarse con el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] porque los scripts y los procedimientos almacenados de [!INCLUDE[tsql](../../includes/tsql-md.md)] no son aplicaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="55790-106">Breakpoint filters are not typically used with the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger because [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and stored procedures are not parallel applications.</span></span>  
  
#### <a name="to-specify-a-breakpoint-filter"></a><span data-ttu-id="55790-107">Para especificar un filtro del punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="55790-107">To Specify a Breakpoint Filter</span></span>  
  
1.  <span data-ttu-id="55790-108">En la ventana del editor, haga clic con el botón derecho en el glifo de punto de interrupción y, después, haga clic en **Filtrar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="55790-108">In the editor window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="55790-109">O bien</span><span class="sxs-lookup"><span data-stu-id="55790-109">-or-</span></span>  
  
     <span data-ttu-id="55790-110">En la ventana **Puntos de interrupción** , haga clic con el botón derecho en el glifo de punto de interrupción y, después, haga clic en **Filtrar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="55790-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="55790-111">En el cuadro de diálogo **Filtros del punto de interrupción** , utilice el cuadro **Filtro** para especificar los equipos por nombre, o los procesos del sistema operativo y los subprocesos por nombre o por número de identificación:</span><span class="sxs-lookup"><span data-stu-id="55790-111">In the **Breakpoint Filters** dialog box, use the **Filter** box to specify computers by name, or operating system processes and threads by either name or ID number:</span></span>  
  
    -   <span data-ttu-id="55790-112">`MachineName` es el equipo que ejecuta la instancia del Motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="55790-112">`MachineName` is the computer running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="55790-113">`ProcessID` y `ProcessName` son el proceso del sistema operativo que ejecuta la instancia del Motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="55790-113">`ProcessID`, and `ProcessName` are the operating system process running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="55790-114">`ThreadID` y `ThreadName` son el subproceso del sistema operativo que ejecuta el lote, procedimiento o función de [!INCLUDE[tsql](../../includes/tsql-md.md)] en la instancia del Motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="55790-114">`ThreadID` and `ThreadName` are the operating system thread running the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, procedure, or function in the instance of the Database Engine.</span></span>  
  
3.  <span data-ttu-id="55790-115">Haga clic en **Aceptar** para implementar los cambios o en **Cancelar** para salir sin aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="55790-115">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55790-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55790-116">See Also</span></span>  
 <span data-ttu-id="55790-117">[Especificar una condición de punto de interrupción](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="55790-117">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 <span data-ttu-id="55790-118">[Especificar un número de llamadas](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="55790-118">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="55790-119">Especificar una acción del punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="55790-119">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
