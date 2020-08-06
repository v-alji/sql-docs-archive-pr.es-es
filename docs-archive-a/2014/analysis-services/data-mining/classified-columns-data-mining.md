---
title: Columnas clasificadas (minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content types [data mining]
- STDEV column
- VARIANCE column
- PROBABLILITY column
- PROBABILITY_STDEV column
- columns [data mining], classified
- classified columns [data mining]
- PROBABILITY_VARIANCE column
- SUPPORT column
ms.assetid: 68bf3b78-dc12-497c-898f-b43a45646123
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c264dfb6a97b8b8f576966e8929f6b0dc51e4ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675673"
---
# <a name="classified-columns-data-mining"></a><span data-ttu-id="cfaa1-102">Columnas clasificadas (Minería de datos)</span><span class="sxs-lookup"><span data-stu-id="cfaa1-102">Classified Columns (Data Mining)</span></span>
  <span data-ttu-id="cfaa1-103">Cuando se define una columna clasificada, se crea una relación entre la columna actual y otra columna de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-103">When you define a classified column, you create a relationship between the current column and another column in the mining structure.</span></span> <span data-ttu-id="cfaa1-104">La columna de la estructura de minería de datos que se designa como columna clasificada contiene información sobre categorías que describe los valores de otra columna de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-104">The data in the mining structure column that you designate as the classified column contains categorical information that describes the values in another column in the mining structure.</span></span>  
  
 <span data-ttu-id="cfaa1-105">Por ejemplo, imagine que tiene dos columnas con datos numéricos: una columna, [Compras anuales], contiene las compras totales que realiza cada cliente durante un año natural determinado, mientras que la otra columna, [Desviaciones estándar], contiene las desviaciones estándar para esos valores.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-105">For example, suppose you have two columns with numerical data: one column, [Yearly Purchases], contains the total yearly purchases per customer for a specific calendar year, and the other column, [Standard Deviations], contains the standard deviations for those values.</span></span> <span data-ttu-id="cfaa1-106">En este caso, podría designar la columna [Compras anuales] como columna clasificada y el modelo podría usar esta relación en el análisis.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-106">In this case you could designate the [Yearly Purchases] column as the classified column, and the model would be able to use this relationship in analysis.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfaa1-107">Los algoritmos proporcionados en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no admiten el uso de columnas clasificadas; esta característica se proporciona para crear algoritmos personalizados.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-107">The algorithms provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not support the use of classified columns; this feature is provided for use in creating custom algorithms.</span></span>  
  
## <a name="defining-a-classified-column"></a><span data-ttu-id="cfaa1-108">Definir una columna clasificada</span><span class="sxs-lookup"><span data-stu-id="cfaa1-108">Defining a Classified Column</span></span>  
 <span data-ttu-id="cfaa1-109">El tipo de datos de una columna clasificada debe ser `Long` o `Double`.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-109">The data type of a classified column must be either `Long` or `Double`.</span></span>  
  
 <span data-ttu-id="cfaa1-110">En la lista siguiente se describen los tipos de contenido que admite [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para las columnas clasificadas.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-110">The following list describes the content types that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports for classified columns.</span></span>  
  
 <span data-ttu-id="cfaa1-111">**PROBABILIDAD**</span><span class="sxs-lookup"><span data-stu-id="cfaa1-111">**PROBABILITY**</span></span>  
 <span data-ttu-id="cfaa1-112">El valor de la columna es la probabilidad del valor asociado, un número entre cero y uno.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-112">The value in the column is the probability of the associated value, and is a number between 0 and 1.</span></span>  
  
 <span data-ttu-id="cfaa1-113">**CONCILIA**</span><span class="sxs-lookup"><span data-stu-id="cfaa1-113">**VARIANCE**</span></span>  
 <span data-ttu-id="cfaa1-114">El valor de la columna es la varianza del valor asociado.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-114">The value in the column is the variance of the associated value.</span></span>  
  
 <span data-ttu-id="cfaa1-115">**STDEV**</span><span class="sxs-lookup"><span data-stu-id="cfaa1-115">**STDEV**</span></span>  
 <span data-ttu-id="cfaa1-116">El valor de la columna es la desviación estándar del valor asociado.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-116">The value in the column is the standard deviation of the associated value.</span></span>  
  
 <span data-ttu-id="cfaa1-117">**PROBABILITY_VARIANCE**</span><span class="sxs-lookup"><span data-stu-id="cfaa1-117">**PROBABILITY_VARIANCE**</span></span>  
 <span data-ttu-id="cfaa1-118">El valor de la columna es la varianza de la probabilidad del valor asociado.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-118">The value in the column is the variance of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="cfaa1-119">**PROBABILITY_STDEV**</span><span class="sxs-lookup"><span data-stu-id="cfaa1-119">**PROBABILITY_STDEV**</span></span>  
 <span data-ttu-id="cfaa1-120">El valor de la columna es la desviación estándar de la probabilidad del valor asociado.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-120">The value in the column is the standard deviation of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="cfaa1-121">**SER**</span><span class="sxs-lookup"><span data-stu-id="cfaa1-121">**SUPPORT**</span></span>  
 <span data-ttu-id="cfaa1-122">El valor de la columna es el peso, o factor de replicación del caso, del valor asociado.</span><span class="sxs-lookup"><span data-stu-id="cfaa1-122">The value in the column is the weight, or case replication factor, of the associated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfaa1-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfaa1-123">See Also</span></span>  
 <span data-ttu-id="cfaa1-124">[Tipos de contenido &#40;minería de datos&#41;](content-types-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cfaa1-124">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) </span></span>  
 <span data-ttu-id="cfaa1-125">[Estructuras de minería de datos &#40;Analysis Services:&#41;de minería de datos](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cfaa1-125">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="cfaa1-126">Tipos de datos &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="cfaa1-126">Data Types &#40;Data Mining&#41;</span></span>](data-types-data-mining.md)  
  
  
