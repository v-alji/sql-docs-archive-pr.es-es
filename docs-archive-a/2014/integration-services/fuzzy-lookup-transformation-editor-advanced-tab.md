---
title: Editor de transformación búsqueda aproximada (pestaña avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 0a2919be-2ea7-4c06-82b8-0ffad5f0dd83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68f53eb2735dc07656fc8ff2b81c3259caa4847b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744773"
---
# <a name="fuzzy-lookup-transformation-editor-advanced-tab"></a><span data-ttu-id="75311-102">Editor de transformación Búsqueda aproximada (pestaña Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="75311-102">Fuzzy Lookup Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="75311-103">Utilice la pestaña **Avanzadas** del cuadro de diálogo **Editor de transformación Búsqueda aproximada** para establecer los parámetros de la búsqueda aproximada.</span><span class="sxs-lookup"><span data-stu-id="75311-103">Use the **Advanced** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set parameters for the fuzzy lookup.</span></span>  
  
 <span data-ttu-id="75311-104">Para obtener más información acerca de la transformación Búsqueda aproximada, vea [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="75311-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="75311-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="75311-105">Options</span></span>  
 <span data-ttu-id="75311-106">**Número máximo de coincidencias por búsqueda para la salida**</span><span class="sxs-lookup"><span data-stu-id="75311-106">**Maximum number of matches to output per lookup**</span></span>  
 <span data-ttu-id="75311-107">Especifique el número máximo de coincidencias que la transformación puede devolver para cada fila de entrada.</span><span class="sxs-lookup"><span data-stu-id="75311-107">Specify the maximum number of matches the transformation can return for each input row.</span></span> <span data-ttu-id="75311-108">El valor predeterminado es **1**.</span><span class="sxs-lookup"><span data-stu-id="75311-108">The default is **1**.</span></span>  
  
 <span data-ttu-id="75311-109">**Umbral de similitud**</span><span class="sxs-lookup"><span data-stu-id="75311-109">**Similarity threshold**</span></span>  
 <span data-ttu-id="75311-110">Establezca el umbral de similitud en el nivel de componente con el control deslizante.</span><span class="sxs-lookup"><span data-stu-id="75311-110">Set the similarity threshold at the component level by using the slider.</span></span> <span data-ttu-id="75311-111">Cuanto más se acerque el valor a 1, más deberá parecerse el valor de búsqueda al valor de origen para que pueda calificarse como coincidencia.</span><span class="sxs-lookup"><span data-stu-id="75311-111">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="75311-112">Al aumentar el umbral se puede mejorar la velocidad de la coincidencia ya que se tendrán en cuanta menos registros candidatos.</span><span class="sxs-lookup"><span data-stu-id="75311-112">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="75311-113">**Delimitadores de token**</span><span class="sxs-lookup"><span data-stu-id="75311-113">**Token delimiters**</span></span>  
 <span data-ttu-id="75311-114">Especifique los delimitadores que la transformación utilizará para dividir en tokens los valores de las columnas.</span><span class="sxs-lookup"><span data-stu-id="75311-114">Specify the delimiters that the transformation uses to tokenize column values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75311-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75311-115">See Also</span></span>  
 <span data-ttu-id="75311-116">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="75311-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="75311-117">[Editor de transformación búsqueda aproximada &#40;pestaña tabla de referencia&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="75311-117">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="75311-118">Editor de transformación Búsqueda aproximada &#40;pestaña Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="75311-118">Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md)  
  
  
