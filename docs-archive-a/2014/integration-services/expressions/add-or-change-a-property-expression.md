---
title: Agregar o cambiar una expresión de propiedad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- expressions [Integration Services], creating
- expressions [Integration Services], property expressions
ms.assetid: cb5da499-065f-4fa6-9f6d-5bc5f385241e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d6d12fbe46930818af2b47b59620963d39616e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674972"
---
# <a name="add-or-change-a-property-expression"></a><span data-ttu-id="39fda-102">Agregar o cambiar una expresión de propiedad</span><span class="sxs-lookup"><span data-stu-id="39fda-102">Add or Change a Property Expression</span></span>
  <span data-ttu-id="39fda-103">Puede crear expresiones de propiedad para paquetes, tareas, contenedores de bucles ForEach, contenedores de bucles For, contenedores de secuencias, controladores de eventos, administradores de conexión de paquetes y proyectos, y proveedores de registro.</span><span class="sxs-lookup"><span data-stu-id="39fda-103">You can create property expressions for packages, tasks, Foreach Loop containers, For Loop containers, Sequence containers, event handlers, package and project level connection managers, and log providers.</span></span>  
  
 <span data-ttu-id="39fda-104">Para crear o cambiar expresiones de propiedad, puede utilizar el **Editor de expresiones de propiedad** o el **Generador de expresiones**.</span><span class="sxs-lookup"><span data-stu-id="39fda-104">To create or change property expressions, you can use either the **Property Expressions Editor** or **Expression Builder**.</span></span> <span data-ttu-id="39fda-105">Se puede tener acceso al **Editor de expresiones de propiedad** desde los editores personalizados que están disponibles para tareas y contenedores, o desde la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="39fda-105">The **Property Expressions Editor** can be accessed from either the custom editors that are available for tasks and containers, or from the **Properties** window.</span></span> <span data-ttu-id="39fda-106">Se puede tener acceso al**Generador de expresiones** desde el **Editor de expresiones de propiedad**.</span><span class="sxs-lookup"><span data-stu-id="39fda-106">**Expression Builder** can be accessed from inside the **Property Expressions Editor**.</span></span> <span data-ttu-id="39fda-107">Aunque puede escribir expresiones en el **Editor de expresiones de propiedad** o en el **Generador de expresiones**, el **Generador de expresiones** proporciona un conjunto gráfico de herramientas que simplifica el proceso de generar expresiones complejas.</span><span class="sxs-lookup"><span data-stu-id="39fda-107">While you can write expressions in either the **Property Expressions Editor** or **Expression Builder**, **Expression Builder** provides a graphical set of tools that makes it simple to build complex expressions.</span></span>  
  
 <span data-ttu-id="39fda-108">Para obtener más información sobre la sintaxis, los operadores y las funciones que proporciona [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vea [Operadores &#40;expresión de SSIS&#41;](operators-ssis-expression.md) y [Funciones &#40;expresión de SSIS&#41;](functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="39fda-108">To learn more about the syntax, operators, and functions that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides, see [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) and [Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md).</span></span> <span data-ttu-id="39fda-109">El tema de cada operador o función incluye ejemplos de uso de ese operador o función en una expresión.</span><span class="sxs-lookup"><span data-stu-id="39fda-109">The topic for each operator or function includes examples of using that operator or function in an expression.</span></span> <span data-ttu-id="39fda-110">Para obtener ejemplos de expresiones más complejas, vea [Usar expresiones de propiedad en paquetes](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="39fda-110">For examples of more complex expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
### <a name="to-create-or-change-a-property-expression"></a><span data-ttu-id="39fda-111">Para agregar o cambiar una expresión de propiedad</span><span class="sxs-lookup"><span data-stu-id="39fda-111">To create or change a property expression</span></span>  
  
1.  <span data-ttu-id="39fda-112">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto que contiene el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que desea.</span><span class="sxs-lookup"><span data-stu-id="39fda-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="39fda-113">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="39fda-113">In Solution Explorer, double-click the package to open it, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="39fda-114">Si el elemento es una tarea o un contenedor, haga doble clic en el elemento y, después, haga clic en **Expresiones** en el editor.</span><span class="sxs-lookup"><span data-stu-id="39fda-114">If the item is a task or a container, double-click the item, and then click **Expressions** in the editor.</span></span>  
  
    -   <span data-ttu-id="39fda-115">Haga clic con el botón derecho en el elemento y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="39fda-115">Right-click the item and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="39fda-116">Haga clic en el cuadro **Expresiones** y, después, en el botón de puntos suspensivos (…).</span><span class="sxs-lookup"><span data-stu-id="39fda-116">Click in the **Expressions** box and then click the ellipsis (...).</span></span>  
  
4.  <span data-ttu-id="39fda-117">En el **Editor de expresiones de propiedad**, seleccione una propiedad de la lista **Propiedades** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="39fda-117">In the **Property Expressions Editor**, select a property in the **Property** list, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="39fda-118">Escriba o cambie directamente la expresión de propiedad en la columna **Expresión** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39fda-118">Type or change the property expression directly in the **Expression** column, and then click **OK**.</span></span>  
  
         <span data-ttu-id="39fda-119">O bien</span><span class="sxs-lookup"><span data-stu-id="39fda-119">-or-</span></span>  
  
    -   <span data-ttu-id="39fda-120">Haga clic en los puntos suspensivos (…) en la fila de expresión de la propiedad para abrir el **Generador de expresiones**.</span><span class="sxs-lookup"><span data-stu-id="39fda-120">Click the ellipsis (...) in the expression row of the property to open the **Expression Builder**.</span></span>  
  
5.  <span data-ttu-id="39fda-121">(Opcional) En el **Generador de expresiones**, haga una de las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="39fda-121">(Optional) In the **Expression Builder**, do any of the following tasks:</span></span>  
  
    -   <span data-ttu-id="39fda-122">Para tener acceso a las variables del sistema y a las definidas por el usuario, expanda **Variables**.</span><span class="sxs-lookup"><span data-stu-id="39fda-122">To access system and user-defined variables, expand **Variables**.</span></span>  
  
    -   <span data-ttu-id="39fda-123">Para tener acceso a las funciones, las conversiones y los operadores que proporciona el lenguaje de expresiones de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , expanda **Funciones matemáticas**, **Funciones de cadena**, **Funciones de fecha y hora**, **Funciones NULL**, **Conversiones de tipo**y **Operadores**.</span><span class="sxs-lookup"><span data-stu-id="39fda-123">To access the functions, the casts, and the operators that the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression language provides, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators**.</span></span>  
  
    -   <span data-ttu-id="39fda-124">Para generar o cambiar una expresión en el **Generador de expresiones**, arrastre variables, columnas, funciones, operadores y conversiones hasta el cuadro **Expresión** , o escriba la expresión en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="39fda-124">To build or change an expression in the **Expression Builder**, drag variables, columns, functions, operators, and casts to the **Expression** box, or type the expression in the box.</span></span>  
  
    -   <span data-ttu-id="39fda-125">Para ver el resultado de la evaluación de la expresión, haga clic en **Evaluar expresión** en el **Generador de expresiones**.</span><span class="sxs-lookup"><span data-stu-id="39fda-125">To view the evaluation result of the expression, click **Evaluate Expression** in the **Expression Builder**.</span></span>  
  
         <span data-ttu-id="39fda-126">Si la expresión no es válida, aparece una alerta que describe los errores de sintaxis de la expresión.</span><span class="sxs-lookup"><span data-stu-id="39fda-126">If the expression is not valid, an alert appears that describes the syntax errors in the expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="39fda-127">Evaluar una expresión no asigna el resultado de la evaluación a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="39fda-127">Evaluating an expression does not assign the evaluation result to the property.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39fda-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39fda-128">See Also</span></span>  
 <span data-ttu-id="39fda-129">[Expresiones de Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="39fda-129">[Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="39fda-130">[Usar expresiones de propiedad en paquetes](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="39fda-130">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="39fda-131">[Paquetes de Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="39fda-131">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="39fda-132">[Contenedores de Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="39fda-132">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="39fda-133">[Tareas de Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="39fda-133">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="39fda-134">[Controladores de eventos de Integration Services &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="39fda-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="39fda-135">[Conexiones de Integration Services &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="39fda-135">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="39fda-136">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="39fda-136">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)  
  
  
