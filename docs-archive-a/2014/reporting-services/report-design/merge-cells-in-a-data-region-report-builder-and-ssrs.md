---
title: Combinar celdas en una región de datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 43551300-89b2-4f4e-af09-69084324afaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c69ce8182bda3e0b644893e97b69280a003f5732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747463"
---
# <a name="merge-cells-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="03f7e-102">Combinar celdas en una región de datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="03f7e-102">Merge Cells in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="03f7e-103">Puede mezclar celdas en una región de datos para combinarlas, mejorar la apariencia de la región de datos o proporcionar etiquetas para los grupos de columnas y de filas.</span><span class="sxs-lookup"><span data-stu-id="03f7e-103">You can merge cells in a data region to combine cells, improve data region appearance, or provide spanning labels for column groups and row groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03f7e-104">Las celdas solo se pueden mezclar dentro de cada área de una región de datos: esquina, encabezados de columna, definición de grupo (o encabezados de fila) y cuerpo.</span><span class="sxs-lookup"><span data-stu-id="03f7e-104">Cells can only be merged within each area of a data region: corner, column headers, group definition (or row headers), and body.</span></span> <span data-ttu-id="03f7e-105">No puede mezclar celdas situadas fuera de los límites del área.</span><span class="sxs-lookup"><span data-stu-id="03f7e-105">You cannot merge cells that cross area boundaries.</span></span> <span data-ttu-id="03f7e-106">Por ejemplo, no puede mezclar una celda situada en el área de esquina de la región de datos con una celda situada en el área de grupo de filas.</span><span class="sxs-lookup"><span data-stu-id="03f7e-106">For example, you cannot merge a cell in the data region corner area with a cell in the row group area.</span></span> <span data-ttu-id="03f7e-107">Para obtener más información sobre las áreas de Tablix, vea [lists &#40;generador de informes and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="03f7e-107">For more information about tablix areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-merge-cells-in-a-data-region"></a><span data-ttu-id="03f7e-108">Para mezclar celdas en una región de datos</span><span class="sxs-lookup"><span data-stu-id="03f7e-108">To merge cells in a data region</span></span>  
  
1.  <span data-ttu-id="03f7e-109">En la región de datos de la superficie de diseño del informe, haga clic en la primera celda que desea mezclar.</span><span class="sxs-lookup"><span data-stu-id="03f7e-109">In the data region on the report design surface, click the first cell to merge.</span></span> <span data-ttu-id="03f7e-110">Mantenga presionado el botón primario del mouse y arrastre vertical u horizontalmente para seleccionar celdas adyacentes.</span><span class="sxs-lookup"><span data-stu-id="03f7e-110">Holding the left mouse button down, drag vertically or horizontally to select adjacent cells.</span></span> <span data-ttu-id="03f7e-111">Las celdas seleccionadas quedan resaltadas.</span><span class="sxs-lookup"><span data-stu-id="03f7e-111">The selected cells are highlighted.</span></span>  
  
2.  <span data-ttu-id="03f7e-112">Haga clic con el botón derecho en las celdas seleccionadas y seleccione **Combinar celdas**.</span><span class="sxs-lookup"><span data-stu-id="03f7e-112">Right-click the selected cells and select **Merge Cells**.</span></span> <span data-ttu-id="03f7e-113">Las celdas seleccionadas se combinan en una celda única.</span><span class="sxs-lookup"><span data-stu-id="03f7e-113">The selected cells are combined into a single cell.</span></span>  
  
3.  <span data-ttu-id="03f7e-114">Repita los pasos 1 y 2 para mezclar otras celdas adyacentes en una región de datos.</span><span class="sxs-lookup"><span data-stu-id="03f7e-114">Repeat steps 1 and 2 to merge other adjacent cells in a data region.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f7e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03f7e-115">See Also</span></span>  
 <span data-ttu-id="03f7e-116">[&#40;de la región de datos Tablix Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03f7e-116">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03f7e-117">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03f7e-117">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03f7e-118">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03f7e-118">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03f7e-119">[Enumera &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03f7e-119">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="03f7e-120">Listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="03f7e-120">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
