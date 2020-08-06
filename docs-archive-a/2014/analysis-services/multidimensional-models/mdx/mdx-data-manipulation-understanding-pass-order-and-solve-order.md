---
title: Descripción de orden de paso y orden de resolución (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- evaluation order [MDX]
- calculation order [MDX]
- SOLVE_ORDER property
- queries [MDX], solve orders
- solve orders [MDX]
- pass orders [MDX]
- expressions [MDX], solve orders
ms.assetid: 7ed7d4ee-4644-4c5d-99a4-c4b429d0203c
author: minewiskan
ms.author: owend
ms.openlocfilehash: d92ccd9d1eeb05272a95c6f429f8c756bcb0022e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671732"
---
# <a name="understanding-pass-order-and-solve-order-mdx"></a><span data-ttu-id="4c236-102">Descripción de orden de paso y orden de resolución (MDX)</span><span class="sxs-lookup"><span data-stu-id="4c236-102">Understanding Pass Order and Solve Order (MDX)</span></span>
  <span data-ttu-id="4c236-103">Cuando un cubo se calcula como el resultado de un script de MDX, puede atravesar varias fases de computación según el uso de varias características relativas al cálculo.</span><span class="sxs-lookup"><span data-stu-id="4c236-103">When a cube is calculated as the result of an MDX script, it can go through many stages of computation depending on the use of various calculation-related features.</span></span> <span data-ttu-id="4c236-104">Cada una de estas fases se denomina paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4c236-104">Each of these stages is referred to as a calculation pass.</span></span>  
  
 <span data-ttu-id="4c236-105">Se puede hacer referencia a un paso de cálculo con una posición ordinal, llamada número de paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4c236-105">A calculation pass can be referred to by an ordinal position, called the calculation pass number.</span></span> <span data-ttu-id="4c236-106">El recuento de los pasos de cálculo necesarios para calcular por completo todas las celdas de un cubo se denomina profundidad de paso de cálculo del cubo.</span><span class="sxs-lookup"><span data-stu-id="4c236-106">The count of calculation passes that are required to fully compute all the cells of a cube is referred to as the calculation pass depth of the cube.</span></span>  
  
 <span data-ttu-id="4c236-107">Los datos de la tabla de hechos y reescritura solo afectan al paso 0.</span><span class="sxs-lookup"><span data-stu-id="4c236-107">Fact table and writeback data only impact pass 0.</span></span> <span data-ttu-id="4c236-108">Los scripts rellenan los datos después del paso 0; cada instrucción de asignación y cálculo de un script crea un nuevo paso.</span><span class="sxs-lookup"><span data-stu-id="4c236-108">Scripts populate data after pass 0; each assignment and calculate statement in a script creates a new pass.</span></span> <span data-ttu-id="4c236-109">Fuera del script MDX, las referencias al paso absoluto 0 hacen referencia al último paso creado por el script del cubo.</span><span class="sxs-lookup"><span data-stu-id="4c236-109">Outside the MDX script, references to absolute pass 0 refer to the last pass created by the script for the cube.</span></span>  
  
 <span data-ttu-id="4c236-110">Los miembros calculados se crean en todos los pasos, pero la expresión se aplica al paso actual.</span><span class="sxs-lookup"><span data-stu-id="4c236-110">Calculated members are created at all passes, but the expression is applied at the current pass.</span></span> <span data-ttu-id="4c236-111">Los pasos anteriores contienen la medida calculada, pero con un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="4c236-111">Prior passes contain the calculated measure, but with a null value.</span></span>  
  
## <a name="solve-order"></a><span data-ttu-id="4c236-112">Orden de resolución</span><span class="sxs-lookup"><span data-stu-id="4c236-112">Solve Order</span></span>  
 <span data-ttu-id="4c236-113">El orden de resolución determina la prioridad de cálculo en el caso de expresiones enfrentadas.</span><span class="sxs-lookup"><span data-stu-id="4c236-113">Solve order determines the priority of calculation in the event of competing expressions.</span></span> <span data-ttu-id="4c236-114">En un solo paso, el orden de resolución determina dos cosas:</span><span class="sxs-lookup"><span data-stu-id="4c236-114">Within a single pass, solve order determines two things:</span></span>  
  
-   <span data-ttu-id="4c236-115">El orden en el que [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evalúa dimensiones, miembros, miembros calculados, resúmenes personalizados y celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="4c236-115">The order in which [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates dimensions, members, calculated members, custom rollups, and calculated cells.</span></span>  
  
-   <span data-ttu-id="4c236-116">El orden en el que [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calcula miembros personalizados, miembros calculados, resúmenes personalizados y celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="4c236-116">The order in which [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates custom members, calculated members, custom rollup, and calculated cells.</span></span>  
  
 <span data-ttu-id="4c236-117">Tendrá prioridad el miembro con el orden de resolución superior.</span><span class="sxs-lookup"><span data-stu-id="4c236-117">The member with the highest solve order takes precedence.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c236-118">La excepción a esta prioridad es la función Agregado.</span><span class="sxs-lookup"><span data-stu-id="4c236-118">The exception to this precedence is the Aggregate function.</span></span> <span data-ttu-id="4c236-119">Los miembros calculados con la función Agregado tienen un orden de resolución inferior al de las medidas calculadas coincidentes.</span><span class="sxs-lookup"><span data-stu-id="4c236-119">Calculated members with the Aggregate function have a lower solve order than any intersecting calculated measure.</span></span>  
  
## <a name="solve-order-values-and-precedence"></a><span data-ttu-id="4c236-120">Valores y prioridad de orden de resolución</span><span class="sxs-lookup"><span data-stu-id="4c236-120">Solve Order Values and Precedence</span></span>  
 <span data-ttu-id="4c236-121">Los valores de orden de resolución varían de -8181 a 65535.</span><span class="sxs-lookup"><span data-stu-id="4c236-121">Solve order values can range from -8181 to 65535.</span></span> <span data-ttu-id="4c236-122">En este intervalo, algunos valores de orden de resolución corresponden a tipos específicos de cálculos, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="4c236-122">In this range, some solve order values correspond to specific kinds of calculations, as shown in the following table.</span></span>  
  
|<span data-ttu-id="4c236-123">Cálculo</span><span class="sxs-lookup"><span data-stu-id="4c236-123">Calculation</span></span>|<span data-ttu-id="4c236-124">Orden de resolución</span><span class="sxs-lookup"><span data-stu-id="4c236-124">Solve Order</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4c236-125">Fórmulas de miembro personalizado</span><span class="sxs-lookup"><span data-stu-id="4c236-125">Custom member formulas</span></span>|<span data-ttu-id="4c236-126">-5119</span><span class="sxs-lookup"><span data-stu-id="4c236-126">-5119</span></span>|  
|<span data-ttu-id="4c236-127">Operadores unarios</span><span class="sxs-lookup"><span data-stu-id="4c236-127">Unary operators</span></span>|<span data-ttu-id="4c236-128">-5119</span><span class="sxs-lookup"><span data-stu-id="4c236-128">-5119</span></span>|  
|<span data-ttu-id="4c236-129">Cálculo de totales visuales</span><span class="sxs-lookup"><span data-stu-id="4c236-129">Visual totals calculation</span></span>|<span data-ttu-id="4c236-130">-4096</span><span class="sxs-lookup"><span data-stu-id="4c236-130">-4096</span></span>|  
|<span data-ttu-id="4c236-131">Resto de cálculos (si no se especifica lo contrario)</span><span class="sxs-lookup"><span data-stu-id="4c236-131">All other calculations (if not otherwise specified)</span></span>|<span data-ttu-id="4c236-132">0</span><span class="sxs-lookup"><span data-stu-id="4c236-132">0</span></span>|  
  
 <span data-ttu-id="4c236-133">Se recomienda utilizar enteros positivos para establecer valores de orden de resolución.</span><span class="sxs-lookup"><span data-stu-id="4c236-133">It is highly recommended that you use only positive integers when setting solve order values.</span></span> <span data-ttu-id="4c236-134">Si asigna valores posteriores a los valores de orden de resolución mostrados en la tabla anterior, el paso de cálculo puede resultar imprevisible.</span><span class="sxs-lookup"><span data-stu-id="4c236-134">If you assign values that are lower than the solve order values shown in the previous table, the calculation pass can become unpredictable.</span></span> <span data-ttu-id="4c236-135">Por ejemplo, el cálculo de un miembro calculado recibe un valor de orden de resolución que es menor que el valor de la fórmula de resumen personalizado predeterminado de -5119.</span><span class="sxs-lookup"><span data-stu-id="4c236-135">For example, the calculation for a calculated member receives a solve order value that is lower than the default custom rollup formula value of -5119.</span></span> <span data-ttu-id="4c236-136">Dicho valor de orden de resolución bajo produce los miembros calculados que se van a calcular antes de las fórmulas de resumen personalizadas y puede generar resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="4c236-136">Such a low solve order value causes the calculated members to be calculated before the custom rollup formulas, and can produce incorrect results.</span></span>  
  
### <a name="creating-and-changing-solve-order"></a><span data-ttu-id="4c236-137">Crear y cambiar el orden de resolución</span><span class="sxs-lookup"><span data-stu-id="4c236-137">Creating and Changing Solve Order</span></span>  
 <span data-ttu-id="4c236-138">En el Diseñador de cubos, en el panel **Cálculos**, puede cambiar el orden de resolución de miembros calculados y celdas calculadas si cambia el orden de los cálculos.</span><span class="sxs-lookup"><span data-stu-id="4c236-138">In Cube Designer, on the **Calculations Pane**, you can change the solve order for calculated members and calculated cells by changing the order of the calculations.</span></span>  
  
 <span data-ttu-id="4c236-139">En MDX, puede utilizar la palabra clave `SOLVE_ORDER` para crear o cambiar miembros calculados y celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="4c236-139">In MDX, you can use the `SOLVE_ORDER` keyword to create or change calculated members and calculated cells.</span></span>  
  
## <a name="solve-order-examples"></a><span data-ttu-id="4c236-140">Ejemplos de orden de resolución</span><span class="sxs-lookup"><span data-stu-id="4c236-140">Solve Order Examples</span></span>  
 <span data-ttu-id="4c236-141">Para ilustrar las posibles complejidades del orden de resolución, la siguiente serie de consultas MDX comienza con dos consultas que no presentan individualmente problemas de orden de resolución.</span><span class="sxs-lookup"><span data-stu-id="4c236-141">To illustrate the potential complexities of solve order, the following series of MDX queries starts with two queries that each individually have no solve order issues.</span></span> <span data-ttu-id="4c236-142">Estas dos consultas se combinan en una consulta que requiere un orden de resolución.</span><span class="sxs-lookup"><span data-stu-id="4c236-142">These two queries are then combined into a query that requires solve order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c236-143">Puede ejecutar estas consultas MDX con la base de datos multidimensional de ejemplo de Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="4c236-143">You can run these MDX queries against the Adventure Works sample multidimensional database.</span></span> <span data-ttu-id="4c236-144">Puede descargar el ejemplo de [modelos multidimensionales AdventureWorks SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) del sitio de codeplex.</span><span class="sxs-lookup"><span data-stu-id="4c236-144">You can download the [AdventureWorks Multidimensional Models SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) sample from the codeplex site.</span></span>  
  
### <a name="query-1-differences-in-income-and-expenses"></a><span data-ttu-id="4c236-145">Consulta 1: diferencias en ingresos y gastos</span><span class="sxs-lookup"><span data-stu-id="4c236-145">Query 1-Differences in Income and Expenses</span></span>  
 <span data-ttu-id="4c236-146">En la primera consulta MDX, calcule la diferencia de ventas y costos de cada año creando una consulta MDX simple similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c236-146">For the first MDX query, calculate the difference in sales and costs for each year by constructing a simple MDX query similar to the following example:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] )  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="4c236-147">En esta consulta, solo existe un miembro calculado: `Year Difference`.</span><span class="sxs-lookup"><span data-stu-id="4c236-147">In this query, there is only one calculated member, `Year Difference`.</span></span> <span data-ttu-id="4c236-148">Dado que solo existe un miembro calculado, el orden de resolución no supone un problema mientras el cubo no utilice miembros calculados.</span><span class="sxs-lookup"><span data-stu-id="4c236-148">Because there is only one calculated member, solve order is not an issue, as long as the cube does not use any calculated members.</span></span>  
  
 <span data-ttu-id="4c236-149">Esta consulta MDX ofrece un conjunto de resultados similar a la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="4c236-149">This MDX query produces a result set similar to the following table.</span></span>  
  
||<span data-ttu-id="4c236-150">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="4c236-150">Internet Sales Amount</span></span>|<span data-ttu-id="4c236-151">Costo total del producto por Internet</span><span class="sxs-lookup"><span data-stu-id="4c236-151">Internet Total Product Cost</span></span>|  
|-|---------------------------|---------------------------------|  
|<span data-ttu-id="4c236-152">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="4c236-152">**CY 2007**</span></span>|<span data-ttu-id="4c236-153">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="4c236-153">$9,791,060.30</span></span>|<span data-ttu-id="4c236-154">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="4c236-154">$5,718,327.17</span></span>|  
|<span data-ttu-id="4c236-155">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="4c236-155">**CY 2008**</span></span>|<span data-ttu-id="4c236-156">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="4c236-156">$9,770,899.74</span></span>|<span data-ttu-id="4c236-157">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="4c236-157">$5,721,205.24</span></span>|  
|<span data-ttu-id="4c236-158">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="4c236-158">**Year Difference**</span></span>|<span data-ttu-id="4c236-159">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="4c236-159">($20,160.56)</span></span>|<span data-ttu-id="4c236-160">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="4c236-160">$2,878.06</span></span>|  
  
### <a name="query-2-percentage-of-income-after-expenses"></a><span data-ttu-id="4c236-161">Consulta 2: porcentaje de ingresos después de gastos</span><span class="sxs-lookup"><span data-stu-id="4c236-161">Query 2-Percentage of Income after Expenses</span></span>  
 <span data-ttu-id="4c236-162">En la segunda consulta, calcule el porcentaje de ingresos después de gastos para cada año con la siguiente consulta MDX:</span><span class="sxs-lookup"><span data-stu-id="4c236-162">For the second query, calculate the percentage of income after expenses for each year using the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Measures].[Profit Margin] AS   
([Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent"  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="4c236-163">En esta consulta MDX, al igual que en la anterior, solo existe un miembro calculado, `Profit Margin`, por lo que no se producen complicaciones por el orden de resolución.</span><span class="sxs-lookup"><span data-stu-id="4c236-163">This MDX query, like the previous one, has only a single calculated member, `Profit Margin`, and therefore does not have any solve order complications.</span></span>  
  
 <span data-ttu-id="4c236-164">Esta consulta MDX ofrece un conjunto de resultados similar a la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="4c236-164">This MDX query produces a slightly different result set, similar to the following table.</span></span>  
  
||<span data-ttu-id="4c236-165">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="4c236-165">Internet Sales Amount</span></span>|<span data-ttu-id="4c236-166">Costo total del producto por Internet</span><span class="sxs-lookup"><span data-stu-id="4c236-166">Internet Total Product Cost</span></span>|<span data-ttu-id="4c236-167">Margen de beneficio</span><span class="sxs-lookup"><span data-stu-id="4c236-167">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="4c236-168">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="4c236-168">**CY 2007**</span></span>|<span data-ttu-id="4c236-169">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="4c236-169">$9,791,060.30</span></span>|<span data-ttu-id="4c236-170">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="4c236-170">$5,718,327.17</span></span>|<span data-ttu-id="4c236-171">41.60 %</span><span class="sxs-lookup"><span data-stu-id="4c236-171">41.60%</span></span>|  
|<span data-ttu-id="4c236-172">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="4c236-172">**CY 2008**</span></span>|<span data-ttu-id="4c236-173">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="4c236-173">$9,770,899.74</span></span>|<span data-ttu-id="4c236-174">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="4c236-174">$5,721,205.24</span></span>|<span data-ttu-id="4c236-175">41.45 %</span><span class="sxs-lookup"><span data-stu-id="4c236-175">41.45%</span></span>|  
  
 <span data-ttu-id="4c236-176">La diferencia de los conjuntos de resultados entre la primera y la segunda consulta radica en la distinta colocación del miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="4c236-176">The difference in result sets between the first query and the second query comes from the difference in placement of the calculated member.</span></span> <span data-ttu-id="4c236-177">En la primera consulta, el miembro calculado se encuentra en el eje ROWS, mientras que en la segunda consulta se encuentra en el eje COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="4c236-177">In the first query, the calculated member is part of the ROWS axis, not the COLUMNS axis shown in the second query.</span></span> <span data-ttu-id="4c236-178">Esta distinta colocación adquiere importancia en la siguiente consulta, en la que se combinan dos miembros calculados en una única consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="4c236-178">This difference in placement becomes important in the next query, which combines the two calculated members in a single MDX query.</span></span>  
  
### <a name="query-3-combined-year-difference-and-net-income-calculations"></a><span data-ttu-id="4c236-179">Consulta 3: diferencia de año combinada y cálculos de ingresos netos</span><span class="sxs-lookup"><span data-stu-id="4c236-179">Query 3-Combined Year Difference and Net Income Calculations</span></span>  
 <span data-ttu-id="4c236-180">En esta consulta final que combina los dos ejemplos previos en una sola consulta MDX, el orden de resolución es importante debido a los cálculos de ambas columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="4c236-180">In this final query combining both of the previous examples into a single MDX query, solve order becomes important because of the calculations on both columns and rows.</span></span> <span data-ttu-id="4c236-181">Para asegurarse de que los cálculos se realizan en la secuencia correcta, defina la secuencia en la que se realizan los cálculos con la palabra clave `SOLVE_ORDER`.</span><span class="sxs-lookup"><span data-stu-id="4c236-181">To make sure that the calculations occur in the correct sequence, define the sequence in which the calculations occur by using the `SOLVE_ORDER` keyword.</span></span>  
  
 <span data-ttu-id="4c236-182">La palabra clave `SOLVE_ORDER` especifica el orden de resolución de los miembros calculados en una consulta MDX o en un comando `CREATE MEMBER`.</span><span class="sxs-lookup"><span data-stu-id="4c236-182">The `SOLVE_ORDER` keyword specifies the solve order of calculated members in an MDX query or a `CREATE MEMBER` command.</span></span> <span data-ttu-id="4c236-183">Los valores de entero utilizados con la palabra clave `SOLVE_ORDER` son relativos, no necesitan comenzar en cero y no tienen que ser consecutivos.</span><span class="sxs-lookup"><span data-stu-id="4c236-183">The integer values used with the `SOLVE_ORDER` keyword are relative, do not need to start at zero, and do not need to be consecutive.</span></span> <span data-ttu-id="4c236-184">El valor ordena a MDX calcular un miembro según los valores resultantes del cálculo de miembros con un valor superior.</span><span class="sxs-lookup"><span data-stu-id="4c236-184">The value simply tells MDX to calculate a member based on values derived from calculating members with a higher value.</span></span> <span data-ttu-id="4c236-185">Si se define un miembro calculado sin la palabra clave `SOLVE_ORDER`, su valor predeterminado es cero.</span><span class="sxs-lookup"><span data-stu-id="4c236-185">If a calculated member is defined without the `SOLVE_ORDER` keyword, the default value of that calculated member is zero.</span></span>  
  
 <span data-ttu-id="4c236-186">Por ejemplo, si combina los cálculos utilizados en las dos primeras consultas de ejemplo, la intersección de los dos miembros calculados, `Year Difference` y `Profit Margin`, se produce en una única celda en el conjunto de datos de resultados del ejemplo de consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="4c236-186">For example, if you combine the calculations used in the first two example queries, the two calculated members, `Year Difference` and `Profit Margin`, intersect at a single cell in the result dataset of the MDX query example.</span></span> <span data-ttu-id="4c236-187">La única manera de determinar cómo [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluará esta celda es mediante el orden de resolución.</span><span class="sxs-lookup"><span data-stu-id="4c236-187">The only way to determine how [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] will evaluate this cell is by the solve order.</span></span> <span data-ttu-id="4c236-188">Las fórmulas utilizadas para crear esta celda ofrecerán resultados diferentes según del orden de resolución de los dos miembros calculados.</span><span class="sxs-lookup"><span data-stu-id="4c236-188">The formulas that are used to construct this cell will produce different results depending upon the solve order of the two calculated members.</span></span>  
  
 <span data-ttu-id="4c236-189">En primer lugar, intente combinar los cálculos utilizados en las dos primeras consultas en la siguiente consulta MDX:</span><span class="sxs-lookup"><span data-stu-id="4c236-189">First, try combining the calculations used in the first two queries in the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 1  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 2  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="4c236-190">En este ejemplo combinado de consulta MDX, `Profit Margin` posee el orden de resolución superior, por lo que tendrá prioridad si interactúan las dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="4c236-190">In this combined MDX query example, `Profit Margin` has the highest solve order, so it takes precedence when the two expressions interact.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="4c236-191">evalúa dicha celda mediante la fórmula `Profit Margin` .</span><span class="sxs-lookup"><span data-stu-id="4c236-191">evaluates the cell in question by using the `Profit Margin` formula.</span></span> <span data-ttu-id="4c236-192">Los resultados de este cálculo anidado pueden verse en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="4c236-192">The results of this nested calculation, as shown in the following table.</span></span>  
  
||<span data-ttu-id="4c236-193">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="4c236-193">Internet Sales Amount</span></span>|<span data-ttu-id="4c236-194">Costo total del producto por Internet</span><span class="sxs-lookup"><span data-stu-id="4c236-194">Internet Total Product Cost</span></span>|<span data-ttu-id="4c236-195">Margen de beneficio</span><span class="sxs-lookup"><span data-stu-id="4c236-195">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="4c236-196">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="4c236-196">**CY 2007**</span></span>|<span data-ttu-id="4c236-197">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="4c236-197">$9,791,060.30</span></span>|<span data-ttu-id="4c236-198">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="4c236-198">$5,718,327.17</span></span>|<span data-ttu-id="4c236-199">41.60 %</span><span class="sxs-lookup"><span data-stu-id="4c236-199">41.60%</span></span>|  
|<span data-ttu-id="4c236-200">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="4c236-200">**CY 2008**</span></span>|<span data-ttu-id="4c236-201">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="4c236-201">$9,770,899.74</span></span>|<span data-ttu-id="4c236-202">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="4c236-202">$5,721,205.24</span></span>|<span data-ttu-id="4c236-203">41.45 %</span><span class="sxs-lookup"><span data-stu-id="4c236-203">41.45%</span></span>|  
|<span data-ttu-id="4c236-204">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="4c236-204">**Year Difference**</span></span>|<span data-ttu-id="4c236-205">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="4c236-205">($20,160.56)</span></span>|<span data-ttu-id="4c236-206">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="4c236-206">$2,878.06</span></span>|<span data-ttu-id="4c236-207">114.28 %</span><span class="sxs-lookup"><span data-stu-id="4c236-207">114.28%</span></span>|  
  
 <span data-ttu-id="4c236-208">El resultado de la celda compartida se basa en la fórmula para `Profit Margin`.</span><span class="sxs-lookup"><span data-stu-id="4c236-208">The result in the shared cell is based on the formula for `Profit Margin`.</span></span> <span data-ttu-id="4c236-209">Es decir, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calcula el resultado en la celda compartida con los datos de `Year Difference` y ofrece la siguiente fórmula (se ha redondeado el resultado para obtener mayor claridad):</span><span class="sxs-lookup"><span data-stu-id="4c236-209">That is, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell with the `Year Difference` data, producing the following formula (the result is rounded for clarity):</span></span>  
  
```  
((9,770,899.74 - 9,791,060.30) - (5,721,205.24 - 5,718,327.17)) / (9,770,899.74 - 9,791,060.30) = 1.14275744   
```  
  
 <span data-ttu-id="4c236-210">or</span><span class="sxs-lookup"><span data-stu-id="4c236-210">or</span></span>  
  
```  
(23,038.63) / (20,160.56) = 114.28%  
```  
  
 <span data-ttu-id="4c236-211">Esto es a todas luces incorrecto.</span><span class="sxs-lookup"><span data-stu-id="4c236-211">This is clearly incorrect.</span></span> <span data-ttu-id="4c236-212">Sin embargo, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calcula el resultado en una celda compartida de distinto modo si cambia el orden de resolución de los miembros calculados en la consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="4c236-212">However, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell differently if you switch the solve orders for the calculated members in the MDX query.</span></span> <span data-ttu-id="4c236-213">La siguiente consulta MDX combinada invierte el orden de resolución de los miembros calculados:</span><span class="sxs-lookup"><span data-stu-id="4c236-213">The following combined MDX query reverses the solve order for the calculated members:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 2  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 1  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="4c236-214">Como se ha cambiado el orden de los miembros calculados, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] utiliza la fórmula `Year Difference` para evaluar la celda, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="4c236-214">As the order of the calculated members has been switched, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the `Year Difference` formula to evaluate the cell, as shown in the following table.</span></span>  
  
||<span data-ttu-id="4c236-215">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="4c236-215">Internet Sales Amount</span></span>|<span data-ttu-id="4c236-216">Costo total del producto por Internet</span><span class="sxs-lookup"><span data-stu-id="4c236-216">Internet Total Product Cost</span></span>|<span data-ttu-id="4c236-217">Margen de beneficio</span><span class="sxs-lookup"><span data-stu-id="4c236-217">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="4c236-218">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="4c236-218">**CY 2007**</span></span>|<span data-ttu-id="4c236-219">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="4c236-219">$9,791,060.30</span></span>|<span data-ttu-id="4c236-220">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="4c236-220">$5,718,327.17</span></span>|<span data-ttu-id="4c236-221">41.60 %</span><span class="sxs-lookup"><span data-stu-id="4c236-221">41.60%</span></span>|  
|<span data-ttu-id="4c236-222">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="4c236-222">**CY 2008**</span></span>|<span data-ttu-id="4c236-223">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="4c236-223">$9,770,899.74</span></span>|<span data-ttu-id="4c236-224">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="4c236-224">$5,721,205.24</span></span>|<span data-ttu-id="4c236-225">41.45 %</span><span class="sxs-lookup"><span data-stu-id="4c236-225">41.45%</span></span>|  
|<span data-ttu-id="4c236-226">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="4c236-226">**Year Difference**</span></span>|<span data-ttu-id="4c236-227">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="4c236-227">($20,160.56)</span></span>|<span data-ttu-id="4c236-228">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="4c236-228">$2,878.06</span></span>|<span data-ttu-id="4c236-229">(0.15 %</span><span class="sxs-lookup"><span data-stu-id="4c236-229">(0.15%)</span></span>|  
  
 <span data-ttu-id="4c236-230">Puesto que la consulta utiliza la fórmula `Year Difference` con los datos de `Profit Margin` , la fórmula de la celda compartida es similar al siguiente cálculo:</span><span class="sxs-lookup"><span data-stu-id="4c236-230">Because this query uses the `Year Difference` formula with the `Profit Margin` data, the formula for the shared cell resembles the following calculation:</span></span>  
  
```  
(($9,770,899.74 - 5,721,205.24) / $9,770,899.74) - ((9,791,060.30 - 5,718,327.17) / 9,791,060.30) = -0.15   
```  
  
 <span data-ttu-id="4c236-231">Or</span><span class="sxs-lookup"><span data-stu-id="4c236-231">Or</span></span>  
  
```  
0.4145 - 0.4160= -0.15  
```  
  
## <a name="additional-considerations"></a><span data-ttu-id="4c236-232">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="4c236-232">Additional Considerations</span></span>  
 <span data-ttu-id="4c236-233">El orden de resolución puede ser un aspecto muy complicado, especialmente en cubos con un gran número de dimensiones que tienen miembros calculados, fórmulas de resúmenes personalizados o celdas calculadas.</span><span class="sxs-lookup"><span data-stu-id="4c236-233">Solve order can be a very complex issue to deal with, especially in cubes with a high number of dimensions involving calculated member, custom rollup formulas, or calculated cells.</span></span> <span data-ttu-id="4c236-234">Cuando [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evalúa una consulta MDX, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] tiene en cuenta los valores del orden de resolución de todos los elementos implicados en un paso determinado, incluidas las dimensiones del cubo especificado en la consulta MDX.</span><span class="sxs-lookup"><span data-stu-id="4c236-234">When [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates an MDX query, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] takes into account the solve order values for everything involved within a given pass, including the dimensions of the cube specified in the MDX query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c236-235">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c236-235">See Also</span></span>  
 <span data-ttu-id="4c236-236">[&#41;CalculationCurrentPass &#40;MDX](/sql/mdx/calculationcurrentpass-mdx) </span><span class="sxs-lookup"><span data-stu-id="4c236-236">[CalculationCurrentPass &#40;MDX&#41;](/sql/mdx/calculationcurrentpass-mdx) </span></span>  
 <span data-ttu-id="4c236-237">[&#41;CalculationPassValue &#40;MDX](/sql/mdx/calculationpassvalue-mdx) </span><span class="sxs-lookup"><span data-stu-id="4c236-237">[CalculationPassValue &#40;MDX&#41;](/sql/mdx/calculationpassvalue-mdx) </span></span>  
 <span data-ttu-id="4c236-238">[Instrucción CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="4c236-238">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 [<span data-ttu-id="4c236-239">Manipular datos &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="4c236-239">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
