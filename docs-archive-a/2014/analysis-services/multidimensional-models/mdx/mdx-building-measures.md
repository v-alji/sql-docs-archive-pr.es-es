---
title: Generar medidas en MDX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0347835-4983-4d26-acbb-6c8fae7992bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac49d37f11584bfbc5d372241056da39e7dd8c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671735"
---
# <a name="building-measures-in-mdx"></a><span data-ttu-id="2f333-102">Generar medidas en MDX</span><span class="sxs-lookup"><span data-stu-id="2f333-102">Building Measures in MDX</span></span>
  <span data-ttu-id="2f333-103">En las expresiones multidimensionales (MDX), una medida es una expresión DAX con nombre que se resuelve calculando la expresión para devolver un valor en un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="2f333-103">In Multidimensional Expressions (MDX), a measure is a named DAX expression that is resolved by calculating the expression to return a value in a Tabular Model.</span></span> <span data-ttu-id="2f333-104">Esta definición tan genérica tiene un alcance notable.</span><span class="sxs-lookup"><span data-stu-id="2f333-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="2f333-105">La capacidad de construir y utilizar medias en una consulta MDX proporciona una gran solución para manipular datos tabulares.</span><span class="sxs-lookup"><span data-stu-id="2f333-105">The ability to construct and use measures in an MDX query provides a great deal of manipulation capability for tabular data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="2f333-106">Las medidas solo pueden definirse en modelos tabulares; si la base de datos se establece en modo multidimensional, al crear una medida se generará un error.</span><span class="sxs-lookup"><span data-stu-id="2f333-106">Measures can only be defined in tabular models; if your database is set in multidimensional mode, creating a measure will generate an error</span></span>  
  
 <span data-ttu-id="2f333-107">Para crear una medida definida como parte de una consulta MDX, y en consecuencia con un ámbito limitado a la consulta, debe usar la palabra clave WITH.</span><span class="sxs-lookup"><span data-stu-id="2f333-107">To create a measure that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="2f333-108">Puede usar la medida en una instrucción MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="2f333-108">You can then use the measure within an MDX SELECT statement.</span></span> <span data-ttu-id="2f333-109">De esta manera, el miembro calculado creado con la palabra clave WITH se puede cambiar sin tener que tocar la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="2f333-109">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span> <span data-ttu-id="2f333-110">Sin embargo, en MDX se hace referencia a la medida de forma diferente que en las expresiones DAX; para hacer referencia a la medida que se denomina como miembro de la dimensión [Measures], vea el siguiente ejemplo MDX:</span><span class="sxs-lookup"><span data-stu-id="2f333-110">However, in MDX you reference the measure in a different way than when in DAX expressions; to reference the measure you name it as a member of the [Measures] dimension, see the following MDX example:</span></span>  
  
```  
with measure  'Sales Territory'[Total Sales Amount] = SUM('Internet Sales'[Sales Amount]) + SUM('Reseller Sales'[Sales Amount])  
select measures.[Total Sales Amount] on columns  
     ,NON EMPTY [Date].[Calendar Year].children on rows  
from [Model]  
  
```  
  
 <span data-ttu-id="2f333-111">Devolverá los siguientes datos cuando se ejecute:</span><span class="sxs-lookup"><span data-stu-id="2f333-111">It will return the following data when executed:</span></span>  
  
||<span data-ttu-id="2f333-112">Total Sales Amount</span><span class="sxs-lookup"><span data-stu-id="2f333-112">Total Sales Amount</span></span>||  
|-|------------------------|-|  
|<span data-ttu-id="2f333-113">2001</span><span class="sxs-lookup"><span data-stu-id="2f333-113">2001</span></span>|<span data-ttu-id="2f333-114">11331808.96</span><span class="sxs-lookup"><span data-stu-id="2f333-114">11331808.96</span></span>||  
|<span data-ttu-id="2f333-115">2002</span><span class="sxs-lookup"><span data-stu-id="2f333-115">2002</span></span>|<span data-ttu-id="2f333-116">30674773.18</span><span class="sxs-lookup"><span data-stu-id="2f333-116">30674773.18</span></span>||  
|<span data-ttu-id="2f333-117">2003</span><span class="sxs-lookup"><span data-stu-id="2f333-117">2003</span></span>|<span data-ttu-id="2f333-118">41993729.72</span><span class="sxs-lookup"><span data-stu-id="2f333-118">41993729.72</span></span>||  
|<span data-ttu-id="2f333-119">2004</span><span class="sxs-lookup"><span data-stu-id="2f333-119">2004</span></span>|<span data-ttu-id="2f333-120">25808962.34</span><span class="sxs-lookup"><span data-stu-id="2f333-120">25808962.34</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="2f333-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f333-121">See Also</span></span>  
 <span data-ttu-id="2f333-122">[Instrucción CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="2f333-122">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="2f333-123">[Referencia de funciones MDX &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="2f333-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="2f333-124">SELECT &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="2f333-124">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
