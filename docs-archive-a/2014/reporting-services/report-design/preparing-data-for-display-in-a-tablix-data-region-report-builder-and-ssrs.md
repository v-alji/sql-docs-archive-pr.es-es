---
title: Preparar datos para su presentación en una región de datos Tablix (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fbb00dc6-7887-480c-b771-cab6fecb8dcc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 72ac150f2dcd227b1e3afb624a5ca5866fb4c360
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676348"
---
# <a name="preparing-data-for-display-in-a-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="8b3bd-102">Preparar datos para su presentación en una región de datos Tablix (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="8b3bd-102">Preparing Data for Display in a Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8b3bd-103">Una región de datos Tablix muestra los datos de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-103">A tablix data region displays data from a dataset.</span></span> <span data-ttu-id="8b3bd-104">Puede ver todos los datos recuperados para el conjunto de datos o puede crear filtros para ver solo un subconjunto de los datos.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-104">You can view all the data retrieved for the dataset or you can create filters so that you see only a subset of the data.</span></span> <span data-ttu-id="8b3bd-105">También puede agregar expresiones condicionales para rellenar los valores NULL o modificar la consulta para que un conjunto de datos incluya columnas que definan el criterio de ordenación para una columna existente.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-105">You can also add conditional expressions to fill in null values or modify the query for a dataset to include columns that define the sort order for an existing column.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="working-with-nulls-and-blanks-in-field-values"></a><span data-ttu-id="8b3bd-106">Trabajar con valores de campo NULL y vacíos</span><span class="sxs-lookup"><span data-stu-id="8b3bd-106">Working with Nulls and Blanks in Field Values</span></span>  
 <span data-ttu-id="8b3bd-107">Los datos para la colección de campos de un conjunto de datos incluyen todos los valores recuperados del origen de datos en tiempo de ejecución, incluyendo los valores NULL y los valores en blanco.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-107">Data for the field collection in a dataset includes all values retrieved from the data source at run time, including null values and blanks.</span></span> <span data-ttu-id="8b3bd-108">Normalmente, no es posible distinguir los valores NULL y los valores en blanco.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-108">Normally null values and blanks are indistinguishable.</span></span> <span data-ttu-id="8b3bd-109">En la mayoría de los casos, éste es el comportamiento deseado.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-109">In most cases, this is the desired behavior.</span></span> <span data-ttu-id="8b3bd-110">Por ejemplo, las funciones de agregado numéricas como [Sum](report-builder-functions-sum-function.md) y [Avg](report-builder-functions-avg-function.md) omiten los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-110">For example, Numeric aggregate functions like [Sum](report-builder-functions-sum-function.md) and [Avg](report-builder-functions-avg-function.md) ignore null values.</span></span> <span data-ttu-id="8b3bd-111">Para más información, vea [Referencia a las funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8b3bd-111">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
 <span data-ttu-id="8b3bd-112">Si desea tratar de manera diferente los valores NULL, puede usar expresiones condicionales o código personalizado para sustituir el valor NULL por un valor personalizado.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-112">If you do want to handle null values differently, you can use conditional expressions or custom code to substitute a custom value for the null value.</span></span> <span data-ttu-id="8b3bd-113">Por ejemplo, la expresión siguiente sustituye el valor del campo por el texto `Null` siempre que el campo `[Size]`contenga un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-113">For example, the following expression substitutes the text `Null` wherever a null value occurs in the field `[Size]`.</span></span>  
  
```  
=IIF(Fields!Size.Value IS NOTHING,"Null",Fields!Size.Value)  
```  
  
 <span data-ttu-id="8b3bd-114">Para obtener más información sobre cómo eliminar los valores NULL en los datos antes de recuperar estos de un origen de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante consultas de [!INCLUDE[tsql](../../includes/tsql-md.md)] , vea "Valores NULL" y "Combinaciones y valores NULL" en la documentación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en los [Libros en pantalla de SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="8b3bd-114">For more information about eliminating nulls in your data before retrieving the data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source using [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, see "Null Values" and "Null Values and Joins" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
## <a name="handling-null-field-names"></a><span data-ttu-id="8b3bd-115">Controlar nombres de campo nulos</span><span class="sxs-lookup"><span data-stu-id="8b3bd-115">Handling Null Field Names</span></span>  
 <span data-ttu-id="8b3bd-116">Comprobar la existencia de valores NULL en una expresión es apropiado siempre que el campo exista en el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-116">Testing for null values in an expression is fine as long as the field itself exists in the query result set.</span></span> <span data-ttu-id="8b3bd-117">Usando código personalizado, puede comprobar si el propio campo se encuentra presente en los campos devueltos desde el origen de datos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-117">From custom code, you can test whether the field itself is present in the collection fields returned from the data source at run time.</span></span> <span data-ttu-id="8b3bd-118">Para obtener más información, vea [Referencias a la colección de campos de conjunto de datos &#40;Generador de informes y SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8b3bd-118">For more information, see [Dataset Fields Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span></span>  
  
## <a name="adding-a-sort-order-column"></a><span data-ttu-id="8b3bd-119">Agregar una columna de criterio de ordenación</span><span class="sxs-lookup"><span data-stu-id="8b3bd-119">Adding a Sort Order Column</span></span>  
 <span data-ttu-id="8b3bd-120">De forma predeterminada, es posible ordenar alfabéticamente los valores de un campo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-120">By default, you can alphabetically sort values in a dataset field.</span></span> <span data-ttu-id="8b3bd-121">Para ordenar por un criterio de ordenación diferente, puede agregar una nueva columna al conjunto de datos que defina el criterio de ordenación que desea en una región de datos.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-121">To sort in a different order, you can add a new column to your dataset that defines the sort order you want in a data region.</span></span> <span data-ttu-id="8b3bd-122">Por ejemplo, para ordenar por el campo `[Color]` y colocar primero los elementos blancos y negros, puede agregar la columna `[ColorSortOrder]`que se muestra en la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="8b3bd-122">For example, to sort on the field `[Color]` and sort white and black items first, you can add a column `[ColorSortOrder]`, shown in the following query:</span></span>  
  
```  
SELECT ProductID, p.Name, Color,  
   CASE  
      WHEN p.Color = 'White' THEN 1  
      WHEN p.Color = 'Black' THEN 2  
      WHEN p.Color = 'Blue' THEN 3  
      WHEN p.Color = 'Yellow' THEN 4  
      ELSE 5  
   END As ColorSortOrder  
FROM Production.Product p  
```  
  
 <span data-ttu-id="8b3bd-123">Para ordenar una región de datos de tabla según este criterio de ordenación, establezca la expresión de ordenación en el grupo de detalles en `=Fields!ColorSortOrder.Value`.</span><span class="sxs-lookup"><span data-stu-id="8b3bd-123">To sort a table data region according to this sort order, set the sort expression on the detail group to `=Fields!ColorSortOrder.Value`.</span></span> <span data-ttu-id="8b3bd-124">Para más información, vea [Ordenar datos en una región de datos &#40;Generador de informes y SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8b3bd-124">For more information, see [Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3bd-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b3bd-125">See Also</span></span>  
 <span data-ttu-id="8b3bd-126">[Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8b3bd-126">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8b3bd-127">[Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8b3bd-127">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8b3bd-128">Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8b3bd-128">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
