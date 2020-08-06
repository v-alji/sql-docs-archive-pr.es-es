---
title: Derivar valores de columna mediante la transformación Columna derivada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- columns [Integration Services]
- derived columns
- columns [Integration Services], values
- Derived Column transformation
ms.assetid: 28b07746-fc6f-42b2-b741-9de6fac3f29c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 837ec552144697b40cf649bc0403edfe4dc57a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663033"
---
# <a name="derive-column-values-by-using-the-derived-column-transformation"></a><span data-ttu-id="6e434-102">Derivar valores de columna mediante la transformación Columna derivada</span><span class="sxs-lookup"><span data-stu-id="6e434-102">Derive Column Values by Using the Derived Column Transformation</span></span>
  <span data-ttu-id="6e434-103">Para agregar y configurar una transformación Columna derivada, el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="6e434-103">To add and configure a Derived Column transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
 <span data-ttu-id="6e434-104">La transformación Columna derivada usa expresiones para actualizar los valores de las columnas existentes o agregar valores a las nuevas.</span><span class="sxs-lookup"><span data-stu-id="6e434-104">The Derived Column transformation uses expressions to update the values of existing or to add values to new columns.</span></span> <span data-ttu-id="6e434-105">Si se elige agregar valores a columnas nuevas, el cuadro de diálogo **Editor de transformación Columna derivada** evalúa la expresión y define los metadatos de las columnas en función del resultado.</span><span class="sxs-lookup"><span data-stu-id="6e434-105">When you choose to add values to new columns, the **Derived Column Transformation Editor** dialog box evaluates the expression and defines the metadata of the columns accordingly.</span></span> <span data-ttu-id="6e434-106">Por ejemplo, si una expresión concatena dos columnas (cada una con el tipo de datos DT_WSTR y una longitud de 50) con un espacio entre los dos valores de las columnas, la nueva columna tiene el tipo de datos DT_WSTR y una longitud de 101.</span><span class="sxs-lookup"><span data-stu-id="6e434-106">For example, if an expression concatenates two columns-each with the DT_WSTR data type and a length of 50-with a space between the two column values, the new column has the DT_WSTR data type and a length of 101.</span></span> <span data-ttu-id="6e434-107">El tipo de datos de las columnas nuevas se puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="6e434-107">You can update the data type of new columns.</span></span> <span data-ttu-id="6e434-108">El único requisito es que el tipo de datos sea compatible con los datos insertados.</span><span class="sxs-lookup"><span data-stu-id="6e434-108">The only requirement is that data type be compatible with the inserted data.</span></span> <span data-ttu-id="6e434-109">Por ejemplo, el cuadro de diálogo **Editor de transformación Columna derivada** genera un error de validación si se asigna un valor de datos a una columna con tipo de datos entero.</span><span class="sxs-lookup"><span data-stu-id="6e434-109">For example, the **Derived Column Transformation Editor** dialog box generates a validation error when you assign a date value to a column with an integer data type.</span></span> <span data-ttu-id="6e434-110">En función del tipo de datos seleccionado, se puede especificar la longitud, precisión, escala y página de códigos de la columna.</span><span class="sxs-lookup"><span data-stu-id="6e434-110">Depending on the data type that you selected, you can specify the length, precision, scale, and code page of the column.</span></span>  
  
### <a name="to-derive-column-values"></a><span data-ttu-id="6e434-111">Para derivar valores de columna</span><span class="sxs-lookup"><span data-stu-id="6e434-111">To derive column values</span></span>  
  
1.  <span data-ttu-id="6e434-112">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="6e434-112">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="6e434-113">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="6e434-113">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="6e434-114">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre la transformación Columna derivada a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="6e434-114">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Derived Column transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="6e434-115">Conecte la transformación Columna derivada al flujo de datos arrastrando el conector desde el origen o la transformación anterior a la transformación Columna derivada.</span><span class="sxs-lookup"><span data-stu-id="6e434-115">Connect the Derived Column transformation to the data flow by dragging the connector from the source or the previous transformation to the Derived Column transformation.</span></span>  
  
5.  <span data-ttu-id="6e434-116">Haga doble clic en la transformación Columna derivada.</span><span class="sxs-lookup"><span data-stu-id="6e434-116">Double-click the Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="6e434-117">En el cuadro de diálogo **Editor de transformación Columna derivada** , genere las expresiones que se usan como condiciones arrastrando variables, columnas, funciones y operadores a la columna **Expresión** en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6e434-117">In the **Derived Column Transformation Editor** dialog box, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Expression** column in the grid.</span></span> <span data-ttu-id="6e434-118">Como alternativa, puede escribir la expresión en la columna **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="6e434-118">Alternatively, you can type the expression in the **Expression** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6e434-119">Si la expresión no es válida, el texto de la expresión se resalta y la información sobre herramientas de la columna describe los errores.</span><span class="sxs-lookup"><span data-stu-id="6e434-119">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="6e434-120">En la lista **Columna derivada**, seleccione **\<add as new column>** para escribir el resultado de la evaluación de la expresión en una columna nueva, o seleccione una columna existente para actualizarla con el resultado de la evaluación.</span><span class="sxs-lookup"><span data-stu-id="6e434-120">In the **Derived Column** list, select **\<add as new column>** to write the evaluation result of the expression to a new column, or select an existing column to update with the evaluation result.</span></span>  
  
     <span data-ttu-id="6e434-121">Si se decide usar una columna nueva, el cuadro de diálogo **Editor de transformación Columna derivada** evalúa la expresión y asigna un tipo de datos a la columna, en función del tipo de datos, la longitud, precisión, escala y página de códigos.</span><span class="sxs-lookup"><span data-stu-id="6e434-121">If you chose to use a new column, the **Derived Column Transformation Editor** dialog box evaluates the expression and assigns a data type to the column, depending on the data type, length, precisions, scale, and code page.</span></span>  
  
8.  <span data-ttu-id="6e434-122">Al utilizar una nueva columna, seleccione un tipo de datos en la lista **Tipo de datos** .</span><span class="sxs-lookup"><span data-stu-id="6e434-122">If using a new column, select a data type in the **Data Type** list.</span></span> <span data-ttu-id="6e434-123">Según el tipo de datos seleccionado, actualice opcionalmente los valores en las columnas **Longitud**, **Precisión**, **Escala**y **Página de códigos** .</span><span class="sxs-lookup"><span data-stu-id="6e434-123">Depending on the selected data type, optionally update the values in the **Length**, **Precision**, **Scale**, and **Code Page** columns.</span></span> <span data-ttu-id="6e434-124">Los metadatos de las columnas existentes no pueden cambiarse.</span><span class="sxs-lookup"><span data-stu-id="6e434-124">Metadata of existing columns cannot be changed.</span></span>  
  
9. <span data-ttu-id="6e434-125">Opcionalmente, modifique los valores de la columna **Nombre de columna derivada** .</span><span class="sxs-lookup"><span data-stu-id="6e434-125">Optionally, modify the values in the **Derived Column Name** column.</span></span>  
  
10. <span data-ttu-id="6e434-126">Para configurar la salida de error, haga clic en **Configurar la salida de errores**.</span><span class="sxs-lookup"><span data-stu-id="6e434-126">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="6e434-127">Para más información, vea [Configurar una salida de error en un componente de flujo de datos](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6e434-127">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="6e434-128">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e434-128">Click **OK**.</span></span>  
  
12. <span data-ttu-id="6e434-129">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="6e434-129">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e434-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e434-130">See Also</span></span>  
 <span data-ttu-id="6e434-131">[Derived Column Transformation](derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="6e434-131">[Derived Column Transformation](derived-column-transformation.md) </span></span>  
 <span data-ttu-id="6e434-132">[Tipos de datos de Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="6e434-132">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="6e434-133">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="6e434-133">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="6e434-134">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="6e434-134">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="6e434-135">[Tarea Flujo de datos](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="6e434-135">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="6e434-136">Expresiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="6e434-136">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
