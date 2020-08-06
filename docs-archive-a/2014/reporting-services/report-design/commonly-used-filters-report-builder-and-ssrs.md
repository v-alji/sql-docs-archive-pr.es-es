---
title: Filtros de uso frecuente (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- multivalued parameters [Reporting Services]
- single-valued parameters [Reporting Services]
- parameters [Reporting Services], multivalued
- valid values [Reporting Services]
ms.assetid: cb70d0cd-707b-4de5-b39f-e4eb57d316aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 201cf83d431d1b61e0f20e9d039b2016ad4f13e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673492"
---
# <a name="commonly-used-filters-report-builder-and-ssrs"></a><span data-ttu-id="905e5-102">Filtros de uso frecuente (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="905e5-102">Commonly Used Filters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="905e5-103">Para crear un filtro, debe especificar una o varias ecuaciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="905e5-103">To create a filter, you must specify one or more filter equations.</span></span> <span data-ttu-id="905e5-104">Una ecuación de filtro incluye una expresión, un tipo de datos, un operador y un valor.</span><span class="sxs-lookup"><span data-stu-id="905e5-104">A filter equation includes an expression, a data type, an operator, and a value.</span></span> <span data-ttu-id="905e5-105">En este tema, se proporcionan ejemplos de filtros usados habitualmente.</span><span class="sxs-lookup"><span data-stu-id="905e5-105">This topic provides examples of commonly used filters.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a><span data-ttu-id="905e5-106">Ejemplos de filtros</span><span class="sxs-lookup"><span data-stu-id="905e5-106">Filter Examples</span></span>  
 <span data-ttu-id="905e5-107">En la tabla siguiente, se muestran ejemplos de ecuaciones de filtro que usan tipos de datos y operadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="905e5-107">The following table shows examples of filter equations that use different data types and different operators.</span></span> <span data-ttu-id="905e5-108">El elemento de informe para el que se define un filtro determina el ámbito de la comparación.</span><span class="sxs-lookup"><span data-stu-id="905e5-108">The scope for the comparison is determined by report item for which a filter is defined.</span></span> <span data-ttu-id="905e5-109">Por ejemplo, para un filtro definido en un conjunto de datos, **TOP % 10** es el 10 por ciento de los valores más altos del conjunto de datos; para un filtro definido en un grupo, **TOP% 10** es el 10 por ciento de los valores más altos del grupo.</span><span class="sxs-lookup"><span data-stu-id="905e5-109">For example, for a filter defined on a dataset, **TOP % 10** is the top 10 percent of values in the dataset; for a filter defined on a group, **TOP % 10** is the top 10 percent of values in the group.</span></span>  
  
|<span data-ttu-id="905e5-110">Expresión simple</span><span class="sxs-lookup"><span data-stu-id="905e5-110">Simple Expression</span></span>|<span data-ttu-id="905e5-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="905e5-111">Data Type</span></span>|<span data-ttu-id="905e5-112">Operator</span><span class="sxs-lookup"><span data-stu-id="905e5-112">Operator</span></span>|<span data-ttu-id="905e5-113">Value</span><span class="sxs-lookup"><span data-stu-id="905e5-113">Value</span></span>|<span data-ttu-id="905e5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="905e5-114">Description</span></span>|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|<span data-ttu-id="905e5-115">Incluye valores de datos que son mayores que 7.</span><span class="sxs-lookup"><span data-stu-id="905e5-115">Includes data values that are greater than 7.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|<span data-ttu-id="905e5-116">Incluye los 10 valores de datos más altos.</span><span class="sxs-lookup"><span data-stu-id="905e5-116">Includes the top 10 data values.</span></span>|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|<span data-ttu-id="905e5-117">Incluye el 20% de los valores de datos más altos.</span><span class="sxs-lookup"><span data-stu-id="905e5-117">Includes the top 20% of data values.</span></span>|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|<span data-ttu-id="905e5-118">Incluye todos los valores de tipo System.Decimal (tipos de datos "money" de SQL) mayores que $100.</span><span class="sxs-lookup"><span data-stu-id="905e5-118">Includes all values of type System.Decimal (SQL "money" data types) greater than $100.</span></span>|  
|`[OrderDate]`|`DateTime`|`>`|`2088-01-01`|<span data-ttu-id="905e5-119">Incluye todas las fechas desde el 1 de enero de 2008 hasta la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="905e5-119">Includes all dates from January 1, 2008 to the present date.</span></span>|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|<span data-ttu-id="905e5-120">Incluye las fechas desde el 1 de enero de 2008 hasta el 1 de febrero de 2008, inclusive.</span><span class="sxs-lookup"><span data-stu-id="905e5-120">Includes dates from January 1, 2008 up to and including February 1, 2008.</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`*east`|<span data-ttu-id="905e5-121">Todos los nombres de territorios que terminan en "east".</span><span class="sxs-lookup"><span data-stu-id="905e5-121">All territory names that end in "east".</span></span>|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|<span data-ttu-id="905e5-122">Todos los nombres de territorios que incluyen North y South al principio del nombre.</span><span class="sxs-lookup"><span data-stu-id="905e5-122">All territory names that include North and South at the beginning of the name.</span></span>|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|<span data-ttu-id="905e5-123">Todos los valores de subcategoría que comienzan con las letras B, C o T.</span><span class="sxs-lookup"><span data-stu-id="905e5-123">All subcategory values that begin with the letters B, C, or T.</span></span>|  
  
## <a name="examples-with-report-parameters"></a><span data-ttu-id="905e5-124">Ejemplos con parámetros de informe</span><span class="sxs-lookup"><span data-stu-id="905e5-124">Examples with Report Parameters</span></span>  
 <span data-ttu-id="905e5-125">En la tabla siguiente, se proporcionan ejemplos de expresiones de filtro que incluyen una referencia a un parámetro con un solo valor o con varios valores.</span><span class="sxs-lookup"><span data-stu-id="905e5-125">The following table provides examples of filter expression that includes a single-value or multivalue parameter reference.</span></span>  
  
|<span data-ttu-id="905e5-126">Tipo de parámetro</span><span class="sxs-lookup"><span data-stu-id="905e5-126">Parameter type</span></span>|<span data-ttu-id="905e5-127">Expresión (Filtro)</span><span class="sxs-lookup"><span data-stu-id="905e5-127">(Filter) Expression</span></span>|<span data-ttu-id="905e5-128">Operador</span><span class="sxs-lookup"><span data-stu-id="905e5-128">Operator</span></span>|<span data-ttu-id="905e5-129">Value</span><span class="sxs-lookup"><span data-stu-id="905e5-129">Value</span></span>|<span data-ttu-id="905e5-130">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="905e5-130">Data Type</span></span>|  
|--------------------|---------------------------|--------------|-----------|---------------|  
|<span data-ttu-id="905e5-131">Un solo valor</span><span class="sxs-lookup"><span data-stu-id="905e5-131">Single value</span></span>|`[EmployeeID]`|=|`[@EmployeeID]`|<span data-ttu-id="905e5-132">Entero</span><span class="sxs-lookup"><span data-stu-id="905e5-132">Integer</span></span>|  
|<span data-ttu-id="905e5-133">Varios valores</span><span class="sxs-lookup"><span data-stu-id="905e5-133">Multivalue</span></span>|`[EmployeeID]`|<span data-ttu-id="905e5-134">IN</span><span class="sxs-lookup"><span data-stu-id="905e5-134">IN</span></span>|`[@EmployeeID]`|<span data-ttu-id="905e5-135">Entero</span><span class="sxs-lookup"><span data-stu-id="905e5-135">Integer</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="905e5-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="905e5-136">See Also</span></span>  
 <span data-ttu-id="905e5-137">[Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="905e5-137">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="905e5-138">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="905e5-138">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="905e5-139">[La expresión usa en los informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="905e5-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="905e5-140">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="905e5-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="905e5-141">Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="905e5-141">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
