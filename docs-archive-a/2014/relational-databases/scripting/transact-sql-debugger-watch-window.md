---
title: Ventana de inspección
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Watch Window [Transact-SQL]
ms.assetid: 23f3baa4-14c2-4262-92f7-3f43fcfa0436
author: rothja
ms.author: jroth
ms.openlocfilehash: c2a3db9b095902fcb5620af91fb86d80f773d606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675255"
---
# <a name="watch-window"></a><span data-ttu-id="77c0a-102">Ventana de inspección</span><span class="sxs-lookup"><span data-stu-id="77c0a-102">Watch Window</span></span>
  <span data-ttu-id="77c0a-103">La ventana **Inspección** muestra información sobre las expresiones que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="77c0a-103">The **Watch** window displays information about the expressions that you have selected.</span></span> <span data-ttu-id="77c0a-104">Puede haber hasta cuatro ventanas Inspección: **Inspección 1**, **Inspección 2, Inspección 3**e **Inspección 4**.</span><span class="sxs-lookup"><span data-stu-id="77c0a-104">There can be up to four watch windows: **Watch 1**, **Watch 2, Watch 3**, and **Watch 4**.</span></span> <span data-ttu-id="77c0a-105">Las expresiones se evalúan dentro del ámbito del marco de la pila de llamadas actual que está seleccionado en la ventana **Pila de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="77c0a-105">The expressions are evaluated within the scope of the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="77c0a-106">Debe estar en modo de depuración para observar las variables y las expresiones.</span><span class="sxs-lookup"><span data-stu-id="77c0a-106">You must be in debug mode to watch variables and expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="77c0a-107">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="77c0a-107">Task List</span></span>  
 <span data-ttu-id="77c0a-108">**Para tener acceso a las ventanas Inspección**</span><span class="sxs-lookup"><span data-stu-id="77c0a-108">**To access the Watch windows**</span></span>  
  
-   <span data-ttu-id="77c0a-109">En el menú **Depurar** , haga clic en **Ventanas**, luego en **Inspección**y, después, haga clic en **Inspección 1**, **Inspección 2, Inspección 3**o **Inspección 4**.</span><span class="sxs-lookup"><span data-stu-id="77c0a-109">On the **Debug** menu, click **Windows**, click **Watch**, and then click **Watch 1**, **Watch 2, Watch 3**, or **Watch 4**.</span></span>  
  
 <span data-ttu-id="77c0a-110">**Para cambiar el valor de una expresión**</span><span class="sxs-lookup"><span data-stu-id="77c0a-110">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="77c0a-111">Haga clic con el botón derecho en la expresión y, después, seleccione **Editar valor**.</span><span class="sxs-lookup"><span data-stu-id="77c0a-111">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="77c0a-112">Columnas</span><span class="sxs-lookup"><span data-stu-id="77c0a-112">Columns</span></span>  
 <span data-ttu-id="77c0a-113">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="77c0a-113">**Name**</span></span>  
 <span data-ttu-id="77c0a-114">Son las expresiones que muestra el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77c0a-114">Are the expressions that are listed by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="77c0a-115">Se admiten las siguientes expresiones:</span><span class="sxs-lookup"><span data-stu-id="77c0a-115">The following expressions are supported:</span></span>  
  
-   <span data-ttu-id="77c0a-116">Variables.</span><span class="sxs-lookup"><span data-stu-id="77c0a-116">Variables.</span></span>  
  
-   <span data-ttu-id="77c0a-117">Parámetros.</span><span class="sxs-lookup"><span data-stu-id="77c0a-117">Parameters.</span></span>  
  
-   <span data-ttu-id="77c0a-118">Funciones del sistema cuyo nombre empieza con @@.</span><span class="sxs-lookup"><span data-stu-id="77c0a-118">System functions whose name starts with @@.</span></span>  
  
-   <span data-ttu-id="77c0a-119">Expresiones generadas mediante la aplicación de operadores a una o más variables, parámetros o funciones del sistema, como @IntegerCounter + 1 o FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="77c0a-119">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
-   <span data-ttu-id="77c0a-120">Instrucciones Transact-SQL que devuelven un valor único, como SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="77c0a-120">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
 <span data-ttu-id="77c0a-121">**Valor**</span><span class="sxs-lookup"><span data-stu-id="77c0a-121">**Value**</span></span>  
 <span data-ttu-id="77c0a-122">Muestra el valor que se devuelve después de que el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] evalúe la expresión especificada en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="77c0a-122">Displays the value that is returned after the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger evaluates the expression specified in **Name**.</span></span>  
  
 <span data-ttu-id="77c0a-123">Si la longitud de una expresión es mayor que el ancho de la columna **Valor** , una información sobre herramientas muestra el valor completo al mover el puntero sobre la celda **Valor** para esa expresión.</span><span class="sxs-lookup"><span data-stu-id="77c0a-123">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="77c0a-124">Un icono de lupa en una celda **Valor** indica que el visualizador del depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] está disponible.</span><span class="sxs-lookup"><span data-stu-id="77c0a-124">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="77c0a-125">En la lista, puede especificar **Visualizador de texto**, **Visualizador XML**o **Visualizador HTML**.</span><span class="sxs-lookup"><span data-stu-id="77c0a-125">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="77c0a-126">Para iniciar un visualizador del depurador, haga clic en el icono de lupa.</span><span class="sxs-lookup"><span data-stu-id="77c0a-126">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="77c0a-127">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] abre un diálogo que muestra los datos en un formato adecuado al tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="77c0a-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="77c0a-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="77c0a-128">**Type**</span></span>  
 <span data-ttu-id="77c0a-129">Muestra el tipo de datos de la expresión.</span><span class="sxs-lookup"><span data-stu-id="77c0a-129">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c0a-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77c0a-130">See Also</span></span>  
 <span data-ttu-id="77c0a-131">[Depurador de Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="77c0a-131">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="77c0a-132">[Ver información del depurador de Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="77c0a-132">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="77c0a-133">[Ventana de locales](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="77c0a-133">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="77c0a-134">[Ventana de pila de llamadas](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="77c0a-134">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="77c0a-135">[Cuadro de diálogo Inspección rápida](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="77c0a-135">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="77c0a-136">Expresiones &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77c0a-136">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
