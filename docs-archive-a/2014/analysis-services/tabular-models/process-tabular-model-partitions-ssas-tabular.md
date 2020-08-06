---
title: Procesar particiones de modelos tabulares (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6c498d2b-22d6-4661-bc21-2ee708336c8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 496874707bd4030a98b1794fe7513d1d857390ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744335"
---
# <a name="process-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="859ba-102">Procesar particiones de modelos tabulares (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="859ba-102">Process Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="859ba-103">Las particiones dividen una tabla en partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="859ba-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="859ba-104">A continuación, cada partición se puede procesar (actualizar) de forma independiente de las demás particiones.</span><span class="sxs-lookup"><span data-stu-id="859ba-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="859ba-105">Las tareas de este tema describen cómo procesar particiones en una base de datos del modelo mediante el cuadro de diálogo **Procesar particiones** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="859ba-105">The tasks in this topic describe how to process partitions in a model database by using the **Process Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="859ba-106">Para procesar una partición</span><span class="sxs-lookup"><span data-stu-id="859ba-106">To process a partition</span></span>  
  
1.  <span data-ttu-id="859ba-107">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho en la tabla que tiene las particiones que quiere procesar y, después, haga clic en **Particiones**.</span><span class="sxs-lookup"><span data-stu-id="859ba-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on the table that has the partitions you want to process, and then click **Partitions**.</span></span>  
  
2.  <span data-ttu-id="859ba-108">En el cuadro de diálogo **Particiones** , en **Particiones**, haga clic en el botón Procesar.</span><span class="sxs-lookup"><span data-stu-id="859ba-108">In the **Partitions** dialog box, in **Partitions**, click on the Process button.</span></span>  
  
3.  <span data-ttu-id="859ba-109">En el cuadro de diálogo **procesar particiones** , en el cuadro de lista **modo** , seleccione uno de los siguientes modos de proceso:</span><span class="sxs-lookup"><span data-stu-id="859ba-109">In the **Process Partition(s)** dialog box, in the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="859ba-110">Mode</span><span class="sxs-lookup"><span data-stu-id="859ba-110">Mode</span></span>|<span data-ttu-id="859ba-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="859ba-111">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="859ba-112">**Proceso predeterminado**</span><span class="sxs-lookup"><span data-stu-id="859ba-112">**Process Default**</span></span>|<span data-ttu-id="859ba-113">Detecta el estado de proceso de un objeto de partición y realiza el procesamiento necesario para devolver objetos de partición sin procesar o procesados parcialmente a un estado de procesamiento completo.</span><span class="sxs-lookup"><span data-stu-id="859ba-113">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="859ba-114">Se cargan los datos de las tablas vacías y las particiones; se generan o se vuelven a generar las jerarquías, las columnas calculadas y las relaciones.</span><span class="sxs-lookup"><span data-stu-id="859ba-114">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="859ba-115">**Proceso completo**</span><span class="sxs-lookup"><span data-stu-id="859ba-115">**Process Full**</span></span>|<span data-ttu-id="859ba-116">Procesa un objeto de partición y todos los objetos que contiene.</span><span class="sxs-lookup"><span data-stu-id="859ba-116">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="859ba-117">Cuando se ejecuta Proceso completo en un objeto que ya se ha procesado, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quita todos los datos del objeto y, a continuación, lo procesa.</span><span class="sxs-lookup"><span data-stu-id="859ba-117">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="859ba-118">Este tipo de procesamiento es necesario cuando se ha realizado un cambio estructural en un objeto.</span><span class="sxs-lookup"><span data-stu-id="859ba-118">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="859ba-119">**Procesar datos**</span><span class="sxs-lookup"><span data-stu-id="859ba-119">**Process Data**</span></span>|<span data-ttu-id="859ba-120">Carga datos en una partición o en una tabla sin volver a generar las jerarquías o las relaciones, ni volver a calcular las columnas calculadas y las medidas.</span><span class="sxs-lookup"><span data-stu-id="859ba-120">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="859ba-121">**Procesar borrado**</span><span class="sxs-lookup"><span data-stu-id="859ba-121">**Process Clear**</span></span>|<span data-ttu-id="859ba-122">Quita todos los datos de una partición.</span><span class="sxs-lookup"><span data-stu-id="859ba-122">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="859ba-123">**Procesar adición**</span><span class="sxs-lookup"><span data-stu-id="859ba-123">**Process Add**</span></span>|<span data-ttu-id="859ba-124">Actualiza la partición con nuevos datos de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="859ba-124">Incrementally update partition with new data.</span></span>|  
  
4.  <span data-ttu-id="859ba-125">En la columna de casilla **Procesar** , seleccione las particiones que desea procesar con el modo seleccionado y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="859ba-125">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859ba-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="859ba-126">See Also</span></span>  
 <span data-ttu-id="859ba-127">[Particiones de modelos tabulares &#40;SSAS tabular&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="859ba-127">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="859ba-128">Crear y administrar particiones de modelos tabulares &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="859ba-128">Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](create-and-manage-tabular-model-partitions-ssas-tabular.md)  
  
  
