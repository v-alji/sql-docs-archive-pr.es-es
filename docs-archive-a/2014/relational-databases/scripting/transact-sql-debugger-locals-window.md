---
title: Ventana de locales
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Locals Window [Transact-SQL]
ms.assetid: 59bea640-7823-4b4d-832c-f384d83cca2f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f8f62eb69a50d7543af41dddb9c62c842d17151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676997"
---
# <a name="locals-window"></a><span data-ttu-id="f52b1-102">Ventana Locales</span><span class="sxs-lookup"><span data-stu-id="f52b1-102">Locals Window</span></span>
  <span data-ttu-id="f52b1-103">La ventana **Variables locales** muestra información sobre las expresiones locales en el ámbito actual del depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f52b1-103">The **Locals** window displays information about the local expressions in the current scope of the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="f52b1-104">El ámbito está establecido en el marco de la pila de llamadas actual que está seleccionado en la ventana **Pila de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="f52b1-104">The scope is set to the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="f52b1-105">Debe estar en modo de depuración para mostrar las expresiones locales.</span><span class="sxs-lookup"><span data-stu-id="f52b1-105">You must be in debug mode to display the local expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="f52b1-106">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="f52b1-106">Task List</span></span>  
 <span data-ttu-id="f52b1-107">**Para tener acceso a la ventana Variables locales**</span><span class="sxs-lookup"><span data-stu-id="f52b1-107">**To access the Locals window**</span></span>  
  
-   <span data-ttu-id="f52b1-108">En el menú **Depurar** , haga clic en **Ventanas**y, a continuación, haga clic en **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="f52b1-108">On the **Debug** menu, click **Windows**, and then click **Locals**.</span></span>  
  
 <span data-ttu-id="f52b1-109">**Para cambiar el valor de una expresión**</span><span class="sxs-lookup"><span data-stu-id="f52b1-109">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="f52b1-110">Haga clic con el botón derecho en la expresión y, después, seleccione **Editar valor**.</span><span class="sxs-lookup"><span data-stu-id="f52b1-110">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="f52b1-111">Columnas</span><span class="sxs-lookup"><span data-stu-id="f52b1-111">Columns</span></span>  
 <span data-ttu-id="f52b1-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="f52b1-112">**Name**</span></span>  
 <span data-ttu-id="f52b1-113">Es el nombre de la expresión local.</span><span class="sxs-lookup"><span data-stu-id="f52b1-113">Is the name of the local expression.</span></span> <span data-ttu-id="f52b1-114">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] muestra las variables, los parámetros y las funciones de sistema cuyos nombres comienzan por @@.</span><span class="sxs-lookup"><span data-stu-id="f52b1-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger lists variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="f52b1-115">**Valor**</span><span class="sxs-lookup"><span data-stu-id="f52b1-115">**Value**</span></span>  
 <span data-ttu-id="f52b1-116">Muestra el valor que está asignado actualmente a la expresión local.</span><span class="sxs-lookup"><span data-stu-id="f52b1-116">Displays the value that is currently assigned to the local expression.</span></span> <span data-ttu-id="f52b1-117">Esta columna está en blanco cuando no se ha asignado ningún valor a la expresión.</span><span class="sxs-lookup"><span data-stu-id="f52b1-117">This column is blank when no value has been assigned to the expression.</span></span>  
  
 <span data-ttu-id="f52b1-118">Si la longitud de una expresión es mayor que el ancho de la columna **Valor** , una información sobre herramientas muestra el valor completo al mover el puntero sobre la celda **Valor** para esa expresión.</span><span class="sxs-lookup"><span data-stu-id="f52b1-118">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="f52b1-119">Un icono de lupa en una celda **Valor** indica que el visualizador del depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] está disponible.</span><span class="sxs-lookup"><span data-stu-id="f52b1-119">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="f52b1-120">En la lista, puede especificar **Visualizador de texto**, **Visualizador XML**o **Visualizador HTML**.</span><span class="sxs-lookup"><span data-stu-id="f52b1-120">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="f52b1-121">Para iniciar un visualizador del depurador, haga clic en el icono de lupa.</span><span class="sxs-lookup"><span data-stu-id="f52b1-121">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="f52b1-122">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] abre un cuadro de diálogo que muestra los datos en un formato adecuado al tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f52b1-122">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="f52b1-123">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f52b1-123">**Type**</span></span>  
 <span data-ttu-id="f52b1-124">Muestra el tipo de datos de la expresión.</span><span class="sxs-lookup"><span data-stu-id="f52b1-124">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52b1-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f52b1-125">See Also</span></span>  
 <span data-ttu-id="f52b1-126">[Depurador de Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="f52b1-126">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="f52b1-127">[Ver información del depurador de Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="f52b1-127">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="f52b1-128">[Ventana de inspección](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="f52b1-128">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="f52b1-129">[Ventana de pila de llamadas](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="f52b1-129">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="f52b1-130">[Cuadro de diálogo Inspección rápida](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="f52b1-130">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="f52b1-131">Expresiones &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f52b1-131">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
