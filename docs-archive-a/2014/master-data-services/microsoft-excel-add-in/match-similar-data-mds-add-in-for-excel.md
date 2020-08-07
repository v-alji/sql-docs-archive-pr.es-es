---
title: Coincidir datos similares (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f6fd6fc1-3569-42a5-b6cb-87a921c88f3b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 70dea36de557c6fda909d06ee19ff8fa2ed6908d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745855"
---
# <a name="match-similar-data-mds-add-in-for-excel"></a><span data-ttu-id="e2a77-102">Coincidir datos similares (Complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="e2a77-102">Match Similar Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="e2a77-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use la funcionalidad Data Quality Services (DQS) para buscar similitudes en los datos.</span><span class="sxs-lookup"><span data-stu-id="e2a77-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use Data Quality Services (DQS) functionality to find similarities in your data.</span></span>  
  
 <span data-ttu-id="e2a77-104">Para realizar este procedimiento, puede:</span><span class="sxs-lookup"><span data-stu-id="e2a77-104">To perform this procedure, you can:</span></span>  
  
-   <span data-ttu-id="e2a77-105">Usar la base de conocimiento de Data Quality Services predeterminada o</span><span class="sxs-lookup"><span data-stu-id="e2a77-105">Use the default Data Quality Services knowledge base, or</span></span>  
  
-   <span data-ttu-id="e2a77-106">Crear su propia base de conocimiento DQS personalizada y directiva correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e2a77-106">Create your own custom DQS knowledge base and matching policy.</span></span> <span data-ttu-id="e2a77-107">Para más información, consulte [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e2a77-107">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2a77-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e2a77-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="e2a77-109">Debe tener una hoja de cálculo activa que contenga los datos administrados por MDS.</span><span class="sxs-lookup"><span data-stu-id="e2a77-109">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="e2a77-110">Para obtener más información, consulte [carga de datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e2a77-110">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="e2a77-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e2a77-111">Optional.</span></span> <span data-ttu-id="e2a77-112">Puede combinar otros datos con datos administrados con MDS antes de comprobar las similitudes.</span><span class="sxs-lookup"><span data-stu-id="e2a77-112">You can combine other data with the MDS-managed data before checking for similarities.</span></span> <span data-ttu-id="e2a77-113">Para obtener más información, consulte [Combinar datos &#40;Complemento MDS para Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="e2a77-113">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
### <a name="to-find-similarities-by-using-the-default-knowledge-base"></a><span data-ttu-id="e2a77-114">Para buscar similitudes con la base de conocimiento predeterminada</span><span class="sxs-lookup"><span data-stu-id="e2a77-114">To find similarities by using the default knowledge base</span></span>  
  
1.  <span data-ttu-id="e2a77-115">En la hoja de cálculo que contiene datos administrados con MDS, en el grupo **Data Quality** , haga clic en **Datos de coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="e2a77-115">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="e2a77-116">En el cuadro de diálogo **Datos de coincidencia** , en la lista **DQS de Knowledge Base** , seleccione **Datos de DQS (predeterminado)**.</span><span class="sxs-lookup"><span data-stu-id="e2a77-116">In the **Match Data** dialog box, from the **DQS Knowledge Base** list, select **DQS Data (default)**.</span></span>  
  
3.  <span data-ttu-id="e2a77-117">Para cada columna que contenga los datos que desee buscar, agregue una fila en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e2a77-117">For each column that contains data you want to match, add a row in the dialog box.</span></span> <span data-ttu-id="e2a77-118">Para obtener información sobre los campos en este cuadro de diálogo, vea [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span><span class="sxs-lookup"><span data-stu-id="e2a77-118">For information about the fields in this dialog box, see [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span></span>  
  
4.  <span data-ttu-id="e2a77-119">Cuando el total de todos los valores de peso sea igual al 100 por ciento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e2a77-119">When the total of all weight values equals 100 percent, click **OK**.</span></span>  
  
### <a name="to-find-similarities-by-using-a-custom-knowledge-base"></a><span data-ttu-id="e2a77-120">Para buscar similitudes con una base de conocimiento personalizada</span><span class="sxs-lookup"><span data-stu-id="e2a77-120">To find similarities by using a custom knowledge base</span></span>  
  
1.  <span data-ttu-id="e2a77-121">En la hoja de cálculo que contiene datos administrados con MDS, en el grupo **Data Quality** , haga clic en **Datos de coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="e2a77-121">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="e2a77-122">En la lista **Base de conocimiento DQS** , seleccione el nombre de la base de conocimiento personalizada.</span><span class="sxs-lookup"><span data-stu-id="e2a77-122">From the **DQS Knowledge Base** list, select the name of your custom knowledge base.</span></span>  
  
3.  <span data-ttu-id="e2a77-123">Para cada columna de la hoja de cálculo, seleccione un dominio DQS.</span><span class="sxs-lookup"><span data-stu-id="e2a77-123">For each column in the worksheet, select a DQS domain.</span></span>  
  
4.  <span data-ttu-id="e2a77-124">Cuando todos los dominios DQS se asignen a las columnas de la hoja de cálculo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e2a77-124">When all DQS domains are mapped to columns in the worksheet, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e2a77-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e2a77-125">Next Steps</span></span>  
  
-   <span data-ttu-id="e2a77-126">Vea información adicional para determinar qué datos son similares.</span><span class="sxs-lookup"><span data-stu-id="e2a77-126">View additional information to determine which data is similar.</span></span> <span data-ttu-id="e2a77-127">Para obtener más información, consulte [Columnas de coincidencia de calidad de datos &#40;Complemento MDS para Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="e2a77-127">For more information, see [Data Quality Matching Columns &#40;MDS Add-in for Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a77-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2a77-128">See Also</span></span>  
 <span data-ttu-id="e2a77-129">[Coincidencia de calidad de datos en el Complemento MDS para Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e2a77-129">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="e2a77-130">Coincidencia de datos</span><span class="sxs-lookup"><span data-stu-id="e2a77-130">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
