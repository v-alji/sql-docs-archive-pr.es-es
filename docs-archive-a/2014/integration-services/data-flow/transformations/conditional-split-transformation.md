---
title: Transformación División condicional | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittrans.f1
helpviewer_keywords:
- Conditional Split transformation
- route rows to different outputs [Integration Services]
ms.assetid: 3f8b5825-226f-413c-ba8f-0bb931ca3770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96ff4b177992c329908ebc93df8f6220168e634d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674237"
---
# <a name="conditional-split-transformation"></a><span data-ttu-id="99917-102">División condicional, transformación</span><span class="sxs-lookup"><span data-stu-id="99917-102">Conditional Split Transformation</span></span>
  <span data-ttu-id="99917-103">La transformación División condicional puede dirigir filas de datos a salidas diferentes en función del contenido de los datos.</span><span class="sxs-lookup"><span data-stu-id="99917-103">The Conditional Split transformation can route data rows to different outputs depending on the content of the data.</span></span> <span data-ttu-id="99917-104">La implementación de la transformación División condicional es similar a una estructura de decisión CASE en un lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="99917-104">The implementation of the Conditional Split transformation is similar to a CASE decision structure in a programming language.</span></span> <span data-ttu-id="99917-105">Evalúa expresiones y, en función de los resultados, dirige la fila de datos a la salida especificada.</span><span class="sxs-lookup"><span data-stu-id="99917-105">The transformation evaluates expressions, and based on the results, directs the data row to the specified output.</span></span> <span data-ttu-id="99917-106">Esta transformación también proporciona una salida predeterminada, por lo que si una fila no coincide con ninguna expresión, se dirige a la salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="99917-106">This transformation also provides a default output, so that if a row matches no expression it is directed to the default output.</span></span>  
  
## <a name="configuration-of-the-conditional-split-transformation"></a><span data-ttu-id="99917-107">Configuración de la transformación División condicional</span><span class="sxs-lookup"><span data-stu-id="99917-107">Configuration of the Conditional Split Transformation</span></span>  
 <span data-ttu-id="99917-108">Puede configurar la transformación División condicional de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="99917-108">You can configure the Conditional Split transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="99917-109">Proporcionar una expresión cuya evaluación devuelva un valor booleano para cada condición que desee probar con la transformación.</span><span class="sxs-lookup"><span data-stu-id="99917-109">Provide an expression that evaluates to a Boolean for each condition you want the transformation to test.</span></span>  
  
-   <span data-ttu-id="99917-110">Especificar el orden de evaluación de las condiciones.</span><span class="sxs-lookup"><span data-stu-id="99917-110">Specify the order in which the conditions are evaluated.</span></span> <span data-ttu-id="99917-111">El orden es importante, ya que una fila se envía a la salida correspondiente a la primera condición que dé como resultado True.</span><span class="sxs-lookup"><span data-stu-id="99917-111">Order is significant, because a row is sent to the output corresponding to the first condition that evaluates to true.</span></span>  
  
-   <span data-ttu-id="99917-112">Especificar la salida predeterminada para la transformación.</span><span class="sxs-lookup"><span data-stu-id="99917-112">Specify the default output for the transformation.</span></span> <span data-ttu-id="99917-113">La transformación requiere que se especifique una salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="99917-113">The transformation requires that a default output be specified.</span></span>  
  
 <span data-ttu-id="99917-114">Cada fila de entrada solo se puede enviar a una salida, la correspondiente a la primera condición que resulte ser verdadera.</span><span class="sxs-lookup"><span data-stu-id="99917-114">Each input row can be sent to only one output, that being the output for the first condition that evaluates to true.</span></span> <span data-ttu-id="99917-115">Por ejemplo, las siguientes condiciones dirigen las filas de la columna **FirstName** que empiecen por la letra *A* a una salida, las filas que empiecen por la letra *B* a una salida diferente y todas las demás filas a la salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="99917-115">For example, the following conditions direct any rows in the **FirstName** column that begin with the letter *A* to one output, rows that begin with the letter *B* to a different output, and all other rows to the default output.</span></span>  
  
 <span data-ttu-id="99917-116">Salida 1</span><span class="sxs-lookup"><span data-stu-id="99917-116">Output 1</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "A"`  
  
 <span data-ttu-id="99917-117">Salida 2</span><span class="sxs-lookup"><span data-stu-id="99917-117">Output 2</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "B"`  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="99917-118">incluye funciones y operadores que se pueden utilizar para crear expresiones que evalúen los datos de entrada y dirijan los datos de salida.</span><span class="sxs-lookup"><span data-stu-id="99917-118">includes functions and operators that you can use to create the expressions that evaluate input data and direct output data.</span></span> <span data-ttu-id="99917-119">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="99917-119">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="99917-120">La transformación División condicional incluye la propiedad personalizada `FriendlyExpression`.</span><span class="sxs-lookup"><span data-stu-id="99917-120">The Conditional Split transformation includes the `FriendlyExpression` custom property.</span></span> <span data-ttu-id="99917-121">Esta propiedad se puede actualizar a través de una expresión de propiedad, al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="99917-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="99917-122">Para más información, vea [Usar expresiones de propiedad en paquetes](../../expressions/use-property-expressions-in-packages.md) y [Propiedades personalizadas de transformación](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="99917-122">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="99917-123">Esta transformación tiene una entrada, una o más salidas, y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="99917-123">This transformation has one input, one or more outputs, and one error output.</span></span>  
  
 <span data-ttu-id="99917-124">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="99917-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="99917-125">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación División condicional** , vea [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="99917-125">For more information about the properties that you can set in the **Conditional Split Transformation Editor** dialog box, see [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="99917-126">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="99917-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="99917-127">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="99917-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="99917-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="99917-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="99917-129">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="99917-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="99917-130">Para obtener más información sobre cómo establecer valores de propiedades, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="99917-130">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="99917-131">Dividir un conjunto de datos usando la transformación División condicional</span><span class="sxs-lookup"><span data-stu-id="99917-131">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
-   [<span data-ttu-id="99917-132">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="99917-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="99917-133">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="99917-133">Related Tasks</span></span>  
 [<span data-ttu-id="99917-134">Dividir un conjunto de datos usando la transformación División condicional</span><span class="sxs-lookup"><span data-stu-id="99917-134">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
## <a name="see-also"></a><span data-ttu-id="99917-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99917-135">See Also</span></span>  
 <span data-ttu-id="99917-136">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="99917-136">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="99917-137">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="99917-137">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
