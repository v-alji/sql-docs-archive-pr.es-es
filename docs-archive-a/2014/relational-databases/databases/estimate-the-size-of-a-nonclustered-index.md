---
title: Estimar el tamaño de un índice no agrupado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: c183b0e4-ef4c-4bfc-8575-5ac219c25b0a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 097c0e5568ba17b12f83d09e347eb3bf8b0bd7da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748122"
---
# <a name="estimate-the-size-of-a-nonclustered-index"></a><span data-ttu-id="68351-102">Estimar el tamaño de un índice no clúster</span><span class="sxs-lookup"><span data-stu-id="68351-102">Estimate the Size of a Nonclustered Index</span></span>
  <span data-ttu-id="68351-103">Siga estos pasos para estimar el espacio necesario para almacenar un índice no clúster:</span><span class="sxs-lookup"><span data-stu-id="68351-103">Follow these steps to estimate the amount of space that is required to store a nonclustered index:</span></span>  
  
1.  <span data-ttu-id="68351-104">Calcular las variables que deben usarse en los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="68351-104">Calculate variables for use in steps 2 and 3.</span></span>  
  
2.  <span data-ttu-id="68351-105">Calcular el espacio utilizado para almacenar información del índice en el nivel hoja del índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="68351-105">Calculate the space used to store index information in the leaf level of the nonclustered index.</span></span>  
  
3.  <span data-ttu-id="68351-106">Calcular el espacio utilizado para almacenar información del índice en los niveles no hoja del índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="68351-106">Calculate the space used to store index information in the non-leaf levels of the nonclustered index.</span></span>  
  
4.  <span data-ttu-id="68351-107">Sumar los valores calculados.</span><span class="sxs-lookup"><span data-stu-id="68351-107">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-variables-for-use-in-steps-2-and-3"></a><span data-ttu-id="68351-108">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="68351-108">Step 1.</span></span> <span data-ttu-id="68351-109">Calcularlas variables que deben usarse en los pasos 2 y 3</span><span class="sxs-lookup"><span data-stu-id="68351-109">Calculate Variables for Use in Steps 2 and 3</span></span>  
 <span data-ttu-id="68351-110">Los siguientes pasos pueden utilizarse para calcular las variables que se utilizan para estimar el espacio necesario para almacenar los niveles superiores del índice:</span><span class="sxs-lookup"><span data-stu-id="68351-110">You can use the following steps to calculate variables that are used to estimate the amount of space that is required to store the upper levels of the index.</span></span>  
  
1.  <span data-ttu-id="68351-111">Especifique el número de filas que habrá en la tabla:</span><span class="sxs-lookup"><span data-stu-id="68351-111">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="68351-112">***Num_Rows***  = número de filas de la tabla</span><span class="sxs-lookup"><span data-stu-id="68351-112">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="68351-113">Especifique el número de columnas de longitud fija y variable de la clave de índice, y calcule el espacio necesario para su almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="68351-113">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="68351-114">Las columnas de clave de un índice pueden incluir columnas de longitud fija y de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="68351-114">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="68351-115">Para estimar el tamaño de las filas de índice de nivel interior, calcule el espacio que ocupa cada uno de estos grupos de columnas en la fila de índice.</span><span class="sxs-lookup"><span data-stu-id="68351-115">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="68351-116">El tamaño de una columna depende del tipo y de la longitud especificados para los datos.</span><span class="sxs-lookup"><span data-stu-id="68351-116">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="68351-117">***Num_Key_Cols***  = número total de columnas de clave (de longitud fija y variable)</span><span class="sxs-lookup"><span data-stu-id="68351-117">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="68351-118">***Fixed_Key_Size***  = tamaño total en bytes de todas las columnas de clave de longitud fija</span><span class="sxs-lookup"><span data-stu-id="68351-118">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="68351-119">***Num_Variable_Key_Cols***  = número de columnas de clave de longitud variable</span><span class="sxs-lookup"><span data-stu-id="68351-119">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="68351-120">***Max_Var_Key_Size***  = tamaño máximo en bytes de todas las columnas de clave de longitud variable</span><span class="sxs-lookup"><span data-stu-id="68351-120">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
3.  <span data-ttu-id="68351-121">Tenga en cuenta el localizador de fila de datos necesario si el índice no es único:</span><span class="sxs-lookup"><span data-stu-id="68351-121">Account for the data row locator that is required if the index is nonunique:</span></span>  
  
     <span data-ttu-id="68351-122">Si el índice no clúster no es único, el localizador de fila de datos se combina con la clave de índice no clúster para generar un valor de clave único para cada fila.</span><span class="sxs-lookup"><span data-stu-id="68351-122">If the nonclustered index is nonunique, the data row locator is combined with the nonclustered index key to produce a unique key value for every row.</span></span>  
  
     <span data-ttu-id="68351-123">Si el índice no clúster se encuentra sobre un montón, el localizador de fila de datos es el RID del montón.</span><span class="sxs-lookup"><span data-stu-id="68351-123">If the nonclustered index is over a heap, the data row locator is the heap RID.</span></span> <span data-ttu-id="68351-124">Tiene un tamaño de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="68351-124">This is a size of 8 bytes.</span></span>  
  
     <span data-ttu-id="68351-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="68351-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="68351-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="68351-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="68351-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="68351-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span></span>  
  
     <span data-ttu-id="68351-128">Si el índice no clúster se encuentra sobre un índice clúster, el localizador de fila de datos es la clave de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="68351-128">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="68351-129">Las columnas que se deben combinar con la clave de índice no clúster son las columnas de la clave de agrupación en clústeres que ya no están presentes en el conjunto de columnas de clave de índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="68351-129">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="68351-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + número de columnas de clave de agrupación en clústeres no presentes en el conjunto de columnas de clave de índice no agrupado (+ 1 si el índice agrupado no es único)</span><span class="sxs-lookup"><span data-stu-id="68351-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="68351-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + tamaño total en bytes de las columnas de clave de agrupación en clústeres de longitud fija que no están presentes en el conjunto de columnas de clave de índice no agrupado</span><span class="sxs-lookup"><span data-stu-id="68351-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="68351-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + número de columnas de clave de agrupación en clústeres de longitud variable no presentes en el conjunto de columnas de clave de índice no agrupado (+ 1 si el índice agrupado no es único)</span><span class="sxs-lookup"><span data-stu-id="68351-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="68351-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + tamaño máximo en bytes de las columnas de clave de agrupación en clústeres de longitud variable no presentes en el conjunto de columnas de clave de índice no agrupado (+ 4 si el índice agrupado no es único)</span><span class="sxs-lookup"><span data-stu-id="68351-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
4.  <span data-ttu-id="68351-134">Se puede reservar parte de la fila, conocida como el mapa de bits NULL, para administrar la nulabilidad de las columnas.</span><span class="sxs-lookup"><span data-stu-id="68351-134">Part of the row, known as the null bitmap, may be reserved to manage column nullability.</span></span> <span data-ttu-id="68351-135">Calcule el tamaño:</span><span class="sxs-lookup"><span data-stu-id="68351-135">Calculate its size:</span></span>  
  
     <span data-ttu-id="68351-136">Si existen columnas que aceptan valores NULL en la clave del índice, incluidas las columnas de clave de agrupación en clústeres necesarias que se describen en el paso 1.3, se reserva parte de la fila de índice para el mapa de bits NULL.</span><span class="sxs-lookup"><span data-stu-id="68351-136">If there are nullable columns in the index key, including any necessary clustering key columns as described in Step 1.3, part of the index row is reserved for the null bitmap.</span></span>  
  
     <span data-ttu-id="68351-137">***Index_Null_Bitmap***  = 2 + ((número de columnas de la fila de índice + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="68351-137">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="68351-138">Solamente debe utilizarse la parte entera de la expresión anterior.</span><span class="sxs-lookup"><span data-stu-id="68351-138">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="68351-139">Descarte el resto.</span><span class="sxs-lookup"><span data-stu-id="68351-139">Discard any remainder.</span></span>  
  
     <span data-ttu-id="68351-140">Si no existen columnas de clave que aceptan valores NULL, establezca ***Index_Null_Bitmap*** en 0.</span><span class="sxs-lookup"><span data-stu-id="68351-140">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
5.  <span data-ttu-id="68351-141">Calcule el tamaño de los datos de longitud variable:</span><span class="sxs-lookup"><span data-stu-id="68351-141">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="68351-142">Si hay columnas de longitud variable en la clave de índice, incluidas las columnas de clave de índice clúster necesarias, determine cuánto espacio se utiliza para almacenar las columnas de la fila de índice:</span><span class="sxs-lookup"><span data-stu-id="68351-142">If there are variable-length columns in the index key, including any necessary clustered index key columns, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="68351-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="68351-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="68351-144">Los bytes agregados a ***Max_Var_Key_Size*** son para el seguimiento de cada columna de longitud variable. En esta fórmula se supone que todas las columnas de longitud variable están llenas al 100 %.</span><span class="sxs-lookup"><span data-stu-id="68351-144">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="68351-145">Si prevé que se va a usar un porcentaje inferior del espacio de almacenamiento de columnas de longitud variable, puede ajustar el valor de ***Max_Var_Key_Size*** en función de ese porcentaje para obtener una estimación más precisa del tamaño global de la tabla.</span><span class="sxs-lookup"><span data-stu-id="68351-145">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="68351-146">Si no hay columnas de longitud variable, establezca ***Variable_Key_Size*** en 0.</span><span class="sxs-lookup"><span data-stu-id="68351-146">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="68351-147">Calcule el tamaño de la fila del índice:</span><span class="sxs-lookup"><span data-stu-id="68351-147">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="68351-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (para la sobrecarga de encabezado de una fila de índice) + 6 (para el puntero de identificador de página secundaria)</span><span class="sxs-lookup"><span data-stu-id="68351-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
7.  <span data-ttu-id="68351-149">Calcule el número de filas de índice por página (8.096 bytes disponibles por página):</span><span class="sxs-lookup"><span data-stu-id="68351-149">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="68351-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="68351-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="68351-151">Dado que las filas de índice no abarcan varias páginas, el número de filas de índice por página debe redondearse hacia abajo a la fila completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="68351-151">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="68351-152">El valor 2 de la fórmula representa la entrada de la fila en la matriz de zonas de la página.</span><span class="sxs-lookup"><span data-stu-id="68351-152">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information-in-the-leaf-level"></a><span data-ttu-id="68351-153">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="68351-153">Step 2.</span></span> <span data-ttu-id="68351-154">Calcular el espacio utilizado para almacenar información del índice en el nivel hoja</span><span class="sxs-lookup"><span data-stu-id="68351-154">Calculate the Space Used to Store Index Information in the Leaf Level</span></span>  
 <span data-ttu-id="68351-155">Para estimar el espacio necesario para almacenar el nivel hoja del índice, puede utilizar los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="68351-155">You can use the following steps to estimate the amount of space that is required to store the leaf level of the index.</span></span> <span data-ttu-id="68351-156">Para completar este paso, necesita los valores del Paso 1.</span><span class="sxs-lookup"><span data-stu-id="68351-156">You will need the values preserved from Step 1 to complete this step.</span></span>  
  
1.  <span data-ttu-id="68351-157">Especifique el número de columnas de longitud fija y variable en el nivel hoja y calcule el espacio necesario para su almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="68351-157">Specify the number of fixed-length and variable-length columns at the leaf level and calculate the space that is required for their storage:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68351-158">Un índice no clúster se puede ampliar incluyendo columnas que no son de clave además de las columnas de clave de índice.</span><span class="sxs-lookup"><span data-stu-id="68351-158">You can extend a nonclustered index by including nonkey columns in addition to the index key columns.</span></span> <span data-ttu-id="68351-159">Estas columnas adicionales solamente se almacenan en el nivel hoja del índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="68351-159">These additional columns are only stored at the leaf level of the nonclustered index.</span></span> <span data-ttu-id="68351-160">Para más información, consulte [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="68351-160">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68351-161">Puede combinar las columnas `varchar`, `nvarchar`, `varbinary` o `sql_variant` que hagan que el ancho total definido para la tabla sea superior a 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="68351-161">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="68351-162">La longitud de cada una de estas columnas debe ajustarse al límite de 8.000 bytes en columnas `varchar`, `varbinary` o `sql_variant` y de 4.000 bytes en columnas `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="68351-162">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="68351-163">Sin embargo, el ancho combinado puede superar el límite de 8.060 bytes de una tabla.</span><span class="sxs-lookup"><span data-stu-id="68351-163">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span> <span data-ttu-id="68351-164">Esto también se aplica a filas de hoja de índice no clúster con columnas incluidas.</span><span class="sxs-lookup"><span data-stu-id="68351-164">This also applies to nonclustered index leaf rows that have included columns.</span></span>  
  
     <span data-ttu-id="68351-165">Si el índice no clúster no incluye columnas, utilice los valores del Paso 1, incluidas las modificaciones determinadas en el Paso 1.3:</span><span class="sxs-lookup"><span data-stu-id="68351-165">If the nonclustered index does not have any included columns, use the values from Step 1, including any modifications determined in Step 1.3:</span></span>  
  
     <span data-ttu-id="68351-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="68351-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span></span>  
  
     <span data-ttu-id="68351-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="68351-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span></span>  
  
     <span data-ttu-id="68351-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="68351-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span></span>  
  
     <span data-ttu-id="68351-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="68351-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="68351-170">Si el índice no clúster no incluye columnas, agregue los valores apropiados a los valores del Paso 1, incluidas las modificaciones del Paso 1.3.</span><span class="sxs-lookup"><span data-stu-id="68351-170">If the nonclustered index does have included columns, add the appropriate values to the values from Step 1, including any modifications in Step 1.3.</span></span> <span data-ttu-id="68351-171">El tamaño de una columna depende del tipo y de la longitud especificados para los datos.</span><span class="sxs-lookup"><span data-stu-id="68351-171">The size of a column depends on the data type and length specification.</span></span> <span data-ttu-id="68351-172">Para obtener más información, vea [Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68351-172">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
     <span data-ttu-id="68351-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + número de columnas incluidas</span><span class="sxs-lookup"><span data-stu-id="68351-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + number of included columns</span></span>  
  
     <span data-ttu-id="68351-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + tamaño total de bytes de las columnas de longitud fija incluidas</span><span class="sxs-lookup"><span data-stu-id="68351-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length included columns</span></span>  
  
     <span data-ttu-id="68351-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + número de columnas de longitud variable incluidas</span><span class="sxs-lookup"><span data-stu-id="68351-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length included columns</span></span>  
  
     <span data-ttu-id="68351-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + tamaño máximo de bytes de todas las columnas de longitud variable incluidas</span><span class="sxs-lookup"><span data-stu-id="68351-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length included columns</span></span>  
  
2.  <span data-ttu-id="68351-177">Tenga en cuenta el localizador de fila de datos:</span><span class="sxs-lookup"><span data-stu-id="68351-177">Account for the data row locator:</span></span>  
  
     <span data-ttu-id="68351-178">Si el índice no clúster no es único, la sobrecarga del localizador de fila de datos ya se ha tenido en cuenta en el Paso 1.3, por lo que no es necesario efectuar ninguna modificación adicional.</span><span class="sxs-lookup"><span data-stu-id="68351-178">If the nonclustered index is nonunique, the overhead for the data row locator has already been considered in Step 1.3 and no additional modifications are required.</span></span> <span data-ttu-id="68351-179">Vaya al paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="68351-179">Go to the next step.</span></span>  
  
     <span data-ttu-id="68351-180">Si el índice no clúster es único, el localizador de fila de datos debe tenerse en cuenta en todas las filas del nivel hoja.</span><span class="sxs-lookup"><span data-stu-id="68351-180">If the nonclustered index is unique, the data row locator must be accounted for in all rows at the leaf level.</span></span>  
  
     <span data-ttu-id="68351-181">Si el índice no clúster se encuentra sobre un montón, el localizador de fila de datos es el RID del montón (tamaño 8 bytes).</span><span class="sxs-lookup"><span data-stu-id="68351-181">If the nonclustered index is over a heap, the data row locator is the heap RID (size 8 bytes).</span></span>  
  
     <span data-ttu-id="68351-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="68351-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="68351-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="68351-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="68351-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="68351-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span></span>  
  
     <span data-ttu-id="68351-185">Si el índice no clúster se encuentra sobre un índice clúster, el localizador de fila de datos es la clave de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="68351-185">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="68351-186">Las columnas que se deben combinar con la clave de índice no clúster son las columnas de la clave de agrupación en clústeres que ya no están presentes en el conjunto de columnas de clave de índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="68351-186">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="68351-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + número de columnas de clave de agrupación en clústeres no presentes en el conjunto de columnas de clave de índice no agrupado (+ 1 si el índice agrupado no es único)</span><span class="sxs-lookup"><span data-stu-id="68351-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="68351-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + número de columnas de clave de agrupación en clústeres de longitud fija que no están presentes en el conjunto de columnas de clave de índice no agrupado</span><span class="sxs-lookup"><span data-stu-id="68351-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + number of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="68351-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + número de columnas de clave de agrupación en clústeres de longitud variable no presentes en el conjunto de columnas de clave de índice no agrupado (+ 1 si el índice agrupado no es único)</span><span class="sxs-lookup"><span data-stu-id="68351-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="68351-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + tamaño en bytes de las columnas de clave de agrupación en clústeres de longitud variable que no están presentes en el conjunto de columnas de clave de índice no agrupado (+ 4 si el índice agrupado no es único)</span><span class="sxs-lookup"><span data-stu-id="68351-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + size in bytes of the variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
3.  <span data-ttu-id="68351-191">Calcule el tamaño del mapa de bits de valor NULL:</span><span class="sxs-lookup"><span data-stu-id="68351-191">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="68351-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="68351-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="68351-193">Solamente debe utilizarse la parte entera de la expresión anterior.</span><span class="sxs-lookup"><span data-stu-id="68351-193">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="68351-194">Descarte el resto.</span><span class="sxs-lookup"><span data-stu-id="68351-194">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="68351-195">Calcule el tamaño de los datos de longitud variable:</span><span class="sxs-lookup"><span data-stu-id="68351-195">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="68351-196">Si hay columnas de longitud variable en la clave de índice, incluidas las columnas de clave de agrupación en clústeres necesarias según se describe en el Paso 2.2, determine cuánto espacio se utiliza para almacenar las columnas de la fila de índice:</span><span class="sxs-lookup"><span data-stu-id="68351-196">If there are variable-length columns in the index key, including any necessary clustering key columns as described previously in Step 2.2, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="68351-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span><span class="sxs-lookup"><span data-stu-id="68351-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span></span>  
  
     <span data-ttu-id="68351-198">Los bytes agregados a ***Max_Var_Key_Size*** son para el seguimiento de cada columna de longitud variable. En esta fórmula se supone que todas las columnas de longitud variable están llenas al 100 %.</span><span class="sxs-lookup"><span data-stu-id="68351-198">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="68351-199">Si prevé que va a usarse un porcentaje inferior del espacio de almacenamiento de las columnas de longitud variable, puede ajustar el valor de ***Max_Var_Leaf_Size*** en función de ese porcentaje para obtener una estimación más precisa del tamaño global de la tabla.</span><span class="sxs-lookup"><span data-stu-id="68351-199">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Leaf_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="68351-200">Si no hay columnas de longitud variable, establezca ***Variable_Leaf_Size*** en 0.</span><span class="sxs-lookup"><span data-stu-id="68351-200">If there are no variable-length columns, set ***Variable_Leaf_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="68351-201">Calcule el tamaño de la fila del índice:</span><span class="sxs-lookup"><span data-stu-id="68351-201">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="68351-202">***Leaf_Row_Size***   =  ***Fixed_Leaf_Size***  +  ***Variable_Leaf_Size***  +  ***Leaf_Null_Bitmap*** + 1 (para la sobrecarga de encabezado de fila de una fila de índice) + 6 (para el puntero de identificador de página secundaria)</span><span class="sxs-lookup"><span data-stu-id="68351-202">***Leaf_Row_Size***  = ***Fixed_Leaf_Size*** + ***Variable_Leaf_Size*** + ***Leaf_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="68351-203">Calcule el número de filas de índice por página (8.096 bytes disponibles por página):</span><span class="sxs-lookup"><span data-stu-id="68351-203">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="68351-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="68351-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="68351-205">Dado que las filas de índice no abarcan varias páginas, el número de filas de índice por página debe redondearse hacia abajo a la fila completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="68351-205">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="68351-206">El valor 2 de la fórmula representa la entrada de la fila en la matriz de zonas de la página.</span><span class="sxs-lookup"><span data-stu-id="68351-206">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="68351-207">Calcule el número de filas libres reservadas por página, basándose en el valor de [factor de relleno](../indexes/specify-fill-factor-for-an-index.md) especificado:</span><span class="sxs-lookup"><span data-stu-id="68351-207">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="68351-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="68351-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="68351-209">El factor de relleno que se utiliza en el cálculo es un valor entero y no un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="68351-209">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="68351-210">Dado que las filas no abarcan varias páginas, el número de filas por página debe redondearse hacia abajo a la fila completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="68351-210">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="68351-211">A medida que aumenta el factor de relleno, más datos se almacenan en cada página y menos páginas habrá.</span><span class="sxs-lookup"><span data-stu-id="68351-211">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="68351-212">El valor 2 de la fórmula representa la entrada de la fila en la matriz de zonas de la página.</span><span class="sxs-lookup"><span data-stu-id="68351-212">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
8.  <span data-ttu-id="68351-213">Calcule el número de páginas necesarias para almacenar todas las filas:</span><span class="sxs-lookup"><span data-stu-id="68351-213">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="68351-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="68351-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="68351-215">El número de páginas estimado debe redondearse hacia arriba a la página completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="68351-215">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
9. <span data-ttu-id="68351-216">Calcule el tamaño del índice (8.192 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="68351-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="68351-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="68351-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-3-calculate-the-space-used-to-store-index-information-in-the-non-leaf-levels"></a><span data-ttu-id="68351-218">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="68351-218">Step 3.</span></span> <span data-ttu-id="68351-219">Calcular el espacio utilizado para almacenar información del índice en los niveles no hoja</span><span class="sxs-lookup"><span data-stu-id="68351-219">Calculate the Space Used to Store Index Information in the Non-leaf Levels</span></span>  
 <span data-ttu-id="68351-220">Siga estos pasos para estimar el espacio necesario para almacenar los niveles intermedio y raíz del índice.</span><span class="sxs-lookup"><span data-stu-id="68351-220">Follow these steps to estimate the amount of space that is required to store the intermediate and root levels of the index.</span></span> <span data-ttu-id="68351-221">Para completar este paso, necesita los valores de los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="68351-221">You will need the values preserved from steps 2 and 3 to complete this step.</span></span>  
  
1.  <span data-ttu-id="68351-222">Calcule el número de niveles no hoja del índice:</span><span class="sxs-lookup"><span data-stu-id="68351-222">Calculate the number of non-leaf levels in the index:</span></span>  
  
     <span data-ttu-id="68351-223">***Niveles no hoja*** = 1 + Index_Rows_Per_Page de registro (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="68351-223">***Non-leaf Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="68351-224">Redondee este valor al número entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="68351-224">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="68351-225">Este valor no incluye el nivel hoja del índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="68351-225">This value does not include the leaf level of the nonclustered index.</span></span>  
  
2.  <span data-ttu-id="68351-226">Calcule el número de páginas no hoja del índice:</span><span class="sxs-lookup"><span data-stu-id="68351-226">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="68351-227">***Num_Index_Pages*** = ∑ nivel (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>nivel</sup>) donde 1 <= nivel <= ***niveles***</span><span class="sxs-lookup"><span data-stu-id="68351-227">***Num_Index_Pages***  = ∑Level (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Level</sup>)where 1 <= Level <= ***Levels***</span></span>  
  
     <span data-ttu-id="68351-228">Redondee cada sumando al número entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="68351-228">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="68351-229">Como ejemplo sencillo, considere un índice en el que ***Num_Leaf_Pages*** = 1000 e ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="68351-229">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="68351-230">El primer nivel de índice por encima del nivel hoja almacena 1000 filas de índice, lo que equivale a una fila de índice por página hoja, y en cada página caben 25 filas de índice.</span><span class="sxs-lookup"><span data-stu-id="68351-230">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="68351-231">Esto significa que se necesitan 40 páginas para almacenar las 1000 filas de índice.</span><span class="sxs-lookup"><span data-stu-id="68351-231">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="68351-232">El siguiente nivel del índice debe almacenar 40 filas.</span><span class="sxs-lookup"><span data-stu-id="68351-232">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="68351-233">Esto significa que necesita 2 páginas.</span><span class="sxs-lookup"><span data-stu-id="68351-233">This means that it requires 2 pages.</span></span> <span data-ttu-id="68351-234">El nivel final del índice debe almacenar 2 filas.</span><span class="sxs-lookup"><span data-stu-id="68351-234">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="68351-235">Esto significa que necesita 1 página.</span><span class="sxs-lookup"><span data-stu-id="68351-235">This means that it requires 1 page.</span></span> <span data-ttu-id="68351-236">Todo ello da lugar a 43 páginas no hoja de índice.</span><span class="sxs-lookup"><span data-stu-id="68351-236">This yields 43 non-leaf index pages.</span></span> <span data-ttu-id="68351-237">Si se utilizan estos números en las fórmulas anteriores, el resultado será el siguiente:</span><span class="sxs-lookup"><span data-stu-id="68351-237">When these numbers are used in the previous formulas, the result is as follows:</span></span>  
  
     <span data-ttu-id="68351-238">***No leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="68351-238">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="68351-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, que es el número de páginas que se describe en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="68351-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
3.  <span data-ttu-id="68351-240">Calcule el tamaño del índice (8.192 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="68351-240">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="68351-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="68351-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-4-total-the-calculated-values"></a><span data-ttu-id="68351-242">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="68351-242">Step 4.</span></span> <span data-ttu-id="68351-243">Sumar los valores calculados</span><span class="sxs-lookup"><span data-stu-id="68351-243">Total the Calculated Values</span></span>  
 <span data-ttu-id="68351-244">Sume los valores obtenidos en los dos pasos anteriores:</span><span class="sxs-lookup"><span data-stu-id="68351-244">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="68351-245">Tamaño del índice no agrupado (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="68351-245">Nonclustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="68351-246">En este cálculo no se tiene en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="68351-246">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="68351-247">Creación de particiones</span><span class="sxs-lookup"><span data-stu-id="68351-247">Partitioning</span></span>  
  
     <span data-ttu-id="68351-248">La sobrecarga de espacio de la creación de particiones es mínima, pero resulta difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="68351-248">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="68351-249">No es importante incluirla.</span><span class="sxs-lookup"><span data-stu-id="68351-249">It is not important to include.</span></span>  
  
-   <span data-ttu-id="68351-250">Páginas de asignación</span><span class="sxs-lookup"><span data-stu-id="68351-250">Allocation pages</span></span>  
  
     <span data-ttu-id="68351-251">Se utiliza al menos una página IAM para realizar un seguimiento de las páginas asignadas a un montón, pero la sobrecarga de espacio es mínima y no existe ningún algoritmo para calcular de forma determinista el número exacto de páginas IAM que se utilizarán.</span><span class="sxs-lookup"><span data-stu-id="68351-251">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="68351-252">Valores de objetos grandes (LOB)</span><span class="sxs-lookup"><span data-stu-id="68351-252">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="68351-253">El algoritmo para determinar exactamente la cantidad de espacio que se utilizará para almacenar los tipos de datos LOB y los valores `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` y `image` es complejo.</span><span class="sxs-lookup"><span data-stu-id="68351-253">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="68351-254">Basta con agregar el tamaño medio de los valores LOB esperados, multiplicarlo por ***Num_Rows***y sumar el resultado al tamaño total del índice no agrupado.</span><span class="sxs-lookup"><span data-stu-id="68351-254">It is sufficient to just add the average size of the LOB values expected, multiply by ***Num_Rows***, and add that to the total nonclustered index size.</span></span>  
  
-   <span data-ttu-id="68351-255">Compresión</span><span class="sxs-lookup"><span data-stu-id="68351-255">Compression</span></span>  
  
     <span data-ttu-id="68351-256">No se puede calcular previamente el tamaño de un índice comprimido.</span><span class="sxs-lookup"><span data-stu-id="68351-256">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="68351-257">Columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="68351-257">Sparse columns</span></span>  
  
     <span data-ttu-id="68351-258">Para obtener información sobre los requisitos de espacio de las columnas dispersas, vea [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="68351-258">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68351-259">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68351-259">See Also</span></span>  
 <span data-ttu-id="68351-260">[Índices agrupados y no agrupados descritos](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="68351-260">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="68351-261">[Crear índices no clúster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="68351-261">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="68351-262">[Crear índices clúster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="68351-262">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="68351-263">[Calcular el tamaño de una tabla](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="68351-263">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="68351-264">[Estimar el tamaño de un índice agrupado](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="68351-264">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="68351-265">[Estimar el tamaño de un montón](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="68351-265">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="68351-266">Estimar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="68351-266">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
