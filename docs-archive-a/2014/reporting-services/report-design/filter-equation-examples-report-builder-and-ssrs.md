---
title: Ejemplos de ecuaciones de filtro (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- filtering data [Reporting Services], filter equation examples
ms.assetid: 66bec93d-7c3b-4d4a-8cb6-7a7bb2f34ec6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b4d7c7c561c9185c141190e26f37bc29fe52eb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671386"
---
# <a name="filter-equation-examples-report-builder-and-ssrs"></a><span data-ttu-id="56721-102">Ejemplos de ecuaciones de filtro (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="56721-102">Filter Equation Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="56721-103">Para crear un filtro, debe especificar una o varias ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="56721-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="56721-104">Una ecuación de filtro incluye una expresión, un tipo de datos, un operador y un valor.</span><span class="sxs-lookup"><span data-stu-id="56721-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="56721-105">En este tema, se proporcionan ejemplos de filtros usados habitualmente.</span><span class="sxs-lookup"><span data-stu-id="56721-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="56721-106">Ejemplos de filtros</span><span class="sxs-lookup"><span data-stu-id="56721-106">Filter Examples</span></span>  
 <span data-ttu-id="56721-107">En la tabla siguiente, se muestran ejemplos de ecuaciones de filtro que usan tipos de datos y operadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="56721-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="56721-108">El elemento de informe para el que se define un filtro determina el ámbito de la comparación.</span><span class="sxs-lookup"><span data-stu-id="56721-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="56721-109">Por ejemplo, para un filtro definido en un conjunto de datos, **TOP % 10** es el 10 por ciento de los valores más altos del conjunto de datos; para un filtro definido en un grupo, **TOP% 10** es el 10 por ciento de los valores más altos del grupo.</span><span class="sxs-lookup"><span data-stu-id="56721-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="56721-110">Expresión simple</span><span class="sxs-lookup"><span data-stu-id="56721-110">Simple Expression</span></span>|<span data-ttu-id="56721-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="56721-111">Data Type</span></span>|<span data-ttu-id="56721-112">Operator</span><span class="sxs-lookup"><span data-stu-id="56721-112">Operator</span></span>|<span data-ttu-id="56721-113">Value</span><span class="sxs-lookup"><span data-stu-id="56721-113">Value</span></span>|<span data-ttu-id="56721-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="56721-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="56721-115">Incluye valores de datos que son mayores que 7.</span><span class="sxs-lookup"><span data-stu-id="56721-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="56721-116">Incluye los 10 valores de datos más altos.</span><span class="sxs-lookup"><span data-stu-id="56721-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="56721-117">Incluye el 20% de los valores de datos más altos.</span><span class="sxs-lookup"><span data-stu-id="56721-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="56721-118">Incluye todos los valores de tipo System.Decimal (tipos de datos "money" de SQL) mayores que $100.</span><span class="sxs-lookup"><span data-stu-id="56721-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2008-01-01`|<span data-ttu-id="56721-119">Incluye todas las fechas desde el 1 de enero de 2008 hasta la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="56721-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="56721-120">Incluye las fechas desde el 1 de enero de 2008 hasta el 1 de febrero de 2008, inclusive.</span><span class="sxs-lookup"><span data-stu-id="56721-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="56721-121">Todos los nombres de territorios que terminan en "east".</span><span class="sxs-lookup"><span data-stu-id="56721-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="56721-122">Todos los nombres de territorios que incluyen North y South al principio del nombre.</span><span class="sxs-lookup"><span data-stu-id="56721-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="56721-123">Todos los valores de subcategoría que comienzan con las letras B, C o T.</span><span class="sxs-lookup"><span data-stu-id="56721-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56721-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56721-124">See Also</span></span>  
 <span data-ttu-id="56721-125">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="56721-125">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="56721-126">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="56721-126">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="56721-127">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56721-127">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="56721-128">[La expresión usa en los informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56721-128">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="56721-129">Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="56721-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
