---
title: Ventana de pila de llamadas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Call Stack Window [Transact-SQL]
ms.assetid: ddb0b19c-87cd-4883-bcb8-ec09ffb30369
author: rothja
ms.author: jroth
ms.openlocfilehash: b4b72e484ade696be81ebac8ea4eed9be295edf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676449"
---
# <a name="call-stack-window"></a><span data-ttu-id="85de8-102">Ventana de pila de llamadas</span><span class="sxs-lookup"><span data-stu-id="85de8-102">Call Stack Window</span></span>
  <span data-ttu-id="85de8-103">La ventana **Pila de llamadas** muestra los módulos de la pila de llamadas y los tipos de datos y valores de los parámetros que se pasen a los módulos.</span><span class="sxs-lookup"><span data-stu-id="85de8-103">The **Call Stack** window displays the modules on the call stack, and the data types and values of any parameters that are passed to the modules.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="85de8-104">incluyen procedimientos almacenados, funciones y desencadenadores).</span><span class="sxs-lookup"><span data-stu-id="85de8-104">modules include stored procedures, functions, and triggers.</span></span> <span data-ttu-id="85de8-105">Para mostrar la pila de llamadas, debe estar en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="85de8-105">To display the call stack, you must be in debug mode.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="85de8-106">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="85de8-106">Task List</span></span>  
 <span data-ttu-id="85de8-107">**Para tener acceso a la ventana Pila de llamadas**</span><span class="sxs-lookup"><span data-stu-id="85de8-107">**To access the Call Stack window**</span></span>  
  
-   <span data-ttu-id="85de8-108">En el menú **Depurar** , haga clic en **Ventanas**y, a continuación, en **Pila de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="85de8-108">On the **Debug** menu, click **Windows**, and then click **Call Stack**.</span></span>  
  
 <span data-ttu-id="85de8-109">**Para cambiar el marco de Pila de llamadas actual**</span><span class="sxs-lookup"><span data-stu-id="85de8-109">**To change the current Call Stack frame**</span></span>  
  
 <span data-ttu-id="85de8-110">Puede utilizar cualquiera de los procedimientos siguientes para convertir un marco de pila en el marco actual:</span><span class="sxs-lookup"><span data-stu-id="85de8-110">You can use either of the following procedures to make a stack frame the current frame:</span></span>  
  
-   <span data-ttu-id="85de8-111">Haga clic con el botón derecho en el marco de pila y, después, haga clic en **Cambiar a marco**.</span><span class="sxs-lookup"><span data-stu-id="85de8-111">Right-click the stack frame, and then click **Switch To Frame**.</span></span>  
  
-   <span data-ttu-id="85de8-112">Haga doble clic en el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="85de8-112">Double-click the stack frame.</span></span>  
  
 <span data-ttu-id="85de8-113">**Para ver el origen de un marco distinto del marco actual**</span><span class="sxs-lookup"><span data-stu-id="85de8-113">**To view the source of a frame other than the current frame**</span></span>  
  
-   <span data-ttu-id="85de8-114">Haga clic con el botón derecho en el marco de pila y, después, haga clic en **Ir al código fuente**.</span><span class="sxs-lookup"><span data-stu-id="85de8-114">Right-click the stack frame, and then click **Go To Source Code**.</span></span>  
  
## <a name="stack-frames"></a><span data-ttu-id="85de8-115">Marcos de pila</span><span class="sxs-lookup"><span data-stu-id="85de8-115">Stack Frames</span></span>  
 <span data-ttu-id="85de8-116">Cada fila de la ventana **Pila de llamadas** se conoce como marco de pila y representa o bien una llamada de un archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] a un módulo o bien una llamada de un módulo a otro.</span><span class="sxs-lookup"><span data-stu-id="85de8-116">Each row in the **Call Stack** window is called a stack frame and represents either a call from a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file to a module or a call from one module to another.</span></span> <span data-ttu-id="85de8-117">El marco de pila inferior de la pantalla indica la línea de la ventana del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que realizó la primera llamada en la pila.</span><span class="sxs-lookup"><span data-stu-id="85de8-117">The bottom stack frame in the display indicates the line in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window that made the first call into the stack.</span></span> <span data-ttu-id="85de8-118">La fila superior indica la línea en la que el depurador pausó la ejecución y se identifica mediante una flecha amarilla en el margen izquierdo de la ventana.</span><span class="sxs-lookup"><span data-stu-id="85de8-118">The top row indicates the line on which the debugger paused execution, and is identified by a yellow arrow in the left margin of the window.</span></span> <span data-ttu-id="85de8-119">Cada fila intermedia indica el módulo y el número de línea del código fuente que llamó al marco de pila superior siguiente.</span><span class="sxs-lookup"><span data-stu-id="85de8-119">Each intermediate row indicates the module and the line number of the source code that called the next higher stack frame.</span></span>  
  
 <span data-ttu-id="85de8-120">Todas las expresiones de las ventanas **Variables locales**, **Inspección**e **Inspección rápida** se evalúan según el marco de pila actual.</span><span class="sxs-lookup"><span data-stu-id="85de8-120">All expressions in the **Locals**, **Watch**, and **QuickWatch** windows are evaluated based on the current stack frame.</span></span> <span data-ttu-id="85de8-121">La ventana del Editor de consultas muestra el código para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="85de8-121">The Query Editor window displays the code for the current frame.</span></span> <span data-ttu-id="85de8-122">De forma predeterminada, este marco es el marco superior de la pila, en el que el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] detuvo la ejecución.</span><span class="sxs-lookup"><span data-stu-id="85de8-122">By default, the current stack frame is the frame in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger paused execution.</span></span> <span data-ttu-id="85de8-123">Al cambiar el marco de pila actual a otro marco, las expresiones en las ventanas **Variables locales**, **Inspección**e **Inspección rápida** se vuelven a evaluar en el contexto del nuevo marco y el código fuente del nuevo marco se muestra en la ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="85de8-123">When you change the current stack frame to another frame, the expressions in the **Locals**, **Watch**, and **QuickWatch** windows are reevaluated in the context of the new frame, and the source code of the new frame is displayed in the Query Editor window.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="85de8-124">Columnas</span><span class="sxs-lookup"><span data-stu-id="85de8-124">Columns</span></span>  
 <span data-ttu-id="85de8-125">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="85de8-125">**Name**</span></span>  
 <span data-ttu-id="85de8-126">Muestra información sobre un módulo en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="85de8-126">Displays information about a module on the call stack.</span></span>  
  
 <span data-ttu-id="85de8-127">En la fila inferior de la pila de llamadas, **Nombre** muestra la ventana de código fuente del Editor de consultas y el número de línea de la primera llamada en la pila.</span><span class="sxs-lookup"><span data-stu-id="85de8-127">For the bottom row in the call stack, **Name** lists the Query Editor source window and line number of the first call into the stack.</span></span> <span data-ttu-id="85de8-128">Para las otras filas, **Nombre** tiene el formato **módulo (instancia.baseDeDatos) (listaDeParámetros) númeroDeLínea**.</span><span class="sxs-lookup"><span data-stu-id="85de8-128">For the other rows, **Name** has the format **Module(Instance.Database)(ParmList) LineNumber**.</span></span>  
  
 <span data-ttu-id="85de8-129">**módulo**</span><span class="sxs-lookup"><span data-stu-id="85de8-129">**Module**</span></span>  
 <span data-ttu-id="85de8-130">Es el nombre del procedimiento almacenado o función que llamó al marco siguiente.</span><span class="sxs-lookup"><span data-stu-id="85de8-130">Is the name of the stored procedure, function, or stored procedure that called to the next frame.</span></span>  
  
 <span data-ttu-id="85de8-131">**instancia.baseDeDatos**</span><span class="sxs-lookup"><span data-stu-id="85de8-131">**Instance.Database**</span></span>  
 <span data-ttu-id="85de8-132">Es la instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y la base de datos que contiene el módulo.</span><span class="sxs-lookup"><span data-stu-id="85de8-132">Is the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the database that is holding the module.</span></span>  
  
 <span data-ttu-id="85de8-133">**listaDeParámetros**</span><span class="sxs-lookup"><span data-stu-id="85de8-133">**ParmList**</span></span>  
 <span data-ttu-id="85de8-134">Indica el tipo de datos, nombre y valor de cada parámetro que se pasa durante la llamada al módulo.</span><span class="sxs-lookup"><span data-stu-id="85de8-134">Indicates the data type, name, and value for each parameter that is passed in during the call to the module.</span></span>  
  
 <span data-ttu-id="85de8-135">**LineNumber**</span><span class="sxs-lookup"><span data-stu-id="85de8-135">**LineNumber**</span></span>  
 <span data-ttu-id="85de8-136">Para todas las filas excepto la fila superior, **númeroDeLínea** indica qué línea en el módulo llamó al marco.</span><span class="sxs-lookup"><span data-stu-id="85de8-136">For all rows except the top row, **LineNumber** indicates which line in the module called to the frame.</span></span> <span data-ttu-id="85de8-137">Para la fila superior, **númeroDeLínea** indica la línea en la que actualmente se centra el depurador.</span><span class="sxs-lookup"><span data-stu-id="85de8-137">For the top row, **LineNumber** indicates the line on which the debugger is currently focused.</span></span>  
  
 <span data-ttu-id="85de8-138">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="85de8-138">**Language**</span></span>  
 <span data-ttu-id="85de8-139">Muestra **Transact-SQL** para [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85de8-139">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85de8-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85de8-140">See Also</span></span>  
 <span data-ttu-id="85de8-141">[Depurador de Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="85de8-141">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="85de8-142">[Información del depurador de Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="85de8-142">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 [<span data-ttu-id="85de8-143">Avanzar paso a paso por el código Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="85de8-143">Step Through Transact-SQL Code</span></span>](step-through-transact-sql-code.md)  
