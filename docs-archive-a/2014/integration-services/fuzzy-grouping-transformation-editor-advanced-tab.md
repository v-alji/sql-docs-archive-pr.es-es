---
title: Editor de transformación agrupación aproximada (pestaña avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: dd820d75-b8a7-4515-aea4-3553ba5b442e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f5dd05eda56b4818914f659734eb3cdfb20c4d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670435"
---
# <a name="fuzzy-grouping-transformation-editor-advanced-tab"></a><span data-ttu-id="70551-102">Editor de transformación Agrupación aproximada (pestaña Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="70551-102">Fuzzy Grouping Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="70551-103">Use la pestaña **Avanzadas** del cuadro de diálogo **Editor de transformación Agrupación aproximada** para especificar las columnas de entrada y salida, configurar umbrales de similitud y definir delimitadores.</span><span class="sxs-lookup"><span data-stu-id="70551-103">Use the **Advanced** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify input and output columns, set similarity thresholds, and define delimiters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70551-104">Las `Exhaustive` propiedades y `MaxMemoryUsage` de la transformación agrupación aproximada no están disponibles en el **Editor de transformación agrupación aproximada**, pero se pueden establecer mediante el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="70551-104">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Grouping transformation are not available in the **Fuzzy Grouping Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="70551-105">Para obtener más información acerca de estas propiedades, vea la sección sobre la transformación Agrupación aproximada en [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="70551-105">For more information on these properties, see the Fuzzy Grouping Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="70551-106">Para obtener más información acerca de la transformación Agrupación aproximada, vea [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="70551-106">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="70551-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="70551-107">Options</span></span>  
 <span data-ttu-id="70551-108">**Nombre de la columna de clave de entrada**</span><span class="sxs-lookup"><span data-stu-id="70551-108">**Input key column name**</span></span>  
 <span data-ttu-id="70551-109">Especifique el nombre de una columna de salida que contenga el identificador único para cada fila de entrada.</span><span class="sxs-lookup"><span data-stu-id="70551-109">Specify the name of an output column that contains the unique identifier for each input row.</span></span> <span data-ttu-id="70551-110">La columna `_key_in` tiene un valor que identifica de forma exclusiva cada fila.</span><span class="sxs-lookup"><span data-stu-id="70551-110">The `_key_in` column has a value that uniquely identifies each row.</span></span>  
  
 <span data-ttu-id="70551-111">**Nombre de la columna de clave de salida**</span><span class="sxs-lookup"><span data-stu-id="70551-111">**Output key column name**</span></span>  
 <span data-ttu-id="70551-112">Especifique el nombre de una columna de salida que contenga el identificador único para la fila canónica de un grupo de filas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="70551-112">Specify the name of an output column that contains the unique identifier for the canonical row of a group of duplicate rows.</span></span> <span data-ttu-id="70551-113">La columna `_key_out` se corresponde con el valor `_key_in` de la fila de datos canónica.</span><span class="sxs-lookup"><span data-stu-id="70551-113">The `_key_out` column corresponds to the `_key_in` value of the canonical data row.</span></span>  
  
 <span data-ttu-id="70551-114">**Nombre de la columna de resultados de similitud**</span><span class="sxs-lookup"><span data-stu-id="70551-114">**Similarity score column name**</span></span>  
 <span data-ttu-id="70551-115">Especifique un nombre para la columna que contiene los resultados de similitud.</span><span class="sxs-lookup"><span data-stu-id="70551-115">Specify a name for the column that contains the similarity score.</span></span> <span data-ttu-id="70551-116">Los resultados de similitud tienen un valor entre 0 y 1 que indica la similitud de la fila de entrada con la fila canónica.</span><span class="sxs-lookup"><span data-stu-id="70551-116">The similarity score is a value between 0 and 1 that indicates the similarity of the input row to the canonical row.</span></span> <span data-ttu-id="70551-117">Cuanto más se acerque el resultado a 1, mayor será la coincidencia entre la fila y la fila canónica.</span><span class="sxs-lookup"><span data-stu-id="70551-117">The closer the score is to 1, the more closely the row matches the canonical row.</span></span>  
  
 <span data-ttu-id="70551-118">**Umbral de similitud**</span><span class="sxs-lookup"><span data-stu-id="70551-118">**Similarity threshold**</span></span>  
 <span data-ttu-id="70551-119">Defina el umbral de similitud utilizando el control deslizante.</span><span class="sxs-lookup"><span data-stu-id="70551-119">Set the similarity threshold by using the slider.</span></span> <span data-ttu-id="70551-120">Cuanto más se acerque el umbral a 1, más deberán parecerse las filas entre sí para ser consideradas duplicados.</span><span class="sxs-lookup"><span data-stu-id="70551-120">The closer the threshold is to 1, the more the rows must resemble each other to qualify as duplicates.</span></span> <span data-ttu-id="70551-121">Aumentar el umbral puede mejorar la velocidad de coincidencia, ya que tendrán que tenerse en cuenta menos registros candidatos.</span><span class="sxs-lookup"><span data-stu-id="70551-121">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="70551-122">**Delimitadores de token**</span><span class="sxs-lookup"><span data-stu-id="70551-122">**Token delimiters**</span></span>  
 <span data-ttu-id="70551-123">La transformación proporciona un conjunto predeterminado de delimitadores para dividir los datos en tokens, pero se pueden agregar o quitar los delimitadores que sea necesario editando la lista.</span><span class="sxs-lookup"><span data-stu-id="70551-123">The transformation provides a default set of delimiters for tokenizing data, but you can add or remove delimiters as needed by editing the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70551-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70551-124">See Also</span></span>  
 <span data-ttu-id="70551-125">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="70551-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="70551-126">Identificar filas de datos similares mediante la transformación Agrupación aproximada</span><span class="sxs-lookup"><span data-stu-id="70551-126">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
