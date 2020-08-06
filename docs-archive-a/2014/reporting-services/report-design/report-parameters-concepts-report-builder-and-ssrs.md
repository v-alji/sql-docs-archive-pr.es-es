---
title: Concepto de parámetros de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b0aa2159-4e49-4713-8824-5ef9a9edbc62
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b740362daea83b50a62f0b4453ce818ab21ace7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745043"
---
# <a name="report-parameters-concept-report-builder-and-ssrs"></a><span data-ttu-id="94568-102">Concepto de parámetros de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="94568-102">Report Parameters Concept (Report Builder and SSRS)</span></span>
  <span data-ttu-id="94568-103">Puede agregar parámetros a un informe para vincular informes relacionados, controlar la apariencia del informe, filtrar datos del informe o restringir el ámbito del informe a usuarios o ubicaciones específicos.</span><span class="sxs-lookup"><span data-stu-id="94568-103">You can add parameters to a report to link related reports, to control the report appearance, to filter report data, or to narrow the scope of a report to specific users or locations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="94568-104">Los parámetros de informe se crean de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="94568-104">Report parameters are created in the following ways:</span></span>  
  
-   <span data-ttu-id="94568-105">Automáticamente, cuando se define una consulta de conjunto de datos que contiene variables de consulta.</span><span class="sxs-lookup"><span data-stu-id="94568-105">Automatically, when you define dataset query that contains query variables.</span></span> <span data-ttu-id="94568-106">Para cada variable de consulta, se crean un parámetro de consulta de conjunto de datos y un parámetro de informe correspondientes con los mismos nombres.</span><span class="sxs-lookup"><span data-stu-id="94568-106">For each query variable, a corresponding dataset query parameter and report parameter with the same names are created.</span></span> <span data-ttu-id="94568-107">Un parámetro de consulta puede ser una referencia a una variable de consulta o a un parámetro de entrada para un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="94568-107">A query parameter can be a reference to a query variable or to an input parameter for a stored procedure.</span></span>  
  
-   <span data-ttu-id="94568-108">Automáticamente, cuando se agrega una referencia a un conjunto de datos compartido que contiene parámetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="94568-108">Automatically, when you add a reference to a shared dataset that contains query parameters.</span></span>  
  
-   <span data-ttu-id="94568-109">Manualmente, cuando se crean parámetros de informe en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="94568-109">Manually, when you create report parameters in the Report Data pane.</span></span> <span data-ttu-id="94568-110">Los parámetros son una de las colecciones integradas que puede incluir en una expresión o informe.</span><span class="sxs-lookup"><span data-stu-id="94568-110">Parameters are one of the built-in collections that you can include in an expression in a report.</span></span> <span data-ttu-id="94568-111">Dado que las expresiones se utilizan para definir valores a lo largo de una definición de informe, puede utilizar parámetros para controlar la apariencia del informe o para pasar valores a los subinformes relacionados o a los informes que también usan parámetros.</span><span class="sxs-lookup"><span data-stu-id="94568-111">Because expressions are used to define values throughout a report definition, you can use parameters to control report appearance or to pass values to related subreports or reports that also use parameters.</span></span>  
  
 <span data-ttu-id="94568-112">Para más información, vea [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="94568-112">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
 <span data-ttu-id="94568-113">Los parámetros se utilizan con frecuencia para filtrar los datos del informe antes y después de que se devuelvan los datos al informe.</span><span class="sxs-lookup"><span data-stu-id="94568-113">Parameters are frequently used to filter report data both before and after the data is returned to the report.</span></span> <span data-ttu-id="94568-114">Para obtener más información, vea [Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="94568-114">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="94568-115">Cuando diseñe un informe, los parámetros de informe se guardarán en la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="94568-115">When you design a report, report parameters are saved in the report definition.</span></span> <span data-ttu-id="94568-116">Cuando diseñe un informe, los parámetros de informe se guardarán y administrarán por separado, no con la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="94568-116">When you publish a report, report parameters are saved and managed separately from the report definition.</span></span> <span data-ttu-id="94568-117">Después de guardar el informe en el servidor de informes, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94568-117">After you save the report to the report server, you can do the following:</span></span>  
  
-   <span data-ttu-id="94568-118">Cambiar directamente los valores de los parámetros de informe en el servidor de informes independientemente de la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="94568-118">Change report parameter values directly on the report server independently from the report definition.</span></span>  
  
-   <span data-ttu-id="94568-119">Crear varios informes vinculados en los que cada uno sea un vínculo a la definición de informe con un conjunto independiente de valores de parámetros que se pueden administrar de forma separada en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="94568-119">Create multiple linked reports in which each linked report is a link to the report definition with a separate set of parameter values that can be managed independently on the report server.</span></span>  
  
 <span data-ttu-id="94568-120">Si está pensando crear instantáneas de informe, historiales o suscripciones a un informe publicado, debe saber cómo afectan los parámetros de informe a los requisitos de diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="94568-120">If you plan to create report snapshots, histories, or subscriptions to a published report, you must understand how report parameters affect the design requirements for the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94568-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94568-121">See Also</span></span>  
 <span data-ttu-id="94568-122">[Conceptos de creación de informes &#40;Generador de informes y SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="94568-122">[Report Authoring Concepts &#40;Report Builder and SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="94568-123">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="94568-123">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="94568-124">Tutorial: Agregar un parámetro a un informe &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="94568-124">Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;</span></span>](../tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
  
