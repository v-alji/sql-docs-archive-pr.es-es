---
title: Usar una expresión en un componente de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], data flow
- expressions [Integration Services], data flow components
ms.assetid: 9181b998-d24a-41fb-bb3c-14eee34f910d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 653bf468d0af6d44c5abe7344fcc13f93f86b430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747088"
---
# <a name="use-an-expression-in-a-data-flow-component"></a><span data-ttu-id="5f56e-102">utilizar una expresión en un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="5f56e-102">Use an Expression in a Data Flow Component</span></span>
  <span data-ttu-id="5f56e-103">Este procedimiento describe cómo agregar una expresión a la transformación División condicional o a la transformación Columna derivada.</span><span class="sxs-lookup"><span data-stu-id="5f56e-103">This procedure describes how to add an expression to the Conditional Split transformation or to the Derived Column transformation.</span></span> <span data-ttu-id="5f56e-104">La transformación División condicional utiliza expresiones para definir las condiciones que dirigen las filas de datos a una salida de transformación y la transformación Columna derivada utiliza expresiones para definir los valores asignados a las columnas.</span><span class="sxs-lookup"><span data-stu-id="5f56e-104">The Conditional Split transformation uses expressions to define the conditions that direct data rows to a transformation output, and the Derived Column transformation uses expressions to define values assigned to columns.</span></span>  
  
 <span data-ttu-id="5f56e-105">Para implementar una expresión en una transformación, el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="5f56e-105">To implement an expression in a transformation, the package must already include at least one Data Flow task and a source.</span></span> <span data-ttu-id="5f56e-106">Para obtener información sobre cómo agregar elementos a paquetes, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5f56e-106">For information about adding items to packages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5f56e-107">Agregar o eliminar tareas o contenedores en un flujo de control</span><span class="sxs-lookup"><span data-stu-id="5f56e-107">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
    
  
-   [<span data-ttu-id="5f56e-108">Agregar o eliminar un componente en un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="5f56e-108">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
-   [<span data-ttu-id="5f56e-109">Conectar componentes de un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="5f56e-109">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)  
  
### <a name="to-create-an-expression"></a><span data-ttu-id="5f56e-110">Para crear una expresión</span><span class="sxs-lookup"><span data-stu-id="5f56e-110">To create an expression</span></span>  
  
1.  <span data-ttu-id="5f56e-111">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="5f56e-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5f56e-112">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="5f56e-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="5f56e-113">En el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , haga clic en la pestaña **Flujo de control** y, a continuación, en la tarea Flujo de datos que contiene el flujo de datos en el que desea implementar la expresión.</span><span class="sxs-lookup"><span data-stu-id="5f56e-113">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow** tab, and then click the Data Flow task that contains the data flow in which you want to implement an expression.</span></span>  
  
4.  <span data-ttu-id="5f56e-114">Haga clic en la pestaña **Flujo de datos** y arrastre una transformación División condicional o Columna derivada del **Cuadro de herramientas** a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="5f56e-114">Click the **Data Flow** tab, and drag either a Conditional Split or Derived Column transformation from the **Toolbox** to the design surface.</span></span>  
  
5.  <span data-ttu-id="5f56e-115">Arrastre el conector verde desde el origen o desde una transformación a la transformación División condicional o Columna derivada.</span><span class="sxs-lookup"><span data-stu-id="5f56e-115">Drag the green connector from the source or a transformation to the Conditional Split or Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="5f56e-116">Haga doble clic en la transformación para abrir el cuadro de diálogo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5f56e-116">Double-click the transformation to open its dialog box.</span></span>  
  
7.  <span data-ttu-id="5f56e-117">En el panel de la izquierda, expanda **Variables** para ver las variables del sistema y las definidas por el usuario, y expanda **Columnas** para ver las columnas de entrada de la transformación.</span><span class="sxs-lookup"><span data-stu-id="5f56e-117">In the left pane, expand **Variables** to display system and user-defined variables, and expand **Columns** to display the transformation input columns.</span></span>  
  
8.  <span data-ttu-id="5f56e-118">En el panel de la derecha, expanda **Funciones matemáticas**, **Funciones de cadena**, **Funciones de fecha y hora**, **Funciones NULL**, **Conversiones de tipo**y **Operadores** para tener acceso a las funciones, las conversiones y los operadores que proporciona la gramática de expresiones.</span><span class="sxs-lookup"><span data-stu-id="5f56e-118">In the right pane, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators** to access the functions, the casts, and the operators that the expression grammar provides.</span></span>  
  
9. <span data-ttu-id="5f56e-119">Dependiendo de la transformación, siga uno de estos procedimientos para crear una expresión:</span><span class="sxs-lookup"><span data-stu-id="5f56e-119">Depending on the transformation, do one of the following to build an expression:</span></span>  
  
    -   <span data-ttu-id="5f56e-120">En el cuadro de diálogo **Editor de transformación División condicional** , arrastre las variables, columnas, funciones, operadores y conversiones a la columna **Condición** .</span><span class="sxs-lookup"><span data-stu-id="5f56e-120">In the **Conditional Split Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Condition** column.</span></span> <span data-ttu-id="5f56e-121">O bien, puede escribir una expresión directamente en la columna **Condición** .</span><span class="sxs-lookup"><span data-stu-id="5f56e-121">Alternatively, you can type an expression directly in the **Condition** column.</span></span>  
  
    -   <span data-ttu-id="5f56e-122">En el cuadro de diálogo **Editor de transformación Columna derivada** , arrastre las variables, columnas, funciones, operadores y conversiones a la columna **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="5f56e-122">In the **Derived Column Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Expression** column.</span></span> <span data-ttu-id="5f56e-123">O bien, puede escribir una expresión directamente en la columna **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="5f56e-123">Alternatively, you can type an expression directly in the **Expression** column.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5f56e-124"> Al quitar el foco de la columna **Condición** o **Expresión** , el texto de la expresión podría resaltarse para indicar que la sintaxis de la expresión es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="5f56e-124">When you remove the focus from the **Condition** column or the **Expression** column, the expression text might be highlighted to indicate that the expression syntax is incorrect.</span></span>  
  
10. <span data-ttu-id="5f56e-125">Haga clic en **Aceptar** para salir del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5f56e-125">Click **OK** to exit the dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f56e-126">Si la expresión no es válida, aparece una alerta que describe los errores de sintaxis de la expresión.</span><span class="sxs-lookup"><span data-stu-id="5f56e-126">If the expression is not valid, an alert appears describing the syntax errors in the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f56e-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f56e-127">See Also</span></span>  
 <span data-ttu-id="5f56e-128">[Integration Services &#40;expresiones de&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="5f56e-128">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="5f56e-129">[División condicional, transformación](data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="5f56e-129">[Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="5f56e-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="5f56e-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span></span>  
 <span data-ttu-id="5f56e-131">[Tarea Flujo de datos](control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="5f56e-131">[Data Flow Task](control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="5f56e-132">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="5f56e-132">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
