---
title: Especificar el tamaño de un indicador mediante una expresión (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab0b86f1-4882-4258-a2b6-c612faecfa4b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b450abb957329b8dbaa4f7f0e4c963c5f63f06b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662528"
---
# <a name="specify-the-size-of-an-indicator-using-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="92a6b-102">Especificar el tamaño de un indicador utilizando una expresión (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="92a6b-102">Specify the Size of an Indicator Using an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="92a6b-103">Además del color, dirección y forma, puede usar el tamaño para maximizar el impacto visual de los indicadores.</span><span class="sxs-lookup"><span data-stu-id="92a6b-103">In addition to color, direction, and shape, you can use size to maximize the visual impact of indicators.</span></span>  
  
 <span data-ttu-id="92a6b-104">Un indicador tiene una colección de estados de indicador denominada IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="92a6b-104">An indicator has a collection of indicator states named IndicatorStates.</span></span> <span data-ttu-id="92a6b-105">La colección IndicatorStates suele tener varios estados.</span><span class="sxs-lookup"><span data-stu-id="92a6b-105">The IndicatorStates collection typically have multiple states.</span></span> <span data-ttu-id="92a6b-106">Cada estado es un miembro de la colección y se representa mediante un icono.</span><span class="sxs-lookup"><span data-stu-id="92a6b-106">Each state is a member of the collection and is represented by an icon.</span></span> <span data-ttu-id="92a6b-107">Juntos, los estados constituyen la colección IndicatorsStates.</span><span class="sxs-lookup"><span data-stu-id="92a6b-107">Together the states constitute the IndicatorsStates collection.</span></span>  
  
 <span data-ttu-id="92a6b-108">Para configurar dinámicamente el tamaño de los iconos, debe establecer propiedades de los miembros de la colección IndicatorsStates en el panel Propiedades del Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="92a6b-108">To dynamically configure the sizes of icons, you set properties of members of the IndicatorsStates collection in the Properties pane of Report Builder.</span></span> <span data-ttu-id="92a6b-109">Si el panel **Propiedades** no está visible, haga clic en la pestaña **Ver** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-109">If the **Properties** pane is not visible, click the **View** tab and select **Properties**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92a6b-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], utilice la ventana **Propiedades** para establecer las propiedades de miembro.</span><span class="sxs-lookup"><span data-stu-id="92a6b-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you use the **Properties** window to set the member properties.</span></span> <span data-ttu-id="92a6b-111">Si la ventana **Propiedades** no está abierta, presione la tecla F4.</span><span class="sxs-lookup"><span data-stu-id="92a6b-111">If the **Properties** window is not open, press the F4 key.</span></span>  
  
 <span data-ttu-id="92a6b-112">El panel **Propiedades** proporciona acceso a las propiedades de la colección IndicatorStates de un indicador.</span><span class="sxs-lookup"><span data-stu-id="92a6b-112">The **Properties** pane provides access to the properties of the IndicatorStates collection of an indicator.</span></span> <span data-ttu-id="92a6b-113">Para configurar los iconos de forma que tengan tamaños distintos, debe establecer la propiedad ScaleFactor de los miembros de la colección IndicatorStates mediante una expresión.</span><span class="sxs-lookup"><span data-stu-id="92a6b-113">You configure the icons to be different sizes by setting the ScaleFactor property of the IndicatorStates collection members using an expression.</span></span> <span data-ttu-id="92a6b-114">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92a6b-114">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="92a6b-115">La expresión usada en este procedimiento se usó también para generar el informe con distintos tamaños de indicadores, como se muestra en [Indicadores &#40;Generador de informes y SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92a6b-115">The expression used in this procedure was also used to generate the report with different sizes of indicators, shown in [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-the-indicator-icon-size-using-an-expression"></a><span data-ttu-id="92a6b-116">Para especificar el tamaño de icono de indicador mediante una expresión</span><span class="sxs-lookup"><span data-stu-id="92a6b-116">To specify the indicator icon size using an expression</span></span>  
  
1.  <span data-ttu-id="92a6b-117">Haga clic en el indicador que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="92a6b-117">Click the indicator you want to change.</span></span>  
  
2.  <span data-ttu-id="92a6b-118">En el panel Propiedades, busque la propiedad IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="92a6b-118">In the Properties pane, locate the IndicatorStates property.</span></span>  
  
     <span data-ttu-id="92a6b-119">Si el panel Propiedades está organizado por categorías, encontrará IndicatorStates en la categoría **Estados** .</span><span class="sxs-lookup"><span data-stu-id="92a6b-119">If the Properties pane is organized by category, you will find IndicatorStates in the **States** category.</span></span>  
  
3.  <span data-ttu-id="92a6b-120">Haga clic en el botón de puntos suspensivos **(…)** situado junto a IndicatorStates.</span><span class="sxs-lookup"><span data-stu-id="92a6b-120">Click the ellipsis **(...)** button next to IndicatorStates.</span></span> <span data-ttu-id="92a6b-121">Se abre el cuadro de diálogo **Editor de la colección IndicatorState** .</span><span class="sxs-lookup"><span data-stu-id="92a6b-121">The **IndicatorState Collection Editor** dialog box opens.</span></span>  
  
     <span data-ttu-id="92a6b-122">Seleccione todos los miembros de la colección.</span><span class="sxs-lookup"><span data-stu-id="92a6b-122">Select all members of the collection.</span></span>  
  
4.  <span data-ttu-id="92a6b-123">En la lista **Selección múltiple de propiedades** , haga clic en la flecha hacia abajo que hay al lado de ScaleFactor y, después, haga clic en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="92a6b-123">In the **Multi-Select Properties** list, click the down arrow next to ScaleFactor and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="92a6b-124">En el cuadro de diálogo **Expresión** escriba la expresión.</span><span class="sxs-lookup"><span data-stu-id="92a6b-124">In the **Expression** dialog box write the expression.</span></span>  
  
     <span data-ttu-id="92a6b-125">La siguiente expresión de ejemplo hace que el icono tenga un tamaño distinto en función del valor del campo **SalesYTD** .</span><span class="sxs-lookup"><span data-stu-id="92a6b-125">The following sample expression makes the icon a different size based on the value of the **SalesYTD** field.</span></span>  
  
     `=IIF(Fields!SalesYTD.value = 0,0,Fields!SalesYTD.value/Max(Fields!SalesYTD.value,"Indicator"))`  
  
     <span data-ttu-id="92a6b-126">Para más información, vea [Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="92a6b-126">For more information, see [Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92a6b-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92a6b-127">See Also</span></span>  
 [<span data-ttu-id="92a6b-128">Indicadores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="92a6b-128">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
