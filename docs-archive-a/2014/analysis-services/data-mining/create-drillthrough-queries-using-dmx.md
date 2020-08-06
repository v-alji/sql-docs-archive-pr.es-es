---
title: Crear consultas de obtención de detalles mediante DMX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42c896ee-e5ee-4017-b66e-31d1fe66d369
author: minewiskan
ms.author: owend
ms.openlocfilehash: 618732bfe48f7b1fe777f7841d686b07877d10ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675054"
---
# <a name="create-drillthrough-queries-using-dmx"></a><span data-ttu-id="8ec9a-102">Crear consultas de obtención de detalles usando DMX</span><span class="sxs-lookup"><span data-stu-id="8ec9a-102">Create Drillthrough Queries using DMX</span></span>
  <span data-ttu-id="8ec9a-103">Para todos los modelos que admitan la obtención de detalles, puede recuperar los datos de los casos y los datos de la estructura creando una consulta DMX en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o en cualquier otro cliente que soporte DMX.</span><span class="sxs-lookup"><span data-stu-id="8ec9a-103">For all models that support drillthrough, you can retrieve case data and structure data by creating a DMX query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any other client that supports DMX.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8ec9a-104">Para ver los datos, debe estar habilitada la obtención de detalles y es necesario tener los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="8ec9a-104">To view the data, drillthrough must have been enabled, and you must have the necessary permissions.</span></span>  
  
## <a name="specifying-drillthrough-options"></a><span data-ttu-id="8ec9a-105">Especificar las opciones de la obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="8ec9a-105">Specifying Drillthrough Options</span></span>  
 <span data-ttu-id="8ec9a-106">La sintaxis general para recuperar los casos de modelos y de estructuras es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ec9a-106">The general syntax is for retrieving model cases and structure cases is as follows:</span></span>  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 <span data-ttu-id="8ec9a-107">Para más información sobre el uso de consultas DMX para devolver datos de casos, vea [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) y [SELECT FROM &#60;estructura&#62;.CASES](/sql/dmx/select-from-structure-cases).</span><span class="sxs-lookup"><span data-stu-id="8ec9a-107">For additional information about using DMX queries to return case data, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) and [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8ec9a-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="8ec9a-108">Examples</span></span>  
 <span data-ttu-id="8ec9a-109">La siguiente consulta DMX devuelve los datos de los casos para una serie de productos concreta de un modelo de serie temporal.</span><span class="sxs-lookup"><span data-stu-id="8ec9a-109">The following DMX query returns the case data for a specific product series, from a time series model.</span></span> <span data-ttu-id="8ec9a-110">La consulta también devuelve la columna `Amount`, que no se usó en el modelo pero que está disponible en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="8ec9a-110">The query also returns the column `Amount`, which was not used in the model but is available in the mining structure.</span></span>  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 <span data-ttu-id="8ec9a-111">Observe que en este ejemplo, se ha usado un alias para cambiar el nombre de la columna de estructura.</span><span class="sxs-lookup"><span data-stu-id="8ec9a-111">Note that in this example, an alias has been used to rename the structure column.</span></span> <span data-ttu-id="8ec9a-112">Si no asigna un alias a la columna de estructura, la columna se devuelve con el nombre 'Expression'.</span><span class="sxs-lookup"><span data-stu-id="8ec9a-112">If you do not assign an alias to the structure column, the column is returned with the name 'Expression'.</span></span> <span data-ttu-id="8ec9a-113">Este es el comportamiento predeterminado para todas las columnas sin nombre.</span><span class="sxs-lookup"><span data-stu-id="8ec9a-113">This is the default behavior for all unnamed columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec9a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ec9a-114">See Also</span></span>  
 <span data-ttu-id="8ec9a-115">[Consultas de obtención de detalles &#40;&#41;de minería de datos](drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8ec9a-115">[Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="8ec9a-116">Obtención de detalles en estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8ec9a-116">Drillthrough on Mining Structures</span></span>](drillthrough-on-mining-structures.md)  
  
  
