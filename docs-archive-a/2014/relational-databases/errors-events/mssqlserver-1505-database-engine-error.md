---
title: MSSQLSERVER_1505 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1505 (Database Engine error)
ms.assetid: ef4df75d-0f36-4c8b-b36c-e427f65f91ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c152404cf2d3710bbe98b29da7a96d86f58859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745321"
---
# <a name="mssqlserver_1505"></a><span data-ttu-id="5e7a4-102">MSSQLSERVER_1505</span><span class="sxs-lookup"><span data-stu-id="5e7a4-102">MSSQLSERVER_1505</span></span>
    
## <a name="details"></a><span data-ttu-id="5e7a4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5e7a4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e7a4-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5e7a4-104">Product Name</span></span>|<span data-ttu-id="5e7a4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e7a4-105">SQL Server</span></span>|  
|<span data-ttu-id="5e7a4-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5e7a4-106">Event ID</span></span>|<span data-ttu-id="5e7a4-107">1505</span><span class="sxs-lookup"><span data-stu-id="5e7a4-107">1505</span></span>|  
|<span data-ttu-id="5e7a4-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5e7a4-108">Event Source</span></span>|<span data-ttu-id="5e7a4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5e7a4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5e7a4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5e7a4-110">Component</span></span>|<span data-ttu-id="5e7a4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5e7a4-111">SQLEngine</span></span>|  
|<span data-ttu-id="5e7a4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5e7a4-112">Symbolic Name</span></span>|<span data-ttu-id="5e7a4-113">DUP_KEY</span><span class="sxs-lookup"><span data-stu-id="5e7a4-113">DUP_KEY</span></span>|  
|<span data-ttu-id="5e7a4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5e7a4-114">Message Text</span></span>|<span data-ttu-id="5e7a4-115">La instrucción CREATE UNIQUE INDEX terminó porque se encontró una clave duplicada para el nombre de objeto "%.\*ls" y el nombre de índice "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="5e7a4-115">CREATE UNIQUE INDEX terminated because a duplicate key was found for object name '%.\*ls' and index name '%.\*ls'.</span></span>  <span data-ttu-id="5e7a4-116">El valor de la clave duplicada es %ls.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-116">The duplicate key value is %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5e7a4-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="5e7a4-117">Explanation</span></span>  
 <span data-ttu-id="5e7a4-118">Este error se produce cuando se intenta crear un índice único y más de una fila de la tabla contiene el valor duplicado especificado.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-118">This error occurs when you attempt to create a unique index and more than one row in the table contains the specified duplicate value.</span></span> <span data-ttu-id="5e7a4-119">Un índice único se crea cuando se crea un índice y se especifica la palabra clave UNIQUE, o cuando se crea una restricción UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-119">A unique index is created when you create an index and specify the UNIQUE keyword, or when you create a UNIQUE constraint.</span></span> <span data-ttu-id="5e7a4-120">La tabla no puede contener filas que tengan valores duplicados en las columnas definidas en el índice o la restricción.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-120">The table cannot contain any rows that have duplicate values in the columns defined in the index or constraint.</span></span>  
  
 <span data-ttu-id="5e7a4-121">Considere los datos de la tabla **Employee** siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e7a4-121">Consider the data in the following **Employee** table:</span></span>  
  
|<span data-ttu-id="5e7a4-122">Apellidos</span><span class="sxs-lookup"><span data-stu-id="5e7a4-122">LastName</span></span>|<span data-ttu-id="5e7a4-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="5e7a4-123">FirstName</span></span>|<span data-ttu-id="5e7a4-124">JobTitle</span><span class="sxs-lookup"><span data-stu-id="5e7a4-124">JobTitle</span></span>|<span data-ttu-id="5e7a4-125">HireDate</span><span class="sxs-lookup"><span data-stu-id="5e7a4-125">HireDate</span></span>|  
|--------------|---------------|--------------|--------------|  
|<span data-ttu-id="5e7a4-126">Walters</span><span class="sxs-lookup"><span data-stu-id="5e7a4-126">Walters</span></span>|<span data-ttu-id="5e7a4-127">Rob</span><span class="sxs-lookup"><span data-stu-id="5e7a4-127">Rob</span></span>|<span data-ttu-id="5e7a4-128">Senior Tool Designer</span><span class="sxs-lookup"><span data-stu-id="5e7a4-128">Senior Tool Designer</span></span>|<span data-ttu-id="5e7a4-129">2004-11-19</span><span class="sxs-lookup"><span data-stu-id="5e7a4-129">2004-11-19</span></span>|  
|<span data-ttu-id="5e7a4-130">Brown</span><span class="sxs-lookup"><span data-stu-id="5e7a4-130">Brown</span></span>|<span data-ttu-id="5e7a4-131">Kevin</span><span class="sxs-lookup"><span data-stu-id="5e7a4-131">Kevin</span></span>|<span data-ttu-id="5e7a4-132">Marketing Assistant</span><span class="sxs-lookup"><span data-stu-id="5e7a4-132">Marketing Assistant</span></span>|<span data-ttu-id="5e7a4-133">NULL</span><span class="sxs-lookup"><span data-stu-id="5e7a4-133">NULL</span></span>|  
|<span data-ttu-id="5e7a4-134">Brown</span><span class="sxs-lookup"><span data-stu-id="5e7a4-134">Brown</span></span>|<span data-ttu-id="5e7a4-135">Jo</span><span class="sxs-lookup"><span data-stu-id="5e7a4-135">Jo</span></span>|<span data-ttu-id="5e7a4-136">Design Engineer</span><span class="sxs-lookup"><span data-stu-id="5e7a4-136">Design Engineer</span></span>|<span data-ttu-id="5e7a4-137">NULL</span><span class="sxs-lookup"><span data-stu-id="5e7a4-137">NULL</span></span>|  
|<span data-ttu-id="5e7a4-138">Walters</span><span class="sxs-lookup"><span data-stu-id="5e7a4-138">Walters</span></span>|<span data-ttu-id="5e7a4-139">Rob</span><span class="sxs-lookup"><span data-stu-id="5e7a4-139">Rob</span></span>|<span data-ttu-id="5e7a4-140">Tool Designer</span><span class="sxs-lookup"><span data-stu-id="5e7a4-140">Tool Designer</span></span>|<span data-ttu-id="5e7a4-141">2001-08-09</span><span class="sxs-lookup"><span data-stu-id="5e7a4-141">2001-08-09</span></span>|  
  
 <span data-ttu-id="5e7a4-142">No se puede crear un índice único en las combinaciones de columnas **LastName** o **LastName**, **FirstName** debido a la presencia de valores duplicados en las filas.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-142">A unique index can not be created on the column combinations **LastName** or **LastName**, **FirstName** because of duplicate values in the rows.</span></span>  
  
 <span data-ttu-id="5e7a4-143">Menos obvia es la posibilidad de una infracción de unicidad en la columna **HireDate**.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-143">Less obvious is the potential for a uniqueness violation in the **HireDate** column.</span></span> <span data-ttu-id="5e7a4-144">A efectos de índices, los valores NULL son comparables a igual.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-144">For indexing purposes, NULL values compare as equal.</span></span> <span data-ttu-id="5e7a4-145">Por lo tanto, no se puede crear un índice o una restricción únicos si los valores de clave son NULL en más de una fila.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-145">Therefore, you cannot create a unique index or constraint if the key values are NULL in more than one row.</span></span> <span data-ttu-id="5e7a4-146">Dados los datos anteriores, no se puede crear un índice único en las combinaciones de columnas **HireDate** o **LastName**, **HireDate**.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-146">Given the data above, a unique index cannot be created on the column combinations **HireDate** or **LastName**, **HireDate**.</span></span>  
  
 <span data-ttu-id="5e7a4-147">El mensaje de error 1505 devuelve la primera fila que infringe la restricción de unicidad.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-147">Error message 1505 returns the first row that violates the uniqueness constraint.</span></span> <span data-ttu-id="5e7a4-148">Puede haber otras filas duplicadas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-148">There may be other duplicate rows in the table.</span></span> <span data-ttu-id="5e7a4-149">Para encontrar todas las filas duplicadas, consulte la tabla especificada y utilice las cláusulas GROUP BY y HAVING para notificar las filas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-149">To find all duplicate rows, query the specified table and use the GROUP BY and HAVING clauses to report the duplicate rows.</span></span> <span data-ttu-id="5e7a4-150">Por ejemplo, la siguiente consulta devuelve las filas de la tabla **Employee** que tengan nombres y apellidos duplicados.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-150">For example, the following query returns the rows in the **Employee** table that have duplicate first and last names.</span></span>  
  
 <span data-ttu-id="5e7a4-151">Seleccione LastName, FirstName, Count ( \* ) de DBO. Employee GROUP BY LastName, FirstName tiene Count ( \* ) > 1;</span><span class="sxs-lookup"><span data-stu-id="5e7a4-151">SELECT LastName, FirstName, count(\*) FROM dbo.Employee GROUP BY LastName, FirstName HAVING count(\*) > 1;</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e7a4-152">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5e7a4-152">User Action</span></span>  
 <span data-ttu-id="5e7a4-153">Considere las soluciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-153">Consider the following solutions.</span></span>  
  
-   <span data-ttu-id="5e7a4-154">Agregar o quitar columnas de la definición de restricción o de índice para crear un índice compuesto único.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-154">Add or remove columns in the index or constraint definition to create a unique composite.</span></span> <span data-ttu-id="5e7a4-155">En el ejemplo anterior, puede que al agregar una columna **MiddleName** a la definición de índice o restricción se resuelva el problema de duplicación.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-155">In the previous example, adding a **MiddleName** column to the index or constraint definition might resolve the duplication problem.</span></span>  
  
-   <span data-ttu-id="5e7a4-156">Seleccionar columnas que se hayan definido como NOT NULL al elegir columnas para un índice o una restricción únicos.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-156">Select columns that are defined as NOT NULL when you choose columns for a unique index or constraint.</span></span> <span data-ttu-id="5e7a4-157">Esto elimina la posibilidad de que se produzca una infracción de unicidad cuando más de una fila contenga NULL en los valores de clave.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-157">This eliminates the possibility of a uniqueness violation caused when more than one row contains NULL in the key values.</span></span>  
  
-   <span data-ttu-id="5e7a4-158">Si los valores duplicados son consecuencia de errores de entrada de datos, corregir manualmente los datos y crear el índice o la restricción.</span><span class="sxs-lookup"><span data-stu-id="5e7a4-158">If the duplicate values are the result of data entry errors, manually correct the data and then create the index or constraint.</span></span> <span data-ttu-id="5e7a4-159">Para obtener información sobre cómo quitar filas duplicadas de una tabla, vea el artículo 139444 de Knowledge Base: [Cómo quitar filas duplicadas de una tabla en SQL Server](https://support.microsoft.com/kb/139444).</span><span class="sxs-lookup"><span data-stu-id="5e7a4-159">For information about removing duplicate rows in a table, see Knowledge Base article 139444: [How to remove duplicate rows from a table in SQL Server](https://support.microsoft.com/kb/139444).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7a4-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e7a4-160">See Also</span></span>  
 <span data-ttu-id="5e7a4-161">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e7a4-161">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="5e7a4-162">[Crear índices únicos](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="5e7a4-162">[Create Unique Indexes](../indexes/indexes.md) </span></span>  
 [<span data-ttu-id="5e7a4-163">Crear restricciones UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5e7a4-163">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
