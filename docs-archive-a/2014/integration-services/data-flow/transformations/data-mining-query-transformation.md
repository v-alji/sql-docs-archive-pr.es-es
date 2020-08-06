---
title: Transformación Consulta de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytrans.f1
helpviewer_keywords:
- Data Mining Query transformation
- prediction queries [Integration Services]
ms.assetid: 7960133b-a3e1-48af-ba43-55ed78c38e71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 278fdc3b1abd38b63f01e967e28d11983a09e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663036"
---
# <a name="data-mining-query-transformation"></a><span data-ttu-id="471d2-102">Consulta de minería de datos, transformación</span><span class="sxs-lookup"><span data-stu-id="471d2-102">Data Mining Query Transformation</span></span>
  <span data-ttu-id="471d2-103">La transformación Consulta de minería de datos realiza consultas de predicción en modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="471d2-103">The Data Mining Query transformation performs prediction queries against data mining models.</span></span> <span data-ttu-id="471d2-104">Esta transformación contiene un generador de consultas para crear consultas de Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="471d2-104">This transformation contains a query builder for creating Data Mining Extensions (DMX) queries.</span></span> <span data-ttu-id="471d2-105">El generador de consultas permite crear instrucciones personalizadas para evaluar los datos de entrada de la transformación en un modelo de minería existente mediante el lenguaje DMX.</span><span class="sxs-lookup"><span data-stu-id="471d2-105">The query builder lets you create custom statements for evaluating the transformation input data against an existing mining model using the DMX language.</span></span> <span data-ttu-id="471d2-106">Para más información, vea [Referencia de Extensiones de minería de datos &#40;DMX&#41;](/sql/dmx/data-mining-extensions-dmx-reference).</span><span class="sxs-lookup"><span data-stu-id="471d2-106">For more information, see [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference).</span></span>  
  
 <span data-ttu-id="471d2-107">Una transformación puede ejecutar múltiples consultas de predicción si los modelos se generan a partir de la misma estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="471d2-107">One transformation can execute multiple prediction queries if the models are built on the same data mining structure.</span></span> <span data-ttu-id="471d2-108">Para obtener más información, vea [interfaces de consulta de minería de datos](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span><span class="sxs-lookup"><span data-stu-id="471d2-108">For more information, see [Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span></span>  
  
## <a name="configuration-of-the-data-mining-query-transformation"></a><span data-ttu-id="471d2-109">Configuración de la transformación Consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="471d2-109">Configuration of the Data Mining Query Transformation</span></span>  
 <span data-ttu-id="471d2-110">La transformación Consulta de minería de datos utiliza un administrador de conexiones de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] para conectar con el proyecto de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] o la instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] que contiene la estructura de minería y los modelos de minería.</span><span class="sxs-lookup"><span data-stu-id="471d2-110">The Data Mining Query transformation uses an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models.</span></span> <span data-ttu-id="471d2-111">Para más información, consulte [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="471d2-111">For more information, see [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="471d2-112">Esta transformación tiene una entrada y una salida.</span><span class="sxs-lookup"><span data-stu-id="471d2-112">This transformation has one input and one output.</span></span> <span data-ttu-id="471d2-113">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="471d2-113">It does not support an error output.</span></span>  
  
 <span data-ttu-id="471d2-114">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="471d2-114">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="471d2-115">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Consulta de minería de datos** , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="471d2-115">For more information about the properties that you can set in the **Data Mining Query Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="471d2-116">Editor de transformación Consulta de minería de datos &#40;pestaña Modelo de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="471d2-116">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
-   [<span data-ttu-id="471d2-117">Editor de transformación Consulta de minería de datos &#40;pestaña Modelo de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="471d2-117">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
 <span data-ttu-id="471d2-118">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="471d2-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="471d2-119">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="471d2-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="471d2-120">Common Properties</span><span class="sxs-lookup"><span data-stu-id="471d2-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="471d2-121">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="471d2-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="471d2-122">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="471d2-122">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
