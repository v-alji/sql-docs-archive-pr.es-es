---
title: Editor de transformación división condicional | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittransformation.f1
helpviewer_keywords:
- Conditional Split Transformation Editor
ms.assetid: c30e1633-537a-4837-9991-6203c6f2a21e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386a93eb7c3058c7c3e98f2b652199d115d841f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663637"
---
# <a name="conditional-split-transformation-editor"></a><span data-ttu-id="b9d18-102">División condicional, editor de transformación</span><span class="sxs-lookup"><span data-stu-id="b9d18-102">Conditional Split Transformation Editor</span></span>
  <span data-ttu-id="b9d18-103">Use el cuadro de diálogo **Editor de transformación División condicional** para crear expresiones, establecer el orden de evaluación de expresiones y asignar un nombre a los resultados de una división condicional.</span><span class="sxs-lookup"><span data-stu-id="b9d18-103">Use the **Conditional Split Transformation Editor** dialog box to create expressions, set the order in which expressions are evaluated, and name the outputs of a conditional split.</span></span> <span data-ttu-id="b9d18-104">Este cuadro de diálogo incluye operadores y funciones matemáticas, de cadenas y de fecha y hora que puede utilizar para generar expresiones.</span><span class="sxs-lookup"><span data-stu-id="b9d18-104">This dialog box includes mathematical, string, and date/time functions and operators that you can use to build expressions.</span></span> <span data-ttu-id="b9d18-105">La primera condición evaluada como True determinará la salida a la que se dirigirá una fila.</span><span class="sxs-lookup"><span data-stu-id="b9d18-105">The first condition that evaluates as true determines the output to which a row is directed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9d18-106">La transformación División condicional dirige cada fila de entrada a una sola salida.</span><span class="sxs-lookup"><span data-stu-id="b9d18-106">The Conditional Split transformation directs each input row to one output only.</span></span> <span data-ttu-id="b9d18-107">Si escribe diversas condiciones, la transformación enviará cada fila a la primera salida para la que la condición es True y descartará las siguientes condiciones para dicha fila.</span><span class="sxs-lookup"><span data-stu-id="b9d18-107">If you enter multiple conditions, the transformation sends each row to the first output for which the condition is true and disregards subsequent conditions for that row.</span></span> <span data-ttu-id="b9d18-108">Si necesita evaluar varias condiciones sucesivamente, podría necesitar concatenar diversas transformaciones de División condicional en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="b9d18-108">If you need to evaluate several conditions successively, you may need to concatenate multiple Conditional Split transformations in the data flow.</span></span>  
  
 <span data-ttu-id="b9d18-109">Para más información sobre la transformación División condicional, vea [Transformación División condicional](data-flow/transformations/conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="b9d18-109">To learn more about the Conditional Split transformation, see [Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9d18-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="b9d18-110">Options</span></span>  
 <span data-ttu-id="b9d18-111">**Pedido**</span><span class="sxs-lookup"><span data-stu-id="b9d18-111">**Order**</span></span>  
 <span data-ttu-id="b9d18-112">Seleccione una fila y utilice las teclas de dirección de la derecha para cambiar el orden de evaluación de las expresiones.</span><span class="sxs-lookup"><span data-stu-id="b9d18-112">Select a row and use the arrow keys at right to change the order in which to evaluate expressions.</span></span>  
  
 <span data-ttu-id="b9d18-113">**Nombre de salida**</span><span class="sxs-lookup"><span data-stu-id="b9d18-113">**Output Name**</span></span>  
 <span data-ttu-id="b9d18-114">Escriba un nombre de salida.</span><span class="sxs-lookup"><span data-stu-id="b9d18-114">Provide an output name.</span></span> <span data-ttu-id="b9d18-115">El valor predeterminado es una lista numerada de casos, pero puede elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="b9d18-115">The default is a numbered list of cases; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="b9d18-116">**Condition**</span><span class="sxs-lookup"><span data-stu-id="b9d18-116">**Condition**</span></span>  
 <span data-ttu-id="b9d18-117">Escriba una expresión o genere una arrastrándola de la lista de columnas, variables, funciones y operadores disponibles.</span><span class="sxs-lookup"><span data-stu-id="b9d18-117">Type an expression or build one by dragging from the list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="b9d18-118">Puede especificar el valor de esta propiedad con una expresión de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b9d18-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="b9d18-119">\*\*Temas relacionados: \*\*  [Expresiones de Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operadores &#40;expresión de SSIS&#41;](expressions/operators-ssis-expression.md) y [Funciones &#40;expresión de SSIS&#41](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="b9d18-119">**Related topics:**  [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="b9d18-120">**Nombre de salida predeterminado**</span><span class="sxs-lookup"><span data-stu-id="b9d18-120">**Default output name**</span></span>  
 <span data-ttu-id="b9d18-121">Escriba un nombre para la salida predeterminada o utilice el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b9d18-121">Type a name for the default output, or use the default.</span></span>  
  
 <span data-ttu-id="b9d18-122">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="b9d18-122">**Configure error output**</span></span>  
 <span data-ttu-id="b9d18-123">Especifique cómo quiere controlar los errores mediante el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="b9d18-123">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d18-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9d18-124">See Also</span></span>  
 <span data-ttu-id="b9d18-125">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b9d18-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="b9d18-126">Dividir un conjunto de datos usando la transformación División condicional</span><span class="sxs-lookup"><span data-stu-id="b9d18-126">Split a Dataset by Using the Conditional Split Transformation</span></span>](data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
