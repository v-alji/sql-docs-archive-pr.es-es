---
title: Usar constantes en expresiones (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b8ae650b-0f46-4848-b62b-15f8a40751b8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d95005a04482cb03d3bb3860aea695c7e7969255
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671440"
---
# <a name="constants-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="542e1-102">Usar constantes en expresiones (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="542e1-102">Constants in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="542e1-103">Una constante consta de texto literal o de texto predefinido.</span><span class="sxs-lookup"><span data-stu-id="542e1-103">A constant consists of literal text or predefined text.</span></span> <span data-ttu-id="542e1-104">El procesador de informes tiene acceso a las constantes predefinidas para que cuando se incluyan en una expresión, los valores que representan se sustituyan en la expresión antes de evaluarla.</span><span class="sxs-lookup"><span data-stu-id="542e1-104">The report processor has access to predefined constants so that when you include them in an expression, the values they represent are substituted in the expression before it is evaluated.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="literal-text"></a><span data-ttu-id="542e1-105">Texto literal</span><span class="sxs-lookup"><span data-stu-id="542e1-105">Literal Text</span></span>  
 <span data-ttu-id="542e1-106">En una expresión, el texto literal es texto que está encerrado entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="542e1-106">In an expression, literal text is text that is in double quotation marks.</span></span> <span data-ttu-id="542e1-107">También puede escribir directamente el texto en un cuadro de texto sin las comillas dobles cuando no forma parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="542e1-107">You can also type text directly into a text box without double quotation marks if it is not part of an expression.</span></span> <span data-ttu-id="542e1-108">Si el valor del cuadro de texto no comienza por un signo igual (=), el texto se trata como texto literal.</span><span class="sxs-lookup"><span data-stu-id="542e1-108">If the text box value does not begin with an equal sign (=), the text is treated as literal text.</span></span> <span data-ttu-id="542e1-109">En la tabla siguiente se muestran varios ejemplos de texto literal en una expresión.</span><span class="sxs-lookup"><span data-stu-id="542e1-109">The following table shows several examples of literal text in an expression.</span></span>  
  
|<span data-ttu-id="542e1-110">Constante</span><span class="sxs-lookup"><span data-stu-id="542e1-110">Constant</span></span>|<span data-ttu-id="542e1-111">Display text</span><span class="sxs-lookup"><span data-stu-id="542e1-111">Display text</span></span>|<span data-ttu-id="542e1-112">Texto de la expresión</span><span class="sxs-lookup"><span data-stu-id="542e1-112">Expression text</span></span>|  
|--------------|------------------|---------------------|  
|<span data-ttu-id="542e1-113">Report run at:</span><span class="sxs-lookup"><span data-stu-id="542e1-113">Report run at:</span></span>|<\<Expr>>|`="Report run at: " & Globals!ExecutionTime`|  
|<span data-ttu-id="542e1-114">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="542e1-114">Adventure Works Cycles</span></span>|<span data-ttu-id="542e1-115">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="542e1-115">Adventure Works Cycles</span></span>|<span data-ttu-id="542e1-116">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="542e1-116">Adventure Works Cycles</span></span>|  
|<span data-ttu-id="542e1-117">[Texto que se muestra entre corchetes]</span><span class="sxs-lookup"><span data-stu-id="542e1-117">[Bracketed display text]</span></span>|<span data-ttu-id="542e1-118">\\[Texto que se muestra entre corchetes\\]</span><span class="sxs-lookup"><span data-stu-id="542e1-118">\\[Bracketed display text\\]</span></span>|<span data-ttu-id="542e1-119">[Texto que se muestra entre corchetes]</span><span class="sxs-lookup"><span data-stu-id="542e1-119">[Bracketed display text]</span></span>|  
  
## <a name="rdl-constants"></a><span data-ttu-id="542e1-120">Constantes RDL</span><span class="sxs-lookup"><span data-stu-id="542e1-120">RDL Constants</span></span>  
 <span data-ttu-id="542e1-121">Puede usar constantes definidas en lenguaje RDL (Report Definition Language) en una expresión.</span><span class="sxs-lookup"><span data-stu-id="542e1-121">You can use constants defined in Report Definition Language (RDL) in an expression.</span></span> <span data-ttu-id="542e1-122">En el cuadro de diálogo **Expresión** , las constantes aparecen al crear una expresión para una propiedad de informe que solo acepta ciertos valores válidos, también conocidos como tipos enumerados.</span><span class="sxs-lookup"><span data-stu-id="542e1-122">In the **Expression** dialog box, constants appear when you create an expression for a report property that only accepts certain valid values, also known as enumerated types.</span></span> <span data-ttu-id="542e1-123">En la tabla siguiente se muestran dos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="542e1-123">The following table shows two examples.</span></span>  
  
|<span data-ttu-id="542e1-124">Propiedad</span><span class="sxs-lookup"><span data-stu-id="542e1-124">Property</span></span>|<span data-ttu-id="542e1-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="542e1-125">Description</span></span>|<span data-ttu-id="542e1-126">Valores</span><span class="sxs-lookup"><span data-stu-id="542e1-126">Values</span></span>|  
|--------------|-----------------|------------|  
|<span data-ttu-id="542e1-127">TextAlign</span><span class="sxs-lookup"><span data-stu-id="542e1-127">TextAlign</span></span>|<span data-ttu-id="542e1-128">Valores válidos para alinear texto en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="542e1-128">Valid values for aligning text in a text box.</span></span>|<span data-ttu-id="542e1-129">General, Left, Center, Right</span><span class="sxs-lookup"><span data-stu-id="542e1-129">General, Left, Center, Right</span></span>|  
|<span data-ttu-id="542e1-130">BorderStyle</span><span class="sxs-lookup"><span data-stu-id="542e1-130">BorderStyle</span></span>|<span data-ttu-id="542e1-131">Valores válidos para una línea agregada a un informe.</span><span class="sxs-lookup"><span data-stu-id="542e1-131">Valid values for a line added to a report.</span></span>|<span data-ttu-id="542e1-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span><span class="sxs-lookup"><span data-stu-id="542e1-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span></span>|  
  
## <a name="visual-basic-constants"></a><span data-ttu-id="542e1-133">Constantes de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="542e1-133">Visual Basic Constants</span></span>  
 <span data-ttu-id="542e1-134">Puede usar constantes definidas en la biblioteca en tiempo de ejecución de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] en una expresión.</span><span class="sxs-lookup"><span data-stu-id="542e1-134">You can use constants defined in the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library in an expression.</span></span> <span data-ttu-id="542e1-135">Por ejemplo, puede usar la constante `DateInterval.Day`.</span><span class="sxs-lookup"><span data-stu-id="542e1-135">For example, you can use the constant `DateInterval.Day`.</span></span> <span data-ttu-id="542e1-136">La siguiente expresión para la fecha 10 de enero de 2008 devuelve el número 10:</span><span class="sxs-lookup"><span data-stu-id="542e1-136">The following expression for the date January 10, 2008 returns the number 10:</span></span>  
  
 `=DatePart("d",Globals!ExecutionTime)`  
  
## <a name="clr-constants"></a><span data-ttu-id="542e1-137">Constantes CLR</span><span class="sxs-lookup"><span data-stu-id="542e1-137">CLR Constants</span></span>  
 <span data-ttu-id="542e1-138">Puede usar constantes definidas en clases de Common Language Runtime (CLR) de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] en una expresión.</span><span class="sxs-lookup"><span data-stu-id="542e1-138">You can use constants defined in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language run-time (CLR) classes in an expression.</span></span> <span data-ttu-id="542e1-139">En la tabla siguiente se muestra un ejemplo de un color definido por el sistema.</span><span class="sxs-lookup"><span data-stu-id="542e1-139">The following table shows an example of a system-defined color.</span></span>  
  
|<span data-ttu-id="542e1-140">Constante</span><span class="sxs-lookup"><span data-stu-id="542e1-140">Constant</span></span>|<span data-ttu-id="542e1-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="542e1-141">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="542e1-142">MistyRose</span><span class="sxs-lookup"><span data-stu-id="542e1-142">MistyRose</span></span>|<span data-ttu-id="542e1-143">Al crear una expresión para una propiedad de informe que está basada en el color de fondo, puede especificar un color por su nombre.</span><span class="sxs-lookup"><span data-stu-id="542e1-143">When you create an expression for a report property that is based on background color, you can specify a color by name.</span></span> <span data-ttu-id="542e1-144">La lista de los nombres válidos se encuentra en el cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="542e1-144">Valid names are listed in the **Expression** dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="542e1-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="542e1-145">See Also</span></span>  
 <span data-ttu-id="542e1-146">[Expresión (cuadro de diálogo)](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="542e1-146">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="542e1-147">[Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="542e1-147">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="542e1-148">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="542e1-148">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="542e1-149">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="542e1-149">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="542e1-150">Expresión &#40;cuadro de diálogo del Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="542e1-150">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
