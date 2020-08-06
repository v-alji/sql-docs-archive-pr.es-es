---
title: Detalle del enlace de consultas (cuadro de diálogo origen de la partición) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitionfilterexpression.f1
ms.assetid: 697874d4-3f7a-4126-96f5-37cc8e2ee306
author: minewiskan
ms.author: owend
ms.openlocfilehash: 59d2ae1fed9d22366786e21a287a621f08418a5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673287"
---
# <a name="query-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="fc2dd-102">Detalle del enlace de consultas (cuadro de diálogo Origen de la partición) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="fc2dd-102">Query Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="fc2dd-103">Use la opción **Enlace de consultas** del cuadro de diálogo **Origen de la partición** para especificar la consulta que proporciona los datos para la partición.</span><span class="sxs-lookup"><span data-stu-id="fc2dd-103">Use the **Query Binding** option in the **Partition Source** dialog box to specify the query that provides the data for the partition.</span></span> <span data-ttu-id="fc2dd-104">Puede mostrar este panel seleccionando **Enlace de consultas** en la opción **Tipo de enlace** del cuadro de diálogo **Origen de la partición** .</span><span class="sxs-lookup"><span data-stu-id="fc2dd-104">You can display this pane by selecting **Query Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fc2dd-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="fc2dd-105">Options</span></span>  
 <span data-ttu-id="fc2dd-106">**Origen de datos**</span><span class="sxs-lookup"><span data-stu-id="fc2dd-106">**Data source**</span></span>  
 <span data-ttu-id="fc2dd-107">Seleccione el origen de datos en el que se ejecuta la consulta para proporcionar datos de hechos para la partición.</span><span class="sxs-lookup"><span data-stu-id="fc2dd-107">Select the data source on which the query is executed to provide fact data for the partition.</span></span>  
  
 <span data-ttu-id="fc2dd-108">**Consultar**</span><span class="sxs-lookup"><span data-stu-id="fc2dd-108">**Query**</span></span>  
 <span data-ttu-id="fc2dd-109">Escriba o modifique la instrucción SQL que se utiliza al recuperar datos de hechos cuando se procesa la partición.</span><span class="sxs-lookup"><span data-stu-id="fc2dd-109">Type or modify the SQL statement used when retrieving fact data when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fc2dd-110">Si se especifica una cláusula WHERE, puede utilizarse un subconjunto de registros para esta partición.</span><span class="sxs-lookup"><span data-stu-id="fc2dd-110">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="fc2dd-111">Esto es muy importante para evitar la duplicación de datos cuando varias particiones se basan en una única tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="fc2dd-111">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span> <span data-ttu-id="fc2dd-112">Para más información, vea [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fc2dd-112">For more information, see [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fc2dd-113">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="fc2dd-113">**Check**</span></span>  
 <span data-ttu-id="fc2dd-114">Haga clic para comprobar que la instrucción en **Consultar** sea una instrucción SQL válida.</span><span class="sxs-lookup"><span data-stu-id="fc2dd-114">Click to verify that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2dd-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc2dd-115">See Also</span></span>  
 [<span data-ttu-id="fc2dd-116">Cuadro de diálogo origen de la partición &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="fc2dd-116">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
