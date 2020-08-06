---
title: Generador de miembros calculados (cuadro de diálogo) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.calculatedmemberbuilderdialog.f1
ms.assetid: 73b89a9f-f403-4ab8-99f7-e3ceb870c260
author: minewiskan
ms.author: owend
ms.openlocfilehash: 240e2f2471bf77c403119fd51278a975badc8358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670088"
---
# <a name="calculated-member-builder-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="5e3f9-102">Generador de miembros calculados (Cuadro de diálogo) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="5e3f9-102">Calculated Member Builder Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5e3f9-103">Use el cuadro de diálogo **Generador de miembros calculados** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para generar un miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-103">Use the **Calculated Member Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to build a calculated member.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e3f9-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="5e3f9-104">Options</span></span>  
  
|<span data-ttu-id="5e3f9-105">Término</span><span class="sxs-lookup"><span data-stu-id="5e3f9-105">Term</span></span>|<span data-ttu-id="5e3f9-106">Definición</span><span class="sxs-lookup"><span data-stu-id="5e3f9-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="5e3f9-107">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5e3f9-107">**Name**</span></span>|<span data-ttu-id="5e3f9-108">Escriba el nombre del miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-108">Type the name of the calculated member.</span></span>|  
|<span data-ttu-id="5e3f9-109">**Jerarquía primaria**</span><span class="sxs-lookup"><span data-stu-id="5e3f9-109">**Parent Hierarchy**</span></span>|<span data-ttu-id="5e3f9-110">Seleccione la jerarquía en la que desea crear el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-110">Select the hierarchy in which to create the calculated member.</span></span>|  
|<span data-ttu-id="5e3f9-111">**Miembro primario**</span><span class="sxs-lookup"><span data-stu-id="5e3f9-111">**Parent Member**</span></span>|<span data-ttu-id="5e3f9-112">Esta opción se habilita si selecciona una jerarquía primaria (que no sea la dimensión `Measures`) con más de un nivel.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-112">This option is enabled if you select a parent hierarchy (other than the `Measures` dimension) that has more than one level.</span></span> <span data-ttu-id="5e3f9-113">Haga clic en el botón de puntos suspensivos (**...**) para seleccionar un miembro primario.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-113">Click the ellipsis (**...**) button to select a parent member.</span></span> <span data-ttu-id="5e3f9-114">El miembro primario determina la ubicación del miembro calculado en la estructura de dimensión.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-114">The parent member determines the location of the calculated member in the dimension structure.</span></span>|  
|<span data-ttu-id="5e3f9-115">**Expression**</span><span class="sxs-lookup"><span data-stu-id="5e3f9-115">**Expression**</span></span>|<span data-ttu-id="5e3f9-116">Escriba la expresión MDX que se utilizará.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-116">Type the MDX expression that will be used.</span></span>|  
|<span data-ttu-id="5e3f9-117">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="5e3f9-117">**Check**</span></span>|<span data-ttu-id="5e3f9-118">Haga clic en **Comprobar** para probar la expresión MDX definida en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-118">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="5e3f9-119">**Metadata**</span><span class="sxs-lookup"><span data-stu-id="5e3f9-119">**Metadata**</span></span>|<span data-ttu-id="5e3f9-120">Muestra los metadatos del objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actual que pueden incluirse en la expresión MDX definida en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-120">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="5e3f9-121">Para copiar la sintaxis MDX del elemento seleccionado, haga clic con el botón derecho en el elemento y seleccione **Copiar**, o arrastre el elemento seleccionado a **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-121">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="5e3f9-122">**Funciones**</span><span class="sxs-lookup"><span data-stu-id="5e3f9-122">**Functions**</span></span>|<span data-ttu-id="5e3f9-123">Muestra las funciones de MDX disponibles para la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actual.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-123">Displays the available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="5e3f9-124">Los elementos enumerados se recuperan del conjunto de filas del esquema MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-124">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="5e3f9-125">Para copiar la sintaxis MDX del elemento seleccionado, haga clic con el botón derecho en el elemento y seleccione **Copiar**, o arrastre el elemento seleccionado a **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="5e3f9-125">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e3f9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e3f9-126">See Also</span></span>  
 [<span data-ttu-id="5e3f9-127">Referencia de expresiones multidimensionales &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="5e3f9-127">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
