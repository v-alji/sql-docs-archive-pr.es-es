---
title: Reflejo e instantáneas de base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- snapshots [SQL Server database snapshots], database mirroring
- database snapshots [SQL Server], database mirroring
ms.assetid: 0bf1be90-7ce4-484c-aaa7-f8a782f57c5f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9df0b74270280bf2315c6a35a80d4b009b75a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670568"
---
# <a name="database-mirroring-and-database-snapshots-sql-server"></a><span data-ttu-id="be03a-102">Reflejo e instantáneas de base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="be03a-102">Database Mirroring and Database Snapshots (SQL Server)</span></span>
  <span data-ttu-id="be03a-103">Puede aprovechar una base de datos reflejada de la cual se está realizando el mantenimiento con fines de disponibilidad para descargar informes.</span><span class="sxs-lookup"><span data-stu-id="be03a-103">You can take advantage of a mirror database that you are maintaining for availability purposes to offload reporting.</span></span> <span data-ttu-id="be03a-104">A fin de utilizar una base de datos reflejada para informes, puede crear una instantánea de base de datos en la base de datos reflejada y dirigir las solicitudes de conexión de cliente a la instantánea más reciente.</span><span class="sxs-lookup"><span data-stu-id="be03a-104">To use a mirror database for reporting, you can create a database snapshot on the mirror database and direct client connection requests to the most recent snapshot.</span></span> <span data-ttu-id="be03a-105">Una instantánea de base de datos es una instantánea estática coherente con las transacciones y de solo lectura de la base de datos de origen tal como existía en el momento de la creación de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="be03a-105">A database snapshot is a static, read-only, transaction-consistent snapshot of its source database as it existed at the moment of the snapshot's creation.</span></span> <span data-ttu-id="be03a-106">Para crear la instantánea de una base de datos en una base de datos reflejada, la base de datos debe hallarse en estado de reflejo sincronizado.</span><span class="sxs-lookup"><span data-stu-id="be03a-106">To create a database snapshot on a mirror database, the database must be in the synchronized mirroring state.</span></span>  
  
 <span data-ttu-id="be03a-107">A diferencia de la base de datos reflejada, los clientes pueden obtener acceso a las instantáneas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="be03a-107">Unlike the mirror database itself, a database snapshot is accessible to clients.</span></span> <span data-ttu-id="be03a-108">Mientras el servidor reflejado se comunique con el servidor principal, podrá dirigir clientes de informe para que se conecten a una instantánea.</span><span class="sxs-lookup"><span data-stu-id="be03a-108">As long as the mirror server is communicating with the principal server, you can direct reporting clients to connect to a snapshot.</span></span> <span data-ttu-id="be03a-109">Observe que, puesto que las instantáneas de base de datos son estáticas, no hay nuevos datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="be03a-109">Note that because a database snapshot is static, new data is not available.</span></span> <span data-ttu-id="be03a-110">Para hacer que los datos relativamente recientes estén disponibles para los usuarios, deberá crear una nueva instantánea de base de datos de forma periódica y hacer que las aplicaciones dirijan las conexiones entrantes de cliente a la instantánea más reciente.</span><span class="sxs-lookup"><span data-stu-id="be03a-110">To make relatively recent data available to your users, you must create a new database snapshot periodically and have applications direct incoming client connections to the newest snapshot.</span></span>  
  
 <span data-ttu-id="be03a-111">Una nueva instantánea de base de datos está prácticamente vacía, pero crece con el tiempo a medida que se actualizan por primera vez más y más páginas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="be03a-111">A new database snapshot is almost empty, but it grows over time as more and more database pages are updated for the first time.</span></span> <span data-ttu-id="be03a-112">Debido a que las instantáneas de base de datos crecen incrementalmente de esta forma, cada instantánea consume tantos recursos como una base de datos normal.</span><span class="sxs-lookup"><span data-stu-id="be03a-112">Because every snapshot on a database grows incrementally in this way, each database snapshot consumes as much resources as a normal database.</span></span> <span data-ttu-id="be03a-113">En función de las configuraciones del servidor principal y el servidor reflejado, un número excesivo de instantáneas de base de datos en una base de datos reflejada puede reducir el rendimiento de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="be03a-113">Depending on the configurations of the mirror server and principal server, having an excessive number of database snapshots on a mirror database might decrease performance on the principal database.</span></span> <span data-ttu-id="be03a-114">Por lo tanto, se recomienda mantener solo algunas instantáneas relativamente recientes en las bases de datos reflejadas.</span><span class="sxs-lookup"><span data-stu-id="be03a-114">Therefore, we recommend that you keep only a few relatively recent snapshots on your mirror databases.</span></span> <span data-ttu-id="be03a-115">Por lo general, tras la creación de una nueva instantánea, deberá redirigir las consultas entrantes a esta nueva instantánea y quitar la instantánea anterior una vez finalizadas las consultas en curso.</span><span class="sxs-lookup"><span data-stu-id="be03a-115">Typically, after you create a replacement snapshot, you should redirect incoming queries to the new snapshot and drop the earlier snapshot after any current queries complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be03a-116">Para obtener más información sobre las instantáneas de base de datos, vea [Instantáneas de bases de datos &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="be03a-116">For more information about database snapshots, see [Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span></span>  
  
 <span data-ttu-id="be03a-117">Si se produce la conmutación de roles, se reinicia la base de datos junto con sus instantáneas y se desconectan los usuarios de forma temporal.</span><span class="sxs-lookup"><span data-stu-id="be03a-117">If role switching occurs, the database and its snapshots are restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="be03a-118">Posteriormente, las instantáneas de base de datos permanecen en la instancia de servidor en la que se crearon (que es ahora la nueva base de datos principal).</span><span class="sxs-lookup"><span data-stu-id="be03a-118">Afterwards, the database snapshots remain on the server instance where they were created, which has become the new principal database.</span></span> <span data-ttu-id="be03a-119">Los usuarios podrán seguir utilizando estas instantáneas tras la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="be03a-119">Users can continue to use the snapshots after the failover.</span></span> <span data-ttu-id="be03a-120">No obstante, esto aumenta la carga del nuevo servidor principal.</span><span class="sxs-lookup"><span data-stu-id="be03a-120">However, this places an additional load on the new principal server.</span></span> <span data-ttu-id="be03a-121">Si el rendimiento es importante en el entorno, se recomienda crear una instantánea en la nueva base de datos reflejada cuando esté disponible, redirigir los clientes a la nueva instantánea y quitar todas las instantáneas de base de datos reflejada anterior.</span><span class="sxs-lookup"><span data-stu-id="be03a-121">If performance is a concern in your environment, we recommend that you create a snapshot on the new mirror database when it becomes available, redirect clients to the new snapshot, and drop all of the database snapshots from the former mirror database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be03a-122">Para una solución de informes dedicada que admita la ampliación horizontal, considere la posibilidad de utilizar la duplicación.</span><span class="sxs-lookup"><span data-stu-id="be03a-122">For a dedicated reporting solution that scales out well, consider replication.</span></span> <span data-ttu-id="be03a-123">Para más información, consulte [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span><span class="sxs-lookup"><span data-stu-id="be03a-123">For more information, see [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be03a-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be03a-124">Example</span></span>  
 <span data-ttu-id="be03a-125">En este ejemplo se crean instantáneas en una base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="be03a-125">This example creates snapshots on a mirrored database.</span></span>  
  
 <span data-ttu-id="be03a-126">Suponga que la base de datos de una sesión de creación de reflejo de la base de datos es [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be03a-126">Assume that the database of a database mirroring session is [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="be03a-127">En este ejemplo se crean tres instantáneas de base de datos en la copia reflejada de la base de datos `AdventureWorks` , que reside en la unidad `F` .</span><span class="sxs-lookup"><span data-stu-id="be03a-127">This example creates three database snapshots on the mirror copy of the `AdventureWorks` database, which resides on the `F` drive.</span></span> <span data-ttu-id="be03a-128">Las instantáneas se denominan `AdventureWorks_0600`, `AdventureWorks_1200`y `AdventureWorks_1800` para indicar su hora de creación aproximada.</span><span class="sxs-lookup"><span data-stu-id="be03a-128">The snapshots are named `AdventureWorks_0600`, `AdventureWorks_1200`, and `AdventureWorks_1800` to identify their approximate creation times.</span></span>  
  
1.  <span data-ttu-id="be03a-129">Cree la primera instantánea de base de datos en el reflejo de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be03a-129">Create the first database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_0600  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_0600.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
2.  <span data-ttu-id="be03a-130">Cree la segunda instantánea de base de datos en el reflejo de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be03a-130">Create the second database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="be03a-131">Los usuarios que aún utilicen `AdventureWorks_0600` podrán seguir utilizándola.</span><span class="sxs-lookup"><span data-stu-id="be03a-131">Users who are still using `AdventureWorks_0600` can continue to use it.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1200  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1200.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="be03a-132">En este momento, se podrán dirigir mediante programación las nuevas conexiones de cliente a la instantánea más reciente.</span><span class="sxs-lookup"><span data-stu-id="be03a-132">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
3.  <span data-ttu-id="be03a-133">Cree la tercera instantánea en el reflejo de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be03a-133">Create the third snapshot on the mirror [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="be03a-134">Los usuarios que aún utilicen `AdventureWorks_0600` o `AdventureWorks_1200` podrán seguir utilizándolas.</span><span class="sxs-lookup"><span data-stu-id="be03a-134">Users who are still using `AdventureWorks_0600` or `AdventureWorks_1200` can continue to use them.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1800  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1800.SNP')  
        AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="be03a-135">En este momento, se podrán dirigir mediante programación las nuevas conexiones de cliente a la instantánea más reciente.</span><span class="sxs-lookup"><span data-stu-id="be03a-135">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="be03a-136">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="be03a-136">Related Tasks</span></span>  
  
-   [<span data-ttu-id="be03a-137">Crear una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="be03a-137">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="be03a-138">Ver una instantánea de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="be03a-138">View a Database Snapshot &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="be03a-139">Eliminar una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="be03a-139">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  

  
## <a name="see-also"></a><span data-ttu-id="be03a-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be03a-140">See Also</span></span>  
 <span data-ttu-id="be03a-141">[Instantáneas de bases de datos &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="be03a-141">[Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span></span>  
 [<span data-ttu-id="be03a-142">Conectar clientes a una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="be03a-142">Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;</span></span>](connect-clients-to-a-database-mirroring-session-sql-server.md)  
  
  
