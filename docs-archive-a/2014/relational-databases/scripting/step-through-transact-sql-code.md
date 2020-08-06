---
title: Avanzar paso a paso por el código Transact-SQL
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, debugging code
- Transact-SQL debugger, step over
- Transact-SQL debugger, step out
- Transact-SQL debugger, step into
ms.assetid: e09079b8-c4c9-42b4-821b-4ce81a98a086
author: rothja
ms.author: jroth
ms.openlocfilehash: 48cb307130c65729640864a26bdf1dfaf344b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675797"
---
# <a name="step-through-transact-sql-code"></a><span data-ttu-id="b9754-102">Avanzar paso a paso por el código Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9754-102">Step Through Transact-SQL Code</span></span>
  <span data-ttu-id="b9754-103">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] permite controlar las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que se ejecutan en una ventana del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9754-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger enables you to control which [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are run in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="b9754-104">Puede detener el depurador en instrucciones individuales y, a continuación, ver el estado de los elementos de código en ese punto.</span><span class="sxs-lookup"><span data-stu-id="b9754-104">You can pause the debugger on individual statements and then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="b9754-105">Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="b9754-105">Breakpoints</span></span>  
 <span data-ttu-id="b9754-106">Un punto de interrupción indica al depurador que detenga la ejecución en una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] específica.</span><span class="sxs-lookup"><span data-stu-id="b9754-106">A breakpoint signals the debugger to pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="b9754-107">Para obtener más información sobre los puntos de interrupción, vea Utilizar puntos de interrupción de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b9754-107">For more information about breakpoints, see Using Transact-SQL Breakpoints.</span></span>  
  
## <a name="controlling-statement-execution"></a><span data-ttu-id="b9754-108">Controlar la ejecución de instrucciones</span><span class="sxs-lookup"><span data-stu-id="b9754-108">Controlling Statement Execution</span></span>  
 <span data-ttu-id="b9754-109">En el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] , puede especificar las siguientes opciones para su ejecución desde la instrucción actual del código [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="b9754-109">In the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can specify the following options for executing from the current statement in [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
-   <span data-ttu-id="b9754-110">Ejecutar un proceso hasta el siguiente punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="b9754-110">Run to the next breakpoint.</span></span>  
  
-   <span data-ttu-id="b9754-111">Ir a la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="b9754-111">Step into the next statement.</span></span>  
  
     <span data-ttu-id="b9754-112">Si la siguiente instrucción invoca un procedimiento almacenado, función o desencadenador de [!INCLUDE[tsql](../../includes/tsql-md.md)] , el depurador muestra una nueva ventana del Editor de consultas que contiene el código del módulo.</span><span class="sxs-lookup"><span data-stu-id="b9754-112">If the next statement invokes a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, function, or trigger, the debugger displays a new Query Editor window that contains the code of the module.</span></span> <span data-ttu-id="b9754-113">La ventana está en el modo de depuración y la ejecución se detiene en la primera instrucción del módulo.</span><span class="sxs-lookup"><span data-stu-id="b9754-113">The window is in debug mode, and execution pauses on the first statement in the module.</span></span> <span data-ttu-id="b9754-114">Después puede desplazarse por el código del módulo, por ejemplo, estableciendo puntos de interrupción o recorriendo el código.</span><span class="sxs-lookup"><span data-stu-id="b9754-114">You can then move through the module code, for example, by setting breakpoints or stepping through the code.</span></span>  
  
-   <span data-ttu-id="b9754-115">Paso a paso por la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="b9754-115">Step over the next statement.</span></span>  
  
     <span data-ttu-id="b9754-116">Se ejecuta la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="b9754-116">The next statement is executed.</span></span> <span data-ttu-id="b9754-117">Sin embargo, si la instrucción invoca un procedimiento almacenado, una función o un desencadenador, el código del módulo se ejecuta hasta que termine y los resultados se devuelven al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="b9754-117">However, if the statement invokes a stored procedure, function, or trigger, the module code runs until it finishes, and the results are returned to the calling code.</span></span> <span data-ttu-id="b9754-118">Si está seguro de que no hay errores en un procedimiento almacenado, puede omitirlo.</span><span class="sxs-lookup"><span data-stu-id="b9754-118">If you are sure there are no errors in a stored procedure, you can step over it.</span></span> <span data-ttu-id="b9754-119">La ejecución se detiene en la instrucción que sigue a la llamada al procedimiento almacenado, a la función o al desencadenador.</span><span class="sxs-lookup"><span data-stu-id="b9754-119">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="b9754-120">Salir de un procedimiento almacenado, función o desencadenador.</span><span class="sxs-lookup"><span data-stu-id="b9754-120">Step out of a stored procedure, function, or trigger.</span></span>  
  
     <span data-ttu-id="b9754-121">La ejecución se detiene en la instrucción que sigue a la llamada al procedimiento almacenado, a la función o al desencadenador.</span><span class="sxs-lookup"><span data-stu-id="b9754-121">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="b9754-122">Ejecutar el proceso desde la ubicación actual hasta la ubicación actual del puntero e ignorar todos los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="b9754-122">Run from the current location to the current location of the pointer, and ignore all breakpoints.</span></span>  
  
 <span data-ttu-id="b9754-123">La tabla siguiente muestra las distintas formas en las que puede controlar la ejecución de las instrucciones del depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9754-123">The following table lists the various ways in which you can control how statements execute in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span>  
  
|<span data-ttu-id="b9754-124">Acción</span><span class="sxs-lookup"><span data-stu-id="b9754-124">Action</span></span>|<span data-ttu-id="b9754-125">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="b9754-125">Procedure</span></span>|  
|------------|---------------|  
|<span data-ttu-id="b9754-126">Ejecutar todas las instrucciones desde la instrucción actual hasta el siguiente punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="b9754-126">Run all statements from the current statement to the next breakpoint</span></span>|<span data-ttu-id="b9754-127">En el menú **Depurar**, haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="b9754-127">On the **Debug** menu, click **Continue**.</span></span><br /><br /> <span data-ttu-id="b9754-128">En la barra de herramientas **depurar** , haga clic en el botón **continuar** .</span><span class="sxs-lookup"><span data-stu-id="b9754-128">On the **Debug** toolbar, click the **Continue** button.</span></span>|  
|<span data-ttu-id="b9754-129">Ir a la siguiente instrucción o módulo</span><span class="sxs-lookup"><span data-stu-id="b9754-129">Step into the next statement or module</span></span>|<span data-ttu-id="b9754-130">En el menú **depurar** , haga clic en **paso a paso por instrucciones**.</span><span class="sxs-lookup"><span data-stu-id="b9754-130">On the **Debug** menu, click **Step Into**.</span></span><br /><br /> <span data-ttu-id="b9754-131">En la barra de herramientas **depurar** , haga clic en el botón **paso a paso por instrucciones** .</span><span class="sxs-lookup"><span data-stu-id="b9754-131">On the **Debug** toolbar, click the **Step Into** button.</span></span><br /><br /> <span data-ttu-id="b9754-132">Presione F11.</span><span class="sxs-lookup"><span data-stu-id="b9754-132">Press F11.</span></span>|  
|<span data-ttu-id="b9754-133">Paso a paso por la siguiente instrucción o módulo</span><span class="sxs-lookup"><span data-stu-id="b9754-133">Step over the next statement or module</span></span>|<span data-ttu-id="b9754-134">En el menú **Depurar**, haga clic en **Paso a paso por procedimientos**.</span><span class="sxs-lookup"><span data-stu-id="b9754-134">On the **Debug** menu, click **Step Over**.</span></span><br /><br /> <span data-ttu-id="b9754-135">En la barra de herramientas **depurar** , haga clic en el botón **paso a paso por procedimientos** .</span><span class="sxs-lookup"><span data-stu-id="b9754-135">On the **Debug** toolbar, click the **Step Over** button.</span></span><br /><br /> <span data-ttu-id="b9754-136">Presione F10.</span><span class="sxs-lookup"><span data-stu-id="b9754-136">Press F10.</span></span>|  
|<span data-ttu-id="b9754-137">Salir de un módulo</span><span class="sxs-lookup"><span data-stu-id="b9754-137">Step out of a module</span></span>|<span data-ttu-id="b9754-138">En el menú **depurar** , haga clic en **paso a paso para salir**.</span><span class="sxs-lookup"><span data-stu-id="b9754-138">On the **Debug** menu, click **Step Out**.</span></span><br /><br /> <span data-ttu-id="b9754-139">En la barra de herramientas **depurar** , haga clic en el botón **paso a paso para salir** .</span><span class="sxs-lookup"><span data-stu-id="b9754-139">On the **Debug** toolbar, click the **Step Out** button.</span></span><br /><br /> <span data-ttu-id="b9754-140">Presione MAYÚS+F11.</span><span class="sxs-lookup"><span data-stu-id="b9754-140">Press SHIFT+F11.</span></span>|  
|<span data-ttu-id="b9754-141">Ejecutar un proceso hasta la ubicación del cursor actual</span><span class="sxs-lookup"><span data-stu-id="b9754-141">Run to the current cursor location</span></span>|<span data-ttu-id="b9754-142">Haga clic con el botón derecho en la ventana del Editor de consultas y, después, haga clic en **Ejecutar hasta el cursor**.</span><span class="sxs-lookup"><span data-stu-id="b9754-142">Right-click in the Query Editor window, and then click **Run To Cursor**.</span></span><br /><br /> <span data-ttu-id="b9754-143">Presione CTRL+F10.</span><span class="sxs-lookup"><span data-stu-id="b9754-143">Press CTRL+F10.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9754-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9754-144">See Also</span></span>  
 [<span data-ttu-id="b9754-145">Ver información del depurador de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9754-145">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
