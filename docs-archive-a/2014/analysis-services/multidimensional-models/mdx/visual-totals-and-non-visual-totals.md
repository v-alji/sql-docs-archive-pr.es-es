---
title: Totales visuales y totales no visuales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ea9d02f2-a668-4547-ade5-e3d077a2e1bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ddff047be6a819d05276848cbeb430fb8e4c9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748324"
---
# <a name="visual-totals-and-non-visual-totals"></a><span data-ttu-id="41c59-102">Totales visuales y totales no visuales</span><span class="sxs-lookup"><span data-stu-id="41c59-102">Visual Totals and Non Visual Totals</span></span>
  <span data-ttu-id="41c59-103">Los totales visuales son totales que se encuentran al final de una columna o fila que suman todos los elementos visibles de la columna o fila.</span><span class="sxs-lookup"><span data-stu-id="41c59-103">Visual Totals are totals at the end of a column or row that add up all of the items visible in the column or row.</span></span> <span data-ttu-id="41c59-104">Este es el comportamiento predeterminado de la mayoría de las tablas cuando se muestran.</span><span class="sxs-lookup"><span data-stu-id="41c59-104">This is the default behavior for most tables when displayed.</span></span> <span data-ttu-id="41c59-105">Sin embargo, a veces el usuario desea mostrar solo ciertas columnas de una tabla manteniendo los totales de toda la fila, incluidos los que no se muestran y que</span><span class="sxs-lookup"><span data-stu-id="41c59-105">However, there are times when the user wants to display only certain columns in a table but keep the totals for the entire row, including those that are not displayed.</span></span> <span data-ttu-id="41c59-106">se denominan `Non Visual Totals`, porque el total proviene de los valores tanto visibles como no visibles.</span><span class="sxs-lookup"><span data-stu-id="41c59-106">These are called `Non Visual Totals`, because the total comes from both the visible and non-visible values.</span></span>  
  
 <span data-ttu-id="41c59-107">En el siguiente escenario se muestra el comportamiento de los totales no visuales.</span><span class="sxs-lookup"><span data-stu-id="41c59-107">The following scenario demonstrates the behavior of Non Visual totals.</span></span> <span data-ttu-id="41c59-108">El primer paso muestra el comportamiento predeterminado de los totales visuales.</span><span class="sxs-lookup"><span data-stu-id="41c59-108">The first step shows the default behavior of Visual Totals.</span></span>  
  
 <span data-ttu-id="41c59-109">El ejemplo siguiente es una consulta de [Adventure Works] para obtener las cifras de [Reseller Sales Amount] en una tabla donde las categorías de producto son las columnas y los tipos comerciales de revendedor son las filas.</span><span class="sxs-lookup"><span data-stu-id="41c59-109">The following example is a query of [Adventure Works] to obtain [Reseller Sales Amount] figures in a table where the product categories are the columns and the reseller business types are the rows.</span></span> <span data-ttu-id="41c59-110">Observe que esos totales se dan tanto para productos como para revendedores cuando se emite la siguiente instrucción SELECT:</span><span class="sxs-lookup"><span data-stu-id="41c59-110">Note that totals are given for both products and resellers when the following SELECT statement is issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="41c59-111">Produce los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="41c59-111">Produces the following results:</span></span>  
  
|||||||  
|-|-|-|-|-|-|  
||<span data-ttu-id="41c59-112">**Todos los productos**</span><span class="sxs-lookup"><span data-stu-id="41c59-112">**All Products**</span></span>|<span data-ttu-id="41c59-113">**Accesorios**</span><span class="sxs-lookup"><span data-stu-id="41c59-113">**Accessories**</span></span>|<span data-ttu-id="41c59-114">**Bicicletas**</span><span class="sxs-lookup"><span data-stu-id="41c59-114">**Bikes**</span></span>|<span data-ttu-id="41c59-115">**Ropa**</span><span class="sxs-lookup"><span data-stu-id="41c59-115">**Clothing**</span></span>|<span data-ttu-id="41c59-116">**Componentes**</span><span class="sxs-lookup"><span data-stu-id="41c59-116">**Components**</span></span>|  
|<span data-ttu-id="41c59-117">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="41c59-117">**All Resellers**</span></span>|<span data-ttu-id="41c59-118">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="41c59-118">**$80,450,596.98**</span></span>|<span data-ttu-id="41c59-119">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="41c59-119">**$571,297.93**</span></span>|<span data-ttu-id="41c59-120">**$66,302,381.56**</span><span class="sxs-lookup"><span data-stu-id="41c59-120">**$66,302,381.56**</span></span>|<span data-ttu-id="41c59-121">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="41c59-121">**$1,777,840.84**</span></span>|<span data-ttu-id="41c59-122">**$11,799,076.66**</span><span class="sxs-lookup"><span data-stu-id="41c59-122">**$11,799,076.66**</span></span>|  
|<span data-ttu-id="41c59-123">**Specialty Bike Shop**</span><span class="sxs-lookup"><span data-stu-id="41c59-123">**Specialty Bike Shop**</span></span>|<span data-ttu-id="41c59-124">**$6,756,166.18**</span><span class="sxs-lookup"><span data-stu-id="41c59-124">**$6,756,166.18**</span></span>|<span data-ttu-id="41c59-125">**$65,125.48**</span><span class="sxs-lookup"><span data-stu-id="41c59-125">**$65,125.48**</span></span>|<span data-ttu-id="41c59-126">**$6,080,117.73**</span><span class="sxs-lookup"><span data-stu-id="41c59-126">**$6,080,117.73**</span></span>|<span data-ttu-id="41c59-127">**$252,933.91**</span><span class="sxs-lookup"><span data-stu-id="41c59-127">**$252,933.91**</span></span>|<span data-ttu-id="41c59-128">**$357,989.07**</span><span class="sxs-lookup"><span data-stu-id="41c59-128">**$357,989.07**</span></span>|  
|<span data-ttu-id="41c59-129">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="41c59-129">**Value Added Reseller**</span></span>|<span data-ttu-id="41c59-130">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="41c59-130">**$34,967,517.33**</span></span>|<span data-ttu-id="41c59-131">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="41c59-131">**$175,002.81**</span></span>|<span data-ttu-id="41c59-132">**$30,892,354.33**</span><span class="sxs-lookup"><span data-stu-id="41c59-132">**$30,892,354.33**</span></span>|<span data-ttu-id="41c59-133">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="41c59-133">**$592,385.71**</span></span>|<span data-ttu-id="41c59-134">**$3,307,774.48**</span><span class="sxs-lookup"><span data-stu-id="41c59-134">**$3,307,774.48**</span></span>|  
|<span data-ttu-id="41c59-135">**Almacén**</span><span class="sxs-lookup"><span data-stu-id="41c59-135">**Warehouse**</span></span>|<span data-ttu-id="41c59-136">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="41c59-136">**$38,726,913.48**</span></span>|<span data-ttu-id="41c59-137">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="41c59-137">**$331,169.64**</span></span>|<span data-ttu-id="41c59-138">**$29,329,909.50**</span><span class="sxs-lookup"><span data-stu-id="41c59-138">**$29,329,909.50**</span></span>|<span data-ttu-id="41c59-139">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="41c59-139">**$932,521.23**</span></span>|<span data-ttu-id="41c59-140">**$8,133,313.11**</span><span class="sxs-lookup"><span data-stu-id="41c59-140">**$8,133,313.11**</span></span>|  
  
## <a name="non-visual-on-rows-and-columns"></a><span data-ttu-id="41c59-141">Filas y columnas no visuales</span><span class="sxs-lookup"><span data-stu-id="41c59-141">Non-Visual on rows and columns</span></span>  
 <span data-ttu-id="41c59-142">Para generar una tabla con datos solo para los productos Accessories y Clothing, y los revendedores Value Added Reseller y Warehouse, manteniendo todavía los totales globales, se podría escribir de la forma siguiente usando NON VISUAL:</span><span class="sxs-lookup"><span data-stu-id="41c59-142">To produce a table with data only for the Accessories and Clothing products, the Value Added Reseller and Warehouse resellers, yet keeping the overall totals could be written as follows using NON VISUAL:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works])`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="41c59-143">Produce los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="41c59-143">Produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="41c59-144">**Todos los productos**</span><span class="sxs-lookup"><span data-stu-id="41c59-144">**All Products**</span></span>|<span data-ttu-id="41c59-145">**Accesorios**</span><span class="sxs-lookup"><span data-stu-id="41c59-145">**Accessories**</span></span>|<span data-ttu-id="41c59-146">**Ropa**</span><span class="sxs-lookup"><span data-stu-id="41c59-146">**Clothing**</span></span>|  
|<span data-ttu-id="41c59-147">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="41c59-147">**All Resellers**</span></span>|<span data-ttu-id="41c59-148">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="41c59-148">**$80,450,596.98**</span></span>|<span data-ttu-id="41c59-149">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="41c59-149">**$571,297.93**</span></span>|<span data-ttu-id="41c59-150">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="41c59-150">**$1,777,840.84**</span></span>|  
|<span data-ttu-id="41c59-151">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="41c59-151">**Value Added Reseller**</span></span>|<span data-ttu-id="41c59-152">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="41c59-152">**$34,967,517.33**</span></span>|<span data-ttu-id="41c59-153">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="41c59-153">**$175,002.81**</span></span>|<span data-ttu-id="41c59-154">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="41c59-154">**$592,385.71**</span></span>|  
|<span data-ttu-id="41c59-155">**Almacén**</span><span class="sxs-lookup"><span data-stu-id="41c59-155">**Warehouse**</span></span>|<span data-ttu-id="41c59-156">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="41c59-156">**$38,726,913.48**</span></span>|<span data-ttu-id="41c59-157">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="41c59-157">**$331,169.64**</span></span>|<span data-ttu-id="41c59-158">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="41c59-158">**$932,521.23**</span></span>|  
  
## <a name="non-visual-on-rows"></a><span data-ttu-id="41c59-159">Filas no visuales</span><span class="sxs-lookup"><span data-stu-id="41c59-159">Non-Visual on rows</span></span>  
 <span data-ttu-id="41c59-160">Para generar una tabla que sume visualmente las columnas pero que tome el total real de todos [Category] para los totales de las filas, debe emitirse la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="41c59-160">To produce a table that visually totals the columns but for row totals brings the true total of all [Category], the following query should be issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0`  
  
 `from ( Select {[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 0`  
  
 `from [Adventure Works])`  
  
 `)`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="41c59-161">Observe cómo NON VISUAL se aplica solamente a [Category].</span><span class="sxs-lookup"><span data-stu-id="41c59-161">Note how NON VISUAL is only applied to [Category].</span></span>  
  
 <span data-ttu-id="41c59-162">La consulta anterior genera los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="41c59-162">The above query produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="41c59-163">All Products</span><span class="sxs-lookup"><span data-stu-id="41c59-163">All Products</span></span>|<span data-ttu-id="41c59-164">Accesorios</span><span class="sxs-lookup"><span data-stu-id="41c59-164">Accessories</span></span>|<span data-ttu-id="41c59-165">Ropa</span><span class="sxs-lookup"><span data-stu-id="41c59-165">Clothing</span></span>|  
|<span data-ttu-id="41c59-166">All Resellers</span><span class="sxs-lookup"><span data-stu-id="41c59-166">All Resellers</span></span>|<span data-ttu-id="41c59-167">$73,694,430.80</span><span class="sxs-lookup"><span data-stu-id="41c59-167">$73,694,430.80</span></span>|<span data-ttu-id="41c59-168">$506,172.45</span><span class="sxs-lookup"><span data-stu-id="41c59-168">$506,172.45</span></span>|<span data-ttu-id="41c59-169">$1,524,906.93</span><span class="sxs-lookup"><span data-stu-id="41c59-169">$1,524,906.93</span></span>|  
|<span data-ttu-id="41c59-170">Value Added Reseller</span><span class="sxs-lookup"><span data-stu-id="41c59-170">Value Added Reseller</span></span>|<span data-ttu-id="41c59-171">$34,967,517.33</span><span class="sxs-lookup"><span data-stu-id="41c59-171">$34,967,517.33</span></span>|<span data-ttu-id="41c59-172">$175,002.81</span><span class="sxs-lookup"><span data-stu-id="41c59-172">$175,002.81</span></span>|<span data-ttu-id="41c59-173">$592,385.71</span><span class="sxs-lookup"><span data-stu-id="41c59-173">$592,385.71</span></span>|  
|<span data-ttu-id="41c59-174">Warehouse</span><span class="sxs-lookup"><span data-stu-id="41c59-174">Warehouse</span></span>|<span data-ttu-id="41c59-175">$38,726,913.48</span><span class="sxs-lookup"><span data-stu-id="41c59-175">$38,726,913.48</span></span>|<span data-ttu-id="41c59-176">$331,169.64</span><span class="sxs-lookup"><span data-stu-id="41c59-176">$331,169.64</span></span>|<span data-ttu-id="41c59-177">$932,521.23</span><span class="sxs-lookup"><span data-stu-id="41c59-177">$932,521.23</span></span>|  
  
 <span data-ttu-id="41c59-178">Al comparar con los resultados anteriores, puede observar que la fila [All Resellers] suma ahora hasta los valores mostrados para [Value Added Reseller] y [Warehouse], pero que la columna [All Products] muestra el valor total de todos los productos, incluso los que no se muestran.</span><span class="sxs-lookup"><span data-stu-id="41c59-178">When compared with the previous results, you can observe that the [All Resellers] row now adds up to the displayed values for [Value Added Reseller] and [Warehouse] but that the [All Products] column shows the total value for all products, including those not displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c59-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41c59-179">See Also</span></span>  
 <span data-ttu-id="41c59-180">[Conceptos clave de &#40;MDX Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="41c59-180">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="41c59-181">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="41c59-181">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="41c59-182">[Trabajar con miembros, tuplas y conjuntos &#40;&#41;MDX](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="41c59-182">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="41c59-183">[Aspectos básicos de las consultas MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="41c59-183">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="41c59-184">[Consulta MDX básica &#40;MDX&#41;](mdx-query-the-basic-query.md) </span><span class="sxs-lookup"><span data-stu-id="41c59-184">[The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md) </span></span>  
 <span data-ttu-id="41c59-185">[Restringir la consulta con ejes de consulta y segmentador &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span><span class="sxs-lookup"><span data-stu-id="41c59-185">[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span></span>  
 [<span data-ttu-id="41c59-186">Establecer el contexto de cubo en una consulta &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="41c59-186">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)  
  
  
