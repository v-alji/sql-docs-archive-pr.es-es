---
title: Función InScope (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8cd209a-e5d3-4dce-ab2d-f271f6c54955
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62c4ad5de7af1ac0762df29deaa17953a8a378db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672710"
---
# <a name="inscope-function-report-builder-and-ssrs"></a><span data-ttu-id="77b84-102">Función InScope (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="77b84-102">InScope Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="77b84-103">Indica si la instancia actual de un elemento se encuentra en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="77b84-103">Indicates whether the current instance of an item is in the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="77b84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77b84-104">Syntax</span></span>  
  
```  
InScope(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77b84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77b84-105">Parameters</span></span>  
 <span data-ttu-id="77b84-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="77b84-106">*scope*</span></span>  
 <span data-ttu-id="77b84-107">(`String`). Nombre de un conjunto de datos, una región de datos o un grupo que especifica un ámbito.</span><span class="sxs-lookup"><span data-stu-id="77b84-107">(`String`) The name of a dataset, data region, or group that specifies a scope.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="77b84-108">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="77b84-108">Return Type</span></span>  
 <span data-ttu-id="77b84-109">Devuelve un `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="77b84-109">Returns a `Boolean`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77b84-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77b84-110">Remarks</span></span>  
 <span data-ttu-id="77b84-111">La `InScope` función prueba el ámbito de la instancia actual de un elemento de informe para su pertenencia en el ámbito especificado por el parámetro de *ámbito*.</span><span class="sxs-lookup"><span data-stu-id="77b84-111">The `InScope` function tests the scope of the current instance of a report item for membership in the scope specified by the *scope*parameter.</span></span>  
  
 <span data-ttu-id="77b84-112">*Scope* no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="77b84-112">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="77b84-113">La función `InScope` se usa habitualmente en regiones de datos que tienen un ámbito dinámico.</span><span class="sxs-lookup"><span data-stu-id="77b84-113">A typical use for the `InScope` function is in data regions that have dynamic scoping.</span></span> <span data-ttu-id="77b84-114">Por ejemplo, se puede usar `InScope` en un vínculo de obtención de detalles de las celdas de una región de datos para ofrecer un nombre de informe distinto y diferentes conjuntos de parámetros en función de la celda en la que se haga clic.</span><span class="sxs-lookup"><span data-stu-id="77b84-114">For example, `InScope` can be used in a drillthrough link in a data region cells to provide a different report name and different sets of parameters depending on which cell is clicked.</span></span> <span data-ttu-id="77b84-115">He aquí un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="77b84-115">An example of this is as follows:</span></span>  
  
-   <span data-ttu-id="77b84-116">La expresión siguiente, usada como nombre de informe en un vínculo de obtención de detalles, abre el informe `ProductDetail` si la celda en la que se hace clic está en el grupo `Month` , o el informe `ProductSummary` si no lo está.</span><span class="sxs-lookup"><span data-stu-id="77b84-116">The following expression, used as the report name in a drillthrough link, opens the `ProductDetail` report if the clicked cell is in the `Month` group, and the `ProductSummary` report if it is not.</span></span>  
  
    ```  
    =Iif(InScope("Month"), "ProductDetail", "ProductSummary")  
    ```  
  
-   <span data-ttu-id="77b84-117">La expresión siguiente, usada en la propiedad `Omit` de un parámetro de informe detallado, pasa el parámetro al informe de destino solo si la celda en la que se hace clic está en el grupo `Product`.</span><span class="sxs-lookup"><span data-stu-id="77b84-117">The following expression, used in the `Omit` property of a drillthrough report parameter, will pass the parameter to the target report only if the clicked cell is in the `Product` group.</span></span>  
  
    ```  
    =Not(InScope("Product"))  
    ```  
  
 <span data-ttu-id="77b84-118">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="77b84-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77b84-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77b84-119">Example</span></span>  
 <span data-ttu-id="77b84-120">El siguiente ejemplo de código indica si la instancia actual del elemento está en el ámbito del conjunto de datos, la región de datos o el grupo `Product` .</span><span class="sxs-lookup"><span data-stu-id="77b84-120">The following code example indicates whether the current instance of the item is in the `Product` dataset, data region, or group scope.</span></span>  
  
```  
=InScope("Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="77b84-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77b84-121">See Also</span></span>  
 <span data-ttu-id="77b84-122">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="77b84-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="77b84-123">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="77b84-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="77b84-124">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="77b84-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="77b84-125">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="77b84-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
