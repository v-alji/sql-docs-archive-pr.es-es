---
title: Generador MDX (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.mdxbuilderdialof.f1
helpviewer_keywords:
- MDX Builder dialog box
ms.assetid: fecbf093-65ea-4e1b-b637-f04876f1cb0f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 391f4abe953184470be60cca41d53ee20e965423
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673937"
---
# <a name="mdx-builder-analysis-services---multidimensional-data"></a><span data-ttu-id="4431d-102">Generador MDX (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="4431d-102">MDX Builder (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4431d-103">Use el cuadro de diálogo **Generador MDX** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para crear una expresión multidimensional (MDX).</span><span class="sxs-lookup"><span data-stu-id="4431d-103">Use the **MDX Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to build a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="4431d-104">Para mostrar el cuadro de diálogo **Generador MDX** , haga clic en el botón de **edición** de puntos suspensivos de MDX (**...**) de la opción **permitir la lectura del contenido del cubo** , la opción **permitir la lectura de un contingente de contenido de celda en la seguridad de celda** o la opción permitir la **lectura y escritura del contenido del cubo** en la página **datos de celda** del **Diseñador de roles**.</span><span class="sxs-lookup"><span data-stu-id="4431d-104">You can display the **MDX Builder** dialog box by clicking the **Edit MDX** ellipsis button (**...**) for the **Allow reading of cube content** option, the **Allow reading of cell content contingent on cell security** option, or the **Allow reading and writing of cube content** option on the **Cell Data** page of **Role Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4431d-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="4431d-105">Options</span></span>  
  
|<span data-ttu-id="4431d-106">Término</span><span class="sxs-lookup"><span data-stu-id="4431d-106">Term</span></span>|<span data-ttu-id="4431d-107">Definición</span><span class="sxs-lookup"><span data-stu-id="4431d-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="4431d-108">**Expression**</span><span class="sxs-lookup"><span data-stu-id="4431d-108">**Expression**</span></span>|<span data-ttu-id="4431d-109">Escriba la expresión MDX que debe utilizarse.</span><span class="sxs-lookup"><span data-stu-id="4431d-109">Type the MDX expression to be used.</span></span>|  
|<span data-ttu-id="4431d-110">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="4431d-110">**Check**</span></span>|<span data-ttu-id="4431d-111">Haga clic en **Comprobar** para probar la expresión MDX definida en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="4431d-111">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="4431d-112">**Metadata**</span><span class="sxs-lookup"><span data-stu-id="4431d-112">**Metadata**</span></span>|<span data-ttu-id="4431d-113">Muestra los metadatos del objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actual que pueden incluirse en la expresión MDX definida en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="4431d-113">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="4431d-114">Para copiar la sintaxis MDX del elemento seleccionado, haga clic con el botón derecho en el elemento y seleccione **Copiar** en el menú contextual, o bien arrastre el elemento seleccionado a **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="4431d-114">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="4431d-115">**Funciones**</span><span class="sxs-lookup"><span data-stu-id="4431d-115">**Functions**</span></span>|<span data-ttu-id="4431d-116">Muestra las funciones de MDX disponibles para la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] actual.</span><span class="sxs-lookup"><span data-stu-id="4431d-116">Displays available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="4431d-117">Los elementos enumerados se recuperan del conjunto de filas del esquema MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="4431d-117">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="4431d-118">Para copiar la sintaxis MDX del elemento seleccionado, haga clic con el botón derecho en el elemento y seleccione **Copiar** en el menú contextual, o bien arrastre el elemento seleccionado a **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="4431d-118">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4431d-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4431d-119">See Also</span></span>  
 <span data-ttu-id="4431d-120">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4431d-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 <span data-ttu-id="4431d-121">[Datos de celda &#40;diseñador de roles&#41; &#40;Analysis Services de datos multidimensionales&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="4431d-121">[Cell Data &#40;Role Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span></span>  
  
  
