---
title: Establecer las propiedades de una tarea o un contenedor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], properties
ms.assetid: 52d47ca4-fb8c-493d-8b2b-48bb269f859b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0a4c556b94af02c2f874f2740a70b1294c35e653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751270"
---
# <a name="set-the-properties-of-a-task-or-container"></a><span data-ttu-id="f2079-102">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="f2079-102">Set the Properties of a Task or Container</span></span>
  <span data-ttu-id="f2079-103">Puede establecer la mayoría de las propiedades de tareas y contenedores utilizando la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="f2079-103">You can set most properties of tasks and containers by using the **Properties** window.</span></span> <span data-ttu-id="f2079-104">Las excepciones son propiedades de colecciones de tareas y propiedades que son demasiado complejas como para establecerse mediante la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="f2079-104">The exceptions are properties of task collections and properties that are too complex to set by using the **Properties** window.</span></span> <span data-ttu-id="f2079-105">Por ejemplo, no puede configurar el enumerador que usa el contenedor de bucles Foreach en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="f2079-105">For example, you cannot configure the enumerator that the Foreach Loop container uses in the **Properties** window.</span></span> <span data-ttu-id="f2079-106">Debe usar un editor de tareas o contenedores para establecer estas propiedades complejas.</span><span class="sxs-lookup"><span data-stu-id="f2079-106">You must use a task or container editor to set these complex properties.</span></span> <span data-ttu-id="f2079-107">La mayoría de los editores de tareas y contenedores tienen varios nodos y cada nodo contiene propiedades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f2079-107">Most task and container editors have multiple nodes and each node contains related properties.</span></span> <span data-ttu-id="f2079-108">El nombre del nodo indica el sujeto de las propiedades que contiene el nodo.</span><span class="sxs-lookup"><span data-stu-id="f2079-108">The name of the node indicates the subject of the properties that the node contains.</span></span>  
  
 <span data-ttu-id="f2079-109">Los procedimientos siguientes describen cómo establecer las propiedades de una tarea o de un contenedor utilizando las ventanas **Propiedades** o el correspondiente editor de tareas y contenedores.</span><span class="sxs-lookup"><span data-stu-id="f2079-109">The following procedures describe how to set the properties of a task or container by using either the **Properties** windows, or the corresponding task or container editor.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-the-properties-window"></a><span data-ttu-id="f2079-110">Para establecer las propiedades de una tarea o de un contenedor mediante la ventana Propiedades</span><span class="sxs-lookup"><span data-stu-id="f2079-110">To set the properties of a task or container by using the Properties window</span></span>  
  
1.  <span data-ttu-id="f2079-111">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="f2079-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f2079-112">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="f2079-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f2079-113">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="f2079-113">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="f2079-114">En la superficie de diseño de la pestaña **Flujo de control** , haga clic con el botón derecho en la tarea o el contenedor y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f2079-114">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="f2079-115">En la ventana **Propiedades** , actualice los valores de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="f2079-115">In the **Properties** window, update the property value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2079-116">La mayoría de las propiedades se pueden establecer escribiendo un valor directamente en el cuadro de texto o seleccionando un valor de una lista.</span><span class="sxs-lookup"><span data-stu-id="f2079-116">Most properties can be set by typing a value directly in the text box, or by selecting a value from a list.</span></span> <span data-ttu-id="f2079-117">Sin embargo, algunas propiedades son más complejas y cuentan con un editor de propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f2079-117">However, some properties are more complex and have a custom property editor.</span></span> <span data-ttu-id="f2079-118">Para establecer la propiedad, haga clic en el cuadro de texto y, después, haga clic en el botón Generar **(…)** para abrir el editor personalizado.</span><span class="sxs-lookup"><span data-stu-id="f2079-118">To set the property, click in the text box, and then click the build **(...)** button to open the custom editor.</span></span>  
  
6.  <span data-ttu-id="f2079-119">Opcionalmente, puede crear expresiones de propiedades para actualizar dinámicamente las propiedades de la tarea o del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f2079-119">Optionally, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="f2079-120">Para más información, vea [Agregar o cambiar una expresión de propiedad](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f2079-120">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="f2079-121">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="f2079-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-a-task-or-container-editor"></a><span data-ttu-id="f2079-122">Para establecer las propiedades de una tarea o de un contenedor mediante un editor de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="f2079-122">To set the properties of a task or container by using a task or container editor</span></span>  
  
1.  <span data-ttu-id="f2079-123">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="f2079-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f2079-124">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="f2079-124">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f2079-125">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="f2079-125">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="f2079-126">En la superficie de diseño de la pestaña **Flujo de control** , haga clic con el botón derecho en la tarea o en el contenedor y, después, haga clic en **Editar** para abrir el editor de tareas o contenedores correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f2079-126">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Edit** to open the corresponding task or container editor.</span></span>  
  
     <span data-ttu-id="f2079-127">Para más información sobre cómo configurar el contenedor de bucles For, vea [Configurar un contenedor de bucles For](control-flow/for-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="f2079-127">For information about how to configure the For Loop container, see [Configure a For Loop Container](control-flow/for-loop-container.md).</span></span>  
  
     <span data-ttu-id="f2079-128">Para obtener información sobre cómo configurar el contenedor de bucles foreach, vea [configurar un contenedor de bucles foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="f2079-128">For information about how to configure the Foreach Loop container, see [Configure a Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2079-129">El contenedor de secuencias no dispone de ningún editor personalizado.</span><span class="sxs-lookup"><span data-stu-id="f2079-129">The Sequence container has no custom editor.</span></span>  
  
5.  <span data-ttu-id="f2079-130">Si el editor de tareas o de contenedores tiene varios nodos, haga clic en el nodo que contiene la propiedad que desea establecer.</span><span class="sxs-lookup"><span data-stu-id="f2079-130">If the task or container editor has multiple nodes, click the node that contains the property that you want to set.</span></span>  
  
6.  <span data-ttu-id="f2079-131">Opcionalmente, haga clic en **Expresiones** y, en la página **Expresiones** , cree expresiones de propiedades para actualizar dinámicamente las propiedades de la tarea o del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f2079-131">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="f2079-132">Para más información, vea [Agregar o cambiar una expresión de propiedad](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f2079-132">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="f2079-133">Actualice el valor de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="f2079-133">Update the property value.</span></span>  
  
8.  <span data-ttu-id="f2079-134">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="f2079-134">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2079-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2079-135">See Also</span></span>  
 <span data-ttu-id="f2079-136">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="f2079-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="f2079-137">Contenedores de Integration Services</span><span class="sxs-lookup"><span data-stu-id="f2079-137">Integration Services Containers</span></span>](control-flow/integration-services-containers.md)  
  
  
