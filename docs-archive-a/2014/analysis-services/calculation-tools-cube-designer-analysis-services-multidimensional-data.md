---
title: Herramientas de cálculo (pestaña cálculos, diseñador de cubos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.calculationtoolspane.f1
ms.assetid: b1aa8a1a-6532-45d2-8f53-d3e211d7197a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6701a15a7d773a90e48ec39dc976b9ef579c9ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670076"
---
# <a name="calculation-tools-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="e5fee-102">Herramientas de cálculo (pestaña Cálculos, Diseñador de cubos) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="e5fee-102">Calculation Tools (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e5fee-103">Use el panel **Herramientas de cálculo** en la pestaña **Cálculos** del Diseñador de cubos para explorar metadatos, funciones y plantillas disponibles para utilizarlos en cálculos.</span><span class="sxs-lookup"><span data-stu-id="e5fee-103">Use the **Calculation Tools** pane on the **Calculations** tab in Cube Designer to explore metadata, functions, and templates available for use in calculations.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e5fee-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="e5fee-104">Options</span></span>  
 <span data-ttu-id="e5fee-105">**Metadata**</span><span class="sxs-lookup"><span data-stu-id="e5fee-105">**Metadata**</span></span>  
 <span data-ttu-id="e5fee-106">Muestra los metadatos del cubo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e5fee-106">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="e5fee-107">Arrastre el elemento seleccionado al panel Editor de script, Editor de Formulario de miembro calculado o Editor de Formulario de conjunto con nombre para incluir la sintaxis de las Expresiones multidimensionales (MDX) de dicho elemento en la ubicación seleccionada del panel.</span><span class="sxs-lookup"><span data-stu-id="e5fee-107">Drag a selected element to the Script Editor, Calculated Member Form Editor, or Named Set Form Editor pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="e5fee-108">**Funciones**</span><span class="sxs-lookup"><span data-stu-id="e5fee-108">**Functions**</span></span>  
 <span data-ttu-id="e5fee-109">Muestra las funciones disponibles para las expresiones y condiciones.</span><span class="sxs-lookup"><span data-stu-id="e5fee-109">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="e5fee-110">Arrastre el elemento seleccionado al panel **Editor de script**, **Editor de Formulario de miembro calculado**o **Editor de Formulario de conjunto con nombre** para incluir la sintaxis MDX de dicho elemento en la ubicación seleccionada del panel.</span><span class="sxs-lookup"><span data-stu-id="e5fee-110">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5fee-111">En el modo de proyecto, el cuadro de diálogo **Herramientas de cálculo** lee la información de esta opción desde un archivo XML con el nombre MDXFunctions.xml, incluido en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5fee-111">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="e5fee-112">En el modo en línea, la información de esta opción se recupera del conjunto de filas del esquema MDSCHEMA_FUNCTIONS para la instancia.</span><span class="sxs-lookup"><span data-stu-id="e5fee-112">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="e5fee-113">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="e5fee-113">**Templates**</span></span>  
 <span data-ttu-id="e5fee-114">Muestra las plantillas predefinidas disponibles para los miembros calculados, los conjuntos con nombre y los comandos de script.</span><span class="sxs-lookup"><span data-stu-id="e5fee-114">Displays the predefined templates available for calculated members, named sets, and script commands.</span></span>  
  
 <span data-ttu-id="e5fee-115">Arrastre el elemento seleccionado al panel **Editor de script**, **Editor de Formulario de miembro calculado**o **Editor de Formulario de conjunto con nombre** para incluir la sintaxis MDX de dicho elemento en la ubicación seleccionada del panel.</span><span class="sxs-lookup"><span data-stu-id="e5fee-115">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="e5fee-116">Menú contextual</span><span class="sxs-lookup"><span data-stu-id="e5fee-116">Context Menu</span></span>  
 <span data-ttu-id="e5fee-117">Las siguientes opciones están disponibles en el menú contextual que se muestra al hacer clic con el botón derecho en un elemento del panel **Herramientas de cálculo** :</span><span class="sxs-lookup"><span data-stu-id="e5fee-117">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="e5fee-118">**Copiar**</span><span class="sxs-lookup"><span data-stu-id="e5fee-118">**Copy**</span></span>  
 <span data-ttu-id="e5fee-119">Seleccione esta opción para copiar el elemento seleccionado en **Metadatos** o **Funciones** en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="e5fee-119">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5fee-120"> No se mostrará esta opción si se selecciona **Plantillas** .</span><span class="sxs-lookup"><span data-stu-id="e5fee-120">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5fee-121"> Se deshabilitará esta opción si no es posible copiar el miembro seleccionado, al igual que la carpeta **Conjuntos** de una dimensión mostrada en **Metadatos** o la carpeta del grupo de función para una función mostrada en **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="e5fee-121">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="e5fee-122">**Filtrar miembros**</span><span class="sxs-lookup"><span data-stu-id="e5fee-122">**Filter Members**</span></span>  
 <span data-ttu-id="e5fee-123">Seleccione esta opción para mostrar el cuadro de diálogo **Filtrar miembros** y filtrar los miembros del elemento seleccionado en **Metadatos**.</span><span class="sxs-lookup"><span data-stu-id="e5fee-123">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="e5fee-124">Para más información sobre el cuadro de diálogo **Filtrar miembros**, vea [Cuadro de diálogo Filtrar miembros &#40;Analysis Services - Datos multidimensionales&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e5fee-124">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5fee-125"> Solo se mostrará esta opción si se selecciona **Metadatos** .</span><span class="sxs-lookup"><span data-stu-id="e5fee-125">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5fee-126"> Solo se habilitará esta opción si se selecciona un nivel para un atributo en **Metadatos**.</span><span class="sxs-lookup"><span data-stu-id="e5fee-126">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="e5fee-127">**Agregar plantilla**</span><span class="sxs-lookup"><span data-stu-id="e5fee-127">**Add Template**</span></span>  
 <span data-ttu-id="e5fee-128">Seleccione esta opción para agregar un nuevo miembro calculado, un conjunto con nombre o un comando de script basado en la plantilla seleccionada al script del cubo y para mostrar el **Editor de script**, el **Editor de Formulario de miembro calculado**o el **Editor de Formulario de conjunto con nombre** según sea necesario para dicho comando (en la vista Formulario) o para desplazarse por el contenido del panel **Editor de script** hasta la ubicación del comando en el script del cubo (en la Vista de script).</span><span class="sxs-lookup"><span data-stu-id="e5fee-128">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** as appropriate for that command (in form view) or to scroll the contents of the **Script Editor** pane to the location of the command in the cube script (in script view).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5fee-129"> Solo se mostrará esta opción si se selecciona **Metadatos** .</span><span class="sxs-lookup"><span data-stu-id="e5fee-129">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fee-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5fee-130">See Also</span></span>  
 <span data-ttu-id="e5fee-131">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e5fee-131">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e5fee-132">[Barra de herramientas &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e5fee-132">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e5fee-133">[Organizador de scripts &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e5fee-133">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e5fee-134">[Editor de formulario de miembro calculado &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services-datos multidimensionales&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e5fee-134">[Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e5fee-135">[Editor de formulario de conjuntos con nombre &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e5fee-135">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e5fee-136">[Editor de scripts &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e5fee-136">[Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e5fee-137">Cálculos &#40;diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="e5fee-137">Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
