---
title: MSSQLSERVER_605 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 605 (Database Engine error)
ms.assetid: d8d3a22e-1ff8-48a4-891f-4c8619437e24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e196fba84af492b25e798629d3e808b1bf22857e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675877"
---
# <a name="mssqlserver_605"></a><span data-ttu-id="cd25d-102">MSSQLSERVER_605</span><span class="sxs-lookup"><span data-stu-id="cd25d-102">MSSQLSERVER_605</span></span>
    
## <a name="details"></a><span data-ttu-id="cd25d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="cd25d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd25d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="cd25d-104">Product Name</span></span>|<span data-ttu-id="cd25d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd25d-105">SQL Server</span></span>|  
|<span data-ttu-id="cd25d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cd25d-106">Event ID</span></span>|<span data-ttu-id="cd25d-107">605</span><span class="sxs-lookup"><span data-stu-id="cd25d-107">605</span></span>|  
|<span data-ttu-id="cd25d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="cd25d-108">Event Source</span></span>|<span data-ttu-id="cd25d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cd25d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cd25d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cd25d-110">Component</span></span>|<span data-ttu-id="cd25d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cd25d-111">SQLEngine</span></span>|  
|<span data-ttu-id="cd25d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="cd25d-112">Symbolic Name</span></span>|<span data-ttu-id="cd25d-113">WRONGPAGE</span><span class="sxs-lookup"><span data-stu-id="cd25d-113">WRONGPAGE</span></span>|  
|<span data-ttu-id="cd25d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="cd25d-114">Message Text</span></span>|<span data-ttu-id="cd25d-115">Error al intentar capturar la página lógica %S_PGID de la base de datos %d,</span><span class="sxs-lookup"><span data-stu-id="cd25d-115">Attempt to fetch logical page %S_PGID in database %d failed.</span></span> <span data-ttu-id="cd25d-116">ya que pertenece a la unidad de asignación %I64d, no a %I64d.</span><span class="sxs-lookup"><span data-stu-id="cd25d-116">It belongs to allocation unit %I64d not to %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cd25d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="cd25d-117">Explanation</span></span>  
 <span data-ttu-id="cd25d-118">Generalmente, este error indica daños en páginas o asignaciones en la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="cd25d-118">This error generally signifies page or allocation corruption in the specified database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cd25d-119">detecta daños al leer las páginas que pertenecen a una tabla siguiendo las vinculaciones de páginas o utilizando el Mapa de asignación de índices (IAM).</span><span class="sxs-lookup"><span data-stu-id="cd25d-119">detects corruption when reading pages belonging to a table either by following the page linkages or by using the Index Allocation Map (IAM).</span></span> <span data-ttu-id="cd25d-120">Todas las páginas asignadas a una tabla deben pertenecer a una de las unidades de asignación asociadas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="cd25d-120">All pages allocated to a table must belong to one of the allocation units associated with the table.</span></span> <span data-ttu-id="cd25d-121">Si el Id. de unidad de asignación incluido en el encabezado de página no coincide con un Id. de unidad de asignación asociado a la tabla, se produce esta excepción.</span><span class="sxs-lookup"><span data-stu-id="cd25d-121">If the allocation unit ID contained in the page header does not match an allocation unit ID associated with the table, this exception is raised.</span></span> <span data-ttu-id="cd25d-122">El primer identificador de unidad de asignación que aparece en el mensaje de error es el identificador presente en el encabezado de página, y el segundo valor de unidad de asignación es el identificador asociado a la tabla.</span><span class="sxs-lookup"><span data-stu-id="cd25d-122">The first allocation unit ID listed in the error message is the ID present in the page header, and the second allocation unit value is the ID associated with the table.</span></span>  
  
 <span data-ttu-id="cd25d-123">**Errores de datos dañados**</span><span class="sxs-lookup"><span data-stu-id="cd25d-123">**Data Corruption Errors**</span></span>  
  
 <span data-ttu-id="cd25d-124">Un nivel de gravedad 21 indica daños potenciales de los datos.</span><span class="sxs-lookup"><span data-stu-id="cd25d-124">A severity level of 21 indicates potential data corruption.</span></span> <span data-ttu-id="cd25d-125">Entre las causas posibles se incluyen una cadena de páginas dañada, un IAM dañado o una entrada no válida en la vista de catálogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="cd25d-125">Possible causes are a damaged page chain, a corrupt IAM, or an invalid entry in the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view for that object.</span></span> <span data-ttu-id="cd25d-126">Estos errores suelen deberse a errores de hardware o de controladores de dispositivos de disco.</span><span class="sxs-lookup"><span data-stu-id="cd25d-126">These errors are often caused by hardware or disk device driver failure.</span></span>  
  
 <span data-ttu-id="cd25d-127">**Errores transitorios**</span><span class="sxs-lookup"><span data-stu-id="cd25d-127">**Transient Errors**</span></span>  
  
 <span data-ttu-id="cd25d-128">Un nivel de gravedad 12 indica un error transitorio potencial; es decir, se produce en la memoria caché y no indica un daño en los datos del disco.</span><span class="sxs-lookup"><span data-stu-id="cd25d-128">A severity level of 12 indicates a potential transient error; that is, it occurs in the cache and does not indicate damage to data on disk.</span></span> <span data-ttu-id="cd25d-129">Los errores transitorios 605 pueden deberse a las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="cd25d-129">Transient 605 errors can be caused by the following conditions:</span></span>  
  
-   <span data-ttu-id="cd25d-130">El sistema operativo notifica prematuramente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ha completado una operación de E/S; el mensaje de error se muestra aunque no se haya producido ningún daño real en los datos.</span><span class="sxs-lookup"><span data-stu-id="cd25d-130">The operating system prematurely notifies [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that an I/O operation has completed; the error message is displayed even though no actual data corruption exists.</span></span>  
  
 <span data-ttu-id="cd25d-131">Ejecutar una consulta con la sugerencia de optimizador NOLOCK o establecer el nivel de aislamiento de transacción en READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="cd25d-131">Running a query with the Optimizer hint NOLOCK or setting the transaction isolation level to READ UNCOMMITTED.</span></span> <span data-ttu-id="cd25d-132">Cuando una consulta que usa NOLOCK o READ UNCOMMITTED intenta leer datos que otro usuario está moviendo o modificando, se produce un error 605.</span><span class="sxs-lookup"><span data-stu-id="cd25d-132">When a query that is using NOLOCK or READ UNCOMMITTED tries to read data that is being moved or changed by another user, a 605 error occurs.</span></span> <span data-ttu-id="cd25d-133">Para comprobar que se trata de un error transitorio 605, vuelva a ejecutar la consulta más tarde.</span><span class="sxs-lookup"><span data-stu-id="cd25d-133">To verify that it is a transient 605 error, rerun the query later.</span></span> <span data-ttu-id="cd25d-134">Para más información, vea este artículo de KB [235880](https://support.microsoft.com/kb/235880/en-us): "Recibirá un mensaje de error "Error 605" al ejecutar una consulta con la sugerencia del optimizador NOLOCK o al establecer el nivel de aislamiento en READ UNCOMMITTED en SQL Server".</span><span class="sxs-lookup"><span data-stu-id="cd25d-134">For more information, see this KB article [235880](https://support.microsoft.com/kb/235880/en-us): "You receive an "Error 605" error message when you run a query with the optimizer hint NOLOCK or you set the transaction isolation level to READ UNCOMMITTED in SQL Server."</span></span>  
  
 <span data-ttu-id="cd25d-135">En general, si el error se produce durante un acceso a datos, pero las operaciones DBCC CHECKDB posteriores se completan sin errores, significa que el error 605 probablemente era transitorio.</span><span class="sxs-lookup"><span data-stu-id="cd25d-135">In general, if the error occurs during data access but subsequent DBCC CHECKDB operations complete without error, the 605 error was probably transient.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd25d-136">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="cd25d-136">User Action</span></span>  
 <span data-ttu-id="cd25d-137">Si el error 605 no es transitorio, significa que el problema es grave y debe corregirse realizando las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="cd25d-137">If the 605 error is not transient, the problem is severe and must be corrected by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="cd25d-138">Identifique las tablas asociadas a las unidades de asignación especificadas en el mensaje ejecutando la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="cd25d-138">Identify the tables associated with the allocation units specified in the message by running the following query.</span></span> <span data-ttu-id="cd25d-139">Reemplace `allocation_unit_id` por las unidades de asignación especificadas en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="cd25d-139">Replace `allocation_unit_id` with the allocation units specified in the error message.</span></span>  
  
     <span data-ttu-id="cd25d-140">USE`database_name`;</span><span class="sxs-lookup"><span data-stu-id="cd25d-140">USE`database_name`;</span></span>  
  
     <span data-ttu-id="cd25d-141">GO</span><span class="sxs-lookup"><span data-stu-id="cd25d-141">GO</span></span>  
  
     <span data-ttu-id="cd25d-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span><span class="sxs-lookup"><span data-stu-id="cd25d-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span></span>  
  
     <span data-ttu-id="cd25d-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span><span class="sxs-lookup"><span data-stu-id="cd25d-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span></span>  
  
     <span data-ttu-id="cd25d-144">FROM sys.allocation_units AS au</span><span class="sxs-lookup"><span data-stu-id="cd25d-144">FROM sys.allocation_units AS au</span></span>  
  
     <span data-ttu-id="cd25d-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span><span class="sxs-lookup"><span data-stu-id="cd25d-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span></span>  
  
     <span data-ttu-id="cd25d-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span><span class="sxs-lookup"><span data-stu-id="cd25d-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span></span>  
  
     <span data-ttu-id="cd25d-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span><span class="sxs-lookup"><span data-stu-id="cd25d-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span></span>  
  
     <span data-ttu-id="cd25d-148">ORDER BY au.allocation_unit_id;</span><span class="sxs-lookup"><span data-stu-id="cd25d-148">ORDER BY au.allocation_unit_id;</span></span>  
  
     <span data-ttu-id="cd25d-149">GO</span><span class="sxs-lookup"><span data-stu-id="cd25d-149">GO</span></span>  
  
2.  <span data-ttu-id="cd25d-150">Ejecute DBCC CHECKTABLE sin la cláusula REPAIR en la tabla asociada al segundo Id. de unidad de asignación especificado en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="cd25d-150">Execute DBCC CHECKTABLE without a REPAIR clause on the table associated with the second allocation unit ID specified in the error message.</span></span>  
  
3.  <span data-ttu-id="cd25d-151">Ejecute DBCC CHECKDB sin la cláusula REPAIR lo antes posible para determinar el alcance de los daños en toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd25d-151">Execute DBCC CHECKDB without a REPAIR clause as soon as possible to determine the full extent of the corruption in the entire database.</span></span>  
  
4.  <span data-ttu-id="cd25d-152">Compruebe en el registro de errores si se han producido otros de los errores que suelen acompañar al error 605 y examine el Registro de eventos de Windows para buscar cualquier problema relacionado con el sistema o el hardware.</span><span class="sxs-lookup"><span data-stu-id="cd25d-152">Check the error log for other errors that often accompany a 605 error and examine the Windows Event Log for any system or hardware related issues.</span></span> <span data-ttu-id="cd25d-153">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="cd25d-153">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="cd25d-154">Si el problema no está relacionado con el hardware, realice una de las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cd25d-154">If the problem is not hardware related, perform one of the following tasks:</span></span>  
  
1.  <span data-ttu-id="cd25d-155">Restaure la base de datos a partir de una copia de seguridad limpia conocida.</span><span class="sxs-lookup"><span data-stu-id="cd25d-155">Restore the database from a known clean backup.</span></span> <span data-ttu-id="cd25d-156">Puede aprovechar la característica de copia de seguridad y restauración de páginas para restaurar simplemente las páginas dañadas.</span><span class="sxs-lookup"><span data-stu-id="cd25d-156">You can leverage the page restore backup feature to restore just the damaged pages.</span></span>  
  
2.  <span data-ttu-id="cd25d-157">Ejecute DBCC CHECKDB con la cláusula REPAIR recomendada por la operación DBCC CHECKDB realizada en el paso 3 para reparar los daños.</span><span class="sxs-lookup"><span data-stu-id="cd25d-157">Run DBCC CHECKDB with the REPAIR clause recommended by the DBCC CHECKDB operation performed in step 3 to repair the corruption.</span></span> <span data-ttu-id="cd25d-158">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="cd25d-158">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span> <span data-ttu-id="cd25d-159">Tenga disponible la salida de DBCC CHECKDB para revisarla.</span><span class="sxs-lookup"><span data-stu-id="cd25d-159">Have the output from DBCC CHECKDB available for review.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="cd25d-160">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="cd25d-160">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd25d-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd25d-161">See Also</span></span>  
 [<span data-ttu-id="cd25d-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd25d-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql)  
  
  
