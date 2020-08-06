---
title: Permisos necesarios para ejecutar SQL Server Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], permissions
- traces [SQL Server], replaying
- replaying traces
- SQL Server Profiler, permissions
- security [SQL Server], SQL Server Profiler
ms.assetid: 5c580a87-88ae-4314-8fe1-54ade83f227f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e73ffe2e127299db9a9e37e48f089aab2cccca52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748423"
---
# <a name="permissions-required-to-run-sql-server-profiler"></a><span data-ttu-id="95b4b-102">Permisos necesarios para ejecutar SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="95b4b-102">Permissions Required to Run SQL Server Profiler</span></span>
  <span data-ttu-id="95b4b-103">De forma predeterminada, la ejecución del [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requiere los mismos permisos de usuario que los procedimientos almacenados de Transact-SQL que se utilizan para crear seguimientos.</span><span class="sxs-lookup"><span data-stu-id="95b4b-103">By default, running [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requires the same user permissions as the Transact-SQL stored procedures that are used to create traces.</span></span> <span data-ttu-id="95b4b-104">Para ejecutar [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], debe concederse a los usuarios el permiso ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="95b4b-104">To run [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], users must be granted the ALTER TRACE permission.</span></span> <span data-ttu-id="95b4b-105">Para obtener más información, vea [GRANT &#40;permisos de servidor de Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95b4b-105">For more information, see [GRANT Server Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="95b4b-106">Los usuarios que tienen el permiso SHOWPLAN, ALTER TRACE o VIEW SERVER STATE pueden ver consultas capturadas en la salida del plan de presentación.</span><span class="sxs-lookup"><span data-stu-id="95b4b-106">Users who have the SHOWPLAN, the ALTER TRACE, or the VIEW SERVER STATE permission can view queries that are captured in Showplan output.</span></span> <span data-ttu-id="95b4b-107">Estas consultas pueden contener información confidencial, como contraseñas.</span><span class="sxs-lookup"><span data-stu-id="95b4b-107">These queries may contain sensitive information such as passwords.</span></span> <span data-ttu-id="95b4b-108">Por consiguiente, se recomienda conceder estos permisos solo a los usuarios que tengan autorización para ver información confidencial, como los miembros del rol fijo de base de datos db_owner o los miembros del rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="95b4b-108">Therefore, we recommend that you only grant these permissions to users who are authorized to view sensitive information, such as members of the db_owner fixed database role, or members of the sysadmin fixed server role.</span></span> <span data-ttu-id="95b4b-109">Además, se recomienda guardar solo los archivos del plan de presentación o los archivos de seguimiento que contengan eventos relacionados con el plan de presentación en una ubicación que utilice el sistema de archivos NTFS, así como restringir el acceso a los usuarios que tengan autorización para ver información confidencial.</span><span class="sxs-lookup"><span data-stu-id="95b4b-109">Additionally, we recommend that you only save Showplan files or trace files that contain Showplan-related events to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view sensitive information.</span></span>

## <a name="permissions-used-to-replay-traces"></a><span data-ttu-id="95b4b-110">Permisos utilizados para reproducir seguimientos</span><span class="sxs-lookup"><span data-stu-id="95b4b-110">Permissions Used to Replay Traces</span></span>
 <span data-ttu-id="95b4b-111">La reproducción de seguimientos también requiere que el usuario que reproduce el seguimiento disponga del permiso ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="95b4b-111">Replaying traces also requires that the user who is replaying the trace have the ALTER TRACE permission.</span></span>

 <span data-ttu-id="95b4b-112">Sin embargo, durante la reproducción, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] utiliza el comando EXECUTE AS si se encuentra un evento Audit Login en el seguimiento que se está reproduciendo.</span><span class="sxs-lookup"><span data-stu-id="95b4b-112">However, during replay, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] uses the EXECUTE AS command if an Audit Login event is encountered in the trace that is being replayed.</span></span> [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="95b4b-113">utiliza el comando EXECUTE AS para suplantar al usuario asociado al evento de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="95b4b-113">uses the EXECUTE AS command to impersonate the user who is associated with the login event.</span></span>

 <span data-ttu-id="95b4b-114">Si el [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encuentra un evento de inicio de sesión en un seguimiento que se está reproduciendo, se realizan las siguientes comprobaciones de permisos:</span><span class="sxs-lookup"><span data-stu-id="95b4b-114">If [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encounters a login event in a trace that is being replayed, the following permission checks are performed:</span></span>

1.  <span data-ttu-id="95b4b-115">El usuario 1, que tiene el permiso ALTER TRACE, comienza a reproducir una seguimiento.</span><span class="sxs-lookup"><span data-stu-id="95b4b-115">User1, who has the ALTER TRACE permission, starts replaying a trace.</span></span>

2.  <span data-ttu-id="95b4b-116">Se encuentra un evento de inicio de sesión para el usuario 2 en la seguimiento reproducida.</span><span class="sxs-lookup"><span data-stu-id="95b4b-116">A login event for User2 is encountered in the replayed trace.</span></span>

3.  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="95b4b-117">utiliza el comando EXECUTE AS para suplantar al usuario 2.</span><span class="sxs-lookup"><span data-stu-id="95b4b-117">uses the EXECUTE AS command to impersonate User2.</span></span>

4.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="95b4b-118">intenta autenticar al usuario 2 y, en función del resultado, tiene lugar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="95b4b-118">attempts to authenticate User2, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="95b4b-119">Si el usuario 2 no se puede autenticar, el [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] devuelve un error y continúa reproduciendo la seguimiento como usuario 1.</span><span class="sxs-lookup"><span data-stu-id="95b4b-119">If User2 cannot be authenticated, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] returns an error, and continues replaying the trace as User1.</span></span>

    2.  <span data-ttu-id="95b4b-120">Si el usuario 2 se autentica correctamente, la reproducción de la seguimiento como usuario 2 continúa.</span><span class="sxs-lookup"><span data-stu-id="95b4b-120">If User2 is successfully authenticated, replaying the trace as User2 continues.</span></span>

5.  <span data-ttu-id="95b4b-121">Los permisos del usuario 2 se comprueban en la base de datos de destino y, en función del resultado, tiene lugar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="95b4b-121">Permissions for User2 are checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="95b4b-122">Si el usuario 2 tiene permisos en la base de datos de destino, la suplantación ha tenido éxito y la seguimiento se reproduce como usuario 2.</span><span class="sxs-lookup"><span data-stu-id="95b4b-122">If User2 has permissions on the target database, impersonation has succeeded, and the trace is replayed as User2.</span></span>

    2.  <span data-ttu-id="95b4b-123">Si el usuario 2 no tiene permisos en la base de datos de destino, el servidor busca un usuario Invitado en esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="95b4b-123">If User2 does not have permissions on the target database, the server checks for a Guest user on that database.</span></span>

6.  <span data-ttu-id="95b4b-124">Se comprueba la existencia de un usuario Invitado en la base de datos de destino y, en función del resultado, tiene lugar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="95b4b-124">Existence of a Guest user is checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="95b4b-125">Si existe una cuenta Invitado, la seguimiento se reproduce como la cuenta Invitado.</span><span class="sxs-lookup"><span data-stu-id="95b4b-125">If a Guest account exists, the trace is replayed as the Guest account.</span></span>

    2.  <span data-ttu-id="95b4b-126">Si no existe una cuenta Invitado en la base de datos de destino, se devuelve un error y la seguimiento se reproduce como el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="95b4b-126">If no Guest account exists on the target database, an error is returned and the trace is replayed as User1.</span></span>

 <span data-ttu-id="95b4b-127">En el siguiente diagrama se muestra el proceso de comprobación de permisos al reproducir seguimientos:</span><span class="sxs-lookup"><span data-stu-id="95b4b-127">The following diagram shows this process of checking permission when replaying traces:</span></span>

 <span data-ttu-id="95b4b-128">![Permisos de seguimiento de reproducción de SQL Server Profiler](../../database-engine/media/replaytracedecisiontree.gif "Permisos de seguimiento de reproducción de SQL Server Profiler")</span><span class="sxs-lookup"><span data-stu-id="95b4b-128">![SQL Server Profiler replay trace permissions](../../database-engine/media/replaytracedecisiontree.gif "SQL Server Profiler replay trace permissions")</span></span>

## <a name="see-also"></a><span data-ttu-id="95b4b-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95b4b-129">See Also</span></span>
 <span data-ttu-id="95b4b-130">[SQL Server Profiler procedimientos almacenados &#40;los seguimientos de la reproducción de&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay Traces](replay-traces.md) [crean un seguimiento &#40;SQL Server Profiler](create-a-trace-sql-server-profiler.md)&#41;[reproducir una tabla de seguimiento](replay-a-trace-table-sql-server-profiler.md) &#40;SQL Server Profiler&#41;[reproducir un archivo de seguimiento &#40;](replay-a-trace-file-sql-server-profiler.md) SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="95b4b-130">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay Traces](replay-traces.md) [Create a Trace &#40;SQL Server Profiler&#41;](create-a-trace-sql-server-profiler.md) [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md)</span></span>


