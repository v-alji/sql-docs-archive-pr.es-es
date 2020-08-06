---
title: Finalización del asistente (Asistente para particiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.finish.f1
ms.assetid: 68a4dd5d-94d9-4a02-be31-949a6da0ef51
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60be28170e8f8ec156d1c37149ddbc04b64bf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670041"
---
# <a name="completing-the-wizard-partition-wizard"></a><span data-ttu-id="daef7-102">Finalización del asistente (Asistente para particiones)</span><span class="sxs-lookup"><span data-stu-id="daef7-102">Completing the Wizard (Partition Wizard)</span></span>
  <span data-ttu-id="daef7-103">Use la página **Finalización del asistente** para asignar un nombre a la partición, definir el diseño de agregaciones para la partición y, opcionalmente, implementar y procesar la partición después de completar el Asistente para particiones.</span><span class="sxs-lookup"><span data-stu-id="daef7-103">Use the **Completing the Wizard** page to name the partition, define the aggregation design for your partition, and optionally deploy and process the partition after completing the Partition Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="daef7-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="daef7-104">Options</span></span>  
 <span data-ttu-id="daef7-105">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="daef7-105">**Name**</span></span>  
 <span data-ttu-id="daef7-106">Escriba el nombre para la nueva partición.</span><span class="sxs-lookup"><span data-stu-id="daef7-106">Type the name for the new partition.</span></span> <span data-ttu-id="daef7-107">Si está trabajando con múltiples tablas, escriba el prefijo que se combinará con el nombre de la tabla para crear el nombre de cada partición.</span><span class="sxs-lookup"><span data-stu-id="daef7-107">If you are working with multiple tables, enter the prefix that will be combined with the table name to create each partition name.</span></span>  
  
 <span data-ttu-id="daef7-108">**Opciones de agregaciones**</span><span class="sxs-lookup"><span data-stu-id="daef7-108">**Aggregation options**</span></span>  
 <span data-ttu-id="daef7-109">Especifica la opción de agregación para la partición.</span><span class="sxs-lookup"><span data-stu-id="daef7-109">Specifies the aggregation option for the partition.</span></span>  
  
 <span data-ttu-id="daef7-110">En la tabla siguiente se enumeran las opciones de agregación disponibles.</span><span class="sxs-lookup"><span data-stu-id="daef7-110">The following table lists the aggregation options that are available.</span></span>  
  
|<span data-ttu-id="daef7-111">Opción</span><span class="sxs-lookup"><span data-stu-id="daef7-111">Option</span></span>|<span data-ttu-id="daef7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="daef7-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="daef7-113">**Diseñar las agregaciones de la partición ahora**</span><span class="sxs-lookup"><span data-stu-id="daef7-113">**Design aggregations for the partition now**</span></span>|<span data-ttu-id="daef7-114">Diseña las agregaciones para la nueva partición después de que el Asistente para particiones cree la nueva partición.</span><span class="sxs-lookup"><span data-stu-id="daef7-114">Designs aggregations for the new partition after the Partition Wizard creates the new partition.</span></span> <span data-ttu-id="daef7-115">Al seleccionar esta opción se inicia el Asistente para diseñar agregaciones después de hacer clic en **Finalizar** en el Asistente para particiones.</span><span class="sxs-lookup"><span data-stu-id="daef7-115">Selecting this option starts the Aggregation Design Wizard after you click **Finish** in the Partition Wizard.</span></span> <span data-ttu-id="daef7-116">Para más información sobre el Asistente para diseñar agregaciones, vea [Asistente para diseñar agregaciones (Ayuda F1, SSAS)](aggregation-design-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="daef7-116">For more information about the Aggregation Design Wizard, see [Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md).</span></span>|  
|<span data-ttu-id="daef7-117">**Diseñar las agregaciones posteriormente**</span><span class="sxs-lookup"><span data-stu-id="daef7-117">**Design the aggregations later**</span></span>|<span data-ttu-id="daef7-118">Crea la partición sin diseñar agregaciones en este momento.</span><span class="sxs-lookup"><span data-stu-id="daef7-118">Creates the partition without designing aggregations at this time.</span></span>|  
|<span data-ttu-id="daef7-119">**Copiar el diseño de las agregaciones de una partición existente**</span><span class="sxs-lookup"><span data-stu-id="daef7-119">**Copy the aggregation design from an existing partition**</span></span>|<span data-ttu-id="daef7-120">Copia en al nueva partición el diseño de agregaciones de una partición existente en el grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="daef7-120">Copies the aggregation design from an existing partition in the measure group to the new partition.</span></span> <span data-ttu-id="daef7-121">Al hacer clic en esta opción, se habilita la opción **Copiar de** .</span><span class="sxs-lookup"><span data-stu-id="daef7-121">Clicking this option makes the **Copy from** option available.</span></span> <span data-ttu-id="daef7-122">Utilice la opción **Copiar de** para seleccionar la partición desde la cual se va a copiar el diseño de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="daef7-122">Use the **Copy from** option to select the partition from which to copy the aggregation design.</span></span><br /><br /> <span data-ttu-id="daef7-123">Tenga en cuenta que las particiones que se puedan mezclar en el futuro deben tener la misma estructura de tabla y el mismo diseño de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="daef7-123">Note that partitions that may be merged in the future must have the same table structure and aggregation design.</span></span> <span data-ttu-id="daef7-124">Si desea mezclar la nueva partición con una partición existente en el grupo de medida, deberá copiar el diseño de agregaciones de la partición existente en la partición nueva.</span><span class="sxs-lookup"><span data-stu-id="daef7-124">If you might merge the new partition with an existing partition in the measure group, you should copy the aggregation design of the existing partition into the new partition.</span></span>|  
  
 <span data-ttu-id="daef7-125">**Implementar y procesar ahora**</span><span class="sxs-lookup"><span data-stu-id="daef7-125">**Deploy and Process Now**</span></span>  
 <span data-ttu-id="daef7-126">Implementa y procesa la partición en la instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] especificada en la página **Ubicaciones de procesamiento y almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="daef7-126">Deploys and processes the partition to the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance specified on the **Processing and Storage Locations** page.</span></span> <span data-ttu-id="daef7-127">El asistente implementa y procesa la partición una vez que se ha hecho clic en **Finalizar** en esta página.</span><span class="sxs-lookup"><span data-stu-id="daef7-127">The wizard deploys and processes the partition after you click **Finish** on this page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daef7-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="daef7-128">See Also</span></span>  
 [<span data-ttu-id="daef7-129">Particiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="daef7-129">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
