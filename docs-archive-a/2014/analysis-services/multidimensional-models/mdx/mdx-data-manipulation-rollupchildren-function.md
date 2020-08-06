---
title: Trabajar con la función RollupChildren (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], RollupChildren function
- RollupChildren function
- custom member properties [MDX]
- IIf function
ms.assetid: 03c624d4-f277-451d-9995-623a07ea2f86
author: minewiskan
ms.author: owend
ms.openlocfilehash: 341468d521cebe1fda33d73ea999f3b6571cb01e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748342"
---
# <a name="working-with-the-rollupchildren-function-mdx"></a><span data-ttu-id="e7eb6-102">Trabajar con la función RollupChildren (MDX)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-102">Working with the RollupChildren Function (MDX)</span></span>
  <span data-ttu-id="e7eb6-103">La función [RollupChildren](/sql/mdx/rollupchildren-mdx) [script for Search and Replace] de las expresiones multidimensionales (MDX) acumula los elementos secundarios de un miembro, aplicando un operador unario diferente a cada elemento secundario y devuelve el valor de este resumen como un número.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-103">The Multidimensional Expressions (MDX) [RollupChildren](/sql/mdx/rollupchildren-mdx) [Script for Search and Replace] function rolls up the children of a member, applying a different unary operator to each child, and returns the value of this rollup as a number.</span></span> <span data-ttu-id="e7eb6-104">El operador unario utilizado puede ser proporcionado mediante una propiedad de miembro asociada al miembro secundario, o bien puede ser una expresión de cadena proporcionada directamente a la función.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-104">The unary operator can be supplied by a member property associated with the child member, or the operator can be a string expression provided directly to the function.</span></span>  
  
## <a name="rollupchildren-function-examples"></a><span data-ttu-id="e7eb6-105">Ejemplos de la función RollupChildren</span><span class="sxs-lookup"><span data-stu-id="e7eb6-105">RollupChildren Function Examples</span></span>  
 <span data-ttu-id="e7eb6-106">El uso de la función `RollupChildren` en instrucciones de expresiones multidimensionales (MDX) es fácil de explicar, pero esta función puede tener un impacto muy variado en las consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-106">The use of the `RollupChildren` function in Multidimensional Expressions (MDX) statements is simple to explain, but the effect of this function on MDX queries can be wide-ranging.</span></span>  
  
 <span data-ttu-id="e7eb6-107">El efecto de la función `RollupChildren` se produce en las consultas MDX diseñadas para realizar un análisis selectivo de los datos del cubo existentes.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-107">The effect of the `RollupChildren` function occurs in MDX queries designed to perform selective analysis on existing cube data.</span></span> <span data-ttu-id="e7eb6-108">Por ejemplo, la siguiente tabla contiene una lista de los miembros secundarios del miembro primario Net Sales, con sus operadores unarios (representados por la propiedad de miembro `UNARY_OPERATOR`) entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-108">For example, the following table contains a list of child members for the Net Sales parent member, with their unary operators (represented by the `UNARY_OPERATOR` member property) shown in parentheses.</span></span>  
  
|<span data-ttu-id="e7eb6-109">Miembro primario</span><span class="sxs-lookup"><span data-stu-id="e7eb6-109">Parent member</span></span>|<span data-ttu-id="e7eb6-110">Miembro secundario</span><span class="sxs-lookup"><span data-stu-id="e7eb6-110">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="e7eb6-111">Ventas netas</span><span class="sxs-lookup"><span data-stu-id="e7eb6-111">Net Sales</span></span>|<span data-ttu-id="e7eb6-112">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-112">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="e7eb6-113">Domestic Returns (-)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-113">Domestic Returns (-)</span></span><br /><br /> <span data-ttu-id="e7eb6-114">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-114">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="e7eb6-115">Foreign Returns (-)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-115">Foreign Returns (-)</span></span>|  
  
 <span data-ttu-id="e7eb6-116">El miembro primario Net Sales actualmente proporciona un total de ventas netas menos los valores de ventas domésticas y extranjeras brutas, con los valores de las ventas domesticas y extranjeras restados como parte del resumen.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-116">The Net Sales parent member currently provides a total of net sales minus the gross domestic and foreign sales values, with the domestic and foreign returns subtracted as part of the rollup.</span></span>  
  
 <span data-ttu-id="e7eb6-117">Sin embargo, suponga que desea proporcionar una previsión rápida y simple de las ventas brutas domésticas y extranjeras más el 10% y omitir los valores devueltos de ventas domésticas y extranjeras.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-117">However, you want to provide a quick and easy forecast of domestic and foreign gross sales plus 10%, ignoring the domestic and foreign returns.</span></span> <span data-ttu-id="e7eb6-118">Para calcular este valor puede utilizar la función `RollupChildren` de dos maneras: con una propiedad de miembro personalizado o con la función `IIf`.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-118">To calculate this value, you can use the `RollupChildren` function in one of two ways: with a custom member property or with the `IIf` function.</span></span>  
  
### <a name="using-a-custom-member-property"></a><span data-ttu-id="e7eb6-119">Usar una propiedad de miembro personalizado</span><span class="sxs-lookup"><span data-stu-id="e7eb6-119">Using a Custom Member Property</span></span>  
 <span data-ttu-id="e7eb6-120">Si el cálculo de resumen se va a realizar habitualmente, un método es crear una propiedad de miembro que almacene el operador que se vaya a utilizar para cada secundario para una función determinada.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-120">If the rollup calculation is to be a frequently performed operation, one method is to create a member property that stores the operator that will be used for each child for a specific function.</span></span> <span data-ttu-id="e7eb6-121">En la siguiente tabla se muestran los operadores unarios válidos y se describe el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-121">The following table displays valid unary operators and describes the expected result.</span></span>  
  
|<span data-ttu-id="e7eb6-122">Operador</span><span class="sxs-lookup"><span data-stu-id="e7eb6-122">Operator</span></span>|<span data-ttu-id="e7eb6-123">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7eb6-123">Result</span></span>|  
|--------------|------------|  
|+|<span data-ttu-id="e7eb6-124">total = total + elemento secundario actual</span><span class="sxs-lookup"><span data-stu-id="e7eb6-124">total = total + current child</span></span>|  
|-|<span data-ttu-id="e7eb6-125">total = total - elemento secundario actual</span><span class="sxs-lookup"><span data-stu-id="e7eb6-125">total = total - current child</span></span>|  
|*|<span data-ttu-id="e7eb6-126">total = total \* elemento secundario actual</span><span class="sxs-lookup"><span data-stu-id="e7eb6-126">total = total \* current child</span></span>|  
|/|<span data-ttu-id="e7eb6-127">total = total / elemento secundario actual</span><span class="sxs-lookup"><span data-stu-id="e7eb6-127">total = total / current child</span></span>|  
|~|<span data-ttu-id="e7eb6-128">El elemento secundario no se utiliza en el resumen.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-128">Child is not used in the rollup.</span></span> <span data-ttu-id="e7eb6-129">El valor del elemento secundario se omite.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-129">The child's value is ignored.</span></span>|  
  
 <span data-ttu-id="e7eb6-130">Por ejemplo, se podría crear una propiedad de miembro llamada `SALES_OPERATOR` a la que se le asignen los siguientes operadores unarios, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-130">For example, a member property called `SALES_OPERATOR` could be created, and the following unary operators would be assigned to that member property, as shown in the following table.</span></span>  
  
|<span data-ttu-id="e7eb6-131">Miembro primario</span><span class="sxs-lookup"><span data-stu-id="e7eb6-131">Parent member</span></span>|<span data-ttu-id="e7eb6-132">Miembro secundario</span><span class="sxs-lookup"><span data-stu-id="e7eb6-132">Child member</span></span>|  
|-------------------|------------------|  
|<span data-ttu-id="e7eb6-133">Ventas netas</span><span class="sxs-lookup"><span data-stu-id="e7eb6-133">Net Sales</span></span>|<span data-ttu-id="e7eb6-134">Domestic Sales (+)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-134">Domestic Sales (+)</span></span><br /><br /> <span data-ttu-id="e7eb6-135">Domestic Returns (~)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-135">Domestic Returns (~)</span></span><br /><br /> <span data-ttu-id="e7eb6-136">Foreign Sales (+)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-136">Foreign Sales (+)</span></span><br /><br /> <span data-ttu-id="e7eb6-137">Foreign Returns (~)</span><span class="sxs-lookup"><span data-stu-id="e7eb6-137">Foreign Returns (~)</span></span>|  
  
 <span data-ttu-id="e7eb6-138">Con esta nueva propiedad de miembro, la siguiente instrucción MDX llevaría a cabo la operación de estimación de ventas brutas de forma rápida y eficaz (omitiendo los valores devueltos para las ventas domésticas y extranjeras):</span><span class="sxs-lookup"><span data-stu-id="e7eb6-138">With this new member property, the following MDX statement would perform the gross sales estimate operation quickly and efficiently (ignoring Foreign and Domestic returns):</span></span>  
  
```  
RollupChildren([Net Sales], [Net Sales].CurrentMember.Properties("SALES_OPERATOR")) * 1.1  
```  
  
 <span data-ttu-id="e7eb6-139">Cuando se llama a la función, el valor de cada secundario se aplica a un total utilizando el operador almacenado en la propiedad de miembro.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-139">When the function is called, the value of each child is applied to a total using the operator stored in the member property.</span></span> <span data-ttu-id="e7eb6-140">Los miembros de los valores domésticos y extranjeros devueltos se omiten y el total del resumen devuelto por la función `RollupChildren` se multiplica por 1.1.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-140">The members for domestic and foreign returns are ignored, and the rollup total returned by the `RollupChildren` function is multiplied by 1.1.</span></span>  
  
### <a name="using-the-iif-function"></a><span data-ttu-id="e7eb6-141">Usar la función IIf</span><span class="sxs-lookup"><span data-stu-id="e7eb6-141">Using the IIf Function</span></span>  
 <span data-ttu-id="e7eb6-142">Si la operación de ejemplo no es habitual o si la operación solo se aplica a una consulta MDX, se puede usar la función [IIf](/sql/mdx/iif-mdx) con la `RollupChildren` función para proporcionar el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-142">If the example operation is not commonplace or if the operation applies only to one MDX query, the [IIf](/sql/mdx/iif-mdx) function can be used with the `RollupChildren` function to provide the same result.</span></span> <span data-ttu-id="e7eb6-143">La siguiente consulta MDX proporciona el mismo resultado que el ejemplo anterior, pero sin recurrir al uso de una propiedad de miembro personalizado:</span><span class="sxs-lookup"><span data-stu-id="e7eb6-143">The following MDX query provides the same result as the earlier MDX example, but does so without resorting to the use of a custom member property:</span></span>  
  
```  
RollupChildren([Net Sales], IIf([Net Sales].CurrentMember.Properties("UNARY_OPERATOR") = "-", "~", [Net Sales].CurrentMember.Properties("UNARY_OPERATOR))) * 1.1  
```  
  
 <span data-ttu-id="e7eb6-144">La instrucción MDX examina el operador unario del miembro secundario.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-144">The MDX statement examines the unary operator of the child member.</span></span> <span data-ttu-id="e7eb6-145">Si el operador unario se utiliza para la operación de resta (como sucede con los miembros de los valores domésticos y extranjeros devueltos), la función `IIf` sustituye al operador unario tilde (~).</span><span class="sxs-lookup"><span data-stu-id="e7eb6-145">If the unary operator is used for subtraction (as in the case with the domestic and foreign returns members), the `IIf` function substitutes the tilde (~) unary operator.</span></span> <span data-ttu-id="e7eb6-146">De lo contrario, la función `IIf` utiliza el operador unario del miembro secundario.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-146">Otherwise, the `IIf` function uses the unary operator of the child member.</span></span> <span data-ttu-id="e7eb6-147">Finalmente, el total de resumen devuelto se multiplica por 1.1 para proporcionar el valor de predicción de las ventas brutas domésticas y extranjeras.</span><span class="sxs-lookup"><span data-stu-id="e7eb6-147">Finally, the returned rollup total is then multiplied by 1.1 to provide the domestic and foreign gross sales forecast value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7eb6-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7eb6-148">See Also</span></span>  
 [<span data-ttu-id="e7eb6-149">Manipular datos &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="e7eb6-149">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
