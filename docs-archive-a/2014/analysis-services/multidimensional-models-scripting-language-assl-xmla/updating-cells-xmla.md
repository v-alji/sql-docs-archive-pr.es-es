---
title: Actualizar celdas (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- modifying cells
- XMLA, cells
- updating cells
- cells [Analysis Services]
- XML for Analysis, cells
ms.assetid: a1c61496-36ee-4bce-98d9-d13440d349aa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c3d9a7c27533666c75102d9eac3b8311bfe4af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748978"
---
# <a name="updating-cells-xmla"></a><span data-ttu-id="c896b-102">Actualizar celdas (XMLA)</span><span class="sxs-lookup"><span data-stu-id="c896b-102">Updating Cells (XMLA)</span></span>
  <span data-ttu-id="c896b-103">Puede usar el comando [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) para cambiar el valor de una o más celdas de un cubo habilitado para la reescritura del cubo.</span><span class="sxs-lookup"><span data-stu-id="c896b-103">You can use the [UpdateCells](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/updatecells-element-xmla) command to change the value of one or more cells in a cube enabled for cube writeback.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="c896b-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] almacena la información actualizada en una tabla de reescritura independiente para cada partición que contiene celdas que se van a actualizar.</span><span class="sxs-lookup"><span data-stu-id="c896b-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stores the updated information in a separate writeback table for each partition that contains cells to be updated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c896b-105">El comando `UpdateCells` no admite las asignaciones durante la reescritura del cubo.</span><span class="sxs-lookup"><span data-stu-id="c896b-105">The `UpdateCells` command does not support allocations during cube writeback.</span></span> <span data-ttu-id="c896b-106">Para usar la reescritura asignada, debe utilizar el comando [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) para enviar una instrucción UPDATE de expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="c896b-106">To use allocated writeback, you should use the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command to send a Multidimensional Expressions (MDX) UPDATE statement.</span></span> <span data-ttu-id="c896b-107">Para obtener más información, vea [instrucción UPDATE CUBE &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span><span class="sxs-lookup"><span data-stu-id="c896b-107">For more information, see [UPDATE CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-update-cube).</span></span>  
  
## <a name="specifying-cells"></a><span data-ttu-id="c896b-108">Especificar celdas</span><span class="sxs-lookup"><span data-stu-id="c896b-108">Specifying Cells</span></span>  
 <span data-ttu-id="c896b-109">La propiedad de [celda](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) del `UpdateCells` comando contiene las celdas que se van a actualizar.</span><span class="sxs-lookup"><span data-stu-id="c896b-109">The [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property of the `UpdateCells` command contains the cells to be updated.</span></span> <span data-ttu-id="c896b-110">Para identificar cada una de las celdas en la propiedad `Cell`, utilice el número ordinal de esa celda.</span><span class="sxs-lookup"><span data-stu-id="c896b-110">You identify each cell in the `Cell` property using that cell's ordinal number.</span></span> <span data-ttu-id="c896b-111">Conceptualmente, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numera las celdas de un cubo como si el cubo fuera *p*una matriz unidimensional, donde *p* es el número de ejes.</span><span class="sxs-lookup"><span data-stu-id="c896b-111">Conceptually, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] numbers cells in a cube as if the cube were a *p*-dimensional array, where *p* is the number of axes.</span></span> <span data-ttu-id="c896b-112">Las celdas se ordenan por importancia de fila.</span><span class="sxs-lookup"><span data-stu-id="c896b-112">Cells are addressed in row-major order.</span></span> <span data-ttu-id="c896b-113">En la ilustración siguiente se muestra la fórmula para calcular el número ordinal de una celda.</span><span class="sxs-lookup"><span data-stu-id="c896b-113">The following illustration shows the formula for calculating the ordinal number of a cell.</span></span>  
  
 <span data-ttu-id="c896b-114">![Fórmula para calcular la posición ordinal de la celda](../../analysis-services/dev-guide/media/cellordinalformula.gif "Fórmula para calcular la posición ordinal de la celda")</span><span class="sxs-lookup"><span data-stu-id="c896b-114">![Formula to calculate the cell ordinal position](../../analysis-services/dev-guide/media/cellordinalformula.gif "Formula to calculate the cell ordinal position")</span></span>  
  
 <span data-ttu-id="c896b-115">Una vez que conozca el número ordinal de una celda, puede indicar el valor previsto de la celda en la propiedad [Value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) de la propiedad [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="c896b-115">Once you know a cell's ordinal number, you can indicate the intended value of the cell in the [Value](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/value-element-xmla) property of the [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c896b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c896b-116">See Also</span></span>  
 <span data-ttu-id="c896b-117">[Elemento Update &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="c896b-117">[Update Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/update-element-xmla) </span></span>  
 [<span data-ttu-id="c896b-118">Desarrollar con XMLA en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c896b-118">Developing with XMLA in Analysis Services</span></span>](../multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
