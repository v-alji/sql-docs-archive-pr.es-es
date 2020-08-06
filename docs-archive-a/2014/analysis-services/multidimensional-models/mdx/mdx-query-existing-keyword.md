---
title: Palabra clave EXISTing (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- EXISTING
helpviewer_keywords:
- Existing keyword
ms.assetid: 651ee9ac-04ef-4316-87c9-a3df5ac27d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: 115444c832fe8fe9b258a0c23b97b97553f32e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663151"
---
# <a name="existing-keyword-mdx"></a><span data-ttu-id="c6cd0-102">EXISTING (Palabra clave, MDX)</span><span class="sxs-lookup"><span data-stu-id="c6cd0-102">EXISTING Keyword (MDX)</span></span>
  <span data-ttu-id="c6cd0-103">Exige que un conjunto especificado se evalúe en el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-103">Forces a specified set to be evaluated within the current context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6cd0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6cd0-104">Syntax</span></span>  
  
```  
  
Existing Set_Expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6cd0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c6cd0-105">Arguments</span></span>  
 <span data-ttu-id="c6cd0-106">*Set_Expression*</span><span class="sxs-lookup"><span data-stu-id="c6cd0-106">*Set_Expression*</span></span>  
 <span data-ttu-id="c6cd0-107">Una expresión de conjunto de MDX (Expresiones multidimensionales) válida.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-107">A valid Multidimensional Expressions (MDX) set expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6cd0-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c6cd0-108">Remarks</span></span>  
 <span data-ttu-id="c6cd0-109">De forma predeterminada, los conjuntos se evalúan en el contexto del cubo que contiene los miembros del conjunto.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-109">By default, sets are evaluated within the context of the cube that contains the members of the set.</span></span> <span data-ttu-id="c6cd0-110">La palabra clave `Existing` fuerza a un conjunto especificado a evaluarse en el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-110">The `Existing` keyword forces a specified set to be evaluated within the current context instead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6cd0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6cd0-111">Example</span></span>  
 <span data-ttu-id="c6cd0-112">El ejemplo siguiente devuelve el recuento de los distribuidores cuyas ventas han disminuido en el período de tiempo anterior, de acuerdo con los valores de los miembros State-Province seleccionados por el usuario, evaluados mediante la función `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-112">The following example returns the count of the resellers whose sales have declined over the previous time period, based on user-selected State-Province member values evaluated using the `Aggregate` function.</span></span> <span data-ttu-id="c6cd0-113">La palabra clave [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) y [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) se usan para devolver valores para las ventas que han disminuido en las categorías de productos de la dimensión Product.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-113">The [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) and [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) functions are used to return values for declining sales for product categories in the Product dimension.</span></span> <span data-ttu-id="c6cd0-114">La `Existing` palabra clave obliga al conjunto de la `Filter` función a evaluarse en el contexto actual, es decir, para los miembros de Washington y Oregon de la jerarquía de atributo State-provincia.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-114">The `Existing` keyword forces the set in the `Filter` function to be evaluated in the current context - that is, for the Washington and Oregon members of the State-Province attribute hierarchy.</span></span>  
  
```  
WITH MEMBER Measures.[Declining Reseller Sales] AS  
   Count  
      (Filter  
         (Existing  
            (Reseller.Reseller.Reseller)  
         , [Measures].[Reseller Sales Amount] <   
            ([Measures].[Reseller Sales Amount]  
               ,[Date].Calendar.PrevMember  
            )  
        )  
      )  
MEMBER [Geography].[State-Province].x AS   
   Aggregate   
      ( {[Geography].[State-Province].&[WA]&[US]  
         , [Geography].[State-Province].&[OR]&[US] }   
      )  
SELECT NON EMPTY HIERARCHIZE   
      (AddCalculatedMembers   
         (   
            {DrillDownLevel  
               ({[Product].[All Products]}  
               )  
            }   
         )   
      ) DIMENSION PROPERTIES PARENT_UNIQUE_NAME ON COLUMNS   
FROM [Adventure Works]  
WHERE   
      ( [Geography].[State-Province].x  
        , [Date].[Calendar].[Calendar Quarter].&[2003]&[4]  
        ,[Measures].[Declining Reseller Sales]  
      )  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6cd0-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6cd0-115">See Also</span></span>  
 <span data-ttu-id="c6cd0-116">[Count &#40;establecer&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span><span class="sxs-lookup"><span data-stu-id="c6cd0-116">[Count &#40;Set&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span></span>  
 <span data-ttu-id="c6cd0-117">[&#41;AddCalculatedMembers &#40;MDX](/sql/mdx/addcalculatedmembers-mdx) </span><span class="sxs-lookup"><span data-stu-id="c6cd0-117">[AddCalculatedMembers &#40;MDX&#41;](/sql/mdx/addcalculatedmembers-mdx) </span></span>  
 <span data-ttu-id="c6cd0-118">[&#40;de&#41;MDX de agregado](/sql/mdx/aggregate-mdx) </span><span class="sxs-lookup"><span data-stu-id="c6cd0-118">[Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) </span></span>  
 <span data-ttu-id="c6cd0-119">[Filtrar &#40;&#41;MDX](/sql/mdx/filter-mdx) </span><span class="sxs-lookup"><span data-stu-id="c6cd0-119">[Filter &#40;MDX&#41;](/sql/mdx/filter-mdx) </span></span>  
 <span data-ttu-id="c6cd0-120">[Propiedades &#40;&#41;MDX](/sql/mdx/properties-mdx) </span><span class="sxs-lookup"><span data-stu-id="c6cd0-120">[Properties &#40;MDX&#41;](/sql/mdx/properties-mdx) </span></span>  
 <span data-ttu-id="c6cd0-121">[&#41;DrilldownLevel &#40;MDX](/sql/mdx/drilldownlevel-mdx) </span><span class="sxs-lookup"><span data-stu-id="c6cd0-121">[DrilldownLevel &#40;MDX&#41;](/sql/mdx/drilldownlevel-mdx) </span></span>  
 <span data-ttu-id="c6cd0-122">[Jerarquía &#40;&#41;MDX](/sql/mdx/hierarchize-mdx) </span><span class="sxs-lookup"><span data-stu-id="c6cd0-122">[Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) </span></span>  
 [<span data-ttu-id="c6cd0-123">Referencia de funciones MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c6cd0-123">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
