---
title: Crear un alias para una columna de modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- mining models [Analysis Services], columns
- column names [Analysis Services]
ms.assetid: c80ebe66-a8f8-4f24-9fe8-8288de9d13bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 908c0a8d8caa810badf4b82dc3dd3f411d09f323
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663794"
---
# <a name="create-an-alias-for-a-model-column"></a><span data-ttu-id="67f9f-102">Crear un alias para una columna de modelo</span><span class="sxs-lookup"><span data-stu-id="67f9f-102">Create an Alias for a Model Column</span></span>
  <span data-ttu-id="67f9f-103">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], puede crear un alias para una columna de modelo.</span><span class="sxs-lookup"><span data-stu-id="67f9f-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can create an alias for a model column.</span></span> <span data-ttu-id="67f9f-104">Esto puede resultar útil cuando el nombre de la estructura de minería de datos es demasiado largo para trabajar con él fácilmente, o si desea cambiar el nombre de la columna para que describa mejor su contenido o su uso en el modelo.</span><span class="sxs-lookup"><span data-stu-id="67f9f-104">This might be useful when the mining structure name is too long to easily work with, or when you want to rename the column to be more descriptive of its contents or usage in the model.</span></span> <span data-ttu-id="67f9f-105">Por ejemplo, si realiza una copia de una columna de estructura y, a continuación, discretiza la columna de manera diferente para un modelo determinado, puede cambiar el nombre de la columna para reflejar con más precisión el contenido.</span><span class="sxs-lookup"><span data-stu-id="67f9f-105">For example, if you make a copy of a structure column and then discretize the column differently for a particular model, you can rename the column to reflect the content more accurately.</span></span>  
  
 <span data-ttu-id="67f9f-106">Para crear un alias para una columna de modelo, utilice el panel **Propiedades** y establezca la propiedad [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) de la columna.</span><span class="sxs-lookup"><span data-stu-id="67f9f-106">To create an alias for a model column, you use the **Properties** pane and set the [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) property of the column.</span></span>  
  
 <span data-ttu-id="67f9f-107">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, el alias parece entre paréntesis al lado de la etiqueta de uso de columna.</span><span class="sxs-lookup"><span data-stu-id="67f9f-107">On the **Mining Models** tab of Data Mining Designer, the alias appears enclosed in parentheses next to the column usage label.</span></span>  
  
 <span data-ttu-id="67f9f-108">Para más información sobre cómo establecer las propiedades de un modelo de minería de datos, vea [Columnas del modelo de minería de datos](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="67f9f-108">For information about how to set the properties of a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-an-alias-to-a-mining-model-column"></a><span data-ttu-id="67f9f-109">Para agregar un alias a una columna de modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="67f9f-109">To add an alias to a mining model column</span></span>  
  
1.  <span data-ttu-id="67f9f-110">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, haga clic con el botón derecho en la celda del modelo de minería perteneciente a la columna que quiere cambiar y, luego, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="67f9f-110">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the mining model for the mining column that you want to change, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="67f9f-111">En la ventana **Propiedades** situada a la derecha de la pantalla, haga clic en la celda existente junto a la propiedad Name y elimine el valor actual.</span><span class="sxs-lookup"><span data-stu-id="67f9f-111">In the **Properties** window on the right side of the screen, click the cell next to the Name property and delete the current value.</span></span> <span data-ttu-id="67f9f-112">Escriba un nuevo nombre para la columna.</span><span class="sxs-lookup"><span data-stu-id="67f9f-112">Type a new name for the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f9f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67f9f-113">See Also</span></span>  
 <span data-ttu-id="67f9f-114">[Tareas y procedimientos del modelo de minería de datos](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="67f9f-114">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="67f9f-115">Propiedades del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="67f9f-115">Mining Model Properties</span></span>](mining-model-properties.md)  
  
  
