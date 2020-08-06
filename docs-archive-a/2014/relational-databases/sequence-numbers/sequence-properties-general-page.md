---
title: Propiedades de secuencia (página General) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.sequence.general.f1
ms.assetid: 0187f413-cdf0-48a2-b2e6-9b3578cd5811
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6fc969dc09663da8150461529ad1e1f1fb094539
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750581"
---
# <a name="sequence-properties-general-page"></a><span data-ttu-id="88a96-102">Propiedades de secuencia (página General)</span><span class="sxs-lookup"><span data-stu-id="88a96-102">Sequence Properties (General Page)</span></span>
  <span data-ttu-id="88a96-103">Crea un objeto de secuencia y especifica sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="88a96-103">Creates a sequence object and specifies its properties.</span></span> <span data-ttu-id="88a96-104">Una secuencia es un objeto enlazado a un esquema definido por el usuario que genera una secuencia de valores numéricos según la especificación con la que se creó la secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-104">A sequence is a user-defined schema bound object that generates a sequence of numeric values according to the specification with which the sequence was created.</span></span> <span data-ttu-id="88a96-105">La secuencia de valores numéricos se genera en orden ascendente o descendente en un intervalo definido y se puede configurar para reiniciarse (en un ciclo) cuando se agota.</span><span class="sxs-lookup"><span data-stu-id="88a96-105">The sequence of numeric values is generated in an ascending or descending order at a defined interval and can be configured to restart (cycle) when exhausted.</span></span> <span data-ttu-id="88a96-106">Las secuencias, a diferencia de las columnas de identidad, no se asocian a tablas concretas.</span><span class="sxs-lookup"><span data-stu-id="88a96-106">Sequences, unlike identity columns, are not associated with specific tables.</span></span> <span data-ttu-id="88a96-107">Las aplicaciones hacen referencia a un objeto de secuencia para recuperar su valor siguiente.</span><span class="sxs-lookup"><span data-stu-id="88a96-107">Applications refer to a sequence object to retrieve its next value.</span></span> <span data-ttu-id="88a96-108">La aplicación controla la relación entre las secuencias y tablas.</span><span class="sxs-lookup"><span data-stu-id="88a96-108">The relationship between sequences and tables is controlled by the application.</span></span> <span data-ttu-id="88a96-109">Las aplicaciones de usuario pueden hacer referencia un objeto de secuencia y coordinar los valores a través de varias filas y tablas.</span><span class="sxs-lookup"><span data-stu-id="88a96-109">User applications can reference a sequence object and coordinate the values across multiple rows and tables.</span></span>  
  
 <span data-ttu-id="88a96-110">A diferencia de los valores de columnas de identidad que se generan en el momento en que se insertan filas, una aplicación puede obtener el número de secuencia siguiente sin insertar la fila llamando a la [función NEXT VALUE FOR](/sql/t-sql/functions/next-value-for-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="88a96-110">Unlike identity columns values which are generated at the time of insert, an application can obtain the next sequence number without inserting the row by calling the [NEXT VALUE FOR function](/sql/t-sql/functions/next-value-for-transact-sql).</span></span> <span data-ttu-id="88a96-111">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) para obtener varios números de secuencia a la vez.</span><span class="sxs-lookup"><span data-stu-id="88a96-111">Use [sp_sequence_get_range](/sql/relational-databases/system-stored-procedures/sp-sequence-get-range-transact-sql) to get multiple sequence numbers at once.</span></span>  
  
 <span data-ttu-id="88a96-112">Para obtener información sobre las funciones **CREATE SEQUENCE** y **NEXT VALUE FOR** y escenarios en los que se usan, vea [Números de secuencia](sequence-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="88a96-112">For information and scenarios that use both **CREATE SEQUENCE** and the **NEXT VALUE FOR** function, see [Sequence Numbers](sequence-numbers.md).</span></span>  
  
 <span data-ttu-id="88a96-113">Se puede obtener acceso a esta página de dos formas: haciendo clic con el botón derecho en **Secuencias** en el Explorador de objetos y haciendo clic en **Nueva secuencia**, o haciendo clic con el botón derecho en una secuencia existente y haciendo clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="88a96-113">This page is accessed in two ways: either by right-clicking **Sequences** in Object Explorer and clicking **New Sequence**, or by right-clicking an existing sequence and clicking **Properties**.</span></span> <span data-ttu-id="88a96-114">Cuando se hace clic con el botón derecho en una secuencia existente y se hace clic en **Propiedades**, no se pueden editar las opciones.</span><span class="sxs-lookup"><span data-stu-id="88a96-114">When you right-click an existing sequence and click **Properties**, the options are not editable.</span></span> <span data-ttu-id="88a96-115">Para cambiar las opciones de secuencia use la instrucción [ALTER SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-sequence-transact-sql) o quite y vuelva a crear el objeto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-115">To change the sequence options use the [ALTER SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-sequence-transact-sql) statement or drop and recreate the sequence object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="88a96-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="88a96-116">Options</span></span>  
 <span data-ttu-id="88a96-117">**Nombre de secuencia**</span><span class="sxs-lookup"><span data-stu-id="88a96-117">**Sequence name**</span></span>  
 <span data-ttu-id="88a96-118">Escriba aquí el nombre de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-118">Enter the sequence name here.</span></span>  
  
 <span data-ttu-id="88a96-119">**Esquema de secuencia**</span><span class="sxs-lookup"><span data-stu-id="88a96-119">**Sequence schema**</span></span>  
 <span data-ttu-id="88a96-120">Especifique el esquema que será el propietario de este flujo.</span><span class="sxs-lookup"><span data-stu-id="88a96-120">Specify the schema that will own this sequence.</span></span>  
  
 <span data-ttu-id="88a96-121">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="88a96-121">**Data type**</span></span>  
 <span data-ttu-id="88a96-122">Una secuencia se puede definir como de cualquier tipo entero.</span><span class="sxs-lookup"><span data-stu-id="88a96-122">A sequence can be defined as any integer type.</span></span> <span data-ttu-id="88a96-123">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="88a96-123">This includes:</span></span>  
  
|<span data-ttu-id="88a96-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="88a96-124">Data type</span></span>|<span data-ttu-id="88a96-125">Intervalo</span><span class="sxs-lookup"><span data-stu-id="88a96-125">Range</span></span>|  
|---------------|-----------|  
|`tinyint`|<span data-ttu-id="88a96-126">De 0 a 255</span><span class="sxs-lookup"><span data-stu-id="88a96-126">0 to 255</span></span>|  
|`smallint`|<span data-ttu-id="88a96-127">De -32 768 a 32 767</span><span class="sxs-lookup"><span data-stu-id="88a96-127">-32,768 to 32,767</span></span>|  
|`int`|<span data-ttu-id="88a96-128">De -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="88a96-128">-2,147,483,648 to 2,147,483,647</span></span>|  
|`bigint`|<span data-ttu-id="88a96-129">De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807</span><span class="sxs-lookup"><span data-stu-id="88a96-129">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|  
  
-   <span data-ttu-id="88a96-130">`decimal` o `numeric` con una escala de 0.</span><span class="sxs-lookup"><span data-stu-id="88a96-130">`decimal` or `numeric` with a scale of 0.</span></span>  
  
-   <span data-ttu-id="88a96-131">Cualquier tipo de datos definido por el usuario (tipo de alias) que se base en estos tipos.</span><span class="sxs-lookup"><span data-stu-id="88a96-131">Any user-defined data type (alias type) that is based on one of these types.</span></span>  
  
 <span data-ttu-id="88a96-132">**Precisión**</span><span class="sxs-lookup"><span data-stu-id="88a96-132">**Precision**</span></span>  
 <span data-ttu-id="88a96-133">Para los tipos de datos `decimal` o `numeric`, especifique la precisión.</span><span class="sxs-lookup"><span data-stu-id="88a96-133">For `decimal` or `numeric` data types, specify the precision.</span></span> <span data-ttu-id="88a96-134">(La escala siempre es 0).</span><span class="sxs-lookup"><span data-stu-id="88a96-134">(The scale is always 0.)</span></span>  
  
 <span data-ttu-id="88a96-135">**Valor inicial**</span><span class="sxs-lookup"><span data-stu-id="88a96-135">**Start with value**</span></span>  
 <span data-ttu-id="88a96-136">El primer valor que el objeto de secuencia devolverá.</span><span class="sxs-lookup"><span data-stu-id="88a96-136">The first value that will be returned by the sequence object.</span></span> <span data-ttu-id="88a96-137">El valor **START** debe ser menor o igual que el máximo, y mayor o igual que el valor mínimo del objeto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-137">The **START** value must be a value that is less than or equal to the maximum and greater than or equal to the minimum value of the sequence object.</span></span> <span data-ttu-id="88a96-138">El valor inicial predeterminado para un nuevo objeto de secuencia es el valor mínimo para un objeto de secuencia ascendente y el valor máximo para uno descendente.</span><span class="sxs-lookup"><span data-stu-id="88a96-138">The default start value for a new sequence object is the minimum value for an ascending sequence object and the maximum value for a descending sequence object.</span></span>  
  
 <span data-ttu-id="88a96-139">**Incrementar en**</span><span class="sxs-lookup"><span data-stu-id="88a96-139">**Increment by**</span></span>  
 <span data-ttu-id="88a96-140">Valor que se usa para incrementar (o disminuir si es negativo) el valor del objeto de secuencia para cada llamada a la función **NEXT VALUE FOR** .</span><span class="sxs-lookup"><span data-stu-id="88a96-140">The value that is used to increment (or decrement if negative) the value of the sequence object for each call to the **NEXT VALUE FOR** function.</span></span> <span data-ttu-id="88a96-141">Si el incremento es un valor negativo el objeto de secuencia es descendente, de lo contrario, es ascendente.</span><span class="sxs-lookup"><span data-stu-id="88a96-141">If the increment is a negative value the sequence object is descending, otherwise, it is ascending.</span></span> <span data-ttu-id="88a96-142">El incremento no puede ser 0.</span><span class="sxs-lookup"><span data-stu-id="88a96-142">The increment cannot be 0.</span></span>  
  
 <span data-ttu-id="88a96-143">**Valor mínimo**</span><span class="sxs-lookup"><span data-stu-id="88a96-143">**Minimum value**</span></span>  
 <span data-ttu-id="88a96-144">Especifica los límites del objeto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-144">Specifies the bounds for sequence object.</span></span> <span data-ttu-id="88a96-145">El valor mínimo predeterminado para un nuevo objeto de secuencia es el valor mínimo del tipo de datos del objeto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-145">The default minimum value for a new sequence object is the minimum value of the data type of the sequence object.</span></span> <span data-ttu-id="88a96-146">Es cero para el tipo de datos `tinyint` y un número negativo para todos los demás.</span><span class="sxs-lookup"><span data-stu-id="88a96-146">This is zero for the `tinyint` data type and a negative number for all other data types.</span></span>  
  
 <span data-ttu-id="88a96-147">**Valor máximo**</span><span class="sxs-lookup"><span data-stu-id="88a96-147">**Maximum value**</span></span>  
 <span data-ttu-id="88a96-148">Especifica los límites del objeto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-148">Specifies the bounds for sequence object.</span></span> <span data-ttu-id="88a96-149">El valor máximo predeterminado para un nuevo objeto de secuencia es el valor máximo del tipo de datos del objeto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-149">The default maximum value for a new sequence object is the maximum value of the data type of the sequence object.</span></span>  
  
 <span data-ttu-id="88a96-150">**La secuencia de ciclos se reiniciará al llegar al límite**</span><span class="sxs-lookup"><span data-stu-id="88a96-150">**Cycle-sequence will restart on reaching limit**</span></span>  
 <span data-ttu-id="88a96-151">Seleccione el objeto de secuencia para permitir el reinicio a partir del valor mínimo (o máximo para objetos de secuencia descendente) cuando se supere su valor mínimo o máximo.</span><span class="sxs-lookup"><span data-stu-id="88a96-151">Select to allow the sequence object to restart from the minimum value (or maximum for descending sequence objects) when its minimum or maximum value is exceeded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88a96-152">Los ciclos no se reinician a partir del valor inicial, sino a partir del valor mínimo o máximo.</span><span class="sxs-lookup"><span data-stu-id="88a96-152">Cycling does not restart from the start value but rather from the minimum/maximum value.</span></span>  
  
 <span data-ttu-id="88a96-153">**Opciones de caché**</span><span class="sxs-lookup"><span data-stu-id="88a96-153">**Cache options**</span></span>  
 <span data-ttu-id="88a96-154">La creación de una memoria caché de valores de secuencia puede incrementar el rendimiento de las aplicaciones que usen objetos de secuencia minimizando el número de las E/S de disco requeridas para crear números de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-154">Creating a cache of sequence values can increase performance for applications that use sequence objects by minimizing the number of disk IOs that are required to create sequence numbers.</span></span>  
  
-   <span data-ttu-id="88a96-155">Tamaño de memoria caché predeterminado: el [!INCLUDE[ssDE](../../includes/ssde-md.md)] seleccionará un tamaño, pero los usuarios no deben confiar en que la selección sea coherente.</span><span class="sxs-lookup"><span data-stu-id="88a96-155">Default cache size - The [!INCLUDE[ssDE](../../includes/ssde-md.md)] will select a size, however users should not rely upon the selection being consistent.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="88a96-156">puede cambiar el método de cálculo del tamaño de la memoria caché sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="88a96-156">might change the method of calculating the cache size without notice.</span></span>  
  
-   <span data-ttu-id="88a96-157">Sin memoria caché: [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no almacenará en la memoria caché los números de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-157">No cache - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] will not cache sequence numbers.</span></span>  
  
-   <span data-ttu-id="88a96-158">Memoria caché con tamaño: [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] almacenará en la memoria caché los valores de secuencia.</span><span class="sxs-lookup"><span data-stu-id="88a96-158">Cache with size - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] will cache sequence values.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="88a96-159">realiza el seguimiento del valor actual y del número de valores que queden en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="88a96-159">keeps track of the current value and the number of values left in the cache.</span></span> <span data-ttu-id="88a96-160">Por consiguiente, la cantidad de memoria necesaria para almacenar la memoria caché siempre es dos veces la del tipo de datos del objeto de secuencia</span><span class="sxs-lookup"><span data-stu-id="88a96-160">Therefore, the amount of memory that is required to store the cache is always two instances of the data type of the sequence object</span></span>  
  
 <span data-ttu-id="88a96-161">Cuando se crea con la opción CACHE, un cierre inesperado, como un error de alimentación, puede perder los números de secuencia de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="88a96-161">When created with the CACHE option, an unexpected shutdown, such as a power failure, can lose the sequence numbers in the cache.</span></span>  
  
 <span data-ttu-id="88a96-162">Para obtener información adicional sobre las opciones de creación de secuencias, vea [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="88a96-162">For additional information about the create sequence options, see [CREATE SEQUENCE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-sequence-transact-sql).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="88a96-163">Permisos</span><span class="sxs-lookup"><span data-stu-id="88a96-163">Permissions</span></span>  
 <span data-ttu-id="88a96-164">Requiere el permiso **CREATE SEQUENCE**, **ALTER**o **CONTROL** en el SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="88a96-164">Requires **CREATE SEQUENCE**, **ALTER**, or **CONTROL** permission on the SCHEMA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88a96-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88a96-165">See Also</span></span>  
 [<span data-ttu-id="88a96-166">sys.sequences &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="88a96-166">sys.sequences &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sequences-transact-sql)  
  
  