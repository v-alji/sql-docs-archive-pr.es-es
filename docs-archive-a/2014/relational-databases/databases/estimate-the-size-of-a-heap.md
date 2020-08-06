---
title: Estimar el tamaño de un montón | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- estimating heap size
- size [SQL Server], heap
- space [SQL Server], indexes
- heaps
ms.assetid: 81fd5ec9-ce0f-4c2c-8ba0-6c483cea6c75
author: stevestein
ms.author: sstein
ms.openlocfilehash: f32432d07a9731d849ceb793daf209cfc505b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677660"
---
# <a name="estimate-the-size-of-a-heap"></a><span data-ttu-id="04f69-102">Estimar el tamaño de un montón</span><span class="sxs-lookup"><span data-stu-id="04f69-102">Estimate the Size of a Heap</span></span>
  <span data-ttu-id="04f69-103">Los siguientes pasos pueden utilizarse para calcular el espacio necesario para almacenar datos en un montón:</span><span class="sxs-lookup"><span data-stu-id="04f69-103">You can use the following steps to estimate the amount of space that is required to store data in a heap:</span></span>  
  
1.  <span data-ttu-id="04f69-104">Especifique el número de filas que habrá en la tabla:</span><span class="sxs-lookup"><span data-stu-id="04f69-104">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="04f69-105">***Num_Rows***  = número de filas de la tabla</span><span class="sxs-lookup"><span data-stu-id="04f69-105">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="04f69-106">Especifique el número de columnas de longitud fija y de longitud variable, y calcule el espacio necesario para su almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="04f69-106">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="04f69-107">Calcule el espacio que ocupa cada uno de estos grupos de columnas en la fila de datos.</span><span class="sxs-lookup"><span data-stu-id="04f69-107">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="04f69-108">El tamaño de una columna depende del tipo y de la longitud especificados para los datos.</span><span class="sxs-lookup"><span data-stu-id="04f69-108">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="04f69-109">***Num_Cols***  = número total de columnas (de longitud fija y variable)</span><span class="sxs-lookup"><span data-stu-id="04f69-109">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="04f69-110">***Fixed_Data_Size***  = tamaño total en bytes de todas las columnas de longitud fija</span><span class="sxs-lookup"><span data-stu-id="04f69-110">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="04f69-111">***Num_Variable_Cols***  = número de columnas de longitud variable</span><span class="sxs-lookup"><span data-stu-id="04f69-111">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="04f69-112">***Max_Var_Size***  = tamaño máximo total en bytes de todas las columnas de longitud variable</span><span class="sxs-lookup"><span data-stu-id="04f69-112">***Max_Var_Size***  = maximum total byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="04f69-113">Una parte de la fila, conocida como el mapa de bits NULL, se reserva para administrar la nulabilidad en las columnas.</span><span class="sxs-lookup"><span data-stu-id="04f69-113">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="04f69-114">Calcule el tamaño:</span><span class="sxs-lookup"><span data-stu-id="04f69-114">Calculate its size:</span></span>  
  
     <span data-ttu-id="04f69-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="04f69-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="04f69-116">Solo debe utilizarse la parte entera de la expresión anterior.</span><span class="sxs-lookup"><span data-stu-id="04f69-116">Only the integer part of this expression should be used.</span></span> <span data-ttu-id="04f69-117">Descarte el resto.</span><span class="sxs-lookup"><span data-stu-id="04f69-117">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="04f69-118">Calcule el tamaño de los datos de longitud variable:</span><span class="sxs-lookup"><span data-stu-id="04f69-118">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="04f69-119">Si hay columnas de longitud variable en la tabla, determine cuánto espacio se utiliza para almacenar las columnas en la fila:</span><span class="sxs-lookup"><span data-stu-id="04f69-119">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="04f69-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="04f69-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="04f69-121">Los bytes agregados a ***Max_Var_Size*** son para el seguimiento de cada columna de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="04f69-121">The bytes added to ***Max_Var_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="04f69-122">En esta fórmula se supone que todas las columnas de longitud variable están llenas al 100%.</span><span class="sxs-lookup"><span data-stu-id="04f69-122">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="04f69-123">Si prevé que se va a usar un porcentaje inferior del espacio de almacenamiento de columnas de longitud variable, puede ajustar el valor de ***Max_Var_Size*** en función de ese porcentaje para obtener una estimación más precisa del tamaño global de la tabla.</span><span class="sxs-lookup"><span data-stu-id="04f69-123">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04f69-124">Puede combinar las columnas `varchar`, `nvarchar`, `varbinary` o `sql_variant` que hagan que el ancho total definido para la tabla sea superior a 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="04f69-124">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="04f69-125">La longitud de cada una de estas columnas todavía debe estar comprendida en el límite de 8.000 bytes para `varchar` una `nvarchar,``varbinary` columna, o `sql_variant` .</span><span class="sxs-lookup"><span data-stu-id="04f69-125">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `nvarchar,``varbinary`, or `sql_variant` column.</span></span> <span data-ttu-id="04f69-126">Sin embargo, el ancho combinado puede superar el límite de 8.060 bytes de una tabla.</span><span class="sxs-lookup"><span data-stu-id="04f69-126">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="04f69-127">Si no hay columnas de longitud variable, establezca ***Variable_Data_Size*** en 0.</span><span class="sxs-lookup"><span data-stu-id="04f69-127">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="04f69-128">Calcule el tamaño total de la fila:</span><span class="sxs-lookup"><span data-stu-id="04f69-128">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="04f69-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="04f69-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="04f69-130">El valor 4 de la fórmula representa la sobrecarga del encabezado de la fila de datos.</span><span class="sxs-lookup"><span data-stu-id="04f69-130">The value 4 in the formula is the row header overhead of the data row.</span></span>  
  
6.  <span data-ttu-id="04f69-131">Calcule el número de filas por página (8096 bytes libres por página):</span><span class="sxs-lookup"><span data-stu-id="04f69-131">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="04f69-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="04f69-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="04f69-133">Dado que las filas no abarcan varias páginas, el número de filas por página debe redondearse hacia abajo a la fila completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="04f69-133">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="04f69-134">El valor 2 de la fórmula representa la entrada de la fila en la matriz de zonas de la página.</span><span class="sxs-lookup"><span data-stu-id="04f69-134">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
7.  <span data-ttu-id="04f69-135">Calcule el número de páginas necesarias para almacenar todas las filas:</span><span class="sxs-lookup"><span data-stu-id="04f69-135">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="04f69-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span><span class="sxs-lookup"><span data-stu-id="04f69-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span></span>  
  
     <span data-ttu-id="04f69-137">El número de páginas estimado debe redondearse hacia arriba a la página completa más cercana.</span><span class="sxs-lookup"><span data-stu-id="04f69-137">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
8.  <span data-ttu-id="04f69-138">Calcule el espacio necesario para almacenar los datos en el montón (8192 bytes en total por página):</span><span class="sxs-lookup"><span data-stu-id="04f69-138">Calculate the amount of space that is required to store the data in the heap (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="04f69-139">Tamaño del montón (bytes) = 8192 x ***Num_Pages***</span><span class="sxs-lookup"><span data-stu-id="04f69-139">Heap size (bytes) = 8192 x ***Num_Pages***</span></span>  
  
 <span data-ttu-id="04f69-140">En este cálculo no se tiene en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04f69-140">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="04f69-141">Creación de particiones</span><span class="sxs-lookup"><span data-stu-id="04f69-141">Partitioning</span></span>  
  
     <span data-ttu-id="04f69-142">La sobrecarga de espacio de la creación de particiones es mínima, pero resulta difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="04f69-142">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="04f69-143">No es importante incluirla.</span><span class="sxs-lookup"><span data-stu-id="04f69-143">It is not important to include.</span></span>  
  
-   <span data-ttu-id="04f69-144">Páginas de asignación</span><span class="sxs-lookup"><span data-stu-id="04f69-144">Allocation pages</span></span>  
  
     <span data-ttu-id="04f69-145">Se utiliza al menos una página IAM para realizar un seguimiento de las páginas asignadas a un montón, pero la sobrecarga de espacio es mínima y no existe ningún algoritmo para calcular de forma determinista el número exacto de páginas IAM que se utilizarán.</span><span class="sxs-lookup"><span data-stu-id="04f69-145">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="04f69-146">Valores de objetos grandes (LOB)</span><span class="sxs-lookup"><span data-stu-id="04f69-146">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="04f69-147">El algoritmo para determinar exactamente la cantidad de espacio que se utilizará para almacenar los tipos de datos LOB `varchar(max)` ,, `varbinary(max)` `nvarchar(max)` , `text` , **ntextxml**y `image` los valores es complejo.</span><span class="sxs-lookup"><span data-stu-id="04f69-147">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, **ntextxml**, and `image` values is complex.</span></span> <span data-ttu-id="04f69-148">Basta con agregar solamente el tamaño medio de los valores de LOB que se esperan y agregarlo al tamaño total del montón.</span><span class="sxs-lookup"><span data-stu-id="04f69-148">It is sufficient to just add the average size of the LOB values that are expected and add that to the total heap size.</span></span>  
  
-   <span data-ttu-id="04f69-149">Compresión</span><span class="sxs-lookup"><span data-stu-id="04f69-149">Compression</span></span>  
  
     <span data-ttu-id="04f69-150">No se puede calcular previamente el tamaño de un montón comprimido.</span><span class="sxs-lookup"><span data-stu-id="04f69-150">You cannot pre-calculate the size of a compressed heap.</span></span>  
  
-   <span data-ttu-id="04f69-151">Columnas dispersas</span><span class="sxs-lookup"><span data-stu-id="04f69-151">Sparse columns</span></span>  
  
     <span data-ttu-id="04f69-152">Para obtener información sobre los requisitos de espacio de las columnas dispersas, vea [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="04f69-152">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f69-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04f69-153">See Also</span></span>  
 <span data-ttu-id="04f69-154">[Montones &#40;tablas sin índices agrupados&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="04f69-154">[Heaps &#40;Tables without Clustered Indexes&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span></span>  
 <span data-ttu-id="04f69-155">[Índices agrupados y no agrupados descritos](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="04f69-155">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="04f69-156">[Crear índices clúster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="04f69-156">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="04f69-157">[Crear índices no clúster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="04f69-157">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="04f69-158">[Calcular el tamaño de una tabla](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="04f69-158">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="04f69-159">[Estimar el tamaño de un índice agrupado](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="04f69-159">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="04f69-160">[Estimar el tamaño de un índice no clúster](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="04f69-160">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 [<span data-ttu-id="04f69-161">Estimar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="04f69-161">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
