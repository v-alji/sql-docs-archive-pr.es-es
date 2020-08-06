---
title: Procesar particiones en la base de datos del área de trabajo (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3a369705-43fa-4961-9045-32e06fbdde33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4a996e90b30794882535327ea3192d7e72818422
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744338"
---
# <a name="process-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="ab2bb-102">Procesar particiones en la base de datos del área de trabajo (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="ab2bb-102">Process Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="ab2bb-103">Las particiones dividen una tabla en partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="ab2bb-104">A continuación, cada partición se puede procesar (actualizar) de forma independiente de las demás particiones.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="ab2bb-105">Las tareas de este tema describen cómo procesar particiones en la base de datos del área de trabajo del modelo mediante el cuadro de diálogo **Procesar particiones** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab2bb-105">The tasks in this topic describe how to process partitions in the model workspace database by using the **Process Partitions** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ab2bb-106">Una vez implementado un modelo en otra instancia de Analysis Services, los administradores de bases de datos pueden crear y administrar las particiones del modelo (implementado) mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], mediante un script o usando un paquete IS.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-106">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], by script, or by using an IS package.</span></span> <span data-ttu-id="ab2bb-107">Para obtener más información, vea [Crear y administrar particiones de modelos tabulares &#40;SSAS tabular&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="ab2bb-107">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="ab2bb-108">Para procesar una partición</span><span class="sxs-lookup"><span data-stu-id="ab2bb-108">To process a partition</span></span>  
  
1.  <span data-ttu-id="ab2bb-109">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** , en **Procesar** (Actualizar) y, por último, en **Procesar particiones**.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-109">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="ab2bb-110">En el cuadro de lista **Modo** , seleccione uno de los modos de procesamiento siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab2bb-110">In the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="ab2bb-111">Mode</span><span class="sxs-lookup"><span data-stu-id="ab2bb-111">Mode</span></span>|<span data-ttu-id="ab2bb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab2bb-112">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="ab2bb-113">**Proceso predeterminado**</span><span class="sxs-lookup"><span data-stu-id="ab2bb-113">**Process Default**</span></span>|<span data-ttu-id="ab2bb-114">Detecta el estado de proceso de un objeto de partición y realiza el procesamiento necesario para devolver objetos de partición sin procesar o procesados parcialmente a un estado de procesamiento completo.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-114">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="ab2bb-115">Se cargan los datos de las tablas vacías y las particiones; se generan o se vuelven a generar las jerarquías, las columnas calculadas y las relaciones.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-115">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="ab2bb-116">**Proceso completo**</span><span class="sxs-lookup"><span data-stu-id="ab2bb-116">**Process Full**</span></span>|<span data-ttu-id="ab2bb-117">Procesa un objeto de partición y todos los objetos que contiene.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-117">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="ab2bb-118">Cuando se ejecuta Proceso completo en un objeto que ya se ha procesado, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quita todos los datos del objeto y, a continuación, lo procesa.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-118">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="ab2bb-119">Este tipo de procesamiento es necesario cuando se ha realizado un cambio estructural en un objeto.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-119">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="ab2bb-120">**Procesar datos**</span><span class="sxs-lookup"><span data-stu-id="ab2bb-120">**Process Data**</span></span>|<span data-ttu-id="ab2bb-121">Carga datos en una partición o en una tabla sin volver a generar las jerarquías o las relaciones, ni volver a calcular las columnas calculadas y las medidas.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-121">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="ab2bb-122">**Procesar borrado**</span><span class="sxs-lookup"><span data-stu-id="ab2bb-122">**Process Clear**</span></span>|<span data-ttu-id="ab2bb-123">Quita todos los datos de una partición.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-123">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="ab2bb-124">**Procesar adición**</span><span class="sxs-lookup"><span data-stu-id="ab2bb-124">**Process Add**</span></span>|<span data-ttu-id="ab2bb-125">Actualiza la partición con nuevos datos de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-125">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="ab2bb-126">En la columna de casilla **Procesar** , seleccione las particiones que desea procesar con el modo seleccionado y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab2bb-126">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2bb-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab2bb-127">See Also</span></span>  
 <span data-ttu-id="ab2bb-128">[Particiones &#40;&#41;tabular de SSAS](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ab2bb-128">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="ab2bb-129">Crear y administrar particiones en la base de datos del área de trabajo &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="ab2bb-129">Create and Manage Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](workspace-database-ssas-tabular.md)  
  
  
