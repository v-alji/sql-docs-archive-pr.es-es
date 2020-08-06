---
title: Editor de transformación columna derivada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntransformation.f1
helpviewer_keywords:
- Derived Column Transformation Editor
ms.assetid: ff73923e-d245-43d8-bf24-af3bdc942e51
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41a0f0dcd253473f78f2f38426b5fbd3d2ac2812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676603"
---
# <a name="derived-column-transformation-editor"></a><span data-ttu-id="13a31-102">Columna derivada, editor de transformación</span><span class="sxs-lookup"><span data-stu-id="13a31-102">Derived Column Transformation Editor</span></span>
  <span data-ttu-id="13a31-103">Utilice el cuadro de diálogo **Editor de transformación Columna derivada** para crear expresiones que rellenan columnas nuevas o de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="13a31-103">Use the **Derived Column Transformation Editor** dialog box to create expressions that populate new or replacement columns.</span></span>  
  
 <span data-ttu-id="13a31-104">Para obtener más información acerca de la transformación Columna derivada, vea [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="13a31-104">To learn more about the Derived Column transformation, see [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="13a31-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="13a31-105">Options</span></span>  
 <span data-ttu-id="13a31-106">**Variables y columnas**</span><span class="sxs-lookup"><span data-stu-id="13a31-106">**Variables and Columns**</span></span>  
 <span data-ttu-id="13a31-107">Genere una expresión que utiliza una variable o una columna de entrada arrastrándolas de la lista de variables y columnas disponibles a una fila de tabla existente en el siguiente panel, o bien a una nueva fila al final de la lista.</span><span class="sxs-lookup"><span data-stu-id="13a31-107">Build an expression that uses a variable or an input column by dragging the variable or column from the list of available variables and columns to an existing table row in the pane below, or to a new row at the bottom of the list.</span></span>  
  
 <span data-ttu-id="13a31-108">**Funciones y operadores**</span><span class="sxs-lookup"><span data-stu-id="13a31-108">**Functions and Operators**</span></span>  
 <span data-ttu-id="13a31-109">Genere una expresión que utiliza una función o un operador para evaluar los datos de entrada y los datos de salida directa arrastrando las funciones y operadores de la lista al siguiente panel.</span><span class="sxs-lookup"><span data-stu-id="13a31-109">Build an expression that uses a function or an operator to evaluate input data and direct output data by dragging functions and operators from the list to the pane below.</span></span>  
  
 <span data-ttu-id="13a31-110">**Nombre de columna derivada**</span><span class="sxs-lookup"><span data-stu-id="13a31-110">**Derived Column Name**</span></span>  
 <span data-ttu-id="13a31-111">Especifique un nombre de columna derivada.</span><span class="sxs-lookup"><span data-stu-id="13a31-111">Provide a derived column name.</span></span> <span data-ttu-id="13a31-112">De forma predeterminada, se muestra una lista numerada de columnas derivadas; no obstante, puede elegir un nombre único descriptivo.</span><span class="sxs-lookup"><span data-stu-id="13a31-112">The default is a numbered list of derived columns; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="13a31-113">**Columna derivada**</span><span class="sxs-lookup"><span data-stu-id="13a31-113">**Derived Column**</span></span>  
 <span data-ttu-id="13a31-114">Seleccione una columna derivada de la lista.</span><span class="sxs-lookup"><span data-stu-id="13a31-114">Select a derived column from the list.</span></span> <span data-ttu-id="13a31-115">Elija si desea agregar la columna derivada como columna de salida nueva o reemplazar los datos de una columna existente.</span><span class="sxs-lookup"><span data-stu-id="13a31-115">Choose whether to add the derived column as a new output column, or to replace the data in an existing column.</span></span>  
  
 <span data-ttu-id="13a31-116">**Expression**</span><span class="sxs-lookup"><span data-stu-id="13a31-116">**Expression**</span></span>  
 <span data-ttu-id="13a31-117">Escriba una expresión o genere una arrastrando elementos de la lista anterior de columnas, variables, funciones y operadores disponibles.</span><span class="sxs-lookup"><span data-stu-id="13a31-117">Type an expression or build one by dragging from the previous list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="13a31-118">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="13a31-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="13a31-119">**Temas relacionados**: [Expresiones de Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operadores &#40;expresión de SSIS&#41;](expressions/operators-ssis-expression.md) y [Funciones &#40;expresión de SSIS&#41](expressions/functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="13a31-119">**Related topics**: [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="13a31-120">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="13a31-120">**Data Type**</span></span>  
 <span data-ttu-id="13a31-121">Si agrega datos a una nueva columna, el cuadro de diálogo **Editor de transformación Columna derivada** evalúa automáticamente la expresión y establece el tipo de datos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="13a31-121">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the data type appropriately.</span></span> <span data-ttu-id="13a31-122">El valor de esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="13a31-122">The value of this column is read-only.</span></span> <span data-ttu-id="13a31-123">Para obtener más información, vea [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="13a31-123">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="13a31-124">**Longitud**</span><span class="sxs-lookup"><span data-stu-id="13a31-124">**Length**</span></span>  
 <span data-ttu-id="13a31-125">Si agrega datos a una nueva columna, el cuadro de diálogo **Editor de transformación Columna derivada** evalúa automáticamente la expresión y establece la longitud de columna para los datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="13a31-125">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the column length for string data.</span></span> <span data-ttu-id="13a31-126">El valor de esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="13a31-126">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="13a31-127">**Precisión**</span><span class="sxs-lookup"><span data-stu-id="13a31-127">**Precision**</span></span>  
 <span data-ttu-id="13a31-128">Si agrega datos a una nueva columna, el cuadro de diálogo **Editor de transformación Columna derivada** establece automáticamente la precisión de los datos numéricos según el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="13a31-128">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the precision for numeric data based on the data type.</span></span> <span data-ttu-id="13a31-129">El valor de esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="13a31-129">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="13a31-130">**Escala**</span><span class="sxs-lookup"><span data-stu-id="13a31-130">**Scale**</span></span>  
 <span data-ttu-id="13a31-131">Si agrega datos a una nueva columna, el cuadro de diálogo **Editor de transformación Columna derivada** establece automáticamente la escala de los datos numéricos según el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="13a31-131">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the scale for numeric data based on the data type.</span></span> <span data-ttu-id="13a31-132">El valor de esta columna es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="13a31-132">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="13a31-133">**Página de códigos**</span><span class="sxs-lookup"><span data-stu-id="13a31-133">**Code Page**</span></span>  
 <span data-ttu-id="13a31-134">Si agrega datos a una nueva columna, el cuadro de diálogo **Editor de transformación Columna derivada** establece automáticamente la página de códigos para el tipo de datos DT_STR.</span><span class="sxs-lookup"><span data-stu-id="13a31-134">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets code page for the DT_STR data type.</span></span> <span data-ttu-id="13a31-135">Puede actualizar la **Página de códigos**.</span><span class="sxs-lookup"><span data-stu-id="13a31-135">You can update **Code Page**.</span></span>  
  
 <span data-ttu-id="13a31-136">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="13a31-136">**Configure error output**</span></span>  
 <span data-ttu-id="13a31-137">Especifique cómo quiere controlar los errores mediante el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="13a31-137">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a31-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13a31-138">See Also</span></span>  
 <span data-ttu-id="13a31-139">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="13a31-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="13a31-140">Derivar valores de columna mediante la transformación Columna derivada</span><span class="sxs-lookup"><span data-stu-id="13a31-140">Derive Column Values by Using the Derived Column Transformation</span></span>](data-flow/transformations/derive-column-values-by-using-the-derived-column-transformation.md)  
  
  
