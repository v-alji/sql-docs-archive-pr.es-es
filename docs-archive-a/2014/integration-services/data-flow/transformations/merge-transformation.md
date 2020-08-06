---
title: Transformación Mezclar | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.mergetrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- merging data [Integration Services]
- Merge transformation
- combining datasets
- datasets [Integration Services], merging
ms.assetid: cff8690c-07ac-46a0-aab5-20bd4848c677
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7d1d35e92b5978016b6a53956e5b6f1f6642f5ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749389"
---
# <a name="merge-transformation"></a><span data-ttu-id="48550-102">Mezclar, transformación</span><span class="sxs-lookup"><span data-stu-id="48550-102">Merge Transformation</span></span>
  <span data-ttu-id="48550-103">La transformación Mezclar combina dos conjuntos de datos ordenados en un solo conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="48550-103">The Merge transformation combines two sorted datasets into a single dataset.</span></span> <span data-ttu-id="48550-104">Las filas de cada conjunto de datos se insertan en la salida en función de los valores de sus columnas de clave.</span><span class="sxs-lookup"><span data-stu-id="48550-104">The rows from each dataset are inserted into the output based on values in their key columns.</span></span>  
  
 <span data-ttu-id="48550-105">Si incluye la transformación Mezclar en un flujo de datos, podrá realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="48550-105">By including the Merge transformation in a data flow, you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="48550-106">Combinar datos de dos orígenes de datos, como tablas y archivos.</span><span class="sxs-lookup"><span data-stu-id="48550-106">Merge data from two data sources, such as tables and files.</span></span>  
  
-   <span data-ttu-id="48550-107">Crear conjuntos de datos complejos anidando transformaciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="48550-107">Create complex datasets by nesting Merge transformations.</span></span>  
  
-   <span data-ttu-id="48550-108">Volver a combinar filas después de corregir errores en los datos.</span><span class="sxs-lookup"><span data-stu-id="48550-108">Remerge rows after correcting errors in the data.</span></span>  
  
 <span data-ttu-id="48550-109">La transformación Mezclar es similar a las transformaciones Unión de todo.</span><span class="sxs-lookup"><span data-stu-id="48550-109">The Merge transformation is similar to the Union All transformations.</span></span> <span data-ttu-id="48550-110">Use la transformación Unión de todo en lugar de la transformación Mezclar en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="48550-110">Use the Union All transformation instead of the Merge transformation in the following situations:</span></span>  
  
-   <span data-ttu-id="48550-111">Las entradas de la transformación no están ordenadas.</span><span class="sxs-lookup"><span data-stu-id="48550-111">The transformation inputs are not sorted.</span></span>  
  
-   <span data-ttu-id="48550-112">La salida combinada no tiene que ordenarse.</span><span class="sxs-lookup"><span data-stu-id="48550-112">The combined output does not need to be sorted.</span></span>  
  
-   <span data-ttu-id="48550-113">La transformación tiene más de dos entradas.</span><span class="sxs-lookup"><span data-stu-id="48550-113">The transformation has more than two inputs.</span></span>  
  
## <a name="input-requirements"></a><span data-ttu-id="48550-114">Requisitos de entrada</span><span class="sxs-lookup"><span data-stu-id="48550-114">Input Requirements</span></span>  
 <span data-ttu-id="48550-115">La transformación Mezclar requiere datos ordenados para sus entradas.</span><span class="sxs-lookup"><span data-stu-id="48550-115">The Merge Transformation requires sorted data for its inputs.</span></span> <span data-ttu-id="48550-116">Para obtener más información sobre este importante requisito, vea [Ordenar datos para las transformaciones Mezclar y Combinación de mezcla](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="48550-116">For more information about this important requirement, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
 <span data-ttu-id="48550-117">La transformación Mezclar también requiere que las columnas combinadas en sus entradas tengan metadatos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="48550-117">The Merge transformation also requires that the merged columns in its inputs have matching metadata.</span></span> <span data-ttu-id="48550-118">Por ejemplo, no puede combinar una columna que tenga un tipo de datos numérico con una columna que tenga un tipo de datos de carácter.</span><span class="sxs-lookup"><span data-stu-id="48550-118">For example, you cannot merge a column that has a numeric data type with a column that has a character data type.</span></span> <span data-ttu-id="48550-119">Si los datos tienen un tipo de datos de cadena, la longitud de la columna de la segunda entrada debe ser menor o igual que la longitud de la columna de la primera entrada con la que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="48550-119">If the data has a string data type, the length of the column in the second input must be less than or equal to the length of the column in the first input with which it is merged.</span></span>  
  
 <span data-ttu-id="48550-120">En el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , la interfaz de usuario para la transformación Mezclar asigna automáticamente las columnas que tienen los mismos metadatos.</span><span class="sxs-lookup"><span data-stu-id="48550-120">In the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, the user interface for the Merge transformation automatically maps columns that have the same metadata.</span></span> <span data-ttu-id="48550-121">Después puede asignar manualmente otras columnas con tipos de datos compatibles.</span><span class="sxs-lookup"><span data-stu-id="48550-121">You can then manually map other columns that have compatible data types.</span></span>  
  
 <span data-ttu-id="48550-122">Esta transformación tiene dos entradas y una salida.</span><span class="sxs-lookup"><span data-stu-id="48550-122">This transformation has two inputs and one output.</span></span> <span data-ttu-id="48550-123">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="48550-123">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-merge-transformation"></a><span data-ttu-id="48550-124">Configuración de la transformación Mezclar</span><span class="sxs-lookup"><span data-stu-id="48550-124">Configuration of the Merge Transformation</span></span>  
 <span data-ttu-id="48550-125">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="48550-125">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="48550-126">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Mezclar** , vea [Merge Transformation Editor](../../merge-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="48550-126">For more information about the properties that you can set in the **Merge Transformation Editor** dialog box, see [Merge Transformation Editor](../../merge-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="48550-127">Para obtener más información acerca de las propiedades que puede establecer mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="48550-127">For more information about the properties that you can programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="48550-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="48550-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="48550-129">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="48550-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="48550-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="48550-130">Related Tasks</span></span>  
 <span data-ttu-id="48550-131">Para obtener información detallada acerca de cómo establecer propiedades, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="48550-131">For details about how to set properties, see the following topics:</span></span>  
  
-   [<span data-ttu-id="48550-132">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="48550-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
-   [<span data-ttu-id="48550-133">Ordenación de datos para las transformaciones Mezclar y Combinación de mezcla</span><span class="sxs-lookup"><span data-stu-id="48550-133">Sort Data for the Merge and Merge Join Transformations</span></span>](sort-data-for-the-merge-and-merge-join-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="48550-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48550-134">See Also</span></span>  
 <span data-ttu-id="48550-135">[Transformación Combinación de mezcla](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="48550-135">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="48550-136">[Transformación Unión de todo](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="48550-136">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="48550-137">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="48550-137">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="48550-138">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="48550-138">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
