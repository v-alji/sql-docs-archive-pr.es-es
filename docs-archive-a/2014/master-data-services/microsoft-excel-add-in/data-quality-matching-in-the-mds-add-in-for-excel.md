---
title: Coincidencia de calidad de datos en el Complemento MDS para Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: be78d051-0d56-46d3-bb89-327e218dadd6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 037e535452e7f19644837e0cbcfd02efec5422b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676031"
---
# <a name="data-quality-matching-in-the-mds-add-in-for-excel"></a><span data-ttu-id="7a6ca-102">Coincidencia de calidad de datos en el Complemento MDS para Excel</span><span class="sxs-lookup"><span data-stu-id="7a6ca-102">Data Quality Matching in the MDS Add-in for Excel</span></span>
  <span data-ttu-id="7a6ca-103">Con el tiempo, le interesará agregar más datos al repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="7a6ca-104">Antes de agregar datos, puede ser útil comparar los nuevos datos con los que ya se administran en MDS, para asegurarse de que no se agregan datos duplicados o imprecisos.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure you are not adding duplicate or inaccurate data.</span></span>  
  
 <span data-ttu-id="7a6ca-105">MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] usa la característica Data Quality Services (DQS) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que coincidan los datos similares.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-105">The MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] uses the Data Quality Services (DQS) feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to match data that's similar.</span></span> <span data-ttu-id="7a6ca-106">Si usa la funcionalidad de coincidencia en el complemento, los registros similares se agrupan y se muestra una puntuación que representa la precisión del resultado.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-106">When you use the matching functionality in the Add-in, similar records are grouped together and a score that represents the accuracy of the result is displayed.</span></span> <span data-ttu-id="7a6ca-107">Para obtener más información acerca de la funcionalidad de coincidencia que proporciona DQS, vea [Data Matching](../../data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="7a6ca-107">For more information about the matching functionality provided by DQS, see [Data Matching](../../data-quality-services/data-matching.md).</span></span>  
  
## <a name="workflow-for-data-quality-matching"></a><span data-ttu-id="7a6ca-108">Flujo de trabajo de la coincidencia de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="7a6ca-108">Workflow for Data Quality Matching</span></span>  
 <span data-ttu-id="7a6ca-109">Al usar DQS con MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use el siguiente flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="7a6ca-109">When using DQS with the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use the following workflow:</span></span>  
  
1.  <span data-ttu-id="7a6ca-110">Recupere una lista de los datos administrados con MDS y combínelos con una lista que no se administre en MDS.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-110">Retrieve a list of MDS-managed data and combine it with a list that is not managed in MDS.</span></span> <span data-ttu-id="7a6ca-111">Para obtener más información, consulte [Combinar datos &#40;Complemento MDS para Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="7a6ca-111">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="7a6ca-112">Use el conocimiento de DQS para comparar los datos de la lista combinada.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-112">Use DQS knowledge to compare the data in the combined list.</span></span> <span data-ttu-id="7a6ca-113">Para obtener más información, consulte [Coincidir datos similares &#40;Complemento MDS para Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="7a6ca-113">For more information, see [Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md).</span></span>  
  
3.  <span data-ttu-id="7a6ca-114">Para ver más detalles sobre las similitudes encontradas por DQS, muestre las columnas de detalles.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-114">To view more details about the similarities found by DQS, show the detail columns.</span></span>  
  
4.  <span data-ttu-id="7a6ca-115">Pase a los resultados y determine qué datos se deben agregar al repositorio MDS y qué datos se duplican.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-115">Go through the results and determine which data should be added to the MDS repository and which data is duplicated.</span></span>  
  
5.  <span data-ttu-id="7a6ca-116">Publique los datos nuevos y/o actualizados en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-116">Publish the new and/or updated data to the MDS repository.</span></span>  
  
## <a name="knowledge-bases"></a><span data-ttu-id="7a6ca-117">Bases de conocimiento</span><span class="sxs-lookup"><span data-stu-id="7a6ca-117">Knowledge Bases</span></span>  
 <span data-ttu-id="7a6ca-118">Los resultados de la coincidencia que se proporcionan en el complemento se basan en una base de conocimiento DQS.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-118">The matching results provided in the Add-in are based on a DQS knowledge base.</span></span>  
  
-   <span data-ttu-id="7a6ca-119">La base de conocimiento predeterminada (DQS Data) se crea al instalar DQS.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-119">The default knowledge base (DQS Data) is created when DQS is installed.</span></span> <span data-ttu-id="7a6ca-120">Si elige utilizar la base de conocimiento predeterminada (sin agregar una directiva correspondiente a la base de conocimiento predeterminada en Data Quality Client), debe asignar columnas en la hoja de cálculo en los dominios de la base de conocimiento y asignar después un valor de ponderación a los dominios que elija.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-120">If you choose to use the default knowledge base (without adding a matching policy to the default knowledge base in the Data Quality Client), you must map columns in the worksheet to domains in the knowledge base, and then assign a weight value to the domains you choose.</span></span>  
  
-   <span data-ttu-id="7a6ca-121">Puede utilizar Data Quality Client para crear una base de conocimiento nueva con una directiva correspondiente o agregar una directiva correspondiente a la base de conocimiento predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-121">You can use the Data Quality Client to create a new knowledge base with a matching policy, or to add a matching policy to the default knowledge base.</span></span> <span data-ttu-id="7a6ca-122">En este caso, los valores de ponderación se determinan mediante la directiva de coincidencia que creó previamente y solo tiene que asignar las columnas a los dominios.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-122">In this case, the weight values are determined by the matching policy you already created and you need only to map the columns to the domains.</span></span> <span data-ttu-id="7a6ca-123">Para más información, consulte [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="7a6ca-123">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
 <span data-ttu-id="7a6ca-124">Para obtener más información acerca de las bases de conocimiento, vea [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="7a6ca-124">For more information about knowledge bases, see [DQS Knowledge Bases and Domains](../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7a6ca-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="7a6ca-125">Related Tasks</span></span>  
  
|<span data-ttu-id="7a6ca-126">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="7a6ca-126">Task Description</span></span>|<span data-ttu-id="7a6ca-127">Tema</span><span class="sxs-lookup"><span data-stu-id="7a6ca-127">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="7a6ca-128">Combinar los datos externos con los datos administrados con MDS en preparación para compararlos.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-128">Combine external data with MDS-managed data in preparation to compare it.</span></span>|[<span data-ttu-id="7a6ca-129">Combinar datos &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7a6ca-129">Combine Data &#40;MDS Add-in for Excel&#41;</span></span>](combine-data-mds-add-in-for-excel.md)|  
|<span data-ttu-id="7a6ca-130">Use el conocimiento de DQS para buscar similitudes en los datos.</span><span class="sxs-lookup"><span data-stu-id="7a6ca-130">Use DQS knowledge to find similarities in your data.</span></span>|[<span data-ttu-id="7a6ca-131">Coincidir datos similares &#40;Complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7a6ca-131">Match Similar Data &#40;MDS Add-in for Excel&#41;</span></span>](match-similar-data-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="7a6ca-132">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="7a6ca-132">Related Content</span></span>  
  
-   [<span data-ttu-id="7a6ca-133">Complemento MDS para Excel de &#40;de datos de publicación&#41;</span><span class="sxs-lookup"><span data-stu-id="7a6ca-133">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="7a6ca-134">Coincidencia de datos</span><span class="sxs-lookup"><span data-stu-id="7a6ca-134">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
