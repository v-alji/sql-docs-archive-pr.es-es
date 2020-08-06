---
title: ADVERTENCIAS (diseñador de bases de datos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.databasedesigner.warnings.f1
ms.assetid: 13f58b4d-f345-4fbc-ae2d-b3c8290a797d
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf635460187fe56f4811de5090cada002ea8ca3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671186"
---
# <a name="warnings-database-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="c3e8a-102">Advertencias (Diseñador de bases de datos) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="c3e8a-102">Warnings (Database Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c3e8a-103">Use la pestaña **Advertencias** para ver y descartar reglas globalmente, así como para ver y volver a habilitar instancias específicas de advertencias descartadas.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-103">Use the **Warnings** tab to view and dismiss rules globally, and to view and re-enable specific instances of dismissed warnings.</span></span> <span data-ttu-id="c3e8a-104">La pestaña **Advertencias** muestra dos cuadrículas: **Reglas de advertencia de diseño** y **Advertencias descartadas**.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-104">The **Warnings** tab displays two grids: **Design Warning Rules** and **Dismissed Warnings**.</span></span>  
  
 <span data-ttu-id="c3e8a-105">**Para mostrar la pestaña Advertencias**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-105">**To display the Warnings tab**</span></span>  
  
1.  <span data-ttu-id="c3e8a-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3e8a-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="c3e8a-107">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , haga clic en **Editar base de datos**y, después, haga clic en la pestaña **Advertencias** .</span><span class="sxs-lookup"><span data-stu-id="c3e8a-107">In **Solution Explorer**, right-click the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, click **Edit Database**, and then click the **Warnings** tab.</span></span>  
  
## <a name="design-warning-rules-grid"></a><span data-ttu-id="c3e8a-108">Cuadrícula Reglas de advertencia de diseño</span><span class="sxs-lookup"><span data-stu-id="c3e8a-108">Design Warning Rules Grid</span></span>  
 <span data-ttu-id="c3e8a-109">La cuadrícula **Reglas de advertencia de diseño** muestra todas las reglas de advertencia de diseño.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-109">The **Design Warning Rules** grid displays all the design warning rules.</span></span> <span data-ttu-id="c3e8a-110">Esta cuadrícula también controla qué reglas están habilitadas para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-110">This grid also controls which rules are enabled for the database.</span></span> <span data-ttu-id="c3e8a-111">Para habilitar o deshabilitar una regla de la advertencia, active o desactive su casilla.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-111">To enable or disable a warning rule, select or clear its check box.</span></span>  
  
 <span data-ttu-id="c3e8a-112">La cuadrícula **Reglas de advertencia de diseño** tiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3e8a-112">The **Design Warning Rules** grid has the following columns:</span></span>  
  
 <span data-ttu-id="c3e8a-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-113">**Description**</span></span>  
 <span data-ttu-id="c3e8a-114">Muestra el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-114">Displays the name of the rule.</span></span> <span data-ttu-id="c3e8a-115">Las reglas se agrupan por categoría.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-115">Rules are grouped by category.</span></span>  
  
 <span data-ttu-id="c3e8a-116">**Importancia**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-116">**Importance**</span></span>  
 <span data-ttu-id="c3e8a-117">Muestra la importancia asignada a la regla.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-117">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="c3e8a-118">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-118">**Comments**</span></span>  
 <span data-ttu-id="c3e8a-119">(Opcional) Permite al usuario escribir un comentario que explica por qué está descartando la advertencia.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-119">(Optional) Allows the user to type a comment that explains why you are dismissing the warning.</span></span>  
  
## <a name="dismissed-warnings-grid"></a><span data-ttu-id="c3e8a-120">Cuadrícula de advertencias descartadas</span><span class="sxs-lookup"><span data-stu-id="c3e8a-120">Dismissed Warnings Grid</span></span>  
 <span data-ttu-id="c3e8a-121">La cuadrícula **Advertencias descartadas** muestra todas las repeticiones de advertencias específicas que se han descartado de la **Lista de errores**.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-121">The **Dismissed Warnings** grid displays all specific warning occurrences that have been dismissed from the **Error List**.</span></span> <span data-ttu-id="c3e8a-122">Para volver a habilitar una advertencia, selecciónela en la cuadrícula y, después, haga clic en **Rehabilitar**.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-122">To re-enable a warning, select it in the grid, and then click **Re-enable**.</span></span>  
  
 <span data-ttu-id="c3e8a-123">La cuadrícula **Advertencias descartadas** tiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3e8a-123">The **Dismissed Warnings** grid has the following :</span></span>  
  
 <span data-ttu-id="c3e8a-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-124">**Object**</span></span>  
 <span data-ttu-id="c3e8a-125">Muestra un icono que representa el tipo y el nombre de objeto.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-125">Displays an icon that represents the object type and the object name.</span></span>  
  
 <span data-ttu-id="c3e8a-126">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-126">**Type**</span></span>  
 <span data-ttu-id="c3e8a-127">Muestra el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-127">Displays the object type.</span></span>  
  
 <span data-ttu-id="c3e8a-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-128">**Description**</span></span>  
 <span data-ttu-id="c3e8a-129">Muestra el nombre de la regla.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-129">Displays the name of the rule.</span></span>  
  
 <span data-ttu-id="c3e8a-130">**Importancia**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-130">**Importance**</span></span>  
 <span data-ttu-id="c3e8a-131">Muestra la importancia asignada a la regla.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-131">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="c3e8a-132">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-132">**Comments**</span></span>  
 <span data-ttu-id="c3e8a-133">Muestra el comentario que se escribió cuando se descartó la advertencia.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-133">Displays the comment that was entered when the warning was dismissed.</span></span> <span data-ttu-id="c3e8a-134">Puede agregar o modificar un comentario aquí.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-134">You can add or modify a comment here.</span></span>  
  
 <span data-ttu-id="c3e8a-135">**Rehabilitar**</span><span class="sxs-lookup"><span data-stu-id="c3e8a-135">**Re-enable**</span></span>  
 <span data-ttu-id="c3e8a-136">Rehabilita las advertencias seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-136">Re-enables the selected warnings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3e8a-137">Si un objeto tiene una advertencia, pero el objeto se encuentra en un estado no válido o se quitó manualmente del proyecto, aparece un icono de error al lado de la advertencia en la lista.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-137">If an object has a warning, but the object is in an invalid state or was manually removed from the project, an error icon appears next to the warning in the list.</span></span> <span data-ttu-id="c3e8a-138">Para descartar la advertencia, selecciónela y, después, haga clic en **Rehabilitar**.</span><span class="sxs-lookup"><span data-stu-id="c3e8a-138">To dismiss the warning, select it and then click **Re-enable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e8a-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3e8a-139">See Also</span></span>  
 <span data-ttu-id="c3e8a-140">[Cuadro de diálogo descartar ADVERTENCIA &#40;Analysis Services de datos multidimensionales&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c3e8a-140">[Dismiss Warning Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="c3e8a-141">Diseñador de bases de datos de &#40;general&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="c3e8a-141">General &#40;Database Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](general-database-designer-analysis-services-multidimensional-data.md)  
  
  
