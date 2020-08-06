---
title: Cambiar un elemento de una celda (Diseñador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91a54778-8929-41f9-bb4c-826cec636be4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 80ef171713e6505867e00e343ce17b70cab9045a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751734"
---
# <a name="change-an-item-within-a-cell-report-builder-and-ssrs"></a><span data-ttu-id="1aaab-102">Cambiar un elemento de una celda (Diseñador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="1aaab-102">Change an Item Within a Cell (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1aaab-103">Solo un elemento no contenedor, como un cuadro de texto, una línea o una imagen, se puede reemplazar por un elemento de informe nuevo.</span><span class="sxs-lookup"><span data-stu-id="1aaab-103">Only a non-container item, such as a text box, line, or image, can be replaced by a new report item.</span></span> <span data-ttu-id="1aaab-104">Por ejemplo, puede arrastrar una tabla hasta un cuadro de texto para reemplazar éste por la tabla.</span><span class="sxs-lookup"><span data-stu-id="1aaab-104">For example, you can drag a table into a text box to replace the text box with a table.</span></span>  
  
 <span data-ttu-id="1aaab-105">Si la celda contiene un elemento contenedor, por ejemplo un rectángulo, una lista, una tabla o una matriz, el nuevo elemento se agrega al elemento contenedor en lugar de reemplazarlo.</span><span class="sxs-lookup"><span data-stu-id="1aaab-105">If the cell contains a container item such as a rectangle, list, table, or matrix, the new item is added to the containing item instead of replacing it.</span></span> <span data-ttu-id="1aaab-106">Para reemplazar un elemento contenedor por un nuevo elemento, elimine el contenedor.</span><span class="sxs-lookup"><span data-stu-id="1aaab-106">To replace a container item with a new item, delete the container.</span></span> <span data-ttu-id="1aaab-107">De este modo, el elemento contenedor se reemplaza por un cuadro de texto que, a su vez, se puede reemplazar por otro elemento.</span><span class="sxs-lookup"><span data-stu-id="1aaab-107">Deleting the container item replaces it with a text box, which you can then replace with another item.</span></span>  
  
 <span data-ttu-id="1aaab-108">De forma predeterminada, todas las celdas de una tabla, matriz o región de datos de lista contienen un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="1aaab-108">By default, all cells in a table, matrix, or list data region contain a text box.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-an-item-within-a-cell"></a><span data-ttu-id="1aaab-109">Para cambiar un elemento de una celda</span><span class="sxs-lookup"><span data-stu-id="1aaab-109">To change an item within a cell</span></span>  
  
-   <span data-ttu-id="1aaab-110">En la pestaña **Insertar** , en el grupo **Regiones de datos** o **Elementos de informe** , haga clic en el elemento que desee agregar al informe y, a continuación, haga clic en este último.</span><span class="sxs-lookup"><span data-stu-id="1aaab-110">On the **Insert** tab, in the **Data Regions** or **Report Items** group, click the item that you want to add to the report, and then click the report.</span></span> <span data-ttu-id="1aaab-111">El elemento se agregará al informe.</span><span class="sxs-lookup"><span data-stu-id="1aaab-111">The item is added to the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1aaab-112">El cuadro de diálogo **Propiedades de la imagen** se abre al arrastrar un elemento de informe de imagen a una celda; en él puede establecer propiedades como el origen de la imagen antes de agregarla a la celda.</span><span class="sxs-lookup"><span data-stu-id="1aaab-112">The **Image Properties** dialog box opens when you drag an image report item to a cell, where you can set properties such as the source of the image before the image is added to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aaab-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1aaab-113">See Also</span></span>  
 <span data-ttu-id="1aaab-114">[Imágenes, cuadros de texto, rectángulos y líneas &#40;Generador de informes y SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1aaab-114">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1aaab-115">Listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1aaab-115">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
