---
title: MSSQLSERVER_2814 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2814 (Database Engine error)
ms.assetid: 22800748-9be9-4511-9428-6b8b40e5bef9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26b1fae5b683ed72cb93c3f81981bd41e2f4ad4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673034"
---
# <a name="mssqlserver_2814"></a><span data-ttu-id="785de-102">MSSQLSERVER_2814</span><span class="sxs-lookup"><span data-stu-id="785de-102">MSSQLSERVER_2814</span></span>
    
## <a name="details"></a><span data-ttu-id="785de-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="785de-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="785de-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="785de-104">Product Name</span></span>|<span data-ttu-id="785de-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="785de-105">SQL Server</span></span>|  
|<span data-ttu-id="785de-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="785de-106">Event ID</span></span>|<span data-ttu-id="785de-107">2814</span><span class="sxs-lookup"><span data-stu-id="785de-107">2814</span></span>|  
|<span data-ttu-id="785de-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="785de-108">Event Source</span></span>|<span data-ttu-id="785de-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="785de-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="785de-110">Componente</span><span class="sxs-lookup"><span data-stu-id="785de-110">Component</span></span>|<span data-ttu-id="785de-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="785de-111">SQLEngine</span></span>|  
|<span data-ttu-id="785de-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="785de-112">Symbolic Name</span></span>|<span data-ttu-id="785de-113">PR_POSSIBLE_INFINITE_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="785de-113">PR_POSSIBLE_INFINITE_RECOMPILE</span></span>|  
|<span data-ttu-id="785de-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="785de-114">Message Text</span></span>|<span data-ttu-id="785de-115">Se detectó una posible recompilación infinita de SQLHANDLE %hs, PlanHandle %hs, desplazamiento de inicio %d, desplazamiento de fin %d.</span><span class="sxs-lookup"><span data-stu-id="785de-115">A possible infinite recompile was detected for SQLHANDLE %hs, PlanHandle %hs, starting offset %d, ending offset %d.</span></span> <span data-ttu-id="785de-116">El motivo de la última recompilación fue % d.</span><span class="sxs-lookup"><span data-stu-id="785de-116">The last recompile reason was %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="785de-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="785de-117">Explanation</span></span>  
 <span data-ttu-id="785de-118">Una o más instrucciones hicieron que el lote de consultas se recompilara por lo menos 50 veces.</span><span class="sxs-lookup"><span data-stu-id="785de-118">One or more statements caused the query batch to recompile at least 50 times.</span></span> <span data-ttu-id="785de-119">La instrucción especificada se debe corregir para evitar más recompilaciones.</span><span class="sxs-lookup"><span data-stu-id="785de-119">The specified statement should be corrected to avoid further recompilations.</span></span>  
  
 <span data-ttu-id="785de-120">En la siguiente tabla se muestran los motivos de la recompilación.</span><span class="sxs-lookup"><span data-stu-id="785de-120">The following table lists the reasons for recompilation.</span></span>  
  
|<span data-ttu-id="785de-121">Código del motivo</span><span class="sxs-lookup"><span data-stu-id="785de-121">Reason code</span></span>|<span data-ttu-id="785de-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="785de-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="785de-123">1</span><span class="sxs-lookup"><span data-stu-id="785de-123">1</span></span>|<span data-ttu-id="785de-124">Esquema modificado</span><span class="sxs-lookup"><span data-stu-id="785de-124">Schema changed</span></span>|  
|<span data-ttu-id="785de-125">2</span><span class="sxs-lookup"><span data-stu-id="785de-125">2</span></span>|<span data-ttu-id="785de-126">Estadísticas modificadas</span><span class="sxs-lookup"><span data-stu-id="785de-126">Statistics changed</span></span>|  
|<span data-ttu-id="785de-127">3</span><span class="sxs-lookup"><span data-stu-id="785de-127">3</span></span>|<span data-ttu-id="785de-128">Compilación diferida</span><span class="sxs-lookup"><span data-stu-id="785de-128">Deferred compile</span></span>|  
|<span data-ttu-id="785de-129">4</span><span class="sxs-lookup"><span data-stu-id="785de-129">4</span></span>|<span data-ttu-id="785de-130">Cambio en opción configurada</span><span class="sxs-lookup"><span data-stu-id="785de-130">Set option changed</span></span>|  
|<span data-ttu-id="785de-131">5</span><span class="sxs-lookup"><span data-stu-id="785de-131">5</span></span>|<span data-ttu-id="785de-132">Cambio en tabla Temp</span><span class="sxs-lookup"><span data-stu-id="785de-132">Temp table changed</span></span>|  
|<span data-ttu-id="785de-133">6</span><span class="sxs-lookup"><span data-stu-id="785de-133">6</span></span>|<span data-ttu-id="785de-134">Conjunto de filas remoto modificado</span><span class="sxs-lookup"><span data-stu-id="785de-134">Remote rowset changed</span></span>|  
|<span data-ttu-id="785de-135">7</span><span class="sxs-lookup"><span data-stu-id="785de-135">7</span></span>|<span data-ttu-id="785de-136">Permisos For Browse cambiados</span><span class="sxs-lookup"><span data-stu-id="785de-136">For Browse permissions changed</span></span>|  
|<span data-ttu-id="785de-137">8</span><span class="sxs-lookup"><span data-stu-id="785de-137">8</span></span>|<span data-ttu-id="785de-138">Entorno de notificación de consultas modificado</span><span class="sxs-lookup"><span data-stu-id="785de-138">Query notification environment changed</span></span>|  
|<span data-ttu-id="785de-139">9</span><span class="sxs-lookup"><span data-stu-id="785de-139">9</span></span>|<span data-ttu-id="785de-140">Vista de partición cambiada</span><span class="sxs-lookup"><span data-stu-id="785de-140">Partition view changed</span></span>|  
|<span data-ttu-id="785de-141">10</span><span class="sxs-lookup"><span data-stu-id="785de-141">10</span></span>|<span data-ttu-id="785de-142">Opciones de cursor modificadas</span><span class="sxs-lookup"><span data-stu-id="785de-142">Cursor options changed</span></span>|  
|<span data-ttu-id="785de-143">11</span><span class="sxs-lookup"><span data-stu-id="785de-143">11</span></span>|<span data-ttu-id="785de-144">Opción (recompilar) solicitada.</span><span class="sxs-lookup"><span data-stu-id="785de-144">Option (recompile) requested</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="785de-145">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="785de-145">User Action</span></span>  
  
1.  <span data-ttu-id="785de-146">Vea la instrucción que produce la recompilación ejecutando la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="785de-146">View the statement causing the recompilation by running the following query.</span></span> <span data-ttu-id="785de-147">Reemplace los marcadores de posición *sql_handle*, *starting_offset*, *ending_offset* y *plan_handle* por los valores especificados en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="785de-147">Replace the *sql_handle*, *starting_offset*, *ending_offset*, and *plan_handle* placeholders with the values specified in the error message.</span></span> <span data-ttu-id="785de-148">Observe que las columnas **database_name** y **object_name** serán NULL para instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc y preparadas.</span><span class="sxs-lookup"><span data-stu-id="785de-148">Note that the **database_name** and **object_name** columns will be NULL for ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="785de-149">SELECT DB_NAME(st.dbid) AS database_name</span><span class="sxs-lookup"><span data-stu-id="785de-149">SELECT DB_NAME(st.dbid) AS database_name</span></span>  
  
     <span data-ttu-id="785de-150">, OBJECT_NAME(st.objectid) AS object_name</span><span class="sxs-lookup"><span data-stu-id="785de-150">, OBJECT_NAME(st.objectid) AS object_name</span></span>  
  
     <span data-ttu-id="785de-151">, st.text</span><span class="sxs-lookup"><span data-stu-id="785de-151">, st.text</span></span>  
  
     <span data-ttu-id="785de-152">FROM sys.dm_exec_query_stats AS qs</span><span class="sxs-lookup"><span data-stu-id="785de-152">FROM sys.dm_exec_query_stats AS qs</span></span>  
  
     <span data-ttu-id="785de-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span><span class="sxs-lookup"><span data-stu-id="785de-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span></span>  
  
     <span data-ttu-id="785de-154">WHERE qs.statement_start_offset = *starting_offset*</span><span class="sxs-lookup"><span data-stu-id="785de-154">WHERE qs.statement_start_offset = *starting_offset*</span></span>  
  
     <span data-ttu-id="785de-155">AND qs.statement_end_offset = *ending_offset*</span><span class="sxs-lookup"><span data-stu-id="785de-155">AND qs.statement_end_offset = *ending_offset*</span></span>  
  
     <span data-ttu-id="785de-156">AND qs.plan_handle = *plan_handle*;</span><span class="sxs-lookup"><span data-stu-id="785de-156">AND qs.plan_handle = *plan_handle*;</span></span>  
  
2.  <span data-ttu-id="785de-157">Según sea la descripción del código del motivo, modifique la instrucción, lote o procedimiento para evitar las recompilaciones.</span><span class="sxs-lookup"><span data-stu-id="785de-157">Based on the reason code description, modify the statement, batch, or procedure to avoid recompilations.</span></span> <span data-ttu-id="785de-158">Por ejemplo, un procedimiento almacenado puede contener una o más instrucciones SET.</span><span class="sxs-lookup"><span data-stu-id="785de-158">For example, a stored procedure may contain one or more SET statements.</span></span> <span data-ttu-id="785de-159">Estas instrucciones se deben quitar del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="785de-159">These statements should be removed from the procedure.</span></span> <span data-ttu-id="785de-160">Para obtener ejemplos adicionales de causas de la recompilación y sus soluciones, vea [Problemas de compilación y recompilación de lotes, y de almacenamiento en caché de planes en SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="785de-160">For additional examples of recompilation causes and resolutions, see [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span></span>  
  
3.  <span data-ttu-id="785de-161">Si el problema persiste, póngase en contacto con los Servicios de soporte al cliente (CSS) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="785de-161">If the problem persists, contact Microsoft Customer Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785de-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="785de-162">See Also</span></span>  
 [<span data-ttu-id="785de-163">SQL:StmtRecompile (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="785de-163">SQL:StmtRecompile Event Class</span></span>](../event-classes/sql-stmtrecompile-event-class.md)  
  
  
