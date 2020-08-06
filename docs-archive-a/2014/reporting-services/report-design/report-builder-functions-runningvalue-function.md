---
title: Función RunningValue (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6bee2f15-0e69-49c8-9689-b04544063b1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 168073a0409455041f4ebe3aa4c5dcfc8fa129a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672690"
---
# <a name="runningvalue-function-report-builder-and-ssrs"></a><span data-ttu-id="deaa1-102">Función RunningValue (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="deaa1-102">RunningValue Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="deaa1-103">Devuelve un agregado actualizado de todos los valores numéricos no NULL especificados por la expresión, que se evalúa en el contexto del ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="deaa1-103">Returns a running aggregate of all non-null numeric values specified by the expression, evaluated for the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="deaa1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="deaa1-104">Syntax</span></span>  
  
```  
  
RunningValue(expression, function, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="deaa1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="deaa1-105">Parameters</span></span>  
 <span data-ttu-id="deaa1-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="deaa1-106">*expression*</span></span>  
 <span data-ttu-id="deaa1-107">Expresión en la que se lleva a cabo la agregación; por ejemplo, `[Quantity]`.</span><span class="sxs-lookup"><span data-stu-id="deaa1-107">The expression on which to perform the aggregation, for example, `[Quantity]`.</span></span>  
  
 <span data-ttu-id="deaa1-108">*function*</span><span class="sxs-lookup"><span data-stu-id="deaa1-108">*function*</span></span>  
 <span data-ttu-id="deaa1-109">(`Enum`). Nombre de la función de agregado que se aplica a la expresión; por ejemplo, `Sum`.</span><span class="sxs-lookup"><span data-stu-id="deaa1-109">(`Enum`) The name of the aggregate function to apply to the expression, for example, `Sum`.</span></span> <span data-ttu-id="deaa1-110">Esta función no puede ser `RunningValue`, `RowNumber` ni `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="deaa1-110">This function cannot be `RunningValue`, `RowNumber`, or `Aggregate`.</span></span>  
  
 <span data-ttu-id="deaa1-111">*scope*</span><span class="sxs-lookup"><span data-stu-id="deaa1-111">*scope*</span></span>  
 <span data-ttu-id="deaa1-112">(`String`) Constante de cadena que es el nombre de un conjunto de datos, grupo, región de datos o NULL (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), que especifica el contexto en el que evaluar la agregación.</span><span class="sxs-lookup"><span data-stu-id="deaa1-112">(`String`) A string constant that is the name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the aggregation.</span></span> <span data-ttu-id="deaa1-113">`Nothing` especifica el contexto más externo, normalmente el conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="deaa1-113">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="deaa1-114">Tipo de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="deaa1-114">Return Type</span></span>  
 <span data-ttu-id="deaa1-115">Viene determinado por la función de agregado especificada en el parámetro *function* .</span><span class="sxs-lookup"><span data-stu-id="deaa1-115">Determined by the aggregate function that is specified in the *function* parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="deaa1-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="deaa1-116">Remarks</span></span>  
 <span data-ttu-id="deaa1-117">El valor para `RunningValue` se restablece en 0 para cada nueva instancia del ámbito.</span><span class="sxs-lookup"><span data-stu-id="deaa1-117">The value for `RunningValue` resets to 0 for each new instance of the scope.</span></span> <span data-ttu-id="deaa1-118">Si se especifica un grupo, el valor actual se restablece cuando cambia la expresión de grupo.</span><span class="sxs-lookup"><span data-stu-id="deaa1-118">If a group is specified, the running value is reset when the group expression changes.</span></span> <span data-ttu-id="deaa1-119">Si se especifica una región de datos, el valor actual se restablece en cada instancia nueva de la región de datos.</span><span class="sxs-lookup"><span data-stu-id="deaa1-119">If a data region is specified, the running value is reset for each new instance of the data region.</span></span> <span data-ttu-id="deaa1-120">Si se especifica un conjunto de datos, el valor actual no se restablece en todo el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="deaa1-120">If a dataset is specified, the running value is not reset throughout the entire dataset.</span></span>  
  
 <span data-ttu-id="deaa1-121">`RunningValue` no se puede utilizar en un filtro o expresión de ordenación.</span><span class="sxs-lookup"><span data-stu-id="deaa1-121">`RunningValue` cannot be used in a filter or sort expression.</span></span>  
  
 <span data-ttu-id="deaa1-122">El conjunto de datos para los que se calcula el valor en ejecución debe tener el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="deaa1-122">The set of data for which the running value is calculated must have the same data type.</span></span> <span data-ttu-id="deaa1-123">Si desea convertir datos de varios tipos de datos numéricos al mismo tipo de datos, use funciones de conversión como `CInt`, `CDbl` o `CDec`.</span><span class="sxs-lookup"><span data-stu-id="deaa1-123">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="deaa1-124">Para obtener más información, vea [Funciones de conversión de tipos](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="deaa1-124">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="deaa1-125">*Scope* no puede ser una expresión.</span><span class="sxs-lookup"><span data-stu-id="deaa1-125">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="deaa1-126">*Expression* puede contener las llamadas a las funciones de agregados anidados con las siguientes excepciones y condiciones:</span><span class="sxs-lookup"><span data-stu-id="deaa1-126">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="deaa1-127">El ámbito para los agregados anidados debe ser igual que el ámbito del agregado exterior, o ser contenido por él.</span><span class="sxs-lookup"><span data-stu-id="deaa1-127">Scope for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="deaa1-128">Para todos los ámbitos distintos de la expresión, un ámbito debe estar en una relación secundaria con respecto a todos los otros ámbitos.</span><span class="sxs-lookup"><span data-stu-id="deaa1-128">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="deaa1-129">El ámbito para los agregados anidados no puede ser el nombre de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="deaa1-129">Scope for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="deaa1-130">*Expression* no debe contener `First` `Last` `Previous` las funciones,, o `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="deaa1-130">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="deaa1-131">*Expression* no debe contener a los agregados anidados que especifican *recursive*.</span><span class="sxs-lookup"><span data-stu-id="deaa1-131">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="deaa1-132">Para calcular el valor actual del número de filas, use `RowNumber`.</span><span class="sxs-lookup"><span data-stu-id="deaa1-132">To calculate the running value of the number of rows, use `RowNumber`.</span></span> <span data-ttu-id="deaa1-133">Para más información, vea [Función RowNumber &#40;Generador de informes y SSRS&#41;](report-builder-functions-rownumber-function.md).</span><span class="sxs-lookup"><span data-stu-id="deaa1-133">For more information, see [RowNumber Function &#40;Report Builder and SSRS&#41;](report-builder-functions-rownumber-function.md).</span></span>  
  
 <span data-ttu-id="deaa1-134">Para más información, vea [Funciones del generador de informes - referencia de funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) y [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="deaa1-134">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="deaa1-135">Para más información sobre los agregados recursivos, vea [Crear un grupo de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="deaa1-135">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="deaa1-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="deaa1-136">Examples</span></span>  
 <span data-ttu-id="deaa1-137">El ejemplo de código siguiente proporciona la suma actual del campo denominado `Cost` en el ámbito más externo, que es el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="deaa1-137">The following code example provides a running sum of the field named `Cost` in the outermost scope, which is the dataset.</span></span>  
  
```  
=RunningValue(Fields!Cost.Value, Sum, Nothing)  
```  
  
 <span data-ttu-id="deaa1-138">El ejemplo de código siguiente proporciona la suma actual del campo denominado `Score` en el conjunto de datos denominado `DataSet1`.</span><span class="sxs-lookup"><span data-stu-id="deaa1-138">The following code example provides a running sum of the field named `Score` in the dataset named `DataSet1`.</span></span>  
  
```  
=RunningValue(Fields!Score.Value,sum,"DataSet1")  
```  
  
 <span data-ttu-id="deaa1-139">El ejemplo de código siguiente proporciona la suma actual del campo denominado `Traffic Charges` en el ámbito más externo.</span><span class="sxs-lookup"><span data-stu-id="deaa1-139">The following code example provides a running sum of the field named `Traffic Charges` in the outermost scope.</span></span>  
  
```  
=RunningValue(Fields!Traffic Charges.Value, Sum, Nothing)  
```  
  
## <a name="see-also"></a><span data-ttu-id="deaa1-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="deaa1-140">See Also</span></span>  
 <span data-ttu-id="deaa1-141">[Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="deaa1-141">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="deaa1-142">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="deaa1-142">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="deaa1-143">[Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="deaa1-143">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="deaa1-144">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="deaa1-144">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
