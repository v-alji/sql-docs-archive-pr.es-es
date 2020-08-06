---
title: Función Level (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dedbf00ce8330242c95e9592f649d95171f0987a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672708"
---
# <a name="level-function-report-builder-and-ssrs"></a><span data-ttu-id="f9f63-102">Función Level (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="f9f63-102">Level Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f9f63-103">Devuelve el nivel actual de profundidad de una jerarquía recursiva.</span><span class="sxs-lookup"><span data-stu-id="f9f63-103">Returns the current level of depth in a recursive hierarchy.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="f9f63-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9f63-104">Syntax</span></span>  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9f63-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9f63-105">Parameters</span></span>  
 <span data-ttu-id="f9f63-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="f9f63-106">*scope*</span></span>  
 <span data-ttu-id="f9f63-107">( `String` ) (Opcional).</span><span class="sxs-lookup"><span data-stu-id="f9f63-107">(`String`) (Optional).</span></span> <span data-ttu-id="f9f63-108">Nombre de un conjunto de datos, un grupo o una región de datos que contiene los elementos de informe a los que se va a aplicar la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f9f63-108">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="f9f63-109">Si no se especifica el parámetro *scope* , se usa el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f9f63-109">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="f9f63-110">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f9f63-110">Return Type</span></span>  
 <span data-ttu-id="f9f63-111">Devuelve un valor `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f9f63-111">Returns an `Integer`.</span></span> <span data-ttu-id="f9f63-112">Si el *ámbito* especifica un conjunto de datos o una región de datos, o especifica una agrupación de no recursiva (es decir, una agrupación sin `Parent` elemento), `Level` devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="f9f63-112">If *scope* specifies a dataset or data region, or specifies a nonrecursive grouping (that is, a grouping with no `Parent` element), `Level` returns 0.</span></span> <span data-ttu-id="f9f63-113">Si se omite el parámetro *scope* , devuelve el nivel del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f9f63-113">If *scope* is omitted, it returns the level of the current scope.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9f63-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f9f63-114">Remarks</span></span>  
 <span data-ttu-id="f9f63-115">El valor que devuelve la función `Level` se basa en cero; es decir, el primer nivel de una jerarquía es 0.</span><span class="sxs-lookup"><span data-stu-id="f9f63-115">The value returned by the `Level` function is zero based; that is, the first level in a hierarchy is 0.</span></span>  
  
 <span data-ttu-id="f9f63-116">La función `Level` puede utilizarse para aplicar sangría en una jerarquía recursiva, como puede ser una lista de empleados.</span><span class="sxs-lookup"><span data-stu-id="f9f63-116">The `Level` function can be used to provide indentation in a recursive hierarchy, such as an employee list.</span></span>  
  
 <span data-ttu-id="f9f63-117">Para más información sobre jerarquías recursivas, vea [Crear grupos de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f9f63-117">For more information about recursive hierarchies, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9f63-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9f63-118">Example</span></span>  
 <span data-ttu-id="f9f63-119">El siguiente ejemplo de código devuelve el nivel de fila del grupo Employees:</span><span class="sxs-lookup"><span data-stu-id="f9f63-119">The following code example provides the level of row in the Employees group:</span></span>  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9f63-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9f63-120">See Also</span></span>  
 <span data-ttu-id="f9f63-121">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f9f63-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f9f63-122">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f9f63-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f9f63-123">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f9f63-123">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f9f63-124">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f9f63-124">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
