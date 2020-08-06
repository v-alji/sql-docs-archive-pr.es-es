---
title: Cuadro de diálogo partición de mezcla (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.mergepartition.f1
ms.assetid: 1c94e250-ee18-4f98-b112-985f6346102a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1978c187bfb5097d286f78650b5bda6645c7a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676235"
---
# <a name="merge-partition-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="a8ffe-102">Cuadro de diálogo Partición de mezcla (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="a8ffe-102">Merge Partition Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="a8ffe-103">Utilice el cuadro de diálogo **Partición de mezcla** de **SQL Server Management Studio** para mezclar las particiones de un grupo de medida en un cubo.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-103">Use the **Merge Partition** dialog box in **SQL Server Management Studio** to merge partitions for a measure group in a cube.</span></span> <span data-ttu-id="a8ffe-104">Para mostrar el cuadro de diálogo **Partición de mezcla** , haga clic con el botón derecho en la carpeta Particiones o en una partición del **Explorador de objetos** y seleccione **Partición de mezcla** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-104">You can display the **Merge Partition** dialog box by right-clicking the Partitions folder or a partition in **Object Explorer** and selecting **Merge Partitions** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a8ffe-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="a8ffe-105">Options</span></span>  
 <span data-ttu-id="a8ffe-106">**Server**</span><span class="sxs-lookup"><span data-stu-id="a8ffe-106">**Server**</span></span>  
 <span data-ttu-id="a8ffe-107">Seleccione el nombre de la instancia de Analysis Services que contiene la partición de destino.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-107">Select the name of the Analysis Services instance that contains the target partition.</span></span>  
  
 <span data-ttu-id="a8ffe-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a8ffe-108">**Name**</span></span>  
 <span data-ttu-id="a8ffe-109">Seleccione el nombre de la partición existente que se utilizará como partición de destino.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-109">Select the name of an existing partition to use as the target partition.</span></span>  
  
 <span data-ttu-id="a8ffe-110">**Carpeta**</span><span class="sxs-lookup"><span data-stu-id="a8ffe-110">**Folder**</span></span>  
 <span data-ttu-id="a8ffe-111">Muestra el nombre de la carpeta que contiene la partición de destino, si la partición seleccionada en Nombre no utiliza la carpeta predeterminada para la instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-111">Displays the name of the folder that contains the target partition, if the partition selected in Name does not use the default folder for the Analysis Services instance.</span></span>  
  
 <span data-ttu-id="a8ffe-112">**Particiones de origen**</span><span class="sxs-lookup"><span data-stu-id="a8ffe-112">**Source Partitions**</span></span>  
 <span data-ttu-id="a8ffe-113">Muestra una cuadrícula que contiene las particiones de origen que se pueden mezclar con la partición de destino.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-113">Displays a grind containing the source partitions that can be merged into the target partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8ffe-114">Solo se pueden mezclar las particiones que conforman el mismo grupo de medida y que comparten el mismo diseño de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-114">Only partitions in the same measure group that share the same aggregation design can be merged.</span></span>  
  
 <span data-ttu-id="a8ffe-115">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8ffe-115">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="a8ffe-116">Columna</span><span class="sxs-lookup"><span data-stu-id="a8ffe-116">Column</span></span>|<span data-ttu-id="a8ffe-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8ffe-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a8ffe-118">**Combinar**</span><span class="sxs-lookup"><span data-stu-id="a8ffe-118">**Merge**</span></span>|<span data-ttu-id="a8ffe-119">Seleccione esta columna para mezclar la partición de origen con la de destino.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-119">Select to merge the source partition into the target partition.</span></span>|  
|<span data-ttu-id="a8ffe-120">**Nombre de la partición**</span><span class="sxs-lookup"><span data-stu-id="a8ffe-120">**Partition Name**</span></span>|<span data-ttu-id="a8ffe-121">Muestra el nombre de la partición de origen.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-121">Displays the name of the source partition.</span></span>|  
|<span data-ttu-id="a8ffe-122">**Procesado por última vez**</span><span class="sxs-lookup"><span data-stu-id="a8ffe-122">**Last Processed**</span></span>|<span data-ttu-id="a8ffe-123">Muestra la fecha y la hora en que la partición de origen se procesó por última vez.</span><span class="sxs-lookup"><span data-stu-id="a8ffe-123">Displays the date and time at which the source partition was last processed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8ffe-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8ffe-124">See Also</span></span>  
 <span data-ttu-id="a8ffe-125">[Particiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a8ffe-125">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="a8ffe-126">Mezclar particiones en Analysis Services &#40;SSAS - Multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="a8ffe-126">Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;</span></span>](multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md)  
  
  
