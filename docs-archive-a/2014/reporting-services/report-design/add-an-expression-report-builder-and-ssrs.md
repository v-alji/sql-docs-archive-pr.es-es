---
title: Agregar una expresión (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 16f414bfad47ae92681de50eb576a6ac2cb3f5fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744485"
---
# <a name="add-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="d183d-102">Agregar una expresión (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="d183d-102">Add an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d183d-103">Las expresiones se usan en los informes para definir propiedades de elementos de informe, filtros, grupos, criterios de ordenación, cadenas de conexión y valores de parámetros.</span><span class="sxs-lookup"><span data-stu-id="d183d-103">Expressions are used throughout a report for defining report item properties, filters, groups, sort order, connection strings, and parameter values.</span></span> <span data-ttu-id="d183d-104">Las expresiones comienzan por un signo igual (=) y se escriben en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d183d-104">Expressions begin with an equal sign (=) and are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="d183d-105">El procesador de informes, que combina el resultado de la evaluación con elementos de diseño de informe, evalúa las expresiones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d183d-105">They are evaluated at run time by the report processor, which combines the evaluation result with report layout elements.</span></span>  
  
 <span data-ttu-id="d183d-106">Las expresiones pueden ser simples o complejas.</span><span class="sxs-lookup"><span data-stu-id="d183d-106">Expressions can be simple or complex.</span></span> <span data-ttu-id="d183d-107">Una expresión simple hace referencia a un único elemento de una colección integrada.</span><span class="sxs-lookup"><span data-stu-id="d183d-107">Simple expression refer to a single item in a built-in collection.</span></span> <span data-ttu-id="d183d-108">Las expresiones complejas pueden contener constantes, operadores, elementos de recopilación globales y llamadas a funciones.</span><span class="sxs-lookup"><span data-stu-id="d183d-108">Complex expressions can contain constants, operators, global collection items, and function calls.</span></span> <span data-ttu-id="d183d-109">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d183d-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a><span data-ttu-id="d183d-110">Para agregar una expresión a un cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="d183d-110">To add an expression to a text box</span></span>  
  
-   <span data-ttu-id="d183d-111">En la vista **Diseño** , haga clic en el cuadro de texto de la superficie de diseño al que desea agregar una expresión.</span><span class="sxs-lookup"><span data-stu-id="d183d-111">In **Design** view, click the text box on the design surface to which you want to add an expression.</span></span>  
  
    -   <span data-ttu-id="d183d-112">Si se trata de una expresión simple, escriba el texto para mostrar de la expresión en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d183d-112">For a simple expression, type the display text for the expression in the text box.</span></span> <span data-ttu-id="d183d-113">Por ejemplo, para el campo de conjunto de datos Sales, escriba `[Sales]`.</span><span class="sxs-lookup"><span data-stu-id="d183d-113">For example, for the dataset field Sales, type `[Sales]`.</span></span>  
  
    -   <span data-ttu-id="d183d-114">Si se trata de una expresión compleja, haga clic con el botón derecho en el cuadro de texto y seleccione **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="d183d-114">For a complex expression, right-click the text box, and select **Expression**.</span></span> <span data-ttu-id="d183d-115">Se abre el cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="d183d-115">The **Expression** dialog box opens.</span></span> <span data-ttu-id="d183d-116">Escriba o cree de forma interactiva la expresión después del signo '=' en el panel de expresión y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="d183d-116">Type or interactively create your expression after the '=' in the expression pane, and then click OK.</span></span>  
  
         <span data-ttu-id="d183d-117">La expresión aparece en la superficie de diseño como `<<Expr>>`.</span><span class="sxs-lookup"><span data-stu-id="d183d-117">The expression appears on the design surface as `<<Expr>>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d183d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d183d-118">See Also</span></span>  
 <span data-ttu-id="d183d-119">[Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d183d-119">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d183d-120">[Cuadros de texto &#40;Generador de informes y SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d183d-120">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d183d-121">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d183d-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d183d-122">[Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d183d-122">[Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d183d-123">[Ejemplos de expresión de grupo &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d183d-123">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d183d-124">[Expresión &#40;cuadro de diálogo del Generador de informes&#41;](../expression-dialog-box-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d183d-124">[Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md) </span></span>  
 <span data-ttu-id="d183d-125">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d183d-125">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d183d-126">Agregar código a un informe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d183d-126">Add Code to a Report &#40;SSRS&#41;</span></span>](add-code-to-a-report-ssrs.md)  
  
  
