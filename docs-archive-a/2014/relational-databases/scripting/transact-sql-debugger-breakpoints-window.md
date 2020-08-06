---
title: Ventana de puntos de interrupción
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Breakpoints Window [Transact-SQL]
ms.assetid: bad88d10-fdd5-4d3d-b5ea-a4f063847485
author: rothja
ms.author: jroth
ms.openlocfilehash: 077d501e581ed5baaac45cc6bbbb34e0040730e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675788"
---
# <a name="breakpoints-window"></a><span data-ttu-id="7cee3-102">Ventana de puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="7cee3-102">Breakpoints Window</span></span>
  <span data-ttu-id="7cee3-103">La ventana **Puntos de interrupción** muestra todos los puntos de interrupción que se establecen en el Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] actual.</span><span class="sxs-lookup"><span data-stu-id="7cee3-103">The **Breakpoints** window lists all the breakpoints that are set in the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="7cee3-104">Para administrar los puntos de interrupción, utilice la barra de herramientas de la ventana **Puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="7cee3-104">To manage the breakpoints, use the toolbar in the **Breakpoints** window.</span></span> <span data-ttu-id="7cee3-105">Los puntos de interrupción son las ubicaciones del código en las que la ejecución se pausa en modo de depuración para que se puedan ver los datos de depuración.</span><span class="sxs-lookup"><span data-stu-id="7cee3-105">Breakpoints are locations in the code where execution pauses in debug mode so that you can view debugging data.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="7cee3-106">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="7cee3-106">Task List</span></span>  
 <span data-ttu-id="7cee3-107">**Para tener acceso a la ventana Puntos de interrupción**</span><span class="sxs-lookup"><span data-stu-id="7cee3-107">**To access the Breakpoints window**</span></span>  
  
-   <span data-ttu-id="7cee3-108">En el menú **Depurar** , haga clic en **Ventanas**y, a continuación, haga clic en **Puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="7cee3-108">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
## <a name="breakpoints-window-columns"></a><span data-ttu-id="7cee3-109">Columnas de la ventana Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="7cee3-109">Breakpoints Window Columns</span></span>  
 <span data-ttu-id="7cee3-110">De forma predeterminada, la ventana **Puntos de interrupción** muestra las columnas siguientes.</span><span class="sxs-lookup"><span data-stu-id="7cee3-110">By default, the **Breakpoints** window lists the following columns.</span></span>  
  
 <span data-ttu-id="7cee3-111">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7cee3-111">**Name**</span></span>  
 <span data-ttu-id="7cee3-112">Muestra el nombre del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="7cee3-112">Displays the name of the breakpoint.</span></span> <span data-ttu-id="7cee3-113">El depurador proporciona los nombres para los puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="7cee3-113">Breakpoint names are provided by the debugger.</span></span> <span data-ttu-id="7cee3-114">Este nombre incluye el de la ventana Editor de consultas del motor de base de datos que contiene el punto de interrupción y el número de línea del Editor de consultas en el que está establecido.</span><span class="sxs-lookup"><span data-stu-id="7cee3-114">This name includes the name of Database Engine Query Editor window that contains the breakpoint, and the line number in the Query Editor on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="7cee3-115">**Condition**</span><span class="sxs-lookup"><span data-stu-id="7cee3-115">**Condition**</span></span>  
 <span data-ttu-id="7cee3-116">Muestra **(sin condición)** .</span><span class="sxs-lookup"><span data-stu-id="7cee3-116">Displays **(no condition)**.</span></span> <span data-ttu-id="7cee3-117">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] no permite establecer las condiciones de punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="7cee3-117">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint conditions.</span></span>  
  
 <span data-ttu-id="7cee3-118">**Número de llamadas**</span><span class="sxs-lookup"><span data-stu-id="7cee3-118">**Hit Count**</span></span>  
 <span data-ttu-id="7cee3-119">Muestra**interrumpir siempre**.</span><span class="sxs-lookup"><span data-stu-id="7cee3-119">Displays**breaks always**.</span></span>  
  
 <span data-ttu-id="7cee3-120">Puede agregar y quitar las columnas siguientes seleccionándolos en la lista **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="7cee3-120">You can add and remove the following columns by selecting them on the **Columns** list.</span></span>  
  
 <span data-ttu-id="7cee3-121">**Filter**</span><span class="sxs-lookup"><span data-stu-id="7cee3-121">**Filter**</span></span>  
 <span data-ttu-id="7cee3-122">Muestra **(ninguno)** .</span><span class="sxs-lookup"><span data-stu-id="7cee3-122">Displays **(none)**.</span></span> <span data-ttu-id="7cee3-123">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] no permite establecer los filtros de punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="7cee3-123">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint filters.</span></span>  
  
 <span data-ttu-id="7cee3-124">**Al visitar**</span><span class="sxs-lookup"><span data-stu-id="7cee3-124">**When Hit**</span></span>  
 <span data-ttu-id="7cee3-125">Muestra **Interrumpir**.</span><span class="sxs-lookup"><span data-stu-id="7cee3-125">Displays **Break**.</span></span>  
  
 <span data-ttu-id="7cee3-126">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="7cee3-126">**Language**</span></span>  
 <span data-ttu-id="7cee3-127">Muestra **Transact-SQL** para [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cee3-127">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7cee3-128">**Function**</span><span class="sxs-lookup"><span data-stu-id="7cee3-128">**Function**</span></span>  
 <span data-ttu-id="7cee3-129">Muestra el número de la línea en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="7cee3-129">Displays the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="7cee3-130">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="7cee3-130">**File**</span></span>  
 <span data-ttu-id="7cee3-131">Muestra el nombre del archivo de código fuente que contiene el punto de interrupción y el número de la línea en la que se establece.</span><span class="sxs-lookup"><span data-stu-id="7cee3-131">Displays the name of the source file that contains the breakpoint, and the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="7cee3-132">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="7cee3-132">**Address**</span></span>  
 <span data-ttu-id="7cee3-133">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] no admite esta característica.</span><span class="sxs-lookup"><span data-stu-id="7cee3-133">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="7cee3-134">**Proceso**</span><span class="sxs-lookup"><span data-stu-id="7cee3-134">**Process**</span></span>  
 <span data-ttu-id="7cee3-135">Muestra **[SQL]** para indicar que se trata de un proceso de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7cee3-135">Displays **[SQL]** to indicate that this is a [!INCLUDE[ssDE](../../includes/ssde-md.md)] process.</span></span> <span data-ttu-id="7cee3-136">A continuación aparece el nombre de la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en la que se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="7cee3-136">This is followed by the name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the code executes.</span></span>  
  
## <a name="breakpoints-window-toolbar"></a><span data-ttu-id="7cee3-137">Barra de herramientas de la ventana Puntos de interrupción</span><span class="sxs-lookup"><span data-stu-id="7cee3-137">Breakpoints Window Toolbar</span></span>  
 <span data-ttu-id="7cee3-138">Cuando la ventana del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] actual tiene puntos de interrupción activos, la ventana **Puntos de interrupción** muestra una barra de herramientas que se puede utilizar para administrarlos.</span><span class="sxs-lookup"><span data-stu-id="7cee3-138">When the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window has active breakpoints, the **Breakpoints** window displays a toolbar that can be used to manage the breakpoints.</span></span>  
  
 <span data-ttu-id="7cee3-139">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="7cee3-139">**Delete**</span></span>  
 <span data-ttu-id="7cee3-140">Elimina el punto de interrupción seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7cee3-140">Deletes the selected breakpoint.</span></span>  
  
 <span data-ttu-id="7cee3-141">**Eliminar todos los puntos de interrupción**</span><span class="sxs-lookup"><span data-stu-id="7cee3-141">**Delete All Breakpoints**</span></span>  
 <span data-ttu-id="7cee3-142">Elimina todos los puntos de interrupción que se muestran en la ventana **Puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="7cee3-142">Deletes all breakpoints that are displayed in the **Breakpoints** window.</span></span>  
  
 <span data-ttu-id="7cee3-143">**Deshabilitar todos los puntos de interrupción**</span><span class="sxs-lookup"><span data-stu-id="7cee3-143">**Disable All Breakpoints**</span></span>  
 <span data-ttu-id="7cee3-144">Deshabilita todos los puntos de interrupción para que ya no detengan la ejecución del código; sin embargo, permanecen.</span><span class="sxs-lookup"><span data-stu-id="7cee3-144">Disables all breakpoints so that they no longer stop code execution; however, the breakpoints remain.</span></span> <span data-ttu-id="7cee3-145">Cuando todos los puntos de interrupción están deshabilitados, este botón se convierte en **Habilitar todos los puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="7cee3-145">When all the breakpoints are disabled, this button becomes **Enable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="7cee3-146">**Habilitar todos los puntos de interrupción**</span><span class="sxs-lookup"><span data-stu-id="7cee3-146">**Enable All Breakpoints**</span></span>  
 <span data-ttu-id="7cee3-147">Habilita todos los puntos de interrupción para que detengan la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="7cee3-147">Enables all breakpoints so that they stop code execution.</span></span> <span data-ttu-id="7cee3-148">Cuando todos los puntos de interrupción están habilitados, este botón se convierte en **Deshabilitar todos los puntos de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="7cee3-148">When all breakpoints are enabled, this button becomes **Disable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="7cee3-149">**Ir a código fuente**</span><span class="sxs-lookup"><span data-stu-id="7cee3-149">**Go To Source Code**</span></span>  
 <span data-ttu-id="7cee3-150">Coloca el cursor en la línea del Editor de consultas que contiene el punto de interrupción seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7cee3-150">Positions the cursor on the line in the Query Editor that contains the selected breakpoint.</span></span>  
  
 <span data-ttu-id="7cee3-151">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="7cee3-151">**Columns**</span></span>  
 <span data-ttu-id="7cee3-152">Muestra todas las columnas que se pueden mostrar en la ventana **Puntos de interrupción** .</span><span class="sxs-lookup"><span data-stu-id="7cee3-152">Lists all the columns that can be displayed in the **Breakpoints** window.</span></span> <span data-ttu-id="7cee3-153">Una casilla indica las columnas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="7cee3-153">A check box indicates the columns that are displayed.</span></span> <span data-ttu-id="7cee3-154">Para agregar o quitar una columna en la ventana **Puntos de interrupción** , seleccione la columna en la lista.</span><span class="sxs-lookup"><span data-stu-id="7cee3-154">To add or remove a column in the **Breakpoints** window, select the column on the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cee3-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7cee3-155">See Also</span></span>  
 [<span data-ttu-id="7cee3-156">Depurador de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7cee3-156">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
