---
title: Cuadro de diálogo plantilla de asignación de nombres de nivel (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.levelnamingtemplatedialog.f1
helpviewer_keywords:
- Level Naming Template dialog box
ms.assetid: 96cad715-213e-4eac-9003-130a2f5fc985
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dd704e619e49f0dd1adb8fed8f1e743b61309af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752473"
---
# <a name="level-naming-template-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="4c5c7-102">Cuadro de diálogo Plantilla de asignación de nombres de nivel (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="4c5c7-102">Level Naming Template Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4c5c7-103">Use el cuadro de diálogo **Plantilla de asignación de nombres de nivel** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para crear la plantilla de asignación de nombres de nivel para un atributo primario de una dimensión.</span><span class="sxs-lookup"><span data-stu-id="4c5c7-103">Use the **Level Naming Template** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to construct the level naming template for a parent attribute in a dimension.</span></span> <span data-ttu-id="4c5c7-104">Para obtener más información sobre el nivel de nomenclatura de plantillas, vea [Elemento NamingTemplate &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span><span class="sxs-lookup"><span data-stu-id="4c5c7-104">For more information about level naming templates, see [NamingTemplate Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span></span> <span data-ttu-id="4c5c7-105">Para mostrar el cuadro de diálogo **plantilla de asignación de nombres de nivel** , haga clic en el botón de puntos suspensivos (**...**) del `NamingTemplate` valor de una traducción de un atributo en el panel **detalles de traducción** de la pestaña **traducciones** del **Diseñador de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="4c5c7-105">You can display the **Level Naming Template** dialog box by clicking the ellipsis button (**...**) on the `NamingTemplate` value of a translation for an attribute in the **Translation Details** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c5c7-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="4c5c7-106">Options</span></span>  
  
|<span data-ttu-id="4c5c7-107">Término</span><span class="sxs-lookup"><span data-stu-id="4c5c7-107">Term</span></span>|<span data-ttu-id="4c5c7-108">Definición</span><span class="sxs-lookup"><span data-stu-id="4c5c7-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="4c5c7-109">**Definir la plantilla de nivel**</span><span class="sxs-lookup"><span data-stu-id="4c5c7-109">**Define the level template**</span></span>|<span data-ttu-id="4c5c7-110">Muestra una cuadrícula en la que se puede diseñar la jerarquía de niveles del atributo primario.</span><span class="sxs-lookup"><span data-stu-id="4c5c7-110">Displays a grid in which you can design the hierarchy of levels in the parent attribute.</span></span> <span data-ttu-id="4c5c7-111">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c5c7-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="4c5c7-112">**Nivel**: muestra la posición ordinal del nivel para el que se utiliza el nombre especificado en **nombre** .</span><span class="sxs-lookup"><span data-stu-id="4c5c7-112">**Level**: Displays the ordinal position of the level for which the name specified in **Name** is used.</span></span> <span data-ttu-id="4c5c7-113">Para agregar una nueva plantilla de asignación de nombres de nivel, seleccione **Nombre** en la fila que contenga un asterisco (\*) en **Nivel**.</span><span class="sxs-lookup"><span data-stu-id="4c5c7-113">To add a new naming template for a level, select **Name** on the row that contains an asterisk (\*) in **Level**.</span></span><br /><br /> <span data-ttu-id="4c5c7-114">**Nombre**: contiene la plantilla de asignación de nombres usada para el nivel indicado en **nivel**.</span><span class="sxs-lookup"><span data-stu-id="4c5c7-114">**Name**: Contains the naming template used for the level indicated in **Level**.</span></span> <span data-ttu-id="4c5c7-115">Si desea agregar un marcador de posición para la posición ordinal del nivel en la plantilla de asignación de nombres, agregue un asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="4c5c7-115">To add a placeholder for the level ordinal position in the naming template, add a single asterisk (\*).</span></span> <span data-ttu-id="4c5c7-116">Para agregar un asterisco como parte del nombre creado por la plantilla de asignación de nombres, agregue dos asteriscos ( \* \* ).</span><span class="sxs-lookup"><span data-stu-id="4c5c7-116">To add an asterisk as part of the name created by the naming template, add two asterisks (\*\*).</span></span>|  
|<span data-ttu-id="4c5c7-117">**Borrar todo**</span><span class="sxs-lookup"><span data-stu-id="4c5c7-117">**Clear All**</span></span>|<span data-ttu-id="4c5c7-118">Seleccione esta opción para borrar todas las filas de **Definir la plantilla de nivel**.</span><span class="sxs-lookup"><span data-stu-id="4c5c7-118">Select to remove all rows in **Define the level template**.</span></span>|  
|<span data-ttu-id="4c5c7-119">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="4c5c7-119">**Result**</span></span>|<span data-ttu-id="4c5c7-120">Muestra la plantilla de asignación de nombres de nivel generada en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4c5c7-120">Displays the level naming template constructed by the dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c5c7-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c5c7-121">See Also</span></span>  
 <span data-ttu-id="4c5c7-122">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4c5c7-122">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="4c5c7-123">Traducciones &#40;diseñador de dimensiones&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="4c5c7-123">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
