---
title: Estimar el tamaño de un índice agrupado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- disk space [SQL Server], indexes
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- space [SQL Server], indexes
- clustered indexes, table size
- nonclustered indexes [SQL Server], table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: 2b5137f8-98ad-46b5-9aae-4c980259bf8d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d224c5ae55cc5ec7690ca0962cbc2130bac22e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751089"
---
# <a name="estimate-the-size-of-a-clustered-index"></a><span data-ttu-id="e7b14-102">Estimar el tamaño de un índice clúster</span><span class="sxs-lookup"><span data-stu-id="e7b14-102">Estimate the Size of a Clustered Index</span></span>
  <span data-ttu-id="e7b14-103">Los siguientes pasos pueden utilizarse para calcular el espacio necesario para almacenar datos en un índice clúster:</span><span class="sxs-lookup"><span data-stu-id="e7b14-103">You can use the following steps to estimate the amount of space that is required to store data in a clustered index:</span></span>  
  
1.  <span data-ttu-id="e7b14-104">Calcule el espacio utilizado para almacenar datos en el nivel hoja del índice clúster.</span><span class="sxs-lookup"><span data-stu-id="e7b14-104">Calculate the space used to store data in the leaf level of the clustered index.</span></span>  
  
2.  <span data-ttu-id="e7b14-105">Calcule el espacio utilizado para almacenar información del índice clúster.</span><span class="sxs-lookup"><span data-stu-id="e7b14-105">Calculate the space used to store index information for the clustered index.</span></span>  
  
3.  <span data-ttu-id="e7b14-106">Sumar los valores calculados.</span><span class="sxs-lookup"><span data-stu-id="e7b14-106">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-the-space-used-to-store-data-in-the-leaf-level"></a><span data-ttu-id="e7b14-107">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="e7b14-107">Step 1.</span></span> <span data-ttu-id="e7b14-108">Calcular el espacio utilizado para almacenar datos en el nivel hoja</span><span class="sxs-lookup"><span data-stu-id="e7b14-108">Calculate the Space Used to Store Data in the Leaf Level</span></span>  
  
1.  <span data-ttu-id="e7b14-109">Especifique el número de filas que habrá en la tabla:</span><span class="sxs-lookup"><span data-stu-id="e7b14-109">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="e7b14-110">***Num_Rows***  = número de filas de la tabla</span><span class="sxs-lookup"><span data-stu-id="e7b14-110">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="e7b14-111">Especifique el número de columnas de longitud fija y de longitud variable, y calcule el espacio necesario para su almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="e7b14-111">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="e7b14-112">Calcule el espacio que ocupa cada uno de estos grupos de columnas en la fila de datos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-112">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="e7b14-113">El tamaño de una columna depende del tipo y de la longitud especificados para los datos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-113">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="e7b14-114">***Num_Cols***  = número total de columnas (de longitud fija y variable)</span><span class="sxs-lookup"><span data-stu-id="e7b14-114">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="e7b14-115">***Fixed_Data_Size***  = tamaño total en bytes de todas las columnas de longitud fija</span><span class="sxs-lookup"><span data-stu-id="e7b14-115">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="e7b14-116">***Num_Variable_Cols***  = número de columnas de longitud variable</span><span class="sxs-lookup"><span data-stu-id="e7b14-116">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="e7b14-117">***Max_Var_Size***  = tamaño máximo en bytes de todas las columnas de longitud variable</span><span class="sxs-lookup"><span data-stu-id="e7b14-117">***Max_Var_Size***  = maximum byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="e7b14-118">Si el índice clúster no es único, tenga en cuenta la columna de *valor de unicidad* :</span><span class="sxs-lookup"><span data-stu-id="e7b14-118">If the clustered index is nonunique, account for the *uniqueifier* column:</span></span>  
  
     <span data-ttu-id="e7b14-119">La columna de valor de unicidad es una columna de longitud variable que admite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="e7b14-119">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="e7b14-120">No será NULL y tendrá 4 bytes de tamaño en filas que tienen valores de clave no únicos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-120">It will be nonnull and 4 bytes in size in rows that have nonunique key values.</span></span> <span data-ttu-id="e7b14-121">Este valor forma parte de la clave de índice y es necesario para asegurarse de que cada fila tiene un valor de clave único.</span><span class="sxs-lookup"><span data-stu-id="e7b14-121">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="e7b14-122">***Num_Cols***  = ***Num_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e7b14-122">***Num_Cols***  = ***Num_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e7b14-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e7b14-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e7b14-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="e7b14-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span></span>  
  
     <span data-ttu-id="e7b14-125">Estas modificaciones presuponen que todos los valores no serán únicos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-125">These modifications assume that all values will be nonunique.</span></span>  
  
4.  <span data-ttu-id="e7b14-126">Una parte de la fila, conocida como el mapa de bits NULL, se reserva para administrar la nulabilidad en las columnas.</span><span class="sxs-lookup"><span data-stu-id="e7b14-126">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="e7b14-127">Calcule el tamaño:</span><span class="sxs-lookup"><span data-stu-id="e7b14-127">Calculate its size:</span></span>  
  
     <span data-ttu-id="e7b14-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="e7b14-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="e7b14-129">Solo debe utilizarse la parte entera de la expresión anterior; descarte el resto.</span><span class="sxs-lookup"><span data-stu-id="e7b14-129">Only the integer part of the previous expression should be used; discard any remainder.</span></span>  
  
5.  <span data-ttu-id="e7b14-130">Calcule el tamaño de los datos de longitud variable:</span><span class="sxs-lookup"><span data-stu-id="e7b14-130">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="e7b14-131">Si hay columnas de longitud variable en la tabla, determine cuánto espacio se utiliza para almacenar las columnas en la fila:</span><span class="sxs-lookup"><span data-stu-id="e7b14-131">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="e7b14-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="e7b14-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="e7b14-133">Los bytes agregados a ***Max_Var_Size*** son para el seguimiento de cada columna de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="e7b14-133">The bytes added to ***Max_Var_Size*** are for tracking each variable column.</span></span> <span data-ttu-id="e7b14-134">En esta fórmula se supone que todas las columnas de longitud variable están llenas al 100%.</span><span class="sxs-lookup"><span data-stu-id="e7b14-134">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="e7b14-135">Si prevé que se va a usar un porcentaje inferior del espacio de almacenamiento de columnas de longitud variable, puede ajustar el valor de ***Max_Var_Size*** en función de ese porcentaje para obtener una estimación más precisa del tamaño global de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e7b14-135">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e7b14-136">Puede combinar las columnas `varchar`, `nvarchar`, `varbinary` o `sql_variant` que hagan que el ancho total definido para la tabla sea superior a 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="e7b14-136">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="e7b14-137">La longitud de cada una de estas columnas debe ajustarse al límite de 8.000 bytes en columnas `varchar`, `varbinary` o `sql_variant` y de 4.000 bytes en columnas `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="e7b14-137">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="e7b14-138">Sin embargo, el ancho combinado puede superar el límite de 8.060 bytes de una tabla.</span><span class="sxs-lookup"><span data-stu-id="e7b14-138">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="e7b14-139">Si no hay columnas de longitud variable, establezca ***Variable_Data_Size*** en 0.</span><span class="sxs-lookup"><span data-stu-id="e7b14-139">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="e7b14-140">Calcule el tamaño total de la fila:</span><span class="sxs-lookup"><span data-stu-id="e7b14-140">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="e7b14-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="e7b14-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="e7b14-142">El valor 4 representa la sobrecarga del encabezado de una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-142">The value 4 is the row header overhead of a data row.</span></span>  
  
7.  <span data-ttu-id="e7b14-143">Calcule el número de filas por página (8096 bytes libres por página):</span><span class="sxs-lookup"><span data-stu-id="e7b14-143">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="e7b14-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e7b14-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e7b14-145">Dado que las filas no abarcan varias páginas, el número de filas por página debe redondearse hacia abajo a la fila completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="e7b14-145">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e7b14-146">El valor 2 de la fórmula representa la entrada de la fila en la matriz de zonas de la página.</span><span class="sxs-lookup"><span data-stu-id="e7b14-146">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
8.  <span data-ttu-id="e7b14-147">Calcule el número de filas libres reservadas por página, basándose en el valor de [factor de relleno](../indexes/specify-fill-factor-for-an-index.md) especificado:</span><span class="sxs-lookup"><span data-stu-id="e7b14-147">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="e7b14-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e7b14-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e7b14-149">El factor de relleno que se utiliza en el cálculo es un valor entero y no un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="e7b14-149">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="e7b14-150">Dado que las filas no abarcan varias páginas, el número de filas por página debe redondearse hacia abajo a la fila completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="e7b14-150">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e7b14-151">A medida que aumenta el factor de relleno, más datos se almacenan en cada página y menos páginas habrá.</span><span class="sxs-lookup"><span data-stu-id="e7b14-151">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="e7b14-152">El valor 2 de la fórmula representa la entrada de la fila en la matriz de zonas de la página.</span><span class="sxs-lookup"><span data-stu-id="e7b14-152">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
9. <span data-ttu-id="e7b14-153">Calcule el número de páginas necesarias para almacenar todas las filas:</span><span class="sxs-lookup"><span data-stu-id="e7b14-153">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="e7b14-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="e7b14-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="e7b14-155">El número de páginas estimado debe redondearse hacia arriba a la página completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="e7b14-155">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
10. <span data-ttu-id="e7b14-156">Calcule la cantidad de espacio necesario para almacenar los datos en el nivel hoja (8.192 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="e7b14-156">Calculate the amount of space that is required to store the data in the leaf level (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="e7b14-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="e7b14-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information"></a><span data-ttu-id="e7b14-158">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="e7b14-158">Step 2.</span></span> <span data-ttu-id="e7b14-159">Calcular el espacio utilizado para almacenar información de índice</span><span class="sxs-lookup"><span data-stu-id="e7b14-159">Calculate the Space Used to Store Index Information</span></span>  
 <span data-ttu-id="e7b14-160">Los siguientes pasos pueden utilizarse para calcular el espacio necesario para almacenar los niveles superiores del índice:</span><span class="sxs-lookup"><span data-stu-id="e7b14-160">You can use the following steps to estimate the amount of space that is required to store the upper levels of the index:</span></span>  
  
1.  <span data-ttu-id="e7b14-161">Especifique el número de columnas de longitud fija y variable de la clave de índice, y calcule el espacio necesario para su almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="e7b14-161">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="e7b14-162">Las columnas de clave de un índice pueden incluir columnas de longitud fija y de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="e7b14-162">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="e7b14-163">Para estimar el tamaño de las filas de índice de nivel interior, calcule el espacio que ocupa cada uno de estos grupos de columnas en la fila de índice.</span><span class="sxs-lookup"><span data-stu-id="e7b14-163">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="e7b14-164">El tamaño de una columna depende del tipo y de la longitud especificados para los datos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-164">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="e7b14-165">***Num_Key_Cols***  = número total de columnas de clave (de longitud fija y variable)</span><span class="sxs-lookup"><span data-stu-id="e7b14-165">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="e7b14-166">***Fixed_Key_Size***  = tamaño total en bytes de todas las columnas de clave de longitud fija</span><span class="sxs-lookup"><span data-stu-id="e7b14-166">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="e7b14-167">***Num_Variable_Key_Cols***  = número de columnas de clave de longitud variable</span><span class="sxs-lookup"><span data-stu-id="e7b14-167">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="e7b14-168">***Max_Var_Key_Size***  = tamaño máximo en bytes de todas las columnas de clave de longitud variable</span><span class="sxs-lookup"><span data-stu-id="e7b14-168">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
2.  <span data-ttu-id="e7b14-169">Tenga en cuenta cualquier columna de valor de unicidad si el índice no es único:</span><span class="sxs-lookup"><span data-stu-id="e7b14-169">Account for any uniqueifier needed if the index is nonunique:</span></span>  
  
     <span data-ttu-id="e7b14-170">La columna de valor de unicidad es una columna de longitud variable que admite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="e7b14-170">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="e7b14-171">No será NULL y tendrá 4 bytes de tamaño en filas que tienen valores de clave de índice no únicos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-171">It will be nonnull and 4 bytes in size in rows that have nonunique index key values.</span></span> <span data-ttu-id="e7b14-172">Este valor forma parte de la clave de índice y es necesario para asegurarse de que cada fila tiene un valor de clave único.</span><span class="sxs-lookup"><span data-stu-id="e7b14-172">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="e7b14-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e7b14-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e7b14-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e7b14-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e7b14-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="e7b14-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span></span>  
  
     <span data-ttu-id="e7b14-176">Estas modificaciones presuponen que todos los valores no serán únicos.</span><span class="sxs-lookup"><span data-stu-id="e7b14-176">These modifications assume that all values will be nonunique.</span></span>  
  
3.  <span data-ttu-id="e7b14-177">Calcule el tamaño del mapa de bits de valor NULL:</span><span class="sxs-lookup"><span data-stu-id="e7b14-177">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="e7b14-178">Si hay columnas que admiten valores NULL en la clave de índice, una parte de la fila de índice se reserva para el mapa de bits NULL.</span><span class="sxs-lookup"><span data-stu-id="e7b14-178">If there are nullable columns in the index key, part of the index row is reserved for the null bitmap.</span></span> <span data-ttu-id="e7b14-179">Calcule el tamaño:</span><span class="sxs-lookup"><span data-stu-id="e7b14-179">Calculate its size:</span></span>  
  
     <span data-ttu-id="e7b14-180">***Index_Null_Bitmap***  = 2 + ((número de columnas de la fila de índice + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="e7b14-180">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="e7b14-181">Solamente debe utilizarse la parte entera de la expresión anterior.</span><span class="sxs-lookup"><span data-stu-id="e7b14-181">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="e7b14-182">Descarte el resto.</span><span class="sxs-lookup"><span data-stu-id="e7b14-182">Discard any remainder.</span></span>  
  
     <span data-ttu-id="e7b14-183">Si no existen columnas de clave que aceptan valores NULL, establezca ***Index_Null_Bitmap*** en 0.</span><span class="sxs-lookup"><span data-stu-id="e7b14-183">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
4.  <span data-ttu-id="e7b14-184">Calcule el tamaño de los datos de longitud variable:</span><span class="sxs-lookup"><span data-stu-id="e7b14-184">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="e7b14-185">Si hay columnas de longitud variable en el índice, determine cuánto espacio se utiliza para almacenar las columnas en la fila de índice:</span><span class="sxs-lookup"><span data-stu-id="e7b14-185">If there are variable-length columns in the index, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="e7b14-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="e7b14-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="e7b14-187">Los bytes agregados a ***Max_Var_Key_Size*** son para el seguimiento de cada columna de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="e7b14-187">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="e7b14-188">En esta fórmula se supone que todas las columnas de longitud variable están llenas al 100%.</span><span class="sxs-lookup"><span data-stu-id="e7b14-188">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="e7b14-189">Si prevé que se va a usar un porcentaje inferior del espacio de almacenamiento de columnas de longitud variable, puede ajustar el valor de ***Max_Var_Key_Size*** en función de ese porcentaje para obtener una estimación más precisa del tamaño global de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e7b14-189">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="e7b14-190">Si no hay columnas de longitud variable, establezca ***Variable_Key_Size*** en 0.</span><span class="sxs-lookup"><span data-stu-id="e7b14-190">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="e7b14-191">Calcule el tamaño de la fila del índice:</span><span class="sxs-lookup"><span data-stu-id="e7b14-191">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="e7b14-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (para la sobrecarga de encabezado de una fila de índice) + 6 (para el puntero de identificador de página secundaria)</span><span class="sxs-lookup"><span data-stu-id="e7b14-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="e7b14-193">Calcule el número de filas de índice por página (8.096 bytes disponibles por página):</span><span class="sxs-lookup"><span data-stu-id="e7b14-193">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="e7b14-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e7b14-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e7b14-195">Dado que las filas de índice no abarcan varias páginas, el número de filas de índice por página debe redondearse hacia abajo a la fila completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="e7b14-195">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e7b14-196">El valor 2 de la fórmula representa la entrada de la fila en la matriz de zonas de la página.</span><span class="sxs-lookup"><span data-stu-id="e7b14-196">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="e7b14-197">Calcule el número de niveles del índice:</span><span class="sxs-lookup"><span data-stu-id="e7b14-197">Calculate the number of levels in the index:</span></span>  
  
     <span data-ttu-id="e7b14-198">***No leaf_Levels*** = 1 + Index_Rows_Per_Page de registro (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="e7b14-198">***Non-leaf_Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="e7b14-199">Redondee este valor al número entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="e7b14-199">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="e7b14-200">Este valor no incluye el nivel hoja del índice clúster.</span><span class="sxs-lookup"><span data-stu-id="e7b14-200">This value does not include the leaf level of the clustered index.</span></span>  
  
8.  <span data-ttu-id="e7b14-201">Calcule el número de páginas no hoja del índice:</span><span class="sxs-lookup"><span data-stu-id="e7b14-201">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="e7b14-202">***Num_Index_Pages =*** ∑ nivel ***(Num_Leaf_Pages/(Index_Rows_Per_Page***<sup>nivel</sup>***))***</span><span class="sxs-lookup"><span data-stu-id="e7b14-202">***Num_Index_Pages =*** ∑Level ***(Num_Leaf_Pages / (Index_Rows_Per_Page***<sup>Level</sup>***))***</span></span>  
  
     <span data-ttu-id="e7b14-203">donde 1 <= Level <= ***Non-leaf_Levels***</span><span class="sxs-lookup"><span data-stu-id="e7b14-203">where 1 <= Level <= ***Non-leaf_Levels***</span></span>  
  
     <span data-ttu-id="e7b14-204">Redondee cada sumando al número entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="e7b14-204">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="e7b14-205">Como ejemplo sencillo, considere un índice en el que ***Num_Leaf_Pages*** = 1000 e ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="e7b14-205">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="e7b14-206">El primer nivel de índice por encima del nivel hoja almacena 1000 filas de índice, lo que equivale a una fila de índice por página hoja, y en cada página caben 25 filas de índice.</span><span class="sxs-lookup"><span data-stu-id="e7b14-206">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="e7b14-207">Esto significa que se necesitan 40 páginas para almacenar las 1000 filas de índice.</span><span class="sxs-lookup"><span data-stu-id="e7b14-207">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="e7b14-208">El siguiente nivel del índice debe almacenar 40 filas.</span><span class="sxs-lookup"><span data-stu-id="e7b14-208">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="e7b14-209">Esto significa que necesita 2 páginas.</span><span class="sxs-lookup"><span data-stu-id="e7b14-209">This means it requires 2 pages.</span></span> <span data-ttu-id="e7b14-210">El nivel final del índice debe almacenar 2 filas.</span><span class="sxs-lookup"><span data-stu-id="e7b14-210">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="e7b14-211">Esto significa que necesita 1 página.</span><span class="sxs-lookup"><span data-stu-id="e7b14-211">This means it requires 1 page.</span></span> <span data-ttu-id="e7b14-212">Todo ello supone 43 páginas de índice no hoja.</span><span class="sxs-lookup"><span data-stu-id="e7b14-212">This gives 43 non-leaf index pages.</span></span> <span data-ttu-id="e7b14-213">Si se utilizan estos números en las fórmulas anteriores, el resultado será el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7b14-213">When these numbers are used in the previous formulas, the outcome is as follows:</span></span>  
  
     <span data-ttu-id="e7b14-214">***No leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="e7b14-214">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="e7b14-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, que es el número de páginas que se describe en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e7b14-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
9. <span data-ttu-id="e7b14-216">Calcule el tamaño del índice (8.192 bytes por página):</span><span class="sxs-lookup"><span data-stu-id="e7b14-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="e7b14-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="e7b14-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-3-total-the-calculated-values"></a><span data-ttu-id="e7b14-218">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="e7b14-218">Step 3.</span></span> <span data-ttu-id="e7b14-219">Sumar los valores calculados</span><span class="sxs-lookup"><span data-stu-id="e7b14-219">Total the Calculated Values</span></span>  
 <span data-ttu-id="e7b14-220">Sume los valores obtenidos en los dos pasos anteriores:</span><span class="sxs-lookup"><span data-stu-id="e7b14-220">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="e7b14-221">Tamaño del índice agrupado (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="e7b14-221">Clustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="e7b14-222">En este cálculo no se tiene en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7b14-222">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="e7b14-223">Creación de particiones</span><span class="sxs-lookup"><span data-stu-id="e7b14-223">Partitioning</span></span>  
  
     <span data-ttu-id="e7b14-224">La sobrecarga de espacio de la creación de particiones es mínima, pero resulta difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="e7b14-224">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="e7b14-225">No es importante incluirla.</span><span class="sxs-lookup"><span data-stu-id="e7b14-225">It is not important to include.</span></span>  
  
-   <span data-ttu-id="e7b14-226">Páginas de asignación</span><span class="sxs-lookup"><span data-stu-id="e7b14-226">Allocation pages</span></span>  
  
     <span data-ttu-id="e7b14-227">Se utiliza al menos una página IAM para realizar un seguimiento de las páginas asignadas a un montón, pero la sobrecarga de espacio es mínima y no existe ningún algoritmo para calcular de forma determinista el número exacto de páginas IAM que se utilizarán.</span><span class="sxs-lookup"><span data-stu-id="e7b14-227">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="e7b14-228">Valores de objetos grandes (LOB)</span><span class="sxs-lookup"><span data-stu-id="e7b14-228">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="e7b14-229">El algoritmo para determinar exactamente la cantidad de espacio que se utilizará para almacenar los tipos de datos LOB y los valores `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` y `image` es complejo.</span><span class="sxs-lookup"><span data-stu-id="e7b14-229">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="e7b14-230">Basta con agregar el tamaño medio de los valores LOB que se esperan, multiplicarlo por ***Num_Rows***y agregarlo al tamaño total del índice agrupado.</span><span class="sxs-lookup"><span data-stu-id="e7b14-230">It is sufficient to just add the average size of the LOB values that are expected, multiply by ***Num_Rows***, and add that to the total clustered index size.</span></span>  
  
-   <span data-ttu-id="e7b14-231">Compresión</span><span class="sxs-lookup"><span data-stu-id="e7b14-231">Compression</span></span>  
  
     <span data-ttu-id="e7b14-232">No se puede calcular previamente el tamaño de un índice comprimido.</span><span class="sxs-lookup"><span data-stu-id="e7b14-232">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="e7b14-233">Columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="e7b14-233">Sparse columns</span></span>  
  
     <span data-ttu-id="e7b14-234">Para obtener información sobre los requisitos de espacio de las columnas dispersas, vea [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e7b14-234">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b14-235">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7b14-235">See Also</span></span>  
 <span data-ttu-id="e7b14-236">[Índices agrupados y no agrupados descritos](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="e7b14-236">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="e7b14-237">[Calcular el tamaño de una tabla](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="e7b14-237">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="e7b14-238">[Crear índices clúster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e7b14-238">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="e7b14-239">[Crear índices no clúster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e7b14-239">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="e7b14-240">[Estimar el tamaño de un índice no clúster](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="e7b14-240">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 <span data-ttu-id="e7b14-241">[Estimar el tamaño de un montón](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="e7b14-241">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="e7b14-242">Estimar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="e7b14-242">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
