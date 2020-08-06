---
title: Cuadro de diálogo filtrar miembros (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.filtermembers.f1
helpviewer_keywords:
- Filter Members dialog box
ms.assetid: 52c6da1d-9fb5-4dbc-bffa-248d11cd337c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66980b1afe9d4eed353ae18c37ed1fdd052e62b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662323"
---
# <a name="filter-members-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="53e49-102">Cuadro de diálogo Filtrar miembros (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="53e49-102">Filter Members Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="53e49-103">Use el cuadro de diálogo **Filtrar miembros** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para filtrar los miembros de dimensión por título del miembro, nombre del miembro, nombre exclusivo del miembro, valor de columna de clave o valor de columna de valor para el nivel actual mientras busca una dimensión en la pestaña **Examinador** del **Diseñador de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="53e49-103">Use the **Filter Members** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to filter dimension members by member caption, member name, member unique name, key column value, or value column value for the current level while browsing a dimension in the **Browser** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="53e49-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="53e49-104">Options</span></span>  
  
|<span data-ttu-id="53e49-105">Término</span><span class="sxs-lookup"><span data-stu-id="53e49-105">Term</span></span>|<span data-ttu-id="53e49-106">Definición</span><span class="sxs-lookup"><span data-stu-id="53e49-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="53e49-107">**Expresión de filtro**</span><span class="sxs-lookup"><span data-stu-id="53e49-107">**Filter expression**</span></span>|<span data-ttu-id="53e49-108">Muestra una cuadrícula de propiedades, operadores y valores utilizados para construir una expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="53e49-108">Displays a grid of properties, operators, and values used to construct a filter expression.</span></span> <span data-ttu-id="53e49-109">Una vez que se ha agregado una fila, no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="53e49-109">Note that after a row is added, it cannot be removed.</span></span> <span data-ttu-id="53e49-110">Debe cerrar y volver a abrir el cuadro de diálogo para especificar una expresión de filtro nueva.</span><span class="sxs-lookup"><span data-stu-id="53e49-110">You must close and reopen the dialog box to specify a new filter expression.</span></span> <span data-ttu-id="53e49-111">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="53e49-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="53e49-112">**Propiedad**: seleccione la propiedad del miembro que se va a usar para la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="53e49-112">**Property**: Select the property of the member to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="53e49-113">**Operador**: seleccione el operador que se va a usar para la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="53e49-113">**Operator**: Select the operator to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="53e49-114">**Valor**: escriba el valor de la propiedad seleccionada en **propiedad** que se va a evaluar utilizando el operador especificado en **operador**.</span><span class="sxs-lookup"><span data-stu-id="53e49-114">**Value**: Type the value of the property selected in **Property** to evaluate using the operator specified in **Operator**.</span></span>|  
|<span data-ttu-id="53e49-115">**Panel Prueba**</span><span class="sxs-lookup"><span data-stu-id="53e49-115">**Test pane**</span></span>|<span data-ttu-id="53e49-116">Al hacer clic en **Probar** , este panel muestra los miembros devueltos por la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="53e49-116">When **Test** is clicked, this pane displays the members returned by the filter expression.</span></span> <span data-ttu-id="53e49-117">Si no se devuelve ningún miembro utilizando el criterio especificado en **Expresión de filtro**, se muestra una advertencia.</span><span class="sxs-lookup"><span data-stu-id="53e49-117">If no members are returned using the criteria specified in **Filter expression**, a warning is displayed.</span></span>|  
|<span data-ttu-id="53e49-118">**Test**</span><span class="sxs-lookup"><span data-stu-id="53e49-118">**Test**</span></span>|<span data-ttu-id="53e49-119">Haga clic para probar el criterio especificado en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="53e49-119">Click to test the criteria specified in **Filter expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53e49-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53e49-120">See Also</span></span>  
 <span data-ttu-id="53e49-121">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="53e49-121">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="53e49-122">Explorador &#40;diseñador de dimensiones&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="53e49-122">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
