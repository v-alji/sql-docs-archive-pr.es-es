---
title: Requisitos de reproducción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event classes [SQL Server], replaying traces
- traces [SQL Server], replaying
- replaying traces
- TSQL_Replay template [SQL Server]
ms.assetid: 0e01dfc7-84b9-47f6-8bf7-b0656df4fa7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65546f6820765286b558d2043e0155a79a07eb58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748409"
---
# <a name="replay-requirements"></a><span data-ttu-id="5e978-102">Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="5e978-102">Replay Requirements</span></span>
  <span data-ttu-id="5e978-103">Para reproducir los datos de seguimiento con [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o Distributed Replay Utility, se debe capturar un conjunto específico de clases de eventos y columnas en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5e978-103">In order to replay trace data with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or the Distributed Replay Utility, a specific set of event classes and columns must be captured in the trace.</span></span> <span data-ttu-id="5e978-104">Esta configuración se habilita de forma predeterminada si se usa la plantilla de seguimiento **TSQL_Replay** para configurar un seguimiento que se usará posteriormente para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="5e978-104">These settings are enabled by default if the **TSQL_Replay** trace template is used to configure a trace that is later used for replay.</span></span> <span data-ttu-id="5e978-105">En este tema se describe esta configuración y otros requisitos de reproducción.</span><span class="sxs-lookup"><span data-stu-id="5e978-105">This topic describes these settings and other replay requirements.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e978-106">Recomendamos usar la Utilidad de reproducción distribuida para reproducir una aplicación de OLTP que se use mucho (con muchas conexiones simultáneas activas o un alto rendimiento).</span><span class="sxs-lookup"><span data-stu-id="5e978-106">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="5e978-107">La utilidad puede reproducir datos de seguimiento desde varios equipos, simulando mejor una carga de trabajo esencial.</span><span class="sxs-lookup"><span data-stu-id="5e978-107">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="5e978-108">Para obtener más información, vea [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="5e978-108">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="event-classes-required-for-replay"></a><span data-ttu-id="5e978-109">Clases de eventos requeridos para reproducción</span><span class="sxs-lookup"><span data-stu-id="5e978-109">Event Classes Required for Replay</span></span>  
 <span data-ttu-id="5e978-110">Para que [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]los reproduzca, se deben capturar el siguiente conjunto de clases de eventos y cualquier otra clase de eventos que desee supervisar en el seguimiento:</span><span class="sxs-lookup"><span data-stu-id="5e978-110">To be replayed by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], the following set of event classes, in addition to any other event classes you want to monitor, must be captured in the trace:</span></span>  
  
-   <span data-ttu-id="5e978-111">**CursorClose**(solo cuando se reproduzcan cursores en el servidor)</span><span class="sxs-lookup"><span data-stu-id="5e978-111">**CursorClose (** only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="5e978-112">**CursorExecute** (solo cuando se reproduzcan cursores en el servidor)</span><span class="sxs-lookup"><span data-stu-id="5e978-112">**CursorExecute** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="5e978-113">**CursorOpen** (solo cuando se reproduzcan cursores en el servidor)</span><span class="sxs-lookup"><span data-stu-id="5e978-113">**CursorOpen** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="5e978-114">**CursorPrepare** (solo cuando se reproduzcan cursores en el servidor)</span><span class="sxs-lookup"><span data-stu-id="5e978-114">**CursorPrepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="5e978-115">**CursorUnprepare** (solo cuando se reproduzcan cursores en el servidor)</span><span class="sxs-lookup"><span data-stu-id="5e978-115">**CursorUnprepare** (only required when replaying server-side cursors)</span></span>  
  
-   <span data-ttu-id="5e978-116">**Audit Login**</span><span class="sxs-lookup"><span data-stu-id="5e978-116">**Audit Login**</span></span>  
  
-   <span data-ttu-id="5e978-117">**Audit Logout**</span><span class="sxs-lookup"><span data-stu-id="5e978-117">**Audit Logout**</span></span>  
  
-   <span data-ttu-id="5e978-118">**ExistingConnection**</span><span class="sxs-lookup"><span data-stu-id="5e978-118">**ExistingConnection**</span></span>  
  
-   <span data-ttu-id="5e978-119">**RPC Output Parameter**</span><span class="sxs-lookup"><span data-stu-id="5e978-119">**RPC Output Parameter**</span></span>  
  
-   <span data-ttu-id="5e978-120">**RPC:Completed**</span><span class="sxs-lookup"><span data-stu-id="5e978-120">**RPC:Completed**</span></span>  
  
-   <span data-ttu-id="5e978-121">**RPC:Starting**</span><span class="sxs-lookup"><span data-stu-id="5e978-121">**RPC:Starting**</span></span>  
  
-   <span data-ttu-id="5e978-122">**Exec Prepared SQL** (solo cuando se reproduzcan instrucciones SQL preparadas en el servidor)</span><span class="sxs-lookup"><span data-stu-id="5e978-122">**Exec Prepared SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="5e978-123">**Prepare SQL** (solo cuando se reproduzcan instrucciones SQL preparadas en el servidor)</span><span class="sxs-lookup"><span data-stu-id="5e978-123">**Prepare SQL** (only required when replaying server-side prepared SQL statements)</span></span>  
  
-   <span data-ttu-id="5e978-124">**SQL:BatchCompleted**</span><span class="sxs-lookup"><span data-stu-id="5e978-124">**SQL:BatchCompleted**</span></span>  
  
-   <span data-ttu-id="5e978-125">**SQL:BatchStarting**</span><span class="sxs-lookup"><span data-stu-id="5e978-125">**SQL:BatchStarting**</span></span>  
  
## <a name="data-columns-required-for-replay"></a><span data-ttu-id="5e978-126">Columnas de datos requeridas para la reproducción</span><span class="sxs-lookup"><span data-stu-id="5e978-126">Data Columns Required for Replay</span></span>  
 <span data-ttu-id="5e978-127">Además de otras columnas de datos que desee capturar, debe capturar las siguientes columnas de datos en un seguimiento para poder reproducirlas:</span><span class="sxs-lookup"><span data-stu-id="5e978-127">In addition to any other data columns you want to capture, the following data columns must be captured in a trace to allow the trace to be replayed:</span></span>  
  
-   <span data-ttu-id="5e978-128">**Clase de eventos**</span><span class="sxs-lookup"><span data-stu-id="5e978-128">**Event Class**</span></span>  
  
-   <span data-ttu-id="5e978-129">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="5e978-129">**EventSequence**</span></span>  
  
-   <span data-ttu-id="5e978-130">**TextData**</span><span class="sxs-lookup"><span data-stu-id="5e978-130">**TextData**</span></span>  
  
-   <span data-ttu-id="5e978-131">**Nombre de la aplicación**</span><span class="sxs-lookup"><span data-stu-id="5e978-131">**Application Name**</span></span>  
  
-   <span data-ttu-id="5e978-132">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="5e978-132">**LoginName**</span></span>  
  
-   <span data-ttu-id="5e978-133">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="5e978-133">**DatabaseName**</span></span>  
  
-   <span data-ttu-id="5e978-134">**Identificador de base de datos**</span><span class="sxs-lookup"><span data-stu-id="5e978-134">**Database ID**</span></span>  
  
-   <span data-ttu-id="5e978-135">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="5e978-135">**ClientProcessID**</span></span>  
  
-   <span data-ttu-id="5e978-136">**HostName**</span><span class="sxs-lookup"><span data-stu-id="5e978-136">**HostName**</span></span>  
  
-   <span data-ttu-id="5e978-137">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="5e978-137">**ServerName**</span></span>  
  
-   <span data-ttu-id="5e978-138">**Binary Data**</span><span class="sxs-lookup"><span data-stu-id="5e978-138">**Binary Data**</span></span>  
  
-   <span data-ttu-id="5e978-139">**SPID**</span><span class="sxs-lookup"><span data-stu-id="5e978-139">**SPID**</span></span>  
  
-   <span data-ttu-id="5e978-140">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="5e978-140">**Start Time**</span></span>  
  
-   <span data-ttu-id="5e978-141">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="5e978-141">**EndTime**</span></span>  
  
-   <span data-ttu-id="5e978-142">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="5e978-142">**IsSystem**</span></span>  
  
-   <span data-ttu-id="5e978-143">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="5e978-143">**NTDomainName**</span></span>  
  
-   <span data-ttu-id="5e978-144">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="5e978-144">**NTUserName**</span></span>  
  
-   <span data-ttu-id="5e978-145">**Error**</span><span class="sxs-lookup"><span data-stu-id="5e978-145">**Error**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e978-146">Use la plantilla de seguimiento **TSQL_Replay** para los seguimientos que capturen datos para su reproducción.</span><span class="sxs-lookup"><span data-stu-id="5e978-146">Use the trace template **TSQL_Replay** for traces that capture data for replay.</span></span>  
  
## <a name="other-replay-requirements"></a><span data-ttu-id="5e978-147">Otros requisitos de reproducción</span><span class="sxs-lookup"><span data-stu-id="5e978-147">Other Replay Requirements</span></span>  
 <span data-ttu-id="5e978-148">En Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la reproducción comprueba la presencia de los eventos y las columnas obligatorios.</span><span class="sxs-lookup"><span data-stu-id="5e978-148">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], replay checks for the presence of required events and columns.</span></span> <span data-ttu-id="5e978-149">Este cambio permite mejorar la precisión de la reproducción y elimina el trabajo de estimación de la reproducción de solución de problemas cuando faltan datos obligatorios.</span><span class="sxs-lookup"><span data-stu-id="5e978-149">This change helps improve the accuracy of replay and takes the guesswork out of troubleshooting replay when required data is missing.</span></span> <span data-ttu-id="5e978-150">La reproducción devuelve un error y detiene la reproducción de un archivo cuando faltan datos obligatorios en un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5e978-150">Replay returns an error and stops replaying a file when required data is missing from a trace.</span></span>  
  
 <span data-ttu-id="5e978-151">Para reproducir un seguimiento en un servidor (destino) en el cual se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] distinto del servidor del que se realiza el seguimiento originalmente (origen), asegúrese de que se cumplen los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e978-151">To replay a trace against a server (the target) on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running other than the server originally traced (the source), make sure the following has been done:</span></span>  
  
-   <span data-ttu-id="5e978-152">Todos los inicios de sesión y usuarios contenidos en el seguimiento deben estar ya creados en el destino y en la misma base de datos que en el origen.</span><span class="sxs-lookup"><span data-stu-id="5e978-152">All logins and users contained in the trace must be created already on the target and in the same database as the source.</span></span>  
  
-   <span data-ttu-id="5e978-153">Todos los inicios de sesión y usuarios del destino deben tener los mismos permisos que tenían en el origen.</span><span class="sxs-lookup"><span data-stu-id="5e978-153">All logins and users in the target must have the same permissions they had in the source.</span></span>  
  
-   <span data-ttu-id="5e978-154">Todas las contraseñas de inicio de sesión deben ser las mismas que las del usuario que ejecute la reproducción.</span><span class="sxs-lookup"><span data-stu-id="5e978-154">All login passwords must be the same as those of the user that executes the replay.</span></span>  
  
-   <span data-ttu-id="5e978-155">Los Id. de base de datos del destino deben ser los mismos que los del origen.</span><span class="sxs-lookup"><span data-stu-id="5e978-155">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="5e978-156">Sin embargo, si no son los mismos, se puede realizar la coincidencia basándose en **DatabaseName** , si está presente en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5e978-156">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="5e978-157">La base de datos predeterminada para cada inicio de sesión contenido en el seguimiento debe estar establecida (en el destino) en la base de datos de destino respectiva del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5e978-157">The default database for each login contained in the trace must be set (on the target) to the respective target database of the login.</span></span> <span data-ttu-id="5e978-158">Por ejemplo, el seguimiento que se va a reproducir contiene actividad de inicio de sesión, **Fred**, en la base de datos **Fred_Db** del origen.</span><span class="sxs-lookup"><span data-stu-id="5e978-158">For example, the trace to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the source.</span></span> <span data-ttu-id="5e978-159">Por tanto, en el destino, la base de datos predeterminada del inicio de sesión, **Fred**, debe estar establecida en la base de datos que coincida con **Fred_Db** (aunque el nombre de la base de datos sea diferente).</span><span class="sxs-lookup"><span data-stu-id="5e978-159">Therefore, on the target, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="5e978-160">Para establecer la base de datos predeterminada del inicio de sesión, use el procedimiento almacenado del sistema **sp_defaultdb** .</span><span class="sxs-lookup"><span data-stu-id="5e978-160">To set the default database of the login, use the **sp_defaultdb** system stored procedure.</span></span>  
  
 <span data-ttu-id="5e978-161">La reproducción de eventos asociados a inicios de sesión que faltan o que son incorrectos tendrá como resultado errores de reproducción, pero la operación de reproducción continuará.</span><span class="sxs-lookup"><span data-stu-id="5e978-161">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
 <span data-ttu-id="5e978-162">Para obtener información acerca de los permisos necesarios para reproducir un seguimiento, vea [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="5e978-162">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e978-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e978-163">See Also</span></span>  
 <span data-ttu-id="5e978-164">[Reproducir una tabla de seguimiento &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5e978-164">[Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5e978-165">[Reproducir un archivo de seguimiento &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5e978-165">[Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5e978-166">[Referencia de las clase de eventos de SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5e978-166">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="5e978-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5e978-167">[sp_defaultdb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) </span></span>  
 [<span data-ttu-id="5e978-168">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="5e978-168">SQL Server Distributed Replay</span></span>](../distributed-replay/sql-server-distributed-replay.md)  
  
  
