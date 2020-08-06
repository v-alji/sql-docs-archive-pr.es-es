---
title: División de un conjunto de datos con la transformación División condicional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Conditional Split transformation
- splitting dataset
- datasets [Integration Services], splitting
ms.assetid: 23b3e84f-9296-4dc9-81c0-c7f06ae3f1ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2efbc3973db1ab1b6b61f6de879e451319b50e49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676084"
---
# <a name="split-a-dataset-by-using-the-conditional-split-transformation"></a><span data-ttu-id="b5f1e-102">Dividir un conjunto de datos usando la transformación División condicional</span><span class="sxs-lookup"><span data-stu-id="b5f1e-102">Split a Dataset by Using the Conditional Split Transformation</span></span>
  <span data-ttu-id="b5f1e-103">Para agregar y configurar una transformación División condicional, el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-103">To add and configure a Conditional Split transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-conditionally-split-a-dataset"></a><span data-ttu-id="b5f1e-104">Para realizar la división condicional de un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="b5f1e-104">To conditionally split a dataset</span></span>  
  
1.  <span data-ttu-id="b5f1e-105">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b5f1e-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b5f1e-107">Haga clic en la pestaña **Flujo de datos** y, desde el **cuadro de herramientas**, arrastre la transformación División condicional a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-107">Click the **Data Flow** tab, and, from the **Toolbox**, drag the Conditional Split transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="b5f1e-108">Conecte la transformación División condicional al flujo de datos arrastrando el conector desde el origen de datos o la transformación anterior a la transformación División condicional.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-108">Connect the Conditional Split transformation to the data flow by dragging the connector from the data source or the previous transformation to the Conditional Split transformation.</span></span>  
  
5.  <span data-ttu-id="b5f1e-109">Haga doble clic en la transformación División condicional.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-109">Double-click the Conditional Split transformation.</span></span>  
  
6.  <span data-ttu-id="b5f1e-110">En el **Editor de transformación División condicional**, genere las expresiones que se usan como condiciones arrastrando variables, columnas, funciones y operadores a la columna **Condición** de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-110">In the **Conditional Split Transformation Editor**, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Condition** column in the grid.</span></span> <span data-ttu-id="b5f1e-111">O bien, puede escribir la expresión en la columna **Condición** .</span><span class="sxs-lookup"><span data-stu-id="b5f1e-111">Or, you can type the expression in the **Condition** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5f1e-112">Se puede usar una variable o columna en varias expresiones.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-112">A variable or column can be used in multiple expressions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5f1e-113">Si la expresión no es válida, el texto de la expresión se resalta y la información sobre herramientas de la columna describe los errores.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-113">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="b5f1e-114">Opcionalmente, modifique los valores en la columna **Nombre de salida** .</span><span class="sxs-lookup"><span data-stu-id="b5f1e-114">Optionally, modify the values in the **Output Name** column.</span></span> <span data-ttu-id="b5f1e-115">Los nombres predeterminados son Caso 1, Caso 2, etc.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-115">The default names are Case 1, Case 2, and so forth.</span></span>  
  
8.  <span data-ttu-id="b5f1e-116">Para modificar la secuencia en la que se evalúan las condiciones, haga clic en la flecha arriba o flecha abajo.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-116">To modify the sequence in which the conditions are evaluated, click the up arrow or down arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5f1e-117">Coloque las condiciones que es más probable encontrar en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-117">Place the conditions that are most likely to be encountered at the top of the list.</span></span>  
  
9. <span data-ttu-id="b5f1e-118">Opcionalmente, modifique el nombre de la salida predeterminada para filas de datos que no coinciden con ninguna condición.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-118">Optionally, modify the name of the default output for data rows that do not match any condition.</span></span>  
  
10. <span data-ttu-id="b5f1e-119">Para configurar una salida de error, haga clic en **Configurar la salida de errores**.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-119">To configure an error output, click **Configure Error Output**.</span></span> <span data-ttu-id="b5f1e-120">Para más información, vea [Configurar una salida de error en un componente de flujo de datos](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="b5f1e-120">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="b5f1e-121">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="b5f1e-122">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="b5f1e-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f1e-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5f1e-123">See Also</span></span>  
 <span data-ttu-id="b5f1e-124">[Conditional Split Transformation](conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="b5f1e-124">[Conditional Split Transformation](conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="b5f1e-125">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="b5f1e-125">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="b5f1e-126">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="b5f1e-126">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="b5f1e-127">[Tipos de datos de Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="b5f1e-127">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="b5f1e-128">[Tarea Flujo de datos](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="b5f1e-128">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="b5f1e-129">Expresiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b5f1e-129">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
