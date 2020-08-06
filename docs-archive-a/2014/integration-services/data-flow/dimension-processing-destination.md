---
title: Destino de procesamiento de dimensiones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimensionprocessingdest.f1
helpviewer_keywords:
- Dimension Processing destination
- loading dimensions
- destinations [Integration Services], Dimension Processing
- dimensions [Analysis Services], processing
ms.assetid: 4c49bb95-7259-42f4-a785-bb6aaf5f8566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61cde87ac4fa5fcb1352491d787674447dd404b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670487"
---
# <a name="dimension-processing-destination"></a><span data-ttu-id="22eef-102">procesamiento de dimensiones, destino</span><span class="sxs-lookup"><span data-stu-id="22eef-102">Dimension Processing Destination</span></span>
  <span data-ttu-id="22eef-103">El destino de Procesamiento de dimensiones carga y procesa una dimensión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22eef-103">The Dimension Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="22eef-104">Para más información sobre las dimensiones, vea [Dimensiones &#40;Analysis Services - Datos multidimensionales&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="22eef-104">For more information about dimensions, see [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="22eef-105">El destino de Procesamiento de dimensiones incluye las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="22eef-105">The Dimension Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="22eef-106">Opciones para ejecutar procesamiento incremental, completo o de actualización.</span><span class="sxs-lookup"><span data-stu-id="22eef-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="22eef-107">Configuración de errores, para especificar si el procesamiento de dimensiones debe pasar por alto los errores o detenerse después de una cantidad de errores especificada.</span><span class="sxs-lookup"><span data-stu-id="22eef-107">Error configuration, to specify whether dimension processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="22eef-108">Asignación de las columnas de entrada a columnas en tablas de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="22eef-108">Mapping of input columns to columns in dimension tables.</span></span>  
  
 <span data-ttu-id="22eef-109">Para más información sobre el procesamiento de objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vea [Opciones y valores de procesamiento &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="22eef-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
## <a name="configuration-of-the-dimension-processing-destination"></a><span data-ttu-id="22eef-110">Configuración del destino de Procesamiento de dimensiones</span><span class="sxs-lookup"><span data-stu-id="22eef-110">Configuration of the Dimension Processing Destination</span></span>  
 <span data-ttu-id="22eef-111">El destino de Procesamiento de dimensiones usa un administrador de conexiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para conectarse al proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene las dimensiones que procesa el destino.</span><span class="sxs-lookup"><span data-stu-id="22eef-111">The Dimension Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the dimensions the destination processes.</span></span> <span data-ttu-id="22eef-112">Para más información, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="22eef-112">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="22eef-113">Este destino tiene una entrada.</span><span class="sxs-lookup"><span data-stu-id="22eef-113">This destination has one input.</span></span> <span data-ttu-id="22eef-114">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="22eef-114">It does not support an error output.</span></span>  
  
 <span data-ttu-id="22eef-115">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="22eef-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="22eef-116">Para obtener más información sobre las propiedades que se pueden establecer en el cuadro de diálogo **Editor de destino de procesamiento de dimensiones** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="22eef-116">For more information about the properties that you can set in the **Dimension Processing Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="22eef-117">Editor de destino de procesamiento de dimensiones &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="22eef-117">Dimension Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../dimension-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="22eef-118">Editor de destino de procesamiento de dimensiones &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="22eef-118">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../dimension-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="22eef-119">Editor de destino de procesamiento de dimensiones &#40;página Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="22eef-119">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../dimension-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="22eef-120">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="22eef-120">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="22eef-121">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="22eef-121">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="22eef-122">Common Properties</span><span class="sxs-lookup"><span data-stu-id="22eef-122">Common Properties</span></span>](../common-properties.md)  
  
 <span data-ttu-id="22eef-123">Para más información sobre cómo establecer las propiedades, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="22eef-123">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22eef-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22eef-124">See Also</span></span>  
 <span data-ttu-id="22eef-125">[Flujo de datos](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="22eef-125">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="22eef-126">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="22eef-126">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
