---
title: Cálculos (diseñador de cubos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.f1
ms.assetid: 46e2fbe2-bb41-4eaa-91f8-eb2bd3b8d00d
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdbc35a8e47557923b90cda4e72280c3cca940dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670704"
---
# <a name="calculations-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="b68f3-102">Cálculos (Diseñador de cubos) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="b68f3-102">Calculations (Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b68f3-103">Use la pestaña **Cálculos** del Diseñador de cubos para ver y editar cálculos, incluidos miembros calculados, conjuntos con nombre y comandos de script MDX (expresiones multidimensionales) del cubo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b68f3-103">Use the **Calculations** tab in Cube Designer to view and edit calculations, including calculated members, named sets, and Multidimensional Expressions (MDX) script commands for the selected cube.</span></span>  
  
## <a name="form-view-and-script-view"></a><span data-ttu-id="b68f3-104">Vista de formulario y Vista de script</span><span class="sxs-lookup"><span data-stu-id="b68f3-104">Form View and Script View</span></span>  
 <span data-ttu-id="b68f3-105">La pestaña **Cálculos** admite dos vistas diferentes para ver y editar cálculos:</span><span class="sxs-lookup"><span data-stu-id="b68f3-105">The **Calculations** tab supports two different views when viewing or editing calculations:</span></span>  
  
-   <span data-ttu-id="b68f3-106">Vista de formulario</span><span class="sxs-lookup"><span data-stu-id="b68f3-106">Form view</span></span>  
  
     <span data-ttu-id="b68f3-107">Esta vista muestra una vista organizada de los miembros calculados, conjuntos con nombre y comandos de script que contiene el script MDX asociado con el cubo, y proporciona editores de formulario para ver y editar miembros calculados y conjuntos con nombre, así como para mostrar metadatos, funciones y herramientas disponibles en el cubo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-107">This view displays an organized view of the calculated members, named sets, and script commands contained in the MDX script associated with the cube and provides form editors to view and edit calculated members and named sets, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
-   <span data-ttu-id="b68f3-108">Vista de script</span><span class="sxs-lookup"><span data-stu-id="b68f3-108">Script view</span></span>  
  
     <span data-ttu-id="b68f3-109">Para usuarios avanzados, esta vista muestra todo el script MDX asociado con el cubo, y también muestra metadatos, funciones y herramientas disponibles en el cubo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-109">For advanced users, this view displays the entire MDX script associated with the cube, as well as displaying the metadata, functions, and tools available to the cube.</span></span>  
  
## <a name="panes"></a><span data-ttu-id="b68f3-110">Paneles</span><span class="sxs-lookup"><span data-stu-id="b68f3-110">Panes</span></span>  
 <span data-ttu-id="b68f3-111">**Barra de herramientas**</span><span class="sxs-lookup"><span data-stu-id="b68f3-111">**Toolbar**</span></span>  
 <span data-ttu-id="b68f3-112">Use la barra de herramientas de la vista de formulario y la vista de script para realizar operaciones comunes en esta pestaña. Para obtener más información sobre este panel, vea [barra de herramientas &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b68f3-112">Use the toolbar in both form view and script view to perform common operations on this tab. For more information about this pane, see [Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b68f3-113">**Organizador de script**</span><span class="sxs-lookup"><span data-stu-id="b68f3-113">**Script Organizer**</span></span>  
 <span data-ttu-id="b68f3-114">Use el panel **Organizador de scripts** de la vista Formulario para mostrar el contenido del script del cubo en un formato ordenado.</span><span class="sxs-lookup"><span data-stu-id="b68f3-114">Use the **Script Organizer** pane in form view to display the contents of the cube script in an ordered format.</span></span> <span data-ttu-id="b68f3-115">Para más información sobre este panel, vea [Organizador de script &#40;pestaña Cálculo, Diseñador de cubos&#41; &#40;Analysis Services - Datos multidimensionales&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b68f3-115">For more information about this pane, see [Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b68f3-116">**Herramientas de cálculo**</span><span class="sxs-lookup"><span data-stu-id="b68f3-116">**Calculation Tools**</span></span>  
 <span data-ttu-id="b68f3-117">Use el panel **Herramientas de cálculo** de la vista Formulario y la vista de script para mostrar metadatos, funciones y herramientas disponibles para el cubo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-117">Use the **Calculation Tools** pane in both form view and script view to display metadata, functions, and tools available to the cube.</span></span> <span data-ttu-id="b68f3-118">Para más información sobre este panel, vea [Herramientas de cálculo &#40;pestaña Cálculos, Diseñador de cubos&#41; &#40;Analysis Services - Datos multidimensionales&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b68f3-118">For more information about this pane, see [Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b68f3-119">**Editor de script**</span><span class="sxs-lookup"><span data-stu-id="b68f3-119">**Script Editor**</span></span>  
 <span data-ttu-id="b68f3-120">Use el panel **Editor de script** de la vista de script para editar todo el script del cubo y, en la vista Formulario, para editar los comandos contenidos en el script del cubo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-120">Use the **Script Editor** pane in script view to edit the entire cube script and in form view to edit script commands contained in the cube script.</span></span> <span data-ttu-id="b68f3-121">Para más información sobre este panel, vea [Editor de script &#40;pestaña Cálculo, Diseñador de cubos&#41; &#40;Analysis Services - Datos multidimensionales&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b68f3-121">For more information about this pane, see [Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b68f3-122">**Editor de Formulario de miembro calculado**</span><span class="sxs-lookup"><span data-stu-id="b68f3-122">**Calculated Member Form Editor**</span></span>  
 <span data-ttu-id="b68f3-123">Use el panel **Editor de Formulario de miembro calculado** de la vista Formulario para editar miembros calculados en el script del cubo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-123">Use the **Calculated Member Form Editor** pane in form view to edit calculated members in the cube script.</span></span> <span data-ttu-id="b68f3-124">Para más información sobre este panel, vea [Editor de Formulario de miembro calculado &#40;pestaña Cálculos, Diseñador de cubos&#41; &#40;Analysis Services - Datos multidimensionales&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b68f3-124">For more information about this pane, see [Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b68f3-125">**Editor de Formulario de conjuntos con nombres**</span><span class="sxs-lookup"><span data-stu-id="b68f3-125">**Named Set Form Editor**</span></span>  
 <span data-ttu-id="b68f3-126">Use el panel **Editor de Formulario de conjuntos con nombres** de la vista Formulario para editar conjuntos con nombre en el script del cubo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-126">Use the **Named Set Form Editor** pane in form view to edit named sets in the cube script.</span></span> <span data-ttu-id="b68f3-127">Para más información sobre este panel, vea [Editor de Formulario de conjuntos con nombres &#40;pestaña Cálculo, Diseñador de cubos&#41; &#40;Analysis Services - Datos multidimensionales&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b68f3-127">For more information about this pane, see [Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68f3-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b68f3-128">See Also</span></span>  
 <span data-ttu-id="b68f3-129">[Objetos de cubo &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b68f3-129">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="b68f3-130">[Realizan](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="b68f3-130">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="b68f3-131">[Aspectos básicos de scripting de MDX &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b68f3-131">[MDX Scripting Fundamentals &#40;Analysis Services&#41;](multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="b68f3-132">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b68f3-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b68f3-133">Crear conjuntos con nombre</span><span class="sxs-lookup"><span data-stu-id="b68f3-133">Create Named Sets</span></span>](multidimensional-models/create-named-sets.md)  
  
  
