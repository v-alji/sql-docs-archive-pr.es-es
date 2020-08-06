---
title: Tamaño de tabla y fila de las tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b0a248a4-4488-4cc8-89fc-46906a8c24a1
author: rothja
ms.author: jroth
ms.openlocfilehash: 74cc40b7d1f2d0132d79d1e9ae15c2321ac9b74a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750946"
---
# <a name="table-and-row-size-in-memory-optimized-tables"></a><span data-ttu-id="37849-102">Tamaño de tabla y fila de las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="37849-102">Table and Row Size in Memory-Optimized Tables</span></span>
  <span data-ttu-id="37849-103">Una tabla optimizada para memoria consta de una colección de filas e índices que contienen punteros a las filas.</span><span class="sxs-lookup"><span data-stu-id="37849-103">A memory-optimized table consists of a collection of rows and indexes that contain pointers to rows.</span></span> <span data-ttu-id="37849-104">En una tabla optimizada para memoria, las filas no pueden ser mayores de 8060 bytes.</span><span class="sxs-lookup"><span data-stu-id="37849-104">In a memory-optimized table, rows cannot be longer than 8,060 bytes.</span></span> <span data-ttu-id="37849-105">Conocer el tamaño de una tabla optimizada para memoria le ayudará a saber si el equipo tiene memoria suficiente.</span><span class="sxs-lookup"><span data-stu-id="37849-105">Understanding the size of a memory-optimized table will help you understand if your computer has enough memory.</span></span>  
  
 <span data-ttu-id="37849-106">Hay dos motivos para calcular el tamaño de tabla y fila:</span><span class="sxs-lookup"><span data-stu-id="37849-106">There are two reasons for computing table and row size:</span></span>  
  
-   <span data-ttu-id="37849-107">¿Cuánta memoria usa una tabla?</span><span class="sxs-lookup"><span data-stu-id="37849-107">How much memory does a table use?</span></span>  
  
    -   <span data-ttu-id="37849-108">La cantidad de memoria utilizada por la tabla no se puede calcular con precisión.</span><span class="sxs-lookup"><span data-stu-id="37849-108">The amount of memory used by the table cannot be calculated exactly.</span></span> <span data-ttu-id="37849-109">Muchos factores afectan a la cantidad de memoria utilizada.</span><span class="sxs-lookup"><span data-stu-id="37849-109">Many factors affect the amount of memory used.</span></span> <span data-ttu-id="37849-110">Factores como la asignación de memoria basada en páginas, localidad, almacenamiento en caché y relleno.</span><span class="sxs-lookup"><span data-stu-id="37849-110">Factors such as page-based memory allocation, locality, caching, and padding.</span></span> <span data-ttu-id="37849-111">Además, varias versiones de fila que tengan transacciones activas asociadas o que estén esperando para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="37849-111">Also, multiple versions of rows that either have active transactions associated or that are waiting for garbage collection.</span></span>  
  
    -   <span data-ttu-id="37849-112">El tamaño mínimo necesario para los datos y los índices de la tabla viene proporcionado por el cálculo del [tamaño de la tabla], descrito a continuación.</span><span class="sxs-lookup"><span data-stu-id="37849-112">The minimum size required for the data and indexes in the table is given by the calculation for [table size], discussed below.</span></span>  
  
    -   <span data-ttu-id="37849-113">El cálculo del uso de memoria es, en el mejor caso, una aproximación y es preferible incluir el planeamiento de la capacidad en los planes de implementación.</span><span class="sxs-lookup"><span data-stu-id="37849-113">Calculating memory use is at best an approximation and you are advised to include capacity planning in your deployment plans.</span></span>  
  
-   <span data-ttu-id="37849-114">El tamaño de los datos de una fila y si cabe en la limitación de tamaño de fila de 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="37849-114">The data size of a row, and does it fit in the 8,060 byte row size limitation?</span></span> <span data-ttu-id="37849-115">Para responder a estas preguntas, utilice el cálculo del [tamaño del texto de la fila], descrito a continuación.</span><span class="sxs-lookup"><span data-stu-id="37849-115">To answer these questions, use the computation for [row body size], discussed below.</span></span>  
  
 <span data-ttu-id="37849-116">La ilustración siguiente muestra una tabla con índices y filas, que a su vez tienen encabezados de fila y cuerpos:</span><span class="sxs-lookup"><span data-stu-id="37849-116">The following figure illustrates a table with indexes and rows, which in turn have row headers and bodies:</span></span>  
  
 <span data-ttu-id="37849-117">![Tabla con optimización para memoria.](../../database-engine/media/hekaton-guide-1.gif "Tabla optimizada para memoria.")</span><span class="sxs-lookup"><span data-stu-id="37849-117">![Memory optimized table.](../../database-engine/media/hekaton-guide-1.gif "Memory optimized table.")</span></span>  
<span data-ttu-id="37849-118">La tabla con optimización para memoria, que consta de índices y filas.</span><span class="sxs-lookup"><span data-stu-id="37849-118">Memory-optimized table, consisting of indexes and rows.</span></span>  
  
 <span data-ttu-id="37849-119">El tamaño en memoria de una tabla, en bytes, se calcula de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="37849-119">The in-memory size of a table, in bytes, is computed as follows:</span></span>  
  
```  
[table size] = [size of index 1] + ... + [size of index n] + ([row size] * [row count])  
```  
  
 <span data-ttu-id="37849-120">El tamaño de un índice hash se fija en el momento de creación de la tabla y depende del número real de cubos.</span><span class="sxs-lookup"><span data-stu-id="37849-120">The size of a hash index is fixed at table creation time and depends on the actual bucket count.</span></span> <span data-ttu-id="37849-121">El bucket_count especificado con la especificación de índice se redondea a la potencia más cercana de 2 para obtener el [número real de cubos].</span><span class="sxs-lookup"><span data-stu-id="37849-121">The bucket_count specified with the index specification is rounded up to the nearest power of 2 to obtain the [actual bucket count].</span></span> <span data-ttu-id="37849-122">Por ejemplo, si el bucket_count especificado es 100000, el [número real de cubos] para el índice es 131072.</span><span class="sxs-lookup"><span data-stu-id="37849-122">For example, if the specified bucket_count is 100000, the [actual bucket count] for the index is 131072.</span></span>  
  
```  
[hash index size] = 8 * [actual bucket count]  
```  
  
 <span data-ttu-id="37849-123">El tamaño de fila se calcula agregando el encabezado y el cuerpo:</span><span class="sxs-lookup"><span data-stu-id="37849-123">The row size is computed by adding the header and the body:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices]  
```  
  
 <span data-ttu-id="37849-124">**Tamaño del cuerpo de la fila**</span><span class="sxs-lookup"><span data-stu-id="37849-124">**Row body size**</span></span>  
  
 <span data-ttu-id="37849-125">El recálculo de [tamaño del cuerpo de la fila] se describe en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="37849-125">The calculation of [row body size] is discussed in the following table.</span></span>  
  
 <span data-ttu-id="37849-126">Hay dos cálculos diferentes para el tamaño del cuerpo de la fila: el tamaño calculado y el tamaño real:</span><span class="sxs-lookup"><span data-stu-id="37849-126">There are two different computations for row body size: computed size and the actual size:</span></span>  
  
-   <span data-ttu-id="37849-127">El tamaño calculado, indicado mediante el [tamaño del cuerpo calculado de la fila], se utiliza para determinar si la limitación de tamaño de fila de 8.060 bytes se supera.</span><span class="sxs-lookup"><span data-stu-id="37849-127">The computed size, denoted with [computed row body size], is used to determine if the row size limitation of 8,060 bytes is exceeded.</span></span>  
  
-   <span data-ttu-id="37849-128">El tamaño real se indica con [tamaño del texto real de la fila], es el tamaño de almacenamiento real del cuerpo de la fila en memoria y en los archivos de puntos de comprobación.</span><span class="sxs-lookup"><span data-stu-id="37849-128">The actual size, denoted with [actual row body size], is the actual storage size of the row body in memory and in the checkpoint files.</span></span>  
  
 <span data-ttu-id="37849-129">Ambos [tamaño del cuerpo calculado de la fila] y [tamaño del texto real de la fila] se calculan de igual forma.</span><span class="sxs-lookup"><span data-stu-id="37849-129">Both [computed row body size] and [actual row body size] are calculated similarly.</span></span> <span data-ttu-id="37849-130">La única diferencia es el cálculo de tamaño de las columnas (n)varchar(i) y varbinary(i), como se refleja en la parte inferior de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="37849-130">The only difference is the calculation of the size of (n)varchar(i) and varbinary(i) columns, as reflected at the bottom of the following table.</span></span> <span data-ttu-id="37849-131">El tamaño del cuerpo calculado de la fila utiliza el tamaño *i* declarado como tamaño de columna, mientras que el tamaño del cuerpo real de la fila utiliza el tamaño real de los datos.</span><span class="sxs-lookup"><span data-stu-id="37849-131">The computed row body size uses the declared size *i* as the size of the column, while the actual row body size uses the actual size of the data.</span></span>  
  
 <span data-ttu-id="37849-132">En la tabla siguiente se describe el cálculo del tamaño del cuerpo de fila, indicado como [tamaño real del cuerpo de fila] = SUM([tamaño de tipos superficiales]) + 2 + 2 \* [número de columnas de tipo profundo].</span><span class="sxs-lookup"><span data-stu-id="37849-132">The following table describes the calculation of the row body size, given as [actual row body size] = SUM([size of shallow types]) + 2 + 2 \* [number of deep type columns].</span></span>  
  
|<span data-ttu-id="37849-133">Sección</span><span class="sxs-lookup"><span data-stu-id="37849-133">Section</span></span>|<span data-ttu-id="37849-134">Size</span><span class="sxs-lookup"><span data-stu-id="37849-134">Size</span></span>|<span data-ttu-id="37849-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37849-135">Comments</span></span>|  
|-------------|----------|--------------|  
|<span data-ttu-id="37849-136">Columnas de tipo superficial</span><span class="sxs-lookup"><span data-stu-id="37849-136">Shallow type columns</span></span>|<span data-ttu-id="37849-137">SUM ([tamaño de tipos superficiales])</span><span class="sxs-lookup"><span data-stu-id="37849-137">SUM([size of shallow types])</span></span><br /><br /> <span data-ttu-id="37849-138">**El tamaño de los tipos individuales es el siguiente:**</span><span class="sxs-lookup"><span data-stu-id="37849-138">**Size of the individual types is as follows:**</span></span><br /><br /> <span data-ttu-id="37849-139">Bit &#124; 1</span><span class="sxs-lookup"><span data-stu-id="37849-139">Bit &#124; 1</span></span><br /><br /> <span data-ttu-id="37849-140">Tinyint &#124; 1</span><span class="sxs-lookup"><span data-stu-id="37849-140">Tinyint &#124; 1</span></span><br /><br /> <span data-ttu-id="37849-141">Smallint &#124; 2</span><span class="sxs-lookup"><span data-stu-id="37849-141">Smallint &#124; 2</span></span><br /><br /> <span data-ttu-id="37849-142">Int &#124; 4</span><span class="sxs-lookup"><span data-stu-id="37849-142">Int &#124; 4</span></span><br /><br /> <span data-ttu-id="37849-143">Real &#124; 4</span><span class="sxs-lookup"><span data-stu-id="37849-143">Real &#124; 4</span></span><br /><br /> <span data-ttu-id="37849-144">Smalldatetime &#124; 4</span><span class="sxs-lookup"><span data-stu-id="37849-144">Smalldatetime &#124; 4</span></span><br /><br /> <span data-ttu-id="37849-145">Smallmoney &#124; 4</span><span class="sxs-lookup"><span data-stu-id="37849-145">Smallmoney &#124; 4</span></span><br /><br /> <span data-ttu-id="37849-146">Bigint &#124; 8</span><span class="sxs-lookup"><span data-stu-id="37849-146">Bigint &#124; 8</span></span><br /><br /> <span data-ttu-id="37849-147">Datetime &#124; 8</span><span class="sxs-lookup"><span data-stu-id="37849-147">Datetime &#124; 8</span></span><br /><br /> <span data-ttu-id="37849-148">Datetime2 &#124; 8</span><span class="sxs-lookup"><span data-stu-id="37849-148">Datetime2 &#124; 8</span></span><br /><br /> <span data-ttu-id="37849-149">Float 8</span><span class="sxs-lookup"><span data-stu-id="37849-149">Float 8</span></span><br /><br /> <span data-ttu-id="37849-150">Money 8</span><span class="sxs-lookup"><span data-stu-id="37849-150">Money 8</span></span><br /><br /> <span data-ttu-id="37849-151">Numeric (precisión <= 18) &#124; 8</span><span class="sxs-lookup"><span data-stu-id="37849-151">Numeric (precision <=18) &#124; 8</span></span><br /><br /> <span data-ttu-id="37849-152">Time &#124; 8</span><span class="sxs-lookup"><span data-stu-id="37849-152">Time &#124; 8</span></span><br /><br /> <span data-ttu-id="37849-153">Numeric (precisión>18) &#124; 16</span><span class="sxs-lookup"><span data-stu-id="37849-153">Numeric(precision>18) &#124; 16</span></span><br /><br /> <span data-ttu-id="37849-154">Uniqueidentifier &#124; 16</span><span class="sxs-lookup"><span data-stu-id="37849-154">Uniqueidentifier &#124; 16</span></span>||  
|<span data-ttu-id="37849-155">Relleno superficial de la columna</span><span class="sxs-lookup"><span data-stu-id="37849-155">Shallow column padding</span></span>|<span data-ttu-id="37849-156">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="37849-156">Possible values are:</span></span><br /><br /> <span data-ttu-id="37849-157">1, si hay columnas de tipo profundo y el tamaño total de datos de las columnas superficiales es un número impar.</span><span class="sxs-lookup"><span data-stu-id="37849-157">1 if there are deep type columns and the total data size of the shallow columns is as odd number.</span></span><br /><br /> <span data-ttu-id="37849-158">De lo contrario, es 0</span><span class="sxs-lookup"><span data-stu-id="37849-158">0 otherwise</span></span>|<span data-ttu-id="37849-159">Los tipos profundos son (var)binary y (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="37849-159">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="37849-160">Matriz de desplazamiento para las columnas de tipo profundo</span><span class="sxs-lookup"><span data-stu-id="37849-160">Offset array for deep type columns</span></span>|<span data-ttu-id="37849-161">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="37849-161">Possible values are:</span></span><br /><br /> <span data-ttu-id="37849-162">0, si no hay columnas de tipos profundos</span><span class="sxs-lookup"><span data-stu-id="37849-162">0 if there are no deep type columns</span></span><br /><br /> <span data-ttu-id="37849-163">2 + 2 \* [número de columnas de tipo profundo], en caso contrario</span><span class="sxs-lookup"><span data-stu-id="37849-163">2 + 2 \* [number of deep type columns] otherwise</span></span>|<span data-ttu-id="37849-164">Los tipos profundos son (var)binary y (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="37849-164">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="37849-165">Matriz NULL</span><span class="sxs-lookup"><span data-stu-id="37849-165">NULL array</span></span>|<span data-ttu-id="37849-166">[número de columnas que admiten valores NULL] / 8, redondeado a bytes completos.</span><span class="sxs-lookup"><span data-stu-id="37849-166">[number of nullable columns] / 8, rounded up to full bytes.</span></span>|<span data-ttu-id="37849-167">La matriz tiene un bit por cada columna que admite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="37849-167">The array has one bit per nullable column.</span></span> <span data-ttu-id="37849-168">Se redondea a bytes completos.</span><span class="sxs-lookup"><span data-stu-id="37849-168">This is rounded up to full bytes.</span></span>|  
|<span data-ttu-id="37849-169">Relleno de matriz NULL</span><span class="sxs-lookup"><span data-stu-id="37849-169">NULL array padding</span></span>|<span data-ttu-id="37849-170">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="37849-170">Possible values are:</span></span><br /><br /> <span data-ttu-id="37849-171">1, si hay columnas de tipo profundo y el tamaño de la matriz NULL es un número de bytes impar.</span><span class="sxs-lookup"><span data-stu-id="37849-171">1 if there are deep type columns and the size of the NULL array is an odd number of bytes.</span></span><br /><br /> <span data-ttu-id="37849-172">De lo contrario, es 0</span><span class="sxs-lookup"><span data-stu-id="37849-172">0 otherwise</span></span>|<span data-ttu-id="37849-173">Los tipos profundos son (var)binary y (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="37849-173">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="37849-174">Relleno</span><span class="sxs-lookup"><span data-stu-id="37849-174">Padding</span></span>|<span data-ttu-id="37849-175">Si no hay columnas de tipos profundos: 0</span><span class="sxs-lookup"><span data-stu-id="37849-175">If there are no deep type columns: 0</span></span><br /><br /> <span data-ttu-id="37849-176">Si hay columnas de tipo profundo, se agregan los bytes de relleno 0-7, según la alineación mayor requerida por una columna superficial.</span><span class="sxs-lookup"><span data-stu-id="37849-176">If there are deep type columns, 0-7 bytes of padding is added, based on the largest alignment required by a shallow column.</span></span> <span data-ttu-id="37849-177">Cada columna superficial requiere una alineación igual a su tamaño según se documentó anteriormente, salvo en que las columnas GUID necesitan la alineación de 1 byte (no 16) y las columnas numéricas necesitan siempre la alineación de 8 bytes (nunca 16).</span><span class="sxs-lookup"><span data-stu-id="37849-177">Each shallow column requires alignment equal to its size as documented above, except that GUID columns need alignment of 1 byte (not 16) and numeric columns always need alignment of 8 bytes (never 16).</span></span> <span data-ttu-id="37849-178">Se usa el requisito de alineación mayor entre todas las columnas superficiales y se agregan los bytes 0 a 7 de relleno de forma que el tamaño total (sin las columnas de tipo profundo) sea un múltiplo de la alineación requerida.</span><span class="sxs-lookup"><span data-stu-id="37849-178">The largest alignment requirement among all shallow columns is used, and 0-7 bytes of padding is added in such a way that the total size so far (without the deep type columns) is a multiple of the required alignment.</span></span>|<span data-ttu-id="37849-179">Los tipos profundos son (var)binary y (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="37849-179">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="37849-180">Columnas de tipo profundo de longitud fija</span><span class="sxs-lookup"><span data-stu-id="37849-180">Fixed-length deep type columns</span></span>|<span data-ttu-id="37849-181">SUM([tamaño de columnas de tipo profundo de longitud fija])</span><span class="sxs-lookup"><span data-stu-id="37849-181">SUM([size of fixed length deep type columns])</span></span><br /><br /> <span data-ttu-id="37849-182">El tamaño de cada columna es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="37849-182">The size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="37849-183">i para char(i) y binary(i).</span><span class="sxs-lookup"><span data-stu-id="37849-183">i for char(i) and binary(i).</span></span><br /><br /> <span data-ttu-id="37849-184">2 \* i para nchar(i)</span><span class="sxs-lookup"><span data-stu-id="37849-184">2 \* i for nchar(i)</span></span>|<span data-ttu-id="37849-185">Las columnas de tipo profundo de longitud fija son de tipo char(i), nchar(i) o binary(i).</span><span class="sxs-lookup"><span data-stu-id="37849-185">Fixed-length deep type columns are columns of type char(i), nchar(i), or binary(i).</span></span>|  
|<span data-ttu-id="37849-186">Columnas de tipo profundo de longitud variable [tamaño calculado]</span><span class="sxs-lookup"><span data-stu-id="37849-186">Variable length deep type columns [computed size]</span></span>|<span data-ttu-id="37849-187">SUM([tamaño calculado de columnas de tipo profundo de longitud variable])</span><span class="sxs-lookup"><span data-stu-id="37849-187">SUM([computed size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="37849-188">El tamaño calculado de cada columna es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="37849-188">The computed size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="37849-189">i para varchar(i) y varbinary(i)</span><span class="sxs-lookup"><span data-stu-id="37849-189">i for varchar(i) and varbinary(i)</span></span><br /><br /> <span data-ttu-id="37849-190">2 \* i para nvarchar(i)</span><span class="sxs-lookup"><span data-stu-id="37849-190">2 \* i for nvarchar(i)</span></span>|<span data-ttu-id="37849-191">Esta fila solo se aplica al [tamaño del texto calculado de la fila].</span><span class="sxs-lookup"><span data-stu-id="37849-191">This row only applied to [computed row body size].</span></span><br /><br /> <span data-ttu-id="37849-192">Las columnas de tipo profundo de longitud variable son de tipo varchar(i), nvarchar(i) o varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="37849-192">Variable-length deep type columns are columns of type varchar(i), nvarchar(i), or varbinary(i).</span></span> <span data-ttu-id="37849-193">El tamaño calculado se determina mediante la longitud máxima (i) de la columna.</span><span class="sxs-lookup"><span data-stu-id="37849-193">The computed size is determined by the max length (i) of the column.</span></span>|  
|<span data-ttu-id="37849-194">Columnas de tipo profundo de longitud variable [tamaño real]</span><span class="sxs-lookup"><span data-stu-id="37849-194">Variable length deep type columns [actual size]</span></span>|<span data-ttu-id="37849-195">SUM([tamaño real de columnas de tipo profundo de longitud variable])</span><span class="sxs-lookup"><span data-stu-id="37849-195">SUM([actual size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="37849-196">El tamaño real de cada columna es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="37849-196">The actual size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="37849-197">n, donde n es el número de caracteres almacenados en la columna, para varchar(i).</span><span class="sxs-lookup"><span data-stu-id="37849-197">n, where n is the number of characters stored in the column, for varchar(i).</span></span><br /><br /> <span data-ttu-id="37849-198">2 \* n, donde n es el número de caracteres almacenados en la columna, para nvarchar(i).</span><span class="sxs-lookup"><span data-stu-id="37849-198">2 \* n, where n is the number of characters stored in the column, for nvarchar(i).</span></span><br /><br /> <span data-ttu-id="37849-199">n, donde n es el número de bytes almacenados en la columna, para varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="37849-199">n, where n is the number of bytes stored in the column, for varbinary(i).</span></span>|<span data-ttu-id="37849-200">Esta fila solo se aplica al [tamaño del texto real de la fila].</span><span class="sxs-lookup"><span data-stu-id="37849-200">This row only applied to [actual row body size].</span></span><br /><br /> <span data-ttu-id="37849-201">El tamaño real se determina con los datos almacenados en las columnas de la fila.</span><span class="sxs-lookup"><span data-stu-id="37849-201">The actual size is determined by the data stored in the columns in the row.</span></span>|  
  
##  <a name="row-structure"></a><a name="bkmk_RowStructure"></a><span data-ttu-id="37849-202">Estructura de filas</span><span class="sxs-lookup"><span data-stu-id="37849-202">Row Structure</span></span>  
 <span data-ttu-id="37849-203">Las filas de una tabla optimizada para memoria tienen los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="37849-203">The rows in a memory-optimized table have the following components:</span></span>  
  
-   <span data-ttu-id="37849-204">El encabezado de fila contiene la marca de tiempo necesaria para implementar las versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="37849-204">The row header contains the timestamp necessary to implement row versioning.</span></span> <span data-ttu-id="37849-205">El encabezado de fila también contiene el puntero de índice para implementar el encadenamiento de filas en cubos de hash (descritos arriba).</span><span class="sxs-lookup"><span data-stu-id="37849-205">The row header also contains the index pointer to implement the row chaining in the hash buckets (described above).</span></span>  
  
-   <span data-ttu-id="37849-206">El cuerpo de la fila contiene los datos de columna reales, lo que incluye cierta información auxiliar como la matriz NULL para las columnas que aceptan valores NULL y la matriz de desplazamiento para los tipos de datos de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="37849-206">The row body contains the actual column data, which includes some auxiliary information like the null array for nullable columns and the offset array for variable-length data types.</span></span>  
  
 <span data-ttu-id="37849-207">La ilustración siguiente muestra la estructura de la fila de una tabla que tenga dos índices:</span><span class="sxs-lookup"><span data-stu-id="37849-207">The following figure illustrates the row structure for a table that has two indexes:</span></span>  
  
 <span data-ttu-id="37849-208">![Estructura de fila de una tabla que tiene dos índices.](../../database-engine/media/hekaton-tables-4.gif "Estructura de fila de una tabla que tiene dos índices.")</span><span class="sxs-lookup"><span data-stu-id="37849-208">![Row structure for a table that has two indexes.](../../database-engine/media/hekaton-tables-4.gif "Row structure for a table that has two indexes.")</span></span>  
  
 <span data-ttu-id="37849-209">Las marcas de tiempo de inicio y fin indican el periodo en el que una determinada versión de fila es válida.</span><span class="sxs-lookup"><span data-stu-id="37849-209">The begin and end timestamps indicate the period in which a particular row version is valid.</span></span> <span data-ttu-id="37849-210">Las transacciones que se inician en este intervalo pueden ver esta versión de fila.</span><span class="sxs-lookup"><span data-stu-id="37849-210">Transactions that start in this interval can see this row version.</span></span> <span data-ttu-id="37849-211">Para obtener más detalles, consulte [Transacciones en tablas con optimización para memoria](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="37849-211">For more details see [Transactions in Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="37849-212">Los punteros de índice señalan a la siguiente fila de la cadena que pertenece al cubo de hash.</span><span class="sxs-lookup"><span data-stu-id="37849-212">The index pointers point to the next row in the chain belonging to the hash bucket.</span></span> <span data-ttu-id="37849-213">La ilustración siguiente muestra la estructura de una tabla con dos columnas (name, city) y dos índices, uno en el nombre de columna y en otro en la ciudad de la columna.</span><span class="sxs-lookup"><span data-stu-id="37849-213">The following figure illustrates the structure of a table with two columns (name, city), and with two indexes, one on the column name, and one on the column city.</span></span>  
  
 <span data-ttu-id="37849-214">![Estructura de una tabla con dos columnas e índices.](../../database-engine/media/hekaton-tables-5.gif "Estructura de una tabla con dos columnas e índices.")</span><span class="sxs-lookup"><span data-stu-id="37849-214">![Structure of a table with two columns and indexes.](../../database-engine/media/hekaton-tables-5.gif "Structure of a table with two columns and indexes.")</span></span>  
  
 <span data-ttu-id="37849-215">En esta ilustración, se aplica un algoritmo hash a los nombres John y Jane para el primer cubo.</span><span class="sxs-lookup"><span data-stu-id="37849-215">In this figure, the names John and Jane are hashed to the first bucket.</span></span> <span data-ttu-id="37849-216">Se aplica el algoritmo hash a Susan para el segundo cubo.</span><span class="sxs-lookup"><span data-stu-id="37849-216">Susan is hashed to the second bucket.</span></span> <span data-ttu-id="37849-217">Se aplica el algoritmo hash a las ciudades Beijing y Bogotá para el primer cubo.</span><span class="sxs-lookup"><span data-stu-id="37849-217">The cities Beijing and Bogota are hashed to the first bucket.</span></span> <span data-ttu-id="37849-218">Se aplica el algoritmo hash a París y Praga para el segundo cubo.</span><span class="sxs-lookup"><span data-stu-id="37849-218">Paris and Prague are hashed to the second bucket.</span></span>  
  
 <span data-ttu-id="37849-219">Por tanto, las cadenas para el índice hash en el nombre son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="37849-219">Thus, the chains for the hash index on name are as follows:</span></span>  
  
-   <span data-ttu-id="37849-220">Primer cubo: (John, Beijing); (John, París); (Jane, Praga)</span><span class="sxs-lookup"><span data-stu-id="37849-220">First bucket: (John, Beijing); (John, Paris); (Jane, Prague)</span></span>  
  
-   <span data-ttu-id="37849-221">Segundo cubo: (Susan, Bogotá)</span><span class="sxs-lookup"><span data-stu-id="37849-221">Second bucket: (Susan, Bogota)</span></span>  
  
 <span data-ttu-id="37849-222">Las cadenas para el índice de la ciudad son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="37849-222">The chains for the index on city are as follows:</span></span>  
  
-   <span data-ttu-id="37849-223">Primer cubo: (John, Beijing), (Susan, Bogotá)</span><span class="sxs-lookup"><span data-stu-id="37849-223">First bucket: (John, Beijing), (Susan, Bogota)</span></span>  
  
-   <span data-ttu-id="37849-224">Segundo cubo: (John, París), (Jane, Praga)</span><span class="sxs-lookup"><span data-stu-id="37849-224">Second bucket: (John, Paris), (Jane, Prague)</span></span>  
  
 <span data-ttu-id="37849-225">Una marca de tiempo de finalización &#x221e; (infinito) indica que se trata de la versión válida actualmente de la fila.</span><span class="sxs-lookup"><span data-stu-id="37849-225">An end timestamp &#x221e; (infinity) indicates that this is the currently valid version of the row.</span></span> <span data-ttu-id="37849-226">La fila no se ha actualizado ni se ha eliminado desde que esta versión de fila se escribió.</span><span class="sxs-lookup"><span data-stu-id="37849-226">The row has not been updated or deleted since this row version was written.</span></span>  
  
 <span data-ttu-id="37849-227">Para un tiempo mayor que 200, la tabla contiene las filas siguientes:</span><span class="sxs-lookup"><span data-stu-id="37849-227">For a time greater than 200, the table contains the following rows:</span></span>  
  
|<span data-ttu-id="37849-228">Nombre</span><span class="sxs-lookup"><span data-stu-id="37849-228">Name</span></span>|<span data-ttu-id="37849-229">City</span><span class="sxs-lookup"><span data-stu-id="37849-229">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="37849-230">John</span><span class="sxs-lookup"><span data-stu-id="37849-230">John</span></span>|<span data-ttu-id="37849-231">Beijing</span><span class="sxs-lookup"><span data-stu-id="37849-231">Beijing</span></span>|  
|<span data-ttu-id="37849-232">Julia</span><span class="sxs-lookup"><span data-stu-id="37849-232">Jane</span></span>|<span data-ttu-id="37849-233">Praga</span><span class="sxs-lookup"><span data-stu-id="37849-233">Prague</span></span>|  
  
 <span data-ttu-id="37849-234">Sin embargo, cualquier transacción activa con el tiempo de inicio 100 verá la versión siguiente de la tabla:</span><span class="sxs-lookup"><span data-stu-id="37849-234">However, any active transaction with begin time 100 will see the following version of the table:</span></span>  
  
|<span data-ttu-id="37849-235">Nombre</span><span class="sxs-lookup"><span data-stu-id="37849-235">Name</span></span>|<span data-ttu-id="37849-236">City</span><span class="sxs-lookup"><span data-stu-id="37849-236">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="37849-237">John</span><span class="sxs-lookup"><span data-stu-id="37849-237">John</span></span>|<span data-ttu-id="37849-238">Paris</span><span class="sxs-lookup"><span data-stu-id="37849-238">Paris</span></span>|  
|<span data-ttu-id="37849-239">Julia</span><span class="sxs-lookup"><span data-stu-id="37849-239">Jane</span></span>|<span data-ttu-id="37849-240">Praga</span><span class="sxs-lookup"><span data-stu-id="37849-240">Prague</span></span>|  
|<span data-ttu-id="37849-241">Susan</span><span class="sxs-lookup"><span data-stu-id="37849-241">Susan</span></span>|<span data-ttu-id="37849-242">Bogotá</span><span class="sxs-lookup"><span data-stu-id="37849-242">Bogata</span></span>|  
  
##  <a name="example-table-and-row-size-computation"></a><a name="bkmk_ExampleComputation"></a> <span data-ttu-id="37849-243">Ejemplo: cálculo del tamaño de fila y tabla</span><span class="sxs-lookup"><span data-stu-id="37849-243">Example: Table and Row Size Computation</span></span>  
 <span data-ttu-id="37849-244">Para los índices hash, el número de cubos real se redondea a la potencia más cercana de 2.</span><span class="sxs-lookup"><span data-stu-id="37849-244">For hash indexes, the actual bucket count is rounded up to the nearest power of 2.</span></span> <span data-ttu-id="37849-245">Por ejemplo, si el bucket_count especificado es 100000, el número real de cubos para el índice es 131072.</span><span class="sxs-lookup"><span data-stu-id="37849-245">For example, if the specified bucket_count is 100000, the actual bucket count for the index is 131072.</span></span>  
  
 <span data-ttu-id="37849-246">Considere una tabla Orders con la definición siguiente:</span><span class="sxs-lookup"><span data-stu-id="37849-246">Consider an Orders table with the following definition:</span></span>  
  
```sql  
CREATE TABLE dbo.Orders (  
     OrderID int NOT NULL   
           PRIMARY KEY NONCLUSTERED,  
     CustomerID int NOT NULL   
           INDEX IX_CustomerID HASH WITH (BUCKET_COUNT=10000),  
     OrderDate datetime NOT NULL,  
     OrderDescription nvarchar(1000)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
```  
  
 <span data-ttu-id="37849-247">Observe que esta tabla tiene un índice hash y un índice no clúster (la clave principal).</span><span class="sxs-lookup"><span data-stu-id="37849-247">Notice that this table has one hash index and a nonclustered index (the primary key).</span></span> <span data-ttu-id="37849-248">También tiene tres columnas de longitud fija y una columna de longitud variable, con una de las columnas que admiten valores NULL (OrderDescription).</span><span class="sxs-lookup"><span data-stu-id="37849-248">It also has three fixed-length columns and one variable-length column, with one of the columns being NULLable (OrderDescription).</span></span> <span data-ttu-id="37849-249">Supongamos que la tabla Orders tiene 8379 filas y que la longitud media de los valores de la columna OrderDescription es de 78 caracteres.</span><span class="sxs-lookup"><span data-stu-id="37849-249">Let's assume the Orders table has 8379 rows, and the average length of the values in the OrderDescription column is 78 characters.</span></span>  
  
 <span data-ttu-id="37849-250">Para determinar el tamaño de la tabla, primero determine el tamaño de los índices.</span><span class="sxs-lookup"><span data-stu-id="37849-250">To determine the table size, first determine the size of the indexes.</span></span> <span data-ttu-id="37849-251">El bucket_count para ambos índices se especifica como 10000.</span><span class="sxs-lookup"><span data-stu-id="37849-251">The bucket_count for both indexes is specified as 10000.</span></span> <span data-ttu-id="37849-252">Se redondea a la potencia más cercana de 2: 16384.</span><span class="sxs-lookup"><span data-stu-id="37849-252">This is rounded up to the nearest power of 2: 16384.</span></span> <span data-ttu-id="37849-253">Por consiguiente, el tamaño total de los índices de la tabla Orders es:</span><span class="sxs-lookup"><span data-stu-id="37849-253">Therefore, the total size of the indexes for the Orders table is:</span></span>  
  
```  
8 * 16384 = 131072 bytes  
```  
  
 <span data-ttu-id="37849-254">Lo que permanece en el tamaño de los datos de la tabla, que es</span><span class="sxs-lookup"><span data-stu-id="37849-254">What remains is the table data size, which is,</span></span>  
  
```  
[row size] * [row count] = [row size] * 8379  
```  
  
 <span data-ttu-id="37849-255">(La tabla de ejemplo tiene 8379 filas.) Ahora, tenemos:</span><span class="sxs-lookup"><span data-stu-id="37849-255">(The example table has 8379 rows.) Now, we have:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices] = 24 + 8 * 1 = 32 bytes  
```  
  
 <span data-ttu-id="37849-256">A continuación, vamos a calcular [tamaño del cuerpo real de la fila]:</span><span class="sxs-lookup"><span data-stu-id="37849-256">Next, let's calculate [actual row body size]:</span></span>  
  
-   <span data-ttu-id="37849-257">Columnas de tipo superficial:</span><span class="sxs-lookup"><span data-stu-id="37849-257">Shallow type columns:</span></span>  
  
    ```  
    SUM([size of shallow types]) = 4 [int] + 4 [int] + 8 [datetime] = 16  
    ```  
  
-   <span data-ttu-id="37849-258">El relleno superficial de la columna es 0, ya que el tamaño total de la columna es uniforme.</span><span class="sxs-lookup"><span data-stu-id="37849-258">Shallow column padding is 0, as the total shallow column size is even.</span></span>  
  
-   <span data-ttu-id="37849-259">Matriz de desplazamiento para las columnas de tipo profundo:</span><span class="sxs-lookup"><span data-stu-id="37849-259">Offset array for deep type columns:</span></span>  
  
    ```  
    2 + 2 * [number of deep type columns] = 2 + 2 * 1 = 4  
    ```  
  
-   <span data-ttu-id="37849-260">Matriz NULL = 1</span><span class="sxs-lookup"><span data-stu-id="37849-260">NULL array = 1</span></span>  
  
-   <span data-ttu-id="37849-261">El relleno NULL de matriz = 1, como el tamaño de la matriz NULL es impar y hay una columna de tipo profundo.</span><span class="sxs-lookup"><span data-stu-id="37849-261">NULL array padding = 1, as the NULL array size is odd and there is a deep type column.</span></span>  
  
-   <span data-ttu-id="37849-262">Relleno</span><span class="sxs-lookup"><span data-stu-id="37849-262">Padding</span></span>  
  
    -   <span data-ttu-id="37849-263">8 es el requisito mayor de alineación.</span><span class="sxs-lookup"><span data-stu-id="37849-263">8 is the largest alignment requirement.</span></span>  
  
    -   <span data-ttu-id="37849-264">El tamaño es hasta ahora 16 + 0 + 4 + 1 + 1 = 22.</span><span class="sxs-lookup"><span data-stu-id="37849-264">Size so far is 16 + 0 + 4 + 1 + 1 = 22.</span></span>  
  
    -   <span data-ttu-id="37849-265">El múltiplo más cercano de 8 es 24.</span><span class="sxs-lookup"><span data-stu-id="37849-265">Nearest multiple of 8 is 24.</span></span>  
  
    -   <span data-ttu-id="37849-266">El relleno total es 24 - 22 = 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="37849-266">Total padding is 24 - 22 = 2 bytes.</span></span>  
  
-   <span data-ttu-id="37849-267">No hay columnas de tipo profundo de longitud fija (columnas de tipo profundo de longitud fija: 0.).</span><span class="sxs-lookup"><span data-stu-id="37849-267">There are no fixed-length deep type columns (Fixed-length deep type columns: 0.).</span></span>  
  
-   <span data-ttu-id="37849-268">El tamaño real de la columna de tipo profundo es 2 \* 78 = 156.</span><span class="sxs-lookup"><span data-stu-id="37849-268">The actual size of deep type column is 2 \* 78 = 156.</span></span> <span data-ttu-id="37849-269">La única columna de tipo profundo OrderDescription tiene el tipo nvarchar.</span><span class="sxs-lookup"><span data-stu-id="37849-269">The single deep type column OrderDescription has type nvarchar.</span></span>  
  
```  
[actual row body size] = 24 + 156 = 180 bytes  
```  
  
 <span data-ttu-id="37849-270">Para completar el cálculo:</span><span class="sxs-lookup"><span data-stu-id="37849-270">To complete the calculation:</span></span>  
  
```  
[row size] = 32 + 180 = 212 bytes  
[table size] = 8 * 16384 + 212 * 8379 = 131072 + 1776348 = 1907420  
```  
  
 <span data-ttu-id="37849-271">El tamaño total de la tabla en memoria es de aproximadamente 2 megabytes.</span><span class="sxs-lookup"><span data-stu-id="37849-271">Total table size in memory is thus approximately 2 megabytes.</span></span> <span data-ttu-id="37849-272">Esto no tiene en cuenta la sobrecarga potencial provocada por la asignación de memoria junto con las versiones de fila necesarias para las transacciones que tienen acceso a esta tabla.</span><span class="sxs-lookup"><span data-stu-id="37849-272">This does not account for potential overhead incurred by memory allocation as well as any row versioning required for the transactions accessing this table.</span></span>  
  
 <span data-ttu-id="37849-273">La memoria real asignada a esta tabla y usada por ella y sus índices se pueden obtener con la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="37849-273">The actual memory allocated for and used by this table and its indexes can be obtained through the following query:</span></span>  
  
```sql  
select * from sys.dm_db_xtp_table_memory_stats  
where object_id = object_id('dbo.Orders')  
```  
  
## <a name="see-also"></a><span data-ttu-id="37849-274">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37849-274">See Also</span></span>  
 [<span data-ttu-id="37849-275">Tablas optimizadas para la memoria</span><span class="sxs-lookup"><span data-stu-id="37849-275">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
