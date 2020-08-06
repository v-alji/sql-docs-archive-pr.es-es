---
title: Actualizar datos (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 58dbe99a-288d-4f1c-9cd5-704d6836c945
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 49b6e7bc19c41911c626965b9d1de132796367f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750010"
---
# <a name="refreshing-data-mds-add-in-for-excel"></a><span data-ttu-id="8f0b3-102">Actualizar datos (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="8f0b3-102">Refreshing Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8f0b3-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], actualice los datos si desea obtener la información más reciente del repositorio MDS sin abrir una nueva hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], refresh data when you want to get the latest information from the MDS repository without opening a new worksheet.</span></span> <span data-ttu-id="8f0b3-104">Puede actualizar todas las celdas o una selección de ellas.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-104">You can refresh either all cells or a selection of cells.</span></span> <span data-ttu-id="8f0b3-105">Esto puede resultar útil si ha insertado columnas con fórmulas personalizadas u otros datos que no se administran en MDS y desea mantenerlos.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-105">This can be useful when you have inserted columns with custom formulas or other data that is not managed in MDS and you want to preserve it.</span></span>  
  
## <a name="when-you-can-refresh-mds-managed-data"></a><span data-ttu-id="8f0b3-106">Cuándo se pueden actualizar datos administrados por MDS</span><span class="sxs-lookup"><span data-stu-id="8f0b3-106">When You Can Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="8f0b3-107">Puede actualizar los datos administrados por MDS en una hoja de cálculo activa si esta ya contiene datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-107">You can refresh MDS-managed data in an active worksheet if the active worksheet already contains MDS-managed data.</span></span> <span data-ttu-id="8f0b3-108">Si ha cambiado los valores de atributo o ha agregado miembros a la hoja de cálculo, debe publicar los cambios para poder actualizar.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-108">If you have changed attribute values or added members to the worksheet, you must publish your changes before you can refresh.</span></span>  
  
## <a name="refreshing-a-selection"></a><span data-ttu-id="8f0b3-109">Actualizar una selección</span><span class="sxs-lookup"><span data-stu-id="8f0b3-109">Refreshing a Selection</span></span>  
 <span data-ttu-id="8f0b3-110">Puede tener la opción de actualizar todas las celdas o solo las seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-110">You have the choice of refreshing all cells or refreshing only selected cells.</span></span> <span data-ttu-id="8f0b3-111">Las celdas seleccionadas deben ser contiguas.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-111">The selected cells must be contiguous.</span></span> <span data-ttu-id="8f0b3-112">Si se selecciona un conjunto de celdas contiguas, todas las celdas administradas de MDS de ese conjunto se actualizarán para que muestren los valores actualmente almacenados en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-112">If a set of contiguous cells is selected, all MDS managed cells in that set will be updated to display the values currently stored on the server.</span></span> <span data-ttu-id="8f0b3-113">Las filas y columnas sin cambios que no administre MDS no se ven afectadas de ningún modo.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-113">Unchanged rows and columns that are not managed by MDS are not affected in any way.</span></span>  
  
## <a name="what-happens-when-you-refresh-mds-managed-data"></a><span data-ttu-id="8f0b3-114">Lo que sucede al actualizar datos administrados por MDS</span><span class="sxs-lookup"><span data-stu-id="8f0b3-114">What Happens When You Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="8f0b3-115">Al actualizar datos en el [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], lo que ocurre en los datos administrados por MDS de la hoja depende de lo que ha cambiado en el repositorio MDS desde que se cargaron los datos por última vez.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-115">When you refresh data in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], what happens to the MDS-managed data in the sheet depends on what has changed in the MDS repository since you last loaded the data.</span></span>  
  
-   <span data-ttu-id="8f0b3-116">Si se han agregado nuevos miembros al repositorio, se agregan al final de la hoja de cálculo y están resaltados en verde.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-116">If new members have been added to repository, they are added to the end of the worksheet and are highlighted in green.</span></span>  
  
-   <span data-ttu-id="8f0b3-117">Si se eliminaron miembros del repositorio, se eliminan de la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-117">If members were deleted from the repository, they are deleted from the worksheet.</span></span>  
  
-   <span data-ttu-id="8f0b3-118">Si un valor de atributo ha cambiado en el repositorio MDS, el valor de la hoja de cálculo se actualiza con el valor del repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-118">If an attribute value has changed in the MDS repository, the value in the worksheet is updated with value from the MDS repository.</span></span> <span data-ttu-id="8f0b3-119">El color de la celda no cambia.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-119">The cell color does not change.</span></span>  
  
> [!WARNING]
>  -   <span data-ttu-id="8f0b3-120">En la hoja de cálculo activa, si existen datos no administrados en las filas situadas bajo los datos administrados por MDS, los datos no administrados pueden sobrescribirse.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-120">In the active worksheet, if non-managed data exists in rows beneath the MDS-managed data, the non-managed data may be overwritten.</span></span> <span data-ttu-id="8f0b3-121">Esto ocurre cuando se actualiza la hoja y se agregan nuevas filas de datos administrados por MDS, que se superponen a los datos no administrados.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-121">This occurs when you refresh the sheet and new rows of MDS-managed data, which overlap with the non-managed data, are added.</span></span>  
> -   <span data-ttu-id="8f0b3-122">Al actualizar, se eliminan los comentarios de las celdas administradas por MDS.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-122">When you refresh, comments on MDS-managed cells are deleted.</span></span>  
  
## <a name="how-to-refresh-mds-managed-data"></a><span data-ttu-id="8f0b3-123">Cómo actualizar los datos administrados por MDS</span><span class="sxs-lookup"><span data-stu-id="8f0b3-123">How to Refresh MDS-Managed Data</span></span>  
 <span data-ttu-id="8f0b3-124">En el grupo de **Conectar y cargar** en la cinta de opciones, el botón **Actualizar** tiene dos opciones, **Actualizar todo** y **Actualizar selección**.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-124">In the **Connect and Load** group on the ribbon, the **Refresh** button has two options, **Refresh All** and **Refresh Selection**.</span></span> <span data-ttu-id="8f0b3-125">La acción predeterminada del botón de la cinta de opciones es **Actualizar todo**.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-125">The default action of the ribbon button is **Refresh All**.</span></span> <span data-ttu-id="8f0b3-126">Para actualizar la hoja completa con valores desde el servidor, haga clic en el botón de **Actualizar** o elija la opción **Actualizar todo** .</span><span class="sxs-lookup"><span data-stu-id="8f0b3-126">To refresh the entire sheet with values from the server, click the **Refresh** button or choose the **Refresh All** option.</span></span> <span data-ttu-id="8f0b3-127">Para actualizar solo algunas de las celdas de una hoja, seleccione las celdas (debe ser una selección contigua) y elija la opción **Actualizar selección** .</span><span class="sxs-lookup"><span data-stu-id="8f0b3-127">To refresh only some of the cells in a sheet, select the cells (must be one contiguous selection) and choose the **Refresh Selection** option.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8f0b3-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8f0b3-128">Related Tasks</span></span>  
  
|<span data-ttu-id="8f0b3-129">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="8f0b3-129">Task Description</span></span>|<span data-ttu-id="8f0b3-130">Tema</span><span class="sxs-lookup"><span data-stu-id="8f0b3-130">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="8f0b3-131">Crear una conexión a una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f0b3-131">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="8f0b3-132">Conectarse a un repositorio MDS &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8f0b3-132">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="8f0b3-133">Cargar datos MDS en Excel.</span><span class="sxs-lookup"><span data-stu-id="8f0b3-133">Load MDS data into Excel.</span></span>|[<span data-ttu-id="8f0b3-134">Cargar datos de MDS en Excel</span><span class="sxs-lookup"><span data-stu-id="8f0b3-134">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="8f0b3-135">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="8f0b3-135">Related Content</span></span>  
  
-   [<span data-ttu-id="8f0b3-136">Conexiones &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8f0b3-136">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="8f0b3-137">Cargando datos &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8f0b3-137">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="8f0b3-138">Complemento Master Data Services para Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8f0b3-138">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
