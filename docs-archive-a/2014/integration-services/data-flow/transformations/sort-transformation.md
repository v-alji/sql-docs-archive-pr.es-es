---
title: Transformación Ordenar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttrans.f1
helpviewer_keywords:
- Sort transformation
- descending sorts
- ascending sorts
- sorting data [Integration Services]
- multiple sorts
- duplicate data [Integration Services]
ms.assetid: 728c9351-84a8-4a89-be4d-d50d4adc04e0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7039d02b6cc55355c3b27e5694474df4666570ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674227"
---
# <a name="sort-transformation"></a><span data-ttu-id="48adf-102">Ordenar, transformación</span><span class="sxs-lookup"><span data-stu-id="48adf-102">Sort Transformation</span></span>
  <span data-ttu-id="48adf-103">La transformación Ordenar ordena los datos de entrada en sentido ascendente o descendente, y copia los datos ordenados a la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="48adf-103">The Sort transformation sorts input data in ascending or descending order and copies the sorted data to the transformation output.</span></span> <span data-ttu-id="48adf-104">Puede aplicar varias ordenaciones a una entrada; cada ordenación se identifica mediante un numeral que determina el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="48adf-104">You can apply multiple sorts to an input; each sort is identified by a numeral that determines the sort order.</span></span> <span data-ttu-id="48adf-105">La columna con el número más bajo se ordenará primero, la columna con el segundo número más bajo se ordena a continuación, etc.</span><span class="sxs-lookup"><span data-stu-id="48adf-105">The column with the lowest number is sorted first, the sort column with the second lowest number is sorted next, and so on.</span></span> <span data-ttu-id="48adf-106">Por ejemplo, si una columna denominada **CountryRegion** tiene un criterio de ordenación 1 y una columna denominada **Ciudad** tiene un criterio de ordenación 2, la salida se ordena por país o región y después por ciudad.</span><span class="sxs-lookup"><span data-stu-id="48adf-106">For example, if a column named **CountryRegion** has a sort order of 1 and a column named **City** has a sort order of 2, the output is sorted by country/region and then by city.</span></span> <span data-ttu-id="48adf-107">Un número positivo indica que la ordenación es ascendente y un número negativo indica que la ordenación es descendente.</span><span class="sxs-lookup"><span data-stu-id="48adf-107">A positive number denotes that the sort is ascending, and a negative number denotes that the sort is descending.</span></span> <span data-ttu-id="48adf-108">Las columnas que no se están ordenadas tienen un criterio de ordenación de 0.</span><span class="sxs-lookup"><span data-stu-id="48adf-108">Columns that are not sorted have a sort order of 0.</span></span> <span data-ttu-id="48adf-109">Las columnas que no están seleccionadas para ordenar se copian automáticamente a la salida de transformación junto con las columnas ordenadas.</span><span class="sxs-lookup"><span data-stu-id="48adf-109">Columns that are not selected for sorting are automatically copied to the transformation output together with the sorted columns.</span></span>  
  
 <span data-ttu-id="48adf-110">La transformación Ordenar incluye un conjunto de opciones de comparación para definir cómo controlará la transformación los datos de cadena de una columna.</span><span class="sxs-lookup"><span data-stu-id="48adf-110">The Sort transformation includes a set of comparison options to define how the transformation handles the string data in a column.</span></span> <span data-ttu-id="48adf-111">Para más información, consulte [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="48adf-111">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48adf-112">La transformación Ordenar no ordena los GUID en el mismo orden que la cláusula ORDER BY lo hace en Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="48adf-112">The Sort transformation does not sort GUIDs in the same order as the ORDER BY clause does in Transact-SQL.</span></span> <span data-ttu-id="48adf-113">Mientras que la transformación Ordenar ordena los GUID que se inician con 0-9 antes que los que se inician con A-F, la cláusula ORDER BY, tal y como se implementa en [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], los ordena de otra manera.</span><span class="sxs-lookup"><span data-stu-id="48adf-113">While the Sort transformation sorts GUIDs that start with 0-9 before GUIDs that start with A-F, the ORDER BY clause, as implemented in the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], sorts them differently.</span></span> <span data-ttu-id="48adf-114">Para obtener más información, vea [ORDER BY &#40;cláusula de Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48adf-114">For more information, see [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="48adf-115">La transformación Ordenar también puede quitar filas duplicadas como parte de la ordenación.</span><span class="sxs-lookup"><span data-stu-id="48adf-115">The Sort transformation can also remove duplicate rows as part of its sort.</span></span> <span data-ttu-id="48adf-116">Las filas duplicadas son filas con los mismos criterios de ordenación.</span><span class="sxs-lookup"><span data-stu-id="48adf-116">Duplicate rows are rows with the same sort key values.</span></span> <span data-ttu-id="48adf-117">El valor del criterio de ordenación se genera a partir de las opciones de comparación de cadenas usadas, lo que implica que cadenas literales diferentes pueden tener los mismos criterios de ordenación.</span><span class="sxs-lookup"><span data-stu-id="48adf-117">The sort key value is generated based on the string comparison options being used, which means that different literal strings may have the same sort key values.</span></span> <span data-ttu-id="48adf-118">La transformación identifica filas en las columnas de entrada que tienen valores distintos pero un mismo criterio de ordenación que los duplicados.</span><span class="sxs-lookup"><span data-stu-id="48adf-118">The transformation identifies rows in the input columns that have different values but the same sort key as duplicates.</span></span>  
  
 <span data-ttu-id="48adf-119">La transformación Ordenar incluye la propiedad personalizada `MaximumThreads`, que se puede actualizar a través de una expresión de propiedad al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="48adf-119">The Sort transformation includes the `MaximumThreads` custom property that can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="48adf-120">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Usar expresiones de propiedad en paquetes](../../expressions/use-property-expressions-in-packages.md) y [Propiedades personalizadas de transformación](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="48adf-120">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="48adf-121">Esta transformación tiene una entrada y una salida.</span><span class="sxs-lookup"><span data-stu-id="48adf-121">This transformation has one input and one output.</span></span> <span data-ttu-id="48adf-122">No admite salidas de error.</span><span class="sxs-lookup"><span data-stu-id="48adf-122">It does not support error outputs.</span></span>  
  
## <a name="configuration-of-the-sort-transformation"></a><span data-ttu-id="48adf-123">Configuración de la transformación Ordenar</span><span class="sxs-lookup"><span data-stu-id="48adf-123">Configuration of the Sort Transformation</span></span>  
 <span data-ttu-id="48adf-124">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="48adf-124">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="48adf-125">Para obtener información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Ordenar** , vea [Sort Transformation Editor](../../sort-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="48adf-125">For information about the properties that you can set in the **Sort Transformation Editor** dialog box, see [Sort Transformation Editor](../../sort-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="48adf-126">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="48adf-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="48adf-127">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="48adf-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="48adf-128">Common Properties</span><span class="sxs-lookup"><span data-stu-id="48adf-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="48adf-129">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="48adf-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="48adf-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="48adf-130">Related Tasks</span></span>  
 <span data-ttu-id="48adf-131">Para obtener más información sobre cómo establecer las propiedades del componente, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="48adf-131">For more information about how to set properties of the component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="48adf-132">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="48adf-132">Related Content</span></span>  
 <span data-ttu-id="48adf-133">Ejemplo, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), en codeplex.com.</span><span class="sxs-lookup"><span data-stu-id="48adf-133">Sample, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), on codeplex.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48adf-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48adf-134">See Also</span></span>  
 <span data-ttu-id="48adf-135">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="48adf-135">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="48adf-136">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="48adf-136">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
