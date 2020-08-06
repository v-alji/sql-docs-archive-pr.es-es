---
title: Agregar un rectángulo o un contenedor (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10061"
- sql12.rtp.rptdesigner.rectangleproperties.general.f1
ms.assetid: f905c35f-754d-4d02-80f3-85e29ddda826
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fddda2f02b9f370d9742ae6add5bae444f8f55f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662557"
---
# <a name="add-a-rectangle-or-container-report-builder-and-ssrs"></a><span data-ttu-id="e32b9-102">Agregar un rectángulo o un contenedor (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="e32b9-102">Add a Rectangle or Container (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e32b9-103">Agregue un rectángulo al informe si desea incluir en él un elemento gráfico para separar distintas áreas, resaltarlas o proporcionar un fondo para uno o más elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="e32b9-103">Add a rectangle to your report when you want a graphical element to separate areas of the report, emphasize areas of a report, or provide a background for one or more report items.</span></span> <span data-ttu-id="e32b9-104">Los rectángulos también se usan como contenedores para ayudar a controlar la manera en la que se representan las regiones de datos en un informe.</span><span class="sxs-lookup"><span data-stu-id="e32b9-104">Rectangles are also used as containers to help control the way data regions render in a report.</span></span> <span data-ttu-id="e32b9-105">Puede personalizar la apariencia de un rectángulo editando sus propiedades, como los colores del borde y de segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e32b9-105">You can customize the appearance of a rectangle by editing rectangle properties such as the background and border colors.</span></span> <span data-ttu-id="e32b9-106">Para más información sobre el uso de un rectángulo como contenedor, vea [Rectángulos y líneas &#40;Generador de informes y SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) y [Mostrar los mismos datos en una matriz y en un gráfico &#40;Generador de informes&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e32b9-106">For more information about using a rectangle as a container, see [Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) and [Display the Same Data on a Matrix and a Chart &#40;Report Builder&#41;](display-the-same-data-on-a-matrix-and-a-chart-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-rectangle"></a><span data-ttu-id="e32b9-107">Para agregar un rectángulo</span><span class="sxs-lookup"><span data-stu-id="e32b9-107">To add a rectangle</span></span>  
  
1.  <span data-ttu-id="e32b9-108">En la pestaña **Insertar** , en el grupo **Elementos de informe** , haga clic en **Rectángulo.**</span><span class="sxs-lookup"><span data-stu-id="e32b9-108">On the **Insert** tab, in the **Report Items** group, click **Rectangle.**</span></span>  
  
2.  <span data-ttu-id="e32b9-109">En la superficie de diseño, haga clic en la ubicación en la que desea que se encuentre la esquina superior izquierda del rectángulo y arrástrelo hasta donde desee que esté la esquina inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="e32b9-109">On the design surface, click the location where you want the upper left corner of the rectangle, and drag to where you want the lower-right corner.</span></span>  
  
     <span data-ttu-id="e32b9-110">Tenga en cuenta que cuando mueve el cursor, da la impresión de que el cursor se alinea con otros objetos de la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="e32b9-110">Note that as you move the cursor, "snap lines" appear as the cursor lines up with other objects on the design surface.</span></span> <span data-ttu-id="e32b9-111">Esto le será de ayuda si desea que los objetos estén alineados.</span><span class="sxs-lookup"><span data-stu-id="e32b9-111">These help you if you want objects to be aligned.</span></span>  
  
### <a name="to-create-a-container"></a><span data-ttu-id="e32b9-112">Para crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="e32b9-112">To create a container</span></span>  
  
1.  <span data-ttu-id="e32b9-113">Agregue un elemento de rectángulo al informe.</span><span class="sxs-lookup"><span data-stu-id="e32b9-113">Add a rectangle report item to the report.</span></span>  
  
2.  <span data-ttu-id="e32b9-114">Arrastre otros elementos de informe al rectángulo.</span><span class="sxs-lookup"><span data-stu-id="e32b9-114">Drag other report items into the rectangle.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e32b9-115">Un rectángulo es solamente un contenedor para los elementos que crea en el rectángulo o que arrastra hasta él.</span><span class="sxs-lookup"><span data-stu-id="e32b9-115">A rectangle is only a container for items that you either create in the rectangle or drag into the rectangle.</span></span> <span data-ttu-id="e32b9-116">Si dibuja un rectángulo alrededor de un elemento que ya existe en la superficie de diseño, el rectángulo no actuará como su contenedor.</span><span class="sxs-lookup"><span data-stu-id="e32b9-116">If you draw a rectangle around an item that already exists on the design surface, the rectangle will not act as its container.</span></span>  
  
### <a name="to-change-rectangle-properties-such-as-color-style-or-weight"></a><span data-ttu-id="e32b9-117">Para cambiar propiedades de rectángulo como color, estilo o peso</span><span class="sxs-lookup"><span data-stu-id="e32b9-117">To change rectangle properties such as color, style, or weight</span></span>  
  
1.  <span data-ttu-id="e32b9-118">Seleccione el rectángulo y, a continuación, haga clic en las opciones de color de línea, estilo o peso en la sección **Borde** de la pestaña Inicio.</span><span class="sxs-lookup"><span data-stu-id="e32b9-118">Select the rectangle, and then click the line color, style, or weight options in the **Border** section of the Home tab.</span></span>  
  
2.  <span data-ttu-id="e32b9-119">Haga clic en la flecha situada al lado del botón **Borde** para determinar qué lados del rectángulo va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="e32b9-119">Click the arrow next to the **Border** button to determine which sides of the rectangle to change.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e32b9-120">Si establece el estilo de línea en **doble** y el ancho de línea es 1 1/2 PT o más estrecho, es posible que la línea no aparezca como doble cuando ejecute el informe en Generador de informes, Diseñador de informes o administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="e32b9-120">If you set the line style to **Double** and the line width is 1 1/2 pt or narrower, the line may not appear double when you run the report in Report Builder, Report Designer, or Report Manager.</span></span> <span data-ttu-id="e32b9-121">Aparecerá como doble cuando exporte el informe a otros formatos, como Microsoft Word y Acrobat PDF.</span><span class="sxs-lookup"><span data-stu-id="e32b9-121">It will appear double when you export the report to other formats such as Microsoft Word and Acrobat PDF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32b9-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e32b9-122">See Also</span></span>  
 <span data-ttu-id="e32b9-123">[Rectángulos y líneas &#40;Generador de informes y SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e32b9-123">[Rectangles and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e32b9-124">Comportamientos de la representación &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e32b9-124">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
