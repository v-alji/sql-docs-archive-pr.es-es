---
title: Ver datos espaciales en el Explorador de objetos
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 59cca562-e3f5-4257-b868-adcbcc0142cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 881adf69ee83ee4b7536afae0b190fbec90f132c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673616"
---
# <a name="view-spatial-data-in-object-explorer"></a><span data-ttu-id="23da1-102">Ver datos espaciales en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="23da1-102">View Spatial Data in Object Explorer</span></span>
  <span data-ttu-id="23da1-103">La ventana **Resultados espaciales** del Editor de consultas proporciona herramientas de asignación visual para ver los resultados de los datos espaciales junto con los datos mostrados en formato de cuadrícula en la ventana **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="23da1-103">The **Spatial results** window in Query Editor provides visual mapping tools for viewing spatial data results in addition to the data displayed in grid format in the **Results** window.</span></span> <span data-ttu-id="23da1-104">Para mostrar datos espaciales en la ventana **Resultados espaciales** , los resultados de la consulta deben contener al menos una columna de datos espaciales con datos de geometría o de geografía.</span><span class="sxs-lookup"><span data-stu-id="23da1-104">To display spatial data in the **Spatial Results** window, your query results must contain at least one spatial data column with either geometry or geography data.</span></span>  
  
### <a name="to-view-spatial-data-in-the-spatial-results-window"></a><span data-ttu-id="23da1-105">Para ver datos espaciales en la ventana de resultados espaciales</span><span class="sxs-lookup"><span data-stu-id="23da1-105">To view spatial data in the Spatial results window</span></span>  
  
1.  <span data-ttu-id="23da1-106">En el Editor de consultas, haga clic en la pestaña **Resultados espaciales** .</span><span class="sxs-lookup"><span data-stu-id="23da1-106">In Query Editor, click the **Spatial results** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23da1-107">Esta ventana no está disponible si los resultados de la consulta no contienen datos espaciales o si se especifica que los resultados se devuelvan como texto.</span><span class="sxs-lookup"><span data-stu-id="23da1-107">This window is not available if your query results do not contain spatial data or if you specify that your results are returned as text.</span></span>  
  
2.  <span data-ttu-id="23da1-108">Seleccione la columna que desea ver en la lista **Seleccionar columna espacial** .</span><span class="sxs-lookup"><span data-stu-id="23da1-108">Select the column you want to view from the **Select spatial column** list.</span></span> <span data-ttu-id="23da1-109">Si solo hay una columna espacial en la tabla, esta columna es la opción predeterminada en la lista.</span><span class="sxs-lookup"><span data-stu-id="23da1-109">If there is only one spatial column in your table, this column is the default option in the list.</span></span>  
  
3.  <span data-ttu-id="23da1-110">Seleccione la columna no espacial que quiere usar como etiquetas de datos en la lista **Seleccionar columna de etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="23da1-110">Select the non-spatial column you want to use as data labels from the **Select label columns** list.</span></span>  
  
4.  <span data-ttu-id="23da1-111">Seleccione la proyección que desea para los datos de geografía en la lista **Seleccionar proyección** .</span><span class="sxs-lookup"><span data-stu-id="23da1-111">Select the projection you want for geography data from the **Select projection** list.</span></span> <span data-ttu-id="23da1-112">La proyección predeterminada es Equirectangular; otras proyecciones disponibles son Mercator, Robinson o Bonne.</span><span class="sxs-lookup"><span data-stu-id="23da1-112">The default projection is Equirectangular; other projections available are Mercator, Robinson, or Bonne.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23da1-113">**Seleccionar proyección** no está disponible si la columna espacial contiene datos de geometría.</span><span class="sxs-lookup"><span data-stu-id="23da1-113">**Select projection** is not available if your spatial column contains geometry data.</span></span>  
  
5.  <span data-ttu-id="23da1-114">Ajuste el control deslizante **Zoom** para aumentar el tamaño visual de los elementos asignados.</span><span class="sxs-lookup"><span data-stu-id="23da1-114">Adjust the **Zoom** slider to increase the visual size of mapped elements.</span></span> <span data-ttu-id="23da1-115">En las formas de polígono, la etiqueta solo está visible cuando la forma es lo suficientemente grande como para contener el texto del rótulo.</span><span class="sxs-lookup"><span data-stu-id="23da1-115">For polygon shapes, the label is visible only when the shape is large enough to hold the label text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23da1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23da1-116">See Also</span></span>  
 <span data-ttu-id="23da1-117">[Ventana Resultados espaciales](spatial-results-window.md) </span><span class="sxs-lookup"><span data-stu-id="23da1-117">[Spatial Results Window](spatial-results-window.md) </span></span>  
 <span data-ttu-id="23da1-118">[Editor de consultas del motor de base de datos &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="23da1-118">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="23da1-119">Editores de consultas y texto &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="23da1-119">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
