---
title: Diseñar agregaciones (Analysis Services-multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- aggregations [Analysis Services], partitions
- partitions [Analysis Services], aggregations
ms.assetid: 3072b7e0-6961-42ad-a287-16f391f2cec4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 18d8ea1adb645868a11b70966ba3be2ed1764fbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677244"
---
# <a name="designing-aggregations-analysis-services---multidimensional"></a><span data-ttu-id="8d21d-102">Diseñar agregaciones (Analysis Services - Multidimensional)</span><span class="sxs-lookup"><span data-stu-id="8d21d-102">Designing Aggregations (Analysis Services - Multidimensional)</span></span>
  <span data-ttu-id="8d21d-103">Las agregaciones son resúmenes precalculados de datos de cubo que permiten a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proporcionar respuestas de consulta rápidas.</span><span class="sxs-lookup"><span data-stu-id="8d21d-103">Aggregations are precalculated summaries of cube data that help enable [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to provide rapid query responses.</span></span>  
  
 <span data-ttu-id="8d21d-104">Utilice el Asistente para diseñar agregaciones para establecer las opciones de almacenamiento y para diseñar agregaciones en una partición.</span><span class="sxs-lookup"><span data-stu-id="8d21d-104">To set storage options and design aggregations for a partition, use the Aggregation Design Wizard.</span></span> <span data-ttu-id="8d21d-105">El asistente funciona en una sola partición de un grupo de medida cada vez, de manera que se pueden seleccionar distintas opciones y diseños para cada partición.</span><span class="sxs-lookup"><span data-stu-id="8d21d-105">The wizard operates on a single partition of a measure group at a time so that you can select different options and designs for each partition.</span></span> <span data-ttu-id="8d21d-106">El asistente le guía por los pasos necesarios para configurar el almacenamiento y el diseño de agregaciones para una partición.</span><span class="sxs-lookup"><span data-stu-id="8d21d-106">The wizard takes you through steps to configure storage and design aggregation for a partition.</span></span> <span data-ttu-id="8d21d-107">Para obtener más información acerca de cómo configurar el almacenamiento, vea.</span><span class="sxs-lookup"><span data-stu-id="8d21d-107">For more information about configuring storage, see.</span></span>  
  
 <span data-ttu-id="8d21d-108">Seleccione un método para controlar el número de agregaciones que diseñará el asistente y, después, deje que el asistente diseñe las agregaciones.</span><span class="sxs-lookup"><span data-stu-id="8d21d-108">Select a method for controlling the number of aggregations the wizard will design, and then let the wizard design the aggregations.</span></span>  
  
 <span data-ttu-id="8d21d-109">El objetivo es diseñar el número óptimo de agregaciones.</span><span class="sxs-lookup"><span data-stu-id="8d21d-109">The goal is to design the optimal number of aggregations.</span></span> <span data-ttu-id="8d21d-110">Este número no solo proporcionará tiempos de respuesta satisfactorios, sino que también evitará que el tamaño de la partición sea excesivo.</span><span class="sxs-lookup"><span data-stu-id="8d21d-110">This number should not only provide satisfactory response time, but also prevent excessive partition size.</span></span> <span data-ttu-id="8d21d-111">Cuanto mayor sea el número de agregaciones, menores serán los tiempos de respuesta, aunque también se necesitará más espacio de almacenamiento y más tiempo para realizar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="8d21d-111">A greater number of aggregations produces faster response times but it also requires more storage space and may take longer to compute.</span></span> <span data-ttu-id="8d21d-112">Además, a medida que el asistente diseña más agregaciones, las primeras agregaciones consiguen mejoras de rendimiento considerablemente mayores que las agregaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="8d21d-112">Moreover, as the wizard designs more and more aggregations, earlier aggregations produce considerably larger performance gains than later aggregations.</span></span> <span data-ttu-id="8d21d-113">La reducción en las agregaciones menos útiles también aumenta el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8d21d-113">Reduction in less useful aggregations increases performance as well.</span></span> <span data-ttu-id="8d21d-114">Puede controlar el número de agregaciones diseñadas por el asistente por medio de uno de los métodos disponibles que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="8d21d-114">You can control the number of aggregations the wizard designs by one of the following methods available in the wizard:</span></span>  
  
-   <span data-ttu-id="8d21d-115">Especifique un límite de espacio de almacenamiento para las agregaciones.</span><span class="sxs-lookup"><span data-stu-id="8d21d-115">Specify a storage space limit for the aggregations.</span></span>  
  
-   <span data-ttu-id="8d21d-116">Especifique un límite de ganancia de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8d21d-116">Specify a performance gain limit.</span></span>  
  
-   <span data-ttu-id="8d21d-117">Detenga manualmente el asistente cuando la curva de rendimiento frente a tamaño comience a mostrar una ganancia aceptable de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8d21d-117">Stop the wizard manually when the displayed performance versus size curve starts to level off at an acceptable performance gain.</span></span>  
  
-   <span data-ttu-id="8d21d-118">Elija no diseñar agregaciones.</span><span class="sxs-lookup"><span data-stu-id="8d21d-118">Choose not to design aggregations.</span></span>  
  
 <span data-ttu-id="8d21d-119">Para diseñar el almacenamiento, el asistente debe poder conectarse con [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="8d21d-119">To design storage, the wizard must be able to connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on the target server.</span></span> <span data-ttu-id="8d21d-120">El asistente mostrará un mensaje de error si [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no se está ejecutando en el servidor de destino o si el proceso de diseño del almacenamiento no ha podido conectarse con el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="8d21d-120">The wizard will display an error message if [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not running on the target server or if the storage design process is otherwise unable to connect to the target server.</span></span>  
  
 <span data-ttu-id="8d21d-121">El paso final del asistente le permitirá realizar el procesamiento o aplazarlo.</span><span class="sxs-lookup"><span data-stu-id="8d21d-121">The final step of the wizard allows you to process or defer processing.</span></span> <span data-ttu-id="8d21d-122">El procesamiento crea las agregaciones que se han diseñado con el asistente, mientras que el aplazamiento guarda las agregaciones diseñadas para procesarlas en el futuro, permitiendo de esta manera que continúen las actividades de diseño sin tener que realizar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8d21d-122">Processing creates the aggregations you design with the wizard, while deferring processing saves the designed aggregations for future processing, thus allowing design activities to continue without processing.</span></span> <span data-ttu-id="8d21d-123">En función del tamaño de la partición, el procesamiento podría prolongarse considerablemente.</span><span class="sxs-lookup"><span data-stu-id="8d21d-123">Depending on the size of the partition, processing may take considerable time.</span></span> <span data-ttu-id="8d21d-124">Si lo elige, puede interrumpir el procesamiento de una partición.</span><span class="sxs-lookup"><span data-stu-id="8d21d-124">If you choose, you can interrupt processing a partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d21d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d21d-125">See Also</span></span>  
 [<span data-ttu-id="8d21d-126">Agregaciones y diseños de agregaciones</span><span class="sxs-lookup"><span data-stu-id="8d21d-126">Aggregations and Aggregation Designs</span></span>](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
