---
title: Procesar datos (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d88f2dc9-2933-4be5-9bf3-48ffbc2d0a1a
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2066cb6d871f43dda719cab3539253db97bfca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750257"
---
# <a name="process-data-ssas-tabular"></a><span data-ttu-id="40cc5-102">Procesar datos (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="40cc5-102">Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="40cc5-103">Cuando se importan datos en un modelo tabular en modo de almacenamiento en caché, se captura una instantánea de esos datos en el momento de la importación.</span><span class="sxs-lookup"><span data-stu-id="40cc5-103">When you import data into a tabular model, in Cached mode, you are capturing a snapshot of that data at the time of import.</span></span> <span data-ttu-id="40cc5-104">En algunos casos, esos datos nunca cambian y no es necesario actualizarlos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="40cc5-104">In some cases, that data may never change and it does not need to be updated in the model.</span></span> <span data-ttu-id="40cc5-105">Sin embargo, es más probable que los datos que se importan cambien con regularidad, y para que el modelo refleje los datos más recientes de los orígenes de datos, es necesario procesar (actualizar) los datos y recalcular los datos calculados.</span><span class="sxs-lookup"><span data-stu-id="40cc5-105">However, it is more likely that the data you are importing from changes regularly, and in order for your model to reflect the most recent data from the data sources, it is necessary to process (refresh) the data and re-calculate calculated data.</span></span> <span data-ttu-id="40cc5-106">Para actualizar los datos del modelo, deberá realizar una acción de procesamiento en todas las tablas o en una tabla individual, mediante una partición o mediante una conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="40cc5-106">To update the data in your model, you perform a process action on all tables, on an individual table, by a partition, or by a data source connection.</span></span>  
  
 <span data-ttu-id="40cc5-107">Al crear el proyecto de modelos, las acciones de procesamiento se deben iniciar manualmente en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40cc5-107">When authoring your model project, process actions must be initiated manually in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="40cc5-108">Una vez implementado el modelo, las operaciones de procesamiento se pueden realizar utilizando [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o programar mediante un script.</span><span class="sxs-lookup"><span data-stu-id="40cc5-108">After a model has been deployed, process operations can be performed by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or scheduled by using a script.</span></span> <span data-ttu-id="40cc5-109">Todas las tareas aquí descritas pertenecen a acciones de procesamiento que puede realizar durante la creación de modelos en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40cc5-109">Tasks described here all pertain to process actions that you can do during model authoring in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="40cc5-110">Para obtener más información sobre las acciones de procesamiento para un modelo implementado, vea [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="40cc5-110">For more information about process actions for a deployed model, see [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="40cc5-111">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="40cc5-111">Related Tasks</span></span>  
  
|<span data-ttu-id="40cc5-112">Tema</span><span class="sxs-lookup"><span data-stu-id="40cc5-112">Topic</span></span>|<span data-ttu-id="40cc5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="40cc5-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="40cc5-114">Procesar manualmente los datos &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="40cc5-114">Manually Process Data &#40;SSAS Tabular&#41;</span></span>](manually-process-data-ssas-tabular.md)|<span data-ttu-id="40cc5-115">Describe cómo procesar manualmente los datos del área de trabajo del modelo.</span><span class="sxs-lookup"><span data-stu-id="40cc5-115">Describes how to manually process model workspace data.</span></span>|  
|[<span data-ttu-id="40cc5-116">Solucionar problemas del procesamiento de datos &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="40cc5-116">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)|<span data-ttu-id="40cc5-117">Describe cómo solucionar problemas de operaciones de proceso.</span><span class="sxs-lookup"><span data-stu-id="40cc5-117">Describes how to troubleshoot process operations.</span></span>|  
  
  
