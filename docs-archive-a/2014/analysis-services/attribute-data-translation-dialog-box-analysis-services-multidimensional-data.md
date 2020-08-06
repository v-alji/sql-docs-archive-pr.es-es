---
title: Cuadro de diálogo traducción de datos de atributos (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.dimensionstoragesettings.f1
helpviewer_keywords:
- Attribute Data Translation dialog box
ms.assetid: bed286de-1e9b-49de-b09e-3cd076aba152
author: minewiskan
ms.author: owend
ms.openlocfilehash: b61022ec2cb8726fc034e13a0d63e432df6ec151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670168"
---
# <a name="attribute-data-translation-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="8f991-102">Cuadro de diálogo Traducción de datos de atributos (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="8f991-102">Attribute Data Translation Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="8f991-103">Use el cuadro de diálogo **Traducción de datos de atributos** para establecer la columna que contiene los datos del título de la traducción, así como la intercalación y el orden que desea utilizar en los datos traducidos.</span><span class="sxs-lookup"><span data-stu-id="8f991-103">Use the **Attribute Data Translation** dialog box to set the column that contains the translation caption data, as well as the collation and sort order to be used with the translated data.</span></span> <span data-ttu-id="8f991-104">Para mostrar el cuadro de diálogo **Traducción de datos de atributos** :</span><span class="sxs-lookup"><span data-stu-id="8f991-104">You can display the **Attribute Data Translation** dialog box by:</span></span>  
  
-   <span data-ttu-id="8f991-105">Haga clic en **Nueva columna de títulos** o **Editar columna de títulos** en el panel **Barra de herramientas** en la pestaña **Traducciones** del **Diseñador de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="8f991-105">Clicking **New caption column** or **Edit caption column** from the **Toolbar** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
-   <span data-ttu-id="8f991-106">Haga clic con el botón derecho en el panel **Detalles de traducción** de la pestaña **Traducciones** del **Diseñador de dimensiones** y seleccione **Nueva columna de títulos** o **Editar columna de títulos**.</span><span class="sxs-lookup"><span data-stu-id="8f991-106">Right-clicking the **Translation Details** pane on the **Translations** tab of **Dimension Designer** and selecting **New caption column** or **Edit caption column**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8f991-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="8f991-107">Options</span></span>  
 <span data-ttu-id="8f991-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="8f991-108">**Attribute**</span></span>  
 <span data-ttu-id="8f991-109">Muestra el atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8f991-109">Displays the selected attribute.</span></span>  
  
 <span data-ttu-id="8f991-110">**Lenguaje**</span><span class="sxs-lookup"><span data-stu-id="8f991-110">**Language**</span></span>  
 <span data-ttu-id="8f991-111">Muestra el idioma seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8f991-111">Displays the selected language.</span></span>  
  
 <span data-ttu-id="8f991-112">**Título traducido**</span><span class="sxs-lookup"><span data-stu-id="8f991-112">**Translated caption**</span></span>  
 <span data-ttu-id="8f991-113">Establece el título traducido para el atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8f991-113">Sets the current translated caption for the selected attribute.</span></span>  
  
 <span data-ttu-id="8f991-114">**Columnas de traducción**</span><span class="sxs-lookup"><span data-stu-id="8f991-114">**Translation columns**</span></span>  
 <span data-ttu-id="8f991-115">Establece la columna en la que se almacenarán los datos del título de traducción.</span><span class="sxs-lookup"><span data-stu-id="8f991-115">Sets the column where the translation caption data is stored.</span></span> <span data-ttu-id="8f991-116">Solo se puede seleccionar una columna.</span><span class="sxs-lookup"><span data-stu-id="8f991-116">Only one column can be selected.</span></span> <span data-ttu-id="8f991-117">Se mostrarán todas las tablas relacionadas a las que hace referencia la tabla de dimensión principal.</span><span class="sxs-lookup"><span data-stu-id="8f991-117">All related tables that are referred to by the primary dimension table will be displayed.</span></span>  
  
 <span data-ttu-id="8f991-118">**Designador de intercalación**</span><span class="sxs-lookup"><span data-stu-id="8f991-118">**Collation designator**</span></span>  
 <span data-ttu-id="8f991-119">Establece el designador de intercalación para el atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8f991-119">Sets the collation designator for the selected attribute.</span></span> <span data-ttu-id="8f991-120">De manera predeterminada, se selecciona la intercalación actual de Windows.</span><span class="sxs-lookup"><span data-stu-id="8f991-120">By default, the current Windows collation is selected.</span></span> <span data-ttu-id="8f991-121">Haga clic en la flecha abajo para seleccionar una de las intercalaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="8f991-121">Click the down arrow to select from the available collations.</span></span>  
  
 <span data-ttu-id="8f991-122">**Binario**</span><span class="sxs-lookup"><span data-stu-id="8f991-122">**Binary**</span></span>  
 <span data-ttu-id="8f991-123">Seleccione esta opción para ordenar y comparar datos según los patrones de bits definidos para cada carácter.</span><span class="sxs-lookup"><span data-stu-id="8f991-123">Select this option to sort and compare data based on the bit patterns defined for each character.</span></span> <span data-ttu-id="8f991-124">El orden binario distingue mayúsculas de minúsculas, es decir, las minúsculas siempre preceden a las mayúsculas, y distingue acentos.</span><span class="sxs-lookup"><span data-stu-id="8f991-124">Binary sort order is case-sensitive, that is, lowercase precedes uppercase, and accent-sensitive.</span></span> <span data-ttu-id="8f991-125">Éste es el orden más rápido.</span><span class="sxs-lookup"><span data-stu-id="8f991-125">This is the fastest sorting order.</span></span>  
  
 <span data-ttu-id="8f991-126">Si no selecciona esta opción, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sigue el orden y las reglas de comparación definidas en los diccionarios del idioma o alfabeto asociado.</span><span class="sxs-lookup"><span data-stu-id="8f991-126">If this option is not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] follows sorting and comparison rules as defined in dictionaries for the associated language or alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f991-127">Si selecciona esta opción, se deshabilitarán las opciones **Distinguir mayúsculas de minúsculas**, **Distinguir acentos**, **Distinguir kana**y **Distinguir ancho** .</span><span class="sxs-lookup"><span data-stu-id="8f991-127">If this option is selected, the **Case sensitive**, **Accent sensitive**, **Kana sensitive**, and **Width sensitive** options are disabled.</span></span>  
  
 <span data-ttu-id="8f991-128">**Distinguir mayúsculas de minúsculas**</span><span class="sxs-lookup"><span data-stu-id="8f991-128">**Case sensitive**</span></span>  
 <span data-ttu-id="8f991-129">Seleccione esta opción para ordenar y comparar datos según las reglas de los diccionarios del idioma o alfabeto asociado y distinguir letras mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8f991-129">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between uppercase and lowercase letters.</span></span>  
  
 <span data-ttu-id="8f991-130">Si no selecciona esta opción, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considera que las mayúsculas y las minúsculas son versiones de letras iguales.</span><span class="sxs-lookup"><span data-stu-id="8f991-130">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the uppercase and lowercase versions of letters to be equal.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]<span data-ttu-id="8f991-131">no define si el orden de las letras minúsculas es inferior o superior al de las letras mayúsculas cuando no se selecciona distinguir mayúsculas de **minúsculas** .</span><span class="sxs-lookup"><span data-stu-id="8f991-131">does not define whether lowercase letters sort lower or higher in relation to uppercase letters when **Case-sensitive** is not selected.</span></span>  
  
 <span data-ttu-id="8f991-132">**Distinguir acentos**</span><span class="sxs-lookup"><span data-stu-id="8f991-132">**Accent sensitive**</span></span>  
 <span data-ttu-id="8f991-133">Seleccione esta opción para ordenar y comparar datos según las reglas de los diccionarios del idioma o alfabeto asociado y distinguir los caracteres acentuados de los no acentuados.</span><span class="sxs-lookup"><span data-stu-id="8f991-133">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between accented and unaccented characters.</span></span> <span data-ttu-id="8f991-134">Por ejemplo, 'a' no es igual a 'á'.</span><span class="sxs-lookup"><span data-stu-id="8f991-134">For example, 'a' is not equal to 'á'.</span></span>  
  
 <span data-ttu-id="8f991-135">Si no está seleccionada, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considera que las letras con y sin acentos son iguales.</span><span class="sxs-lookup"><span data-stu-id="8f991-135">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the accented and unaccented versions of letters to be equal.</span></span>  
  
 <span data-ttu-id="8f991-136">**Distinguir kana**</span><span class="sxs-lookup"><span data-stu-id="8f991-136">**Kana sensitive**</span></span>  
 <span data-ttu-id="8f991-137">Seleccione esta opción para ordenar y comparar datos según las reglas de los diccionarios del idioma o alfabeto asociado y distinguir los dos tipos de caracteres kana japoneses: hiragana y katakana.</span><span class="sxs-lookup"><span data-stu-id="8f991-137">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between the two types of Japanese kana characters: Hiragana and Katakana.</span></span>  
  
 <span data-ttu-id="8f991-138">Si no está seleccionada, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considera que los caracteres hiragana y katakana son iguales.</span><span class="sxs-lookup"><span data-stu-id="8f991-138">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers Hiragana and Katakana characters to be equal.</span></span>  
  
 <span data-ttu-id="8f991-139">**Distinguir ancho**</span><span class="sxs-lookup"><span data-stu-id="8f991-139">**Width sensitive**</span></span>  
 <span data-ttu-id="8f991-140">Seleccione esta opción para ordenar y comparar datos según las reglas de los diccionarios del idioma o alfabeto asociado y distinguir un carácter de un byte del mismo carácter representado con un carácter de dos bytes.</span><span class="sxs-lookup"><span data-stu-id="8f991-140">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between a single-byte character (half-width) and the same character when represented as a double-byte character (full-width).</span></span>  
  
 <span data-ttu-id="8f991-141">Si no está seleccionada, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considera que la representación de un byte y la de dos bytes del mismo carácter son iguales.</span><span class="sxs-lookup"><span data-stu-id="8f991-141">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the single-byte and double-byte representation of the same character to be equal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f991-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f991-142">See Also</span></span>  
 <span data-ttu-id="8f991-143">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="8f991-143">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="8f991-144">Detalles de traducción &#40;pestaña traducciones, diseñador de dimensiones&#41; &#40;Analysis Services-datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="8f991-144">Translation Details &#40;Translations Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translation-details-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
