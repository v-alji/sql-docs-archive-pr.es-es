---
title: Excluir una columna de un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- excluding mining model columns
- mining models [Analysis Services], columns
- columns [data mining], excluding
ms.assetid: 404fe5fe-3ba2-4b9b-8780-0d02343d467f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30affebc143184c6287858f60b5d4f5d089c322a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671268"
---
# <a name="exclude-a-column-from-a-mining-model"></a><span data-ttu-id="4c540-102">Excluir una columna de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="4c540-102">Exclude a Column from a Mining Model</span></span>
  <span data-ttu-id="4c540-103">Cuando cree un modelo de minería de datos, es posible que no desee utilizar todas las columnas que existen en la estructura de minería de datos en la que se basa el modelo.</span><span class="sxs-lookup"><span data-stu-id="4c540-103">When you create a new mining model, you may not want to use all the columns that exist in the mining structure on which the model is based.</span></span> <span data-ttu-id="4c540-104">Por ejemplo, podría haber agregado una columna de nombre de cliente para la obtención de detalles, pero no desea utilizarla para el modelado.</span><span class="sxs-lookup"><span data-stu-id="4c540-104">For example, you might have added a customer name column for drillthrough, but don't want to use it for modeling.</span></span> <span data-ttu-id="4c540-105">También puede ser que decida crear múltiples copias de una columna con diversas discretizaciones y usar solamente una de las copias en cada modelo, e ignorar el resto.</span><span class="sxs-lookup"><span data-stu-id="4c540-105">Or, you might decide to create multiple copies of a column with different discretizations, and use only one of the copies in each model, and ignore the rest.</span></span> <span data-ttu-id="4c540-106">También podría añadir de forma selectiva columnas de entrada en varios modelos distintos para ver cómo la variable añadida afecta a la columna de salida.</span><span class="sxs-lookup"><span data-stu-id="4c540-106">You could also selectively add input columns in several different models to see how the added variable affects the output column.</span></span>  
  
 <span data-ttu-id="4c540-107">No necesita crear una nueva estructura de minería de datos para cada combinación de columnas; basta con que marque una columna como no usada en un modelo determinado.</span><span class="sxs-lookup"><span data-stu-id="4c540-107">You do not need to create a new mining structure for each combination of columns; instead, you can simply flag a column as not being used in a particular model.</span></span>  
  
### <a name="to-exclude-a-column-from-a-mining-model"></a><span data-ttu-id="4c540-108">Para excluir una columna de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="4c540-108">To exclude a column from a mining model</span></span>  
  
1.  <span data-ttu-id="4c540-109">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], seleccione la celda que se corresponda con la columna que desee excluir bajo el modelo de minería de datos pertinente.</span><span class="sxs-lookup"><span data-stu-id="4c540-109">In the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the cell that corresponds to the column you want to exclude, under the appropriate mining model.</span></span>  
  
2.  <span data-ttu-id="4c540-110">Seleccione **Omitir** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4c540-110">Select **Ignore** from the drop-down list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c540-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c540-111">See Also</span></span>  
 [<span data-ttu-id="4c540-112">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="4c540-112">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
