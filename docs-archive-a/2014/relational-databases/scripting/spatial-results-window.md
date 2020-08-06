---
title: Ventana Resultados espaciales
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2d5a477-6496-4d01-adee-7322ebdfadf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e018ec9f016dfc51ed1bb055ba94abf12bc878f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752082"
---
# <a name="spatial-results-window"></a><span data-ttu-id="6c677-102">Ventana Resultados espaciales</span><span class="sxs-lookup"><span data-stu-id="6c677-102">Spatial Results Window</span></span>
  <span data-ttu-id="6c677-103">La ventana **Resultados espaciales** proporciona herramientas de asignación visual para ver los datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="6c677-103">The **Spatial results** window provides visual mapping tools for viewing spatial data.</span></span> <span data-ttu-id="6c677-104">Para ver los resultados espaciales, los resultados de la consulta deben incluir una columna espacial con datos de geometría o de geografía.</span><span class="sxs-lookup"><span data-stu-id="6c677-104">To view spatial results, your query results must include a spatial column with either geometry or geography data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c677-105">La ventana **Resultados espaciales** solo está disponible si los resultados se devuelven a una cuadrícula en la ventana **Resultados** .</span><span class="sxs-lookup"><span data-stu-id="6c677-105">The **Spatial results** window is only available if your results are returned to a grid in the **Results** window.</span></span> <span data-ttu-id="6c677-106">Si especifica que los resultados se deben devolver como texto, esta ventana no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6c677-106">If you specify that your results are returned as text, this window is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c677-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="6c677-107">Options</span></span>  
 <span data-ttu-id="6c677-108">**Seleccionar columna espacial**</span><span class="sxs-lookup"><span data-stu-id="6c677-108">**Select spatial column**</span></span>  
 <span data-ttu-id="6c677-109">Especifique la columna espacial que desea ver en las columnas espaciales de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6c677-109">Specify the spatial column you want to view from the spatial columns in the query results.</span></span> <span data-ttu-id="6c677-110">Solo puede seleccionarse una columna cada vez.</span><span class="sxs-lookup"><span data-stu-id="6c677-110">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="6c677-111">**Seleccionar columna de etiqueta**</span><span class="sxs-lookup"><span data-stu-id="6c677-111">**Select label column**</span></span>  
 <span data-ttu-id="6c677-112">Especifique la columna no espacial en las columnas devueltas en los resultados de la consulta para etiquetar los datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="6c677-112">Specify the non-spatial column from the columns returned in the query results to label the spatial data.</span></span> <span data-ttu-id="6c677-113">Solo puede seleccionarse una columna cada vez.</span><span class="sxs-lookup"><span data-stu-id="6c677-113">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="6c677-114">Esta opción no está disponible si solo se devuelven instancias de punto en una consulta.</span><span class="sxs-lookup"><span data-stu-id="6c677-114">This option is not available when only point instances are returned in a query.</span></span>  
  
 <span data-ttu-id="6c677-115">**Seleccionar proyección**</span><span class="sxs-lookup"><span data-stu-id="6c677-115">**Select projection**</span></span>  
 <span data-ttu-id="6c677-116">Muestre los datos de geografía en una de estas cuatro proyecciones: Equirectangular, Mercator, Robinson o Bonne.</span><span class="sxs-lookup"><span data-stu-id="6c677-116">Display geography data in one of four projections: Equirectangular, Mercator, Robinson, or Bonne.</span></span>  
  
 <span data-ttu-id="6c677-117">Esta opción no está disponible para los datos de geometría.</span><span class="sxs-lookup"><span data-stu-id="6c677-117">This option is not available for geometry data.</span></span>  
  
 <span data-ttu-id="6c677-118">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="6c677-118">**Zoom**</span></span>  
 <span data-ttu-id="6c677-119">Ajuste la presentación del mapa en una escala exponencial.</span><span class="sxs-lookup"><span data-stu-id="6c677-119">Adjust the map display on an exponential scale.</span></span>  
  
 <span data-ttu-id="6c677-120">**Mostrar líneas de cuadrícula**</span><span class="sxs-lookup"><span data-stu-id="6c677-120">**Show grid lines**</span></span>  
 <span data-ttu-id="6c677-121">Activa o desactiva las líneas de cuadrícula de coordenadas.</span><span class="sxs-lookup"><span data-stu-id="6c677-121">Toggle coordinate gridlines on or off.</span></span>  
  
 <span data-ttu-id="6c677-122">En las formas de polígono, la etiqueta solo se muestra cuando la forma es lo suficientemente grande como para contener el texto del rótulo.</span><span class="sxs-lookup"><span data-stu-id="6c677-122">For polygon shapes, the label is displayed only when the shape is large enough to hold the label text.</span></span> <span data-ttu-id="6c677-123">Si desea mostrar las etiquetas para las formas pequeñas, ajuste el zoom.</span><span class="sxs-lookup"><span data-stu-id="6c677-123">To display labels for small shapes, adjust the zoom.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c677-124">Las instancias de punto no se pueden etiquetar.</span><span class="sxs-lookup"><span data-stu-id="6c677-124">Point instances cannot be labeled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c677-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c677-125">See Also</span></span>  
 <span data-ttu-id="6c677-126">[Ver datos espaciales en el Explorador de objetos](view-spatial-data-in-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="6c677-126">[View Spatial Data in Object Explorer](view-spatial-data-in-object-explorer.md) </span></span>  
 <span data-ttu-id="6c677-127">[Datos espaciales &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6c677-127">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span></span>  
 <span data-ttu-id="6c677-128">[Editor de consultas del motor de base de datos &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6c677-128">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="6c677-129">Editores de consultas y texto &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6c677-129">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
