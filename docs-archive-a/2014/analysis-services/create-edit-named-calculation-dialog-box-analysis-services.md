---
title: Cuadro de diálogo crear-editar cálculo con nombre (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsveditor.createnamedcalculation.f1
helpviewer_keywords:
- Named Calculation dialog box
ms.assetid: 66fb30ae-f5c5-4bfc-80ca-8c8a3a9bb30d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b6777feb47a1ce6b601d0190e413b4baae35f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662371"
---
# <a name="create-edit-named-calculation-dialog-box-analysis-services"></a><span data-ttu-id="bcaa6-102">Cuadro de diálogo crear-editar cálculo con nombre (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="bcaa6-102">Create-Edit Named Calculation Dialog Box (Analysis Services)</span></span>
  <span data-ttu-id="bcaa6-103">Utilice el cuadro de diálogo **crear/editar cálculo con nombre** en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para definir o modificar un cálculo con nombre para una tabla en una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-103">Use the **Create/Edit Named Calculation** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a named calculation for a table in a data source view.</span></span> <span data-ttu-id="bcaa6-104">Para mostrar el cuadro de diálogo **Crear/editar cálculo con nombre**:</span><span class="sxs-lookup"><span data-stu-id="bcaa6-104">You can display the **Create/Edit Named Calculation** dialog box by:</span></span>  
  
-   <span data-ttu-id="bcaa6-105">Haga clic en **Nuevo cálculo con nombre** en el panel de la **barra de herramientas** del **Diseñador de vistas del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-105">Clicking **New Named Calculation** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="bcaa6-106">Haga clic con el botón derecho en el panel **Tablas** o **Diagrama** del **Diseñador de vistas del origen de datos** y seleccione **Nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Named Calculation**.</span></span>  
  
-   <span data-ttu-id="bcaa6-107">Haga clic con el botón derecho en un cálculo con nombre del panel **Diagrama**, en el **Diseñador de vistas del origen de datos**, y seleccione **Editar cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-107">Right-clicking the name of a named calculation in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Named Calculation**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bcaa6-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="bcaa6-108">Options</span></span>  
 <span data-ttu-id="bcaa6-109">**Nombre de columna**</span><span class="sxs-lookup"><span data-stu-id="bcaa6-109">**Column Name**</span></span>  
 <span data-ttu-id="bcaa6-110">Escriba el nombre del cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-110">Type the name of the named calculation.</span></span>  
  
 <span data-ttu-id="bcaa6-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bcaa6-111">**Description**</span></span>  
 <span data-ttu-id="bcaa6-112">Escriba la descripción opcional del cálculo con nombre.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-112">Type the optional description of the named calculation.</span></span>  
  
 <span data-ttu-id="bcaa6-113">**Expression**</span><span class="sxs-lookup"><span data-stu-id="bcaa6-113">**Expression**</span></span>  
 <span data-ttu-id="bcaa6-114">Escriba una expresión SQL válida que devuelva un valor escalar.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-114">Type a valid SQL expression that returns a scalar value.</span></span> <span data-ttu-id="bcaa6-115">La expresión se envía al proveedor y se valida en la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="bcaa6-115">The expression is sent to the provider, and validated in the following expression:</span></span>  
  
```  
SELECT <Table Name in Data Source>.* , <Expression> AS <Column Name> FROM <Table Name in Data Source>AS <Table Name in Data Source View>  
```  
  
 <span data-ttu-id="bcaa6-116">La expresión puede tener referencias a otras tablas, mediante una instrucción sub-SELECT.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-116">The expression can contain references to other tables, by means of a sub-select statement.</span></span> <span data-ttu-id="bcaa6-117">Si la expresión requiere el uso de paréntesis en una instrucción SELECT, la expresión que se especifique debe estar entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="bcaa6-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcaa6-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcaa6-118">See Also</span></span>  
 <span data-ttu-id="bcaa6-119">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bcaa6-119">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="bcaa6-120">Diseñador de vistas del origen de datos &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="bcaa6-120">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
