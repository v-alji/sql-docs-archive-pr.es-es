---
title: Detalles de traducción (pestaña traducciones, diseñador de dimensiones) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.translations.translationpane.tranlationdetails.f1
ms.assetid: 0aa61df3-f2b0-4703-a63b-124da672dcc3
author: minewiskan
ms.author: owend
ms.openlocfilehash: a7cbe4a3c69111d0f82f96ff5125f80fe0c2c57f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748919"
---
# <a name="translation-details-translations-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="a0bca-102">Detalles de la traducción (pestaña Traducciones, Diseñador de dimensiones) (Analysis Services – Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="a0bca-102">Translation Details (Translations Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="a0bca-103">Use el panel de **Detalles de la traducción** de la pestaña **Traducciones** del Diseñador de dimensiones para definir y administrar traducciones para la dimensión seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="a0bca-103">Use the **Translation Details** pane on the **Translations** tab of Dimension Designer to define and manage translations for the currently selected dimension.</span></span>  
  
 <span data-ttu-id="a0bca-104">**Para mostrar el panel Detalles de la traducción**</span><span class="sxs-lookup"><span data-stu-id="a0bca-104">**To display the Translations Details pane**</span></span>  
  
1.  <span data-ttu-id="a0bca-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, a continuación, abra la dimensión que desea.</span><span class="sxs-lookup"><span data-stu-id="a0bca-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then open the dimension that you want.</span></span>  
  
2.  <span data-ttu-id="a0bca-106">Haga clic en la pestaña **Traducciones** .</span><span class="sxs-lookup"><span data-stu-id="a0bca-106">Click the **Translations** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a0bca-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="a0bca-107">Options</span></span>  
 <span data-ttu-id="a0bca-108">**Idioma predeterminado**</span><span class="sxs-lookup"><span data-stu-id="a0bca-108">**Default Language**</span></span>  
 <span data-ttu-id="a0bca-109">Establece los nombres de los objetos de la dimensión en el idioma predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a0bca-109">Sets the names of the dimension objects in the default language.</span></span>  
  
 <span data-ttu-id="a0bca-110">**Tipo de objeto**</span><span class="sxs-lookup"><span data-stu-id="a0bca-110">**Object Type**</span></span>  
 <span data-ttu-id="a0bca-111">Muestra la propiedad que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="a0bca-111">Displays the property that will be translated.</span></span> <span data-ttu-id="a0bca-112">Solo se pueden traducir los objetos y las propiedades para los cuales se han especificado valores.</span><span class="sxs-lookup"><span data-stu-id="a0bca-112">Only objects and properties for which values have been specified can be translated.</span></span> <span data-ttu-id="a0bca-113">Es posible traducir las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="a0bca-113">The following properties can be translated:</span></span>  
  
-   <span data-ttu-id="a0bca-114">Dimensión</span><span class="sxs-lookup"><span data-stu-id="a0bca-114">Dimension</span></span>  
  
     <span data-ttu-id="a0bca-115">Propiedades `Caption` y `AttributeAllMember`</span><span class="sxs-lookup"><span data-stu-id="a0bca-115">`Caption` and `AttributeAllMember` properties</span></span>  
  
-   <span data-ttu-id="a0bca-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="a0bca-116">Attribute</span></span>  
  
     <span data-ttu-id="a0bca-117">Propiedades `Caption`, `AttributeHierarchyDisplayFolder` y `NamingTemplate`.</span><span class="sxs-lookup"><span data-stu-id="a0bca-117">`Caption`, `AttributeHierarchyDisplayFolder`, and `NamingTemplate` properties</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0bca-118">La propiedad `NamingTemplate` solo está disponible para atributos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0bca-118">The `NamingTemplate` property is available only for parent attributes.</span></span>  
  
-   <span data-ttu-id="a0bca-119">Hierarchy</span><span class="sxs-lookup"><span data-stu-id="a0bca-119">Hierarchy</span></span>  
  
     <span data-ttu-id="a0bca-120">Propiedades `Caption` y `AllMemberName`</span><span class="sxs-lookup"><span data-stu-id="a0bca-120">`Caption` and `AllMemberName` properties</span></span>  
  
-   <span data-ttu-id="a0bca-121">Nivel</span><span class="sxs-lookup"><span data-stu-id="a0bca-121">Level</span></span>  
  
     <span data-ttu-id="a0bca-122">Propiedad de `Caption`</span><span class="sxs-lookup"><span data-stu-id="a0bca-122">`Caption` property</span></span>  
  
 **\<Language>**  
 <span data-ttu-id="a0bca-123">Escriba o seleccione el valor de la propiedad del objeto de la dimensión en el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a0bca-123">Type or select the property value of the dimension object in the selected language.</span></span> <span data-ttu-id="a0bca-124">Si hace clic en el botón de puntos suspensivos (**…**), se abrirán otros cuadros de diálogo, según la propiedad que edite:</span><span class="sxs-lookup"><span data-stu-id="a0bca-124">Clicking the ellipsis button (**...**) opens additional dialog boxes, depending on the property being edited:</span></span>  
  
-   <span data-ttu-id="a0bca-125">Propiedad de `NamingTemplate`</span><span class="sxs-lookup"><span data-stu-id="a0bca-125">`NamingTemplate` property</span></span>  
  
     <span data-ttu-id="a0bca-126">Muestra el [Cuadro de diálogo Plantilla de asignación de nombres de nivel &#40;Analysis Services - Datos multidimensionales&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="a0bca-126">Displays the [Level Naming Template Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
-   <span data-ttu-id="a0bca-127">Propiedad `Caption` (para atributos)</span><span class="sxs-lookup"><span data-stu-id="a0bca-127">`Caption` property (for attributes)</span></span>  
  
     <span data-ttu-id="a0bca-128">Muestra el [Cuadro de diálogo Traducción de datos de atributos &#40;Analysis Services - Datos multidimensionales&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="a0bca-128">Displays the [Attribute Data Translation Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="shortcut-menu"></a><span data-ttu-id="a0bca-129">Menú contextual</span><span class="sxs-lookup"><span data-stu-id="a0bca-129">Shortcut Menu</span></span>  
 <span data-ttu-id="a0bca-130">Las opciones siguientes están disponibles en el menú contextual que se abre al hacer clic con el botón derecho en el panel **Detalles de traducción** :</span><span class="sxs-lookup"><span data-stu-id="a0bca-130">The following options are available in the shortcut menu displayed by right-clicking a translation in the **Translation Details** pane:</span></span>  
  
 <span data-ttu-id="a0bca-131">**Nueva traducción**</span><span class="sxs-lookup"><span data-stu-id="a0bca-131">**New Translation**</span></span>  
 <span data-ttu-id="a0bca-132">Seleccione esta opción para mostrar el cuadro de diálogo **Seleccionar idioma** y crear una nueva traducción.</span><span class="sxs-lookup"><span data-stu-id="a0bca-132">Select to display the **Select Language** dialog box and create a new translation.</span></span> <span data-ttu-id="a0bca-133">La traducción aparecerá como una nueva columna en la cuadrícula **Detalles de la traducción** .</span><span class="sxs-lookup"><span data-stu-id="a0bca-133">The translation will appear as a new column in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="a0bca-134">**Eliminar traducción**</span><span class="sxs-lookup"><span data-stu-id="a0bca-134">**Delete Translation**</span></span>  
 <span data-ttu-id="a0bca-135">Seleccione esta opción para eliminar la traducción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a0bca-135">Select to delete the selected translation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0bca-136">Esta opción solo se habilita si hizo clic con el botón secundario en una celda para eliminar una traducción.</span><span class="sxs-lookup"><span data-stu-id="a0bca-136">The option is enabled only if you right-clicked a cell to delete the translation.</span></span>  
  
 <span data-ttu-id="a0bca-137">**Nueva columna de leyenda**</span><span class="sxs-lookup"><span data-stu-id="a0bca-137">**New Caption Column**</span></span>  
 <span data-ttu-id="a0bca-138">Seleccione esta opción para mostrar el cuadro de diálogo **Traducción de datos de atributos** y definir una nueva columna de leyendas cuando modifique un atributo en la cuadrícula **Detalles de traducción** .</span><span class="sxs-lookup"><span data-stu-id="a0bca-138">Select to display the **Attribute Data Translation** dialog box and define a new caption column when you modify an attribute in the **Translation Details** grid.</span></span> <span data-ttu-id="a0bca-139">Para habilitar esta opción, se debe seleccionar una celda de una columna de traducción para un atributo en la cuadrícula **Detalles de traducción** .</span><span class="sxs-lookup"><span data-stu-id="a0bca-139">To enable this option, a cell in a translation column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0bca-140">Esta opción solo se habilita si hizo clic con el botón secundario en una celda para eliminar la columna de traducción de un atributo.</span><span class="sxs-lookup"><span data-stu-id="a0bca-140">The option is enabled only if you right-clicked a cell to delete the translation column of an attribute.</span></span>  
  
 <span data-ttu-id="a0bca-141">**Editar columna de leyenda**</span><span class="sxs-lookup"><span data-stu-id="a0bca-141">**Edit Caption Column**</span></span>  
 <span data-ttu-id="a0bca-142">Seleccione esta opción para mostrar el cuadro de diálogo **Traducción de datos de atributos** y modificar una columna de leyendas existente al modificar un atributo en la cuadrícula **Detalles de traducción** .</span><span class="sxs-lookup"><span data-stu-id="a0bca-142">Select to display the **Attribute Data Translation** dialog box and modify an existing caption column when you modify an attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0bca-143"> La opción solo se habilita si se ha seleccionado una celda de una columna traducción que contiene una columna de leyenda de un atributo en la cuadrícula **Detalles de traducción** .</span><span class="sxs-lookup"><span data-stu-id="a0bca-143">The option is enabled only if a cell in a translation column that contains a caption column for an attribute must be selected in the **Translation Details** grid.</span></span>  
  
 <span data-ttu-id="a0bca-144">**Eliminar columna de leyenda**</span><span class="sxs-lookup"><span data-stu-id="a0bca-144">**Delete Caption Column**</span></span>  
 <span data-ttu-id="a0bca-145">Elija esta opción para eliminar la columna de leyendas del atributo seleccionado en la cuadrícula **Detalles de traducción** .</span><span class="sxs-lookup"><span data-stu-id="a0bca-145">Select to delete the caption column for the selected attribute in the **Translation Details** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0bca-146">Esta opción solo se habilita si hizo clic con el botón secundario en una columna de traducción que contiene una columna de leyenda para un atributo.</span><span class="sxs-lookup"><span data-stu-id="a0bca-146">The option is enabled only if you right-clicked a cell in a translation column that contains a caption column for an attribute.</span></span>  
  
 <span data-ttu-id="a0bca-147">**Mostrar todos los atributos**</span><span class="sxs-lookup"><span data-stu-id="a0bca-147">**Show All Attributes**</span></span>  
 <span data-ttu-id="a0bca-148">Seleccione esta opción para alternar la visualización de todos los atributos definidos para la dimensión seleccionada. Entre ellos se incluyen los atributos en los que se han deshabilitado las jerarquías de atributo.</span><span class="sxs-lookup"><span data-stu-id="a0bca-148">Select to toggle the display of all attributes defined for the selected dimension, including attributes for which attribute hierarchies are disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bca-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0bca-149">See Also</span></span>  
 [<span data-ttu-id="a0bca-150">Traducciones &#40;diseñador de dimensiones&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="a0bca-150">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
