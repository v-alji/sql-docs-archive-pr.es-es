---
title: MDX compatible (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], statements
- MDX [Analysis Services], functions
ms.assetid: 308bc0b3-4fd6-4435-972b-5e40d9e3c99b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e8df6a2aa6da6b88a07a2abdef99d6ea03d8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748339"
---
# <a name="supported-mdx-mdx"></a><span data-ttu-id="4411c-102">Compatibilidad con MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="4411c-102">Supported MDX (MDX)</span></span>
  <span data-ttu-id="4411c-103">Las siguientes instrucciones y funciones se admiten en script MDX (Expresiones multidimensionales):</span><span class="sxs-lookup"><span data-stu-id="4411c-103">The following statements and functions are supported within Multidimensional Expressions (MDX) Script:</span></span>  
  
 [<span data-ttu-id="4411c-104">&#40;Comentario&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-104">&#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="4411c-105">-- &#40;Comentario&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-105">-- &#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="4411c-106">Comentario &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-106">Comment &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="4411c-107">ALTER CUBE &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-107">ALTER CUBE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-alter-cube)  
  
> [!NOTE]  
>  <span data-ttu-id="4411c-108">El scripting MDX solo permite la modificación del miembro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4411c-108">Only altering the default member is supported in MDX Scripting.</span></span>  
  
 [<span data-ttu-id="4411c-109">CALCULATE &#40;instrucción MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-109">CALCULATE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
 [<span data-ttu-id="4411c-110">Instrucción CASE &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-110">CASE Statement &#40;MDX&#41;</span></span>](/sql/mdx/case-statement-mdx)  
  
 [<span data-ttu-id="4411c-111">CREATE CELL CALCULATION &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-111">CREATE CELL CALCULATION Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-cell-calculation)  
  
 [<span data-ttu-id="4411c-112">CREATE MEMBER &#40;instrucción MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-112">CREATE MEMBER Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-member)  
  
 [<span data-ttu-id="4411c-113">CREATE SET &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-113">CREATE SET Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-set)  
  
 [<span data-ttu-id="4411c-114">EXISTING &#40;Palabra clave, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-114">EXISTING Keyword &#40;MDX&#41;</span></span>](mdx-query-existing-keyword.md)  
  
 [<span data-ttu-id="4411c-115">FREEZE &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-115">FREEZE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
 [<span data-ttu-id="4411c-116">IF &#40;instrucción de MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-116">IF Statement  &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-if)  
  
 [<span data-ttu-id="4411c-117">This &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-117">This &#40;MDX&#41;</span></span>](/sql/mdx/this-mdx)  
  
> [!NOTE]  
>  <span data-ttu-id="4411c-118">MDX admite la asignación a las siguientes propiedades de celda: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME` y `FONT_SIZE`.</span><span class="sxs-lookup"><span data-stu-id="4411c-118">MDX supports assignment to the following cell properties: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME`, and `FONT_SIZE`.</span></span> <span data-ttu-id="4411c-119">Para obtener más información, vea [Usar las propiedades de celda &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4411c-119">For more information, see [Using Cell Properties &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span></span> <span data-ttu-id="4411c-120">MDX también admite la asignación a la `NON_EMPTY_BEHAVIOR` propiedad de la instrucción [Create Member](/sql/mdx/mdx-data-definition-create-member) .</span><span class="sxs-lookup"><span data-stu-id="4411c-120">MDX also supports assignment to the `NON_EMPTY_BEHAVIOR` property of the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span>  
  
 [<span data-ttu-id="4411c-121">SCOPE &#40;Instrucción, MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-121">SCOPE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-scope)  
  
## <a name="see-also"></a><span data-ttu-id="4411c-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4411c-122">See Also</span></span>  
 [<span data-ttu-id="4411c-123">Script MDX básico &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4411c-123">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)  
  
  
