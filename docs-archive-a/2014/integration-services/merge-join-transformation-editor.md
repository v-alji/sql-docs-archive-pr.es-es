---
title: Editor de transformación combinación de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergejointransformation.f1
helpviewer_keywords:
- Merge Join Transformation Editor
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0d15d1233c2e0ff836e9dbd17459e56c48183f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674199"
---
# <a name="merge-join-transformation-editor"></a><span data-ttu-id="cb493-102">Editor de transformación Combinación de mezcla</span><span class="sxs-lookup"><span data-stu-id="cb493-102">Merge Join Transformation Editor</span></span>
  <span data-ttu-id="cb493-103">Use el cuadro de diálogo **Editor de transformación Combinación de mezcla** para especificar el tipo de combinación, las columnas de combinación y las columnas de salida para mezclar dos entradas fusionadas por combinación.</span><span class="sxs-lookup"><span data-stu-id="cb493-103">Use the **Merge Join Transformation Editor** dialog box to specify the join type, the join columns, and the output columns for merging two inputs combined by a join.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cb493-104">La transformación Combinación de mezcla requiere datos ordenados para sus entradas.</span><span class="sxs-lookup"><span data-stu-id="cb493-104">The Merge Join Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="cb493-105">Para obtener más información sobre este importante requisito, vea [Ordenar datos para las transformaciones Mezclar y Combinación de mezcla](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="cb493-105">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="cb493-106">Para obtener más información acerca de la transformación Combinación de mezcla, vea [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="cb493-106">To learn more about the Merge Join transformation, see [Merge Join Transformation](data-flow/transformations/merge-join-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb493-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="cb493-107">Options</span></span>  
 <span data-ttu-id="cb493-108">**Tipo de combinación**</span><span class="sxs-lookup"><span data-stu-id="cb493-108">**Join type**</span></span>  
 <span data-ttu-id="cb493-109">Especifique si desea utilizar una combinación interna (inner join), una combinación externa izquierda (left outer join) o una combinación completa (full join).</span><span class="sxs-lookup"><span data-stu-id="cb493-109">Specify whether you want to use an inner join, left outer join, or full join.</span></span>  
  
 <span data-ttu-id="cb493-110">**Intercambiar entradas**</span><span class="sxs-lookup"><span data-stu-id="cb493-110">**Swap Inputs**</span></span>  
 <span data-ttu-id="cb493-111">Para cambiar el orden de las entradas, use el botón **Intercambiar entradas** .</span><span class="sxs-lookup"><span data-stu-id="cb493-111">Switch the order between inputs by using the **Swap Inputs** button.</span></span> <span data-ttu-id="cb493-112">Esta selección resulta útil con la opción de combinación externa izquierda (left outer join).</span><span class="sxs-lookup"><span data-stu-id="cb493-112">This selection may be useful with the Left outer join option.</span></span>  
  
 <span data-ttu-id="cb493-113">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="cb493-113">**Input**</span></span>  
 <span data-ttu-id="cb493-114">Seleccione las columnas que desee en la salida combinada de la lista de entradas disponibles.</span><span class="sxs-lookup"><span data-stu-id="cb493-114">For each column that you want in the merged output, first select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="cb493-115">Las entradas se muestran en dos tablas independientes.</span><span class="sxs-lookup"><span data-stu-id="cb493-115">Inputs are displayed in two separate tables.</span></span> <span data-ttu-id="cb493-116">Seleccione las columnas que desea incluir en la salida.</span><span class="sxs-lookup"><span data-stu-id="cb493-116">Select columns to include in the output.</span></span> <span data-ttu-id="cb493-117">Arrastre las columnas para crear una combinación entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="cb493-117">Drag columns to create a join between the tables.</span></span> <span data-ttu-id="cb493-118">Para eliminar una combinación, selecciónela y presione la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="cb493-118">To delete a join, select it and then press the DELETE key.</span></span>  
  
 <span data-ttu-id="cb493-119">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="cb493-119">**Input Column**</span></span>  
 <span data-ttu-id="cb493-120">Seleccione una columna de la lista de columnas disponibles para incluirla en la salida combinada de la entrada seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cb493-120">Select a column to include in the merged output from the list of available columns on the selected input.</span></span>  
  
 <span data-ttu-id="cb493-121">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="cb493-121">**Output Alias**</span></span>  
 <span data-ttu-id="cb493-122">Escriba un alias para cada columna de salida.</span><span class="sxs-lookup"><span data-stu-id="cb493-122">Type an alias for each output column.</span></span> <span data-ttu-id="cb493-123">El nombre predeterminado es el de la columna de entrada, pero puede elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="cb493-123">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb493-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb493-124">See Also</span></span>  
 <span data-ttu-id="cb493-125">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cb493-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cb493-126">[Ordenar datos para las transformaciones mezclar y combinación de mezcla](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="cb493-126">[Sort Data for the Merge and Merge Join Transformations](data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md) </span></span>  
 <span data-ttu-id="cb493-127">[Extender un conjunto de objetos mediante la transformación combinación de mezcla](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="cb493-127">[Extend a Dataset by Using the Merge Join Transformation](data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md) </span></span>  
 <span data-ttu-id="cb493-128">[Transformación Mezclar](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="cb493-128">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="cb493-129">Transformación Unión de todo</span><span class="sxs-lookup"><span data-stu-id="cb493-129">Union All Transformation</span></span>](data-flow/transformations/union-all-transformation.md)  
  
  
