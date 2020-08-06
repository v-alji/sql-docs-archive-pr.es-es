---
title: Cuadro de diálogo Inspección rápida
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.quickwatch
helpviewer_keywords:
- QuickWatch Dialog [Transact-SQL]
ms.assetid: d6bbb373-1452-41f2-bdc5-86ae689c3dc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 48e4bda558b75bec0c81815c90feff9d6500a803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676995"
---
# <a name="quickwatch-dialog-box"></a><span data-ttu-id="72269-102">Cuadro de diálogo Inspección rápida</span><span class="sxs-lookup"><span data-stu-id="72269-102">QuickWatch Dialog Box</span></span>
  <span data-ttu-id="72269-103">Utilice el cuadro de diálogo **Inspección rápida** para ver rápidamente el tipo de datos y el valor de una expresión de [!INCLUDE[tsql](../../includes/tsql-md.md)] , como una variable o un parámetro, cuando esté depurando el código de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72269-103">Use the **QuickWatch** dialog box to quickly view the data type and value of one [!INCLUDE[tsql](../../includes/tsql-md.md)] expression, such as a variable or parameter, when you are debugging [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="72269-104">Para inspeccionar varias expresiones, puede agregar también la expresión a una ventana **Inspección** .</span><span class="sxs-lookup"><span data-stu-id="72269-104">To watch multiple expressions, you can also add the expression to a **Watch** window.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="72269-105">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="72269-105">Task List</span></span>  
 <span data-ttu-id="72269-106">**Para tener acceso al cuadro de diálogo Inspección rápida**</span><span class="sxs-lookup"><span data-stu-id="72269-106">**To access the QuickWatch dialog box**</span></span>  
  
-   <span data-ttu-id="72269-107">En el menú **Depurar** , haga clic en **Inspección rápida**.</span><span class="sxs-lookup"><span data-stu-id="72269-107">On the **Debug** menu, click **QuickWatch**.</span></span>  
  
 <span data-ttu-id="72269-108">**Para ver la información sobre una expresión**</span><span class="sxs-lookup"><span data-stu-id="72269-108">**To view the information about an expression**</span></span>  
  
1.  <span data-ttu-id="72269-109">En el cuadro de lista **Expresión** , escriba o seleccione la expresión que desea.</span><span class="sxs-lookup"><span data-stu-id="72269-109">In the **Expression** list box, type or select the expression that you want.</span></span> <span data-ttu-id="72269-110">Se admiten las expresiones [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes:</span><span class="sxs-lookup"><span data-stu-id="72269-110">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] expressions are supported:</span></span>  
  
    -   <span data-ttu-id="72269-111">Variables.</span><span class="sxs-lookup"><span data-stu-id="72269-111">Variables.</span></span>  
  
    -   <span data-ttu-id="72269-112">Parámetros.</span><span class="sxs-lookup"><span data-stu-id="72269-112">Parameters.</span></span>  
  
    -   <span data-ttu-id="72269-113">Funciones del sistema cuyo nombre empieza con @@.</span><span class="sxs-lookup"><span data-stu-id="72269-113">System functions whose name starts with @@.</span></span>  
  
    -   <span data-ttu-id="72269-114">Expresiones generadas mediante la aplicación de operadores a una o más variables, parámetros o funciones del sistema, como @IntegerCounter + 1 o FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="72269-114">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
    -   <span data-ttu-id="72269-115">Instrucciones Transact-SQL que devuelven un valor único, como SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="72269-115">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
2.  <span data-ttu-id="72269-116">Haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="72269-116">Click **Reevaluate**.</span></span>  
  
 <span data-ttu-id="72269-117">**Para agregar una expresión de Inspección rápida a la ventana Inspección**</span><span class="sxs-lookup"><span data-stu-id="72269-117">**To add the QuickWatch expression to a Watch window**</span></span>  
  
-   <span data-ttu-id="72269-118">Haga clic en **Agregar inspección**.</span><span class="sxs-lookup"><span data-stu-id="72269-118">Click **Add Watch**.</span></span>  
  
 <span data-ttu-id="72269-119">**Para cambiar el valor de una expresión de Inspección rápida**</span><span class="sxs-lookup"><span data-stu-id="72269-119">**To change the value of the QuickWatch expression**</span></span>  
  
-   <span data-ttu-id="72269-120">Haga clic con el botón derecho en la expresión y, después, seleccione **Editar valor**.</span><span class="sxs-lookup"><span data-stu-id="72269-120">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="72269-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="72269-121">Options</span></span>  
 <span data-ttu-id="72269-122">**Lista de expresiones**</span><span class="sxs-lookup"><span data-stu-id="72269-122">**Expression list**</span></span>  
 <span data-ttu-id="72269-123">Muestra la expresión seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="72269-123">Displays the currently selected expression.</span></span> <span data-ttu-id="72269-124">La lista desplegable contiene un conjunto de expresiones que puede seleccionar para mostrarse.</span><span class="sxs-lookup"><span data-stu-id="72269-124">The drop-down list contains a set of expressions that you can select to display.</span></span> <span data-ttu-id="72269-125">Las expresiones de la lista son las que están disponibles en el ámbito del marco de pila que está seleccionado actualmente en la ventana **Pila de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="72269-125">The expressions in the list are those available in the scope of the stack frame that is currently selected in the **Call Stack** window.</span></span> <span data-ttu-id="72269-126">Para mostrar una expresión diferente, escríbala o selecciónela en la lista.</span><span class="sxs-lookup"><span data-stu-id="72269-126">To display a different expression, either enter the expression or select it from list.</span></span> <span data-ttu-id="72269-127">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] admite las expresiones siguientes: variables, parámetros y funciones de sistema cuyos nombres comienzan por @@.</span><span class="sxs-lookup"><span data-stu-id="72269-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports the following expressions: variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="72269-128">**Cuadrícula Valor**</span><span class="sxs-lookup"><span data-stu-id="72269-128">**Value grid**</span></span>  
 <span data-ttu-id="72269-129">Muestra las propiedades de la expresión que se está inspeccionando.</span><span class="sxs-lookup"><span data-stu-id="72269-129">Displays the properties of the expression that is currently being watched.</span></span>  
  
 <span data-ttu-id="72269-130">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="72269-130">**Name**</span></span>  
 <span data-ttu-id="72269-131">Expresión [!INCLUDE[tsql](../../includes/tsql-md.md)] que se va a observar.</span><span class="sxs-lookup"><span data-stu-id="72269-131">Is the [!INCLUDE[tsql](../../includes/tsql-md.md)] expression being watched.</span></span>  
  
 <span data-ttu-id="72269-132">**Valor**</span><span class="sxs-lookup"><span data-stu-id="72269-132">**Value**</span></span>  
 <span data-ttu-id="72269-133">Muestra el valor que está asignado actualmente a la expresión.</span><span class="sxs-lookup"><span data-stu-id="72269-133">Displays the value that is currently assigned to the expression.</span></span> <span data-ttu-id="72269-134">Se muestra un espacio en blanco cuando la expresión no tiene ningún valor en este momento.</span><span class="sxs-lookup"><span data-stu-id="72269-134">A blank is displayed when the expression currently has no value.</span></span>  
  
 <span data-ttu-id="72269-135">Si la longitud de una expresión es mayor que el ancho de la columna **Valor** , una información sobre herramientas muestra el valor completo al mover el puntero sobre la celda **Valor** para esa expresión.</span><span class="sxs-lookup"><span data-stu-id="72269-135">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="72269-136">Un icono de lupa en una celda **Valor** indica que el visualizador del depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] está disponible.</span><span class="sxs-lookup"><span data-stu-id="72269-136">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="72269-137">En la lista, puede especificar **Visualizador de texto**, **Visualizador XML**o **Visualizador HTML**.</span><span class="sxs-lookup"><span data-stu-id="72269-137">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="72269-138">Para iniciar un visualizador del depurador, haga clic en el icono de lupa.</span><span class="sxs-lookup"><span data-stu-id="72269-138">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="72269-139">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] abre un cuadro de diálogo que muestra los datos en un formato adecuado al tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="72269-139">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="72269-140">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="72269-140">**Type**</span></span>  
 <span data-ttu-id="72269-141">Muestra el tipo de datos de la expresión.</span><span class="sxs-lookup"><span data-stu-id="72269-141">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72269-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72269-142">See Also</span></span>  
 <span data-ttu-id="72269-143">[Depurador de Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="72269-143">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="72269-144">[Ver información del depurador de Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="72269-144">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="72269-145">[Ventana de inspección](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="72269-145">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="72269-146">[Ventana de locales](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="72269-146">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="72269-147">[Ventana de pila de llamadas](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="72269-147">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 [<span data-ttu-id="72269-148">Expresiones &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72269-148">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
  
  
