---
title: Asistente para optimización basada en el uso (ayuda F1) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.f1
helpviewer_keywords:
- Usage-Based Optimization Wizard
ms.assetid: e5f5a938-ae7c-4f4e-9416-a7f94ac82763
author: minewiskan
ms.author: owend
ms.openlocfilehash: 517c122f79421294e1dfa562665948c4dc7bf95f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747730"
---
# <a name="usage-based-optimization-wizard-f1-help"></a><span data-ttu-id="b1338-102">Asistente para optimización basada en el uso (Ayuda F1)</span><span class="sxs-lookup"><span data-stu-id="b1338-102">Usage-Based Optimization Wizard F1 Help</span></span>
  <span data-ttu-id="b1338-103">El Asistente para optimización basada en el uso es parecido en su resultado al Asistente para diseñar agregaciones, y se utiliza para diseñar agregaciones para una partición.</span><span class="sxs-lookup"><span data-stu-id="b1338-103">The Usage-Based Optimization Wizard is similar in output to the Aggregation Design Wizard, and is used to design aggregations for a partition.</span></span> <span data-ttu-id="b1338-104">No obstante, el Asistente para optimización basada en el uso diseña agregaciones en función de patrones de uso específicos de consultas registradas en un registro de consultas de una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1338-104">However, the Usage-Based Optimization Wizard designs aggregations based on the specific usage patterns of queries recorded in the query log of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="b1338-105">Las agregaciones proporcionan mejoras de rendimiento al permitir [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que recupere los totales calculados previamente directamente desde el almacenamiento de cubos en lugar de tener que volver a calcular los datos de un origen de datos subyacente para cada consulta.</span><span class="sxs-lookup"><span data-stu-id="b1338-105">Aggregations provide performance improvements by allowing [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to retrieve pre-calculated totals directly from cube storage instead of having to recalculate data from an underlying data source for each query.</span></span>  
  
 <span data-ttu-id="b1338-106">Para abrir el Asistente para optimización basada en el uso desde [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , abra el diseñador de cubos para un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proyecto de y, a continuación, haga clic en la pestaña **agregaciones** . Haga clic en el botón **optimización basada** en el uso en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b1338-106">To open the Usage-Based Optimization Wizard from within [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the cube designer for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click the **Aggregations** tab. Click the **Usage Based Optimization** button in the toolbar.</span></span>  
  
 <span data-ttu-id="b1338-107">Para abrir el Asistente para optimización basada en el uso desde dentro de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], conéctese a una base de datos [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, después, abra la carpeta **Cubos** .</span><span class="sxs-lookup"><span data-stu-id="b1338-107">To open the Usage-Based Optimization Wizard from within [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and then open the **Cubes** folder.</span></span> <span data-ttu-id="b1338-108">Seleccione un cubo y, a continuación, abra la carpeta **Grupos de medida** y expanda el grupo de medida que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="b1338-108">Select a cube and then open the **Measure Groups** folder and expand the measure group that you want to modify.</span></span> <span data-ttu-id="b1338-109">Haga clic con el botón derecho en la carpeta **Particiones** y, después, seleccione **Optimización basada en el uso**.</span><span class="sxs-lookup"><span data-stu-id="b1338-109">Right-click the **Partitions** folder and then select **Usage Based Optimization**.</span></span>  
  
 <span data-ttu-id="b1338-110">Para diseñar estas agregaciones, puede utilizar el Asistente para diseñar agregaciones.</span><span class="sxs-lookup"><span data-stu-id="b1338-110">To design these aggregations, you can use the Aggregation Design Wizard.</span></span> <span data-ttu-id="b1338-111">Este asistente le guía por los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="b1338-111">This wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="b1338-112">Seleccionar una configuración estándar o personalizada para las opciones de almacenamiento y almacenamiento en caché de una partición, grupo de medida o cubo.</span><span class="sxs-lookup"><span data-stu-id="b1338-112">Selecting standard or custom settings for the storage and caching options of a partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="b1338-113">Proporcionar recuentos estimados o reales de los objetos a los que hace referencia la partición, el grupo de medida o el cubo.</span><span class="sxs-lookup"><span data-stu-id="b1338-113">Providing estimated or actual counts for objects referenced by the partition, measure group, or cube.</span></span>  
  
-   <span data-ttu-id="b1338-114">Especificar opciones y límites de agregación para optimizar el rendimiento de almacenamiento y de consulta de las agregaciones diseñadas.</span><span class="sxs-lookup"><span data-stu-id="b1338-114">Specifying aggregation options and limits to optimize the storage and query performance delivered by designed aggregations.</span></span>  
  
-   <span data-ttu-id="b1338-115">Guardar y, opcionalmente, procesar la partición, el grupo de medida o el cubo para generar las agregaciones definidas.</span><span class="sxs-lookup"><span data-stu-id="b1338-115">Saving and optionally processing the partition, measure group, or cube to generate the defined aggregations.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="b1338-116">proporciona el Asistente para diseñar agregaciones para diseñar agregaciones basadas en el análisis estadístico de la estructura de la partición y ofrecer, de este modo, un diseño de agregaciones que pueda limitarse según el tamaño de almacenamiento o la ganancia de rendimiento estimada.</span><span class="sxs-lookup"><span data-stu-id="b1338-116">provides the Aggregation Design Wizard to design aggregations based on statistical analysis of the structure of the partition to deliver an aggregation design that can be limited by storage size or estimated performance gain.</span></span> <span data-ttu-id="b1338-117">Puede utilizar el Asistente para diseñar agregaciones para mejorar el rendimiento global de una partición, pero el diseño de la agregación no va destinado a las necesidades específicas de los usuarios de empresa.</span><span class="sxs-lookup"><span data-stu-id="b1338-117">You can use the Aggregation Design Wizard to improve the overall performance of a partition, but the aggregation design is not targeted to the specific needs of your business users.</span></span> <span data-ttu-id="b1338-118">El Asistente para optimización basada en el uso puede proporcionar un diseño de agregaciones destinado a estas necesidades específicas, pero el asistente solo puede hacerlo si el registro de consultas para la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] contiene suficiente información para construir dichas consultas.</span><span class="sxs-lookup"><span data-stu-id="b1338-118">The Usage-Based Optimization Wizard can provide an aggregation design targeted to these specific needs, but the wizard can do so only if the query log for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance contains enough information to construct such queries.</span></span>  
  
 <span data-ttu-id="b1338-119">Generalmente, ambos asistentes se utilizan conjuntamente para mejorar el rendimiento durante la implementación y a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="b1338-119">Typically, both wizards are used together to improve performance both upon deployment and over time.</span></span> <span data-ttu-id="b1338-120">El Asistente para diseñar agregaciones debe utilizarse en primer lugar, cuando se implementa inicialmente la partición (o el cubo o grupo de medida que contiene la partición), para proporcionar beneficios sobre el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="b1338-120">The Aggregation Design Wizard should be used first, when the partition (or the cube or measure group containing the partition) is initially deployed, to provide an overall performance benefit.</span></span> <span data-ttu-id="b1338-121">Tras un período de tiempo durante el que habrá registrado las consultas de los usuarios de empresa para la partición en el registro de consultas, puede utilizar el Asistente para optimización basada en el uso para centrar la agregación en el diseño con el fin de optimizar el rendimiento y satisfacer los requisitos de las consultas de los usuarios de empresa.</span><span class="sxs-lookup"><span data-stu-id="b1338-121">After a period of time during which you have recorded the queries of business users for the partition in the query log, you can then use the Usage-Based Optimization Wizard to further focus the aggregation design to better serve the performance and query requirements of your business users.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1338-122">Para más información sobre cómo configurar el registro de consultas, vea [Configuring the Analysis Services Query Log (Configuración del registro de consultas de Analysis Services)](instances/log-operations-in-analysis-services.md?view=sql-server-2014#bkmk_querylog).</span><span class="sxs-lookup"><span data-stu-id="b1338-122">For information about configuring the query log, see [Configuring the Analysis Services Query Log](instances/log-operations-in-analysis-services.md?view=sql-server-2014#bkmk_querylog).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1338-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b1338-123">In This Section</span></span>  
  
-   [<span data-ttu-id="b1338-124">Seleccione las particiones para modificar &#40;Asistente para optimización basada en el uso&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-124">Select Partitions to Modify &#40;Usage-Based Optimization Wizard&#41;</span></span>](select-partitions-to-modify-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="b1338-125">Especificar criterios de consulta &#40;Asistente para optimización basada en el uso&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-125">Specify Query Criteria &#40;Usage-Based Optimization Wizard&#41;</span></span>](specify-query-criteria-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="b1338-126">Revise las consultas que se optimizarán &#40;Asistente para optimización basada en el uso&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-126">Review the Queries that will be Optimized &#40;Usage-Based Optimization Wizard&#41;</span></span>](review-the-queries-that-will-be-optimized-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="b1338-127">Revise el uso de agregaciones &#40;Asistente para optimización basado en el uso&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-127">Review Aggregation Usage &#40;Usage-Based Optimiation Wizard&#41;</span></span>](review-aggregation-usage-usage-based-optimiation-wizard.md)  
  
-   [<span data-ttu-id="b1338-128">Especificar recuentos de objetos &#40;Asistente para optimización basada en el uso&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-128">Specify Object Counts &#40;Usage-Based Optimization Wizard&#41;</span></span>](specify-object-counts-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="b1338-129">Establezca las opciones de agregación &#40;Asistente para optimización basada en el uso&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-129">Set Aggregation Options &#40;Usage-Based Optimization Wizard&#41;</span></span>](set-aggregation-options-usage-based-optimization-wizard.md)  
  
-   [<span data-ttu-id="b1338-130">Finalización del asistente &#40;Asistente para optimización basada en el uso&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-130">Completing the Wizard &#40;Usage-Based Optimization Wizard&#41;</span></span>](completing-the-wizard-usage-based-optimization-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1338-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1338-131">See Also</span></span>  
 <span data-ttu-id="b1338-132">[Agregaciones y diseños de agregaciones](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span><span class="sxs-lookup"><span data-stu-id="b1338-132">[Aggregations and Aggregation Designs](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md) </span></span>  
 <span data-ttu-id="b1338-133">[Cubos en modelos multidimensionales](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b1338-133">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="b1338-134">[Asistente para diseñar agregaciones (ayuda F1)](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b1338-134">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="b1338-135">Analysis Services asistentes &#40;datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="b1338-135">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  