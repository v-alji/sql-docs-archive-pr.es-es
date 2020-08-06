---
title: Crear relaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.createrelationships.f1
ms.assetid: 6ebd305f-ffd2-4a1d-b24c-e28c151b94f5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a1095e193587ae7d416311031e5297a035ca37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670455"
---
# <a name="create-relationships"></a><span data-ttu-id="fa565-102">Crear relaciones</span><span class="sxs-lookup"><span data-stu-id="fa565-102">Create Relationships</span></span>
  <span data-ttu-id="fa565-103">Utilice el cuadro de diálogo **Crear relaciones** para editar asignaciones entre las columnas de origen y las columnas de la tabla de búsqueda configuradas en el Editor de transformación Búsqueda aproximada, el Editor de transformación Búsqueda y el Editor de transformación Búsqueda de términos.</span><span class="sxs-lookup"><span data-stu-id="fa565-103">Use the **Create Relationships** dialog box to edit mappings between the source columns and the lookup table columns that you configured in the Fuzzy Lookup Transformation Editor, the Lookup Transformation Editor, and the Term Lookup Transformation Editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa565-104">En el cuadro de diálogo **Crear relaciones** se muestran únicamente las listas **Columna de entrada** y **Columna de búsqueda** cuando se invoca desde el Editor de transformación Búsqueda de términos.</span><span class="sxs-lookup"><span data-stu-id="fa565-104">The **Create Relationships** dialog box displays only the **Input Column** and **Lookup Column** lists when invoked from the Term Lookup Transformation Editor.</span></span>  
  
 <span data-ttu-id="fa565-105">Para obtener más información acerca de las transformaciones que utilizan en el cuadro de diálogo **Crear relaciones** , vea [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md)y [Term Lookup Transformation](term-lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fa565-105">To learn more about the transformations that use the **Create Relationships** dialog box, see [Fuzzy Lookup Transformation](lookup-transformation.md), [Lookup Transformation](lookup-transformation.md), and [Term Lookup Transformation](term-lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa565-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="fa565-106">Options</span></span>  
 <span data-ttu-id="fa565-107">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="fa565-107">**Input Column**</span></span>  
 <span data-ttu-id="fa565-108">Seleccione las columnas de entrada disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="fa565-108">Select from the list of available input columns.</span></span>  
  
 <span data-ttu-id="fa565-109">**columna de búsqueda**</span><span class="sxs-lookup"><span data-stu-id="fa565-109">**Lookup Column**</span></span>  
 <span data-ttu-id="fa565-110">Seleccione columnas de la lista de columnas de búsqueda disponibles.</span><span class="sxs-lookup"><span data-stu-id="fa565-110">Select from the list of available lookup columns.</span></span>  
  
 <span data-ttu-id="fa565-111">**Tipo de asignación**</span><span class="sxs-lookup"><span data-stu-id="fa565-111">**Mapping Type**</span></span>  
 <span data-ttu-id="fa565-112">Seleccione coincidencia exacta o aproximada.</span><span class="sxs-lookup"><span data-stu-id="fa565-112">Select fuzzy or exact matching.</span></span>  
  
 <span data-ttu-id="fa565-113">Cuando se utiliza la coincidencia aproximada, las filas se consideran duplicadas si son lo suficientemente similares en todas las columnas que tienen un tipo de coincidencia aproximada.</span><span class="sxs-lookup"><span data-stu-id="fa565-113">When you use fuzzy matching, rows are considered duplicates if they are sufficiently similar across all columns that have a fuzzy match type.</span></span> <span data-ttu-id="fa565-114">Para obtener mejores resultados en la coincidencia aproximada, puede especificar que algunas columnas deben utilizar la coincidencia exacta en lugar de la coincidencia aproximada.</span><span class="sxs-lookup"><span data-stu-id="fa565-114">To obtain better results from fuzzy matching, you can specify that some columns should use exact matching instead of fuzzy matching.</span></span> <span data-ttu-id="fa565-115">Por ejemplo, si sabe que una determinada columna no tiene errores ni incoherencias, puede especificar una coincidencia exacta en esa columna, de tal modo que solo las filas que contengan valores idénticos en esta columna se consideren como posibles duplicados.</span><span class="sxs-lookup"><span data-stu-id="fa565-115">For example, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column, so that only rows which contain identical values in this column are considered as possible duplicates.</span></span> <span data-ttu-id="fa565-116">Esto aumenta la precisión de la coincidencia aproximada en otras columnas.</span><span class="sxs-lookup"><span data-stu-id="fa565-116">This increases the accuracy of fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="fa565-117">**Marcas de comparación**</span><span class="sxs-lookup"><span data-stu-id="fa565-117">**Comparison Flags**</span></span>  
 <span data-ttu-id="fa565-118">Para más información sobre las opciones de comparación de cadenas, vea [Comparar datos de cadena](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="fa565-118">For information about the string comparison options, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="fa565-119">**Similitud mínima**</span><span class="sxs-lookup"><span data-stu-id="fa565-119">**Minimum Similarity**</span></span>  
 <span data-ttu-id="fa565-120">Establezca el umbral de similitud del nivel de columna con el control deslizante.</span><span class="sxs-lookup"><span data-stu-id="fa565-120">Set the similarity threshold at the column level by using the slider.</span></span> <span data-ttu-id="fa565-121">Cuanto más se acerque el valor a 1, mayor deberá ser el parecido entre el valor de búsqueda y el valor de origen para que pueda calificarse como coincidencia.</span><span class="sxs-lookup"><span data-stu-id="fa565-121">The closer the value is to 1, the more the lookup value must resemble the source value to qualify as a match.</span></span> <span data-ttu-id="fa565-122">Aumentar el umbral puede mejorar la velocidad de coincidencia, ya que tendrán que tenerse en cuenta menos registros candidatos.</span><span class="sxs-lookup"><span data-stu-id="fa565-122">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="fa565-123">**Alias de salida de similitud**</span><span class="sxs-lookup"><span data-stu-id="fa565-123">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="fa565-124">Especifique el nombre de una nueva columna de salida que contendrá los resultados de similitud de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fa565-124">Specify the name for a new output column that contains the similarity scores for the selected column.</span></span> <span data-ttu-id="fa565-125">Si este valor se deja vacío, la columna de salida no se crea.</span><span class="sxs-lookup"><span data-stu-id="fa565-125">If you leave this value empty, the output column is not created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa565-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa565-126">See Also</span></span>  
 <span data-ttu-id="fa565-127">[Referencia de errores y mensajes de Integration Services](../../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fa565-127">[Integration Services Error and Message Reference](../../integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fa565-128">[Editor de transformación Búsqueda aproximada &#40;pestaña Columnas&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="fa565-128">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 <span data-ttu-id="fa565-129">[Editor de transformación Búsqueda &#40;página Columnas&#41;](../../lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="fa565-129">[Lookup Transformation Editor &#40;Columns Page&#41;](../../lookup-transformation-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="fa565-130">Editor de transformación Búsqueda de términos &#40;pestaña Búsqueda de términos&#41;</span><span class="sxs-lookup"><span data-stu-id="fa565-130">Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;</span></span>](../../term-lookup-transformation-editor-term-lookup-tab.md)  
  
  
