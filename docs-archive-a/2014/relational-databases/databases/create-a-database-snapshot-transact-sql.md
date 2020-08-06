---
title: Creación de una instantánea de base de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], creating
ms.assetid: 187fbba3-c555-4030-9bdf-0f01994c5230
author: stevestein
ms.author: sstein
ms.openlocfilehash: bae68c2d507e1dd3809e76a9d842b765d72234e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751122"
---
# <a name="create-a-database-snapshot-transact-sql"></a><span data-ttu-id="2f137-102">Crear una instantánea de base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2f137-102">Create a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="2f137-103">El único modo de crear una instantánea de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consiste en usar [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f137-103">The only way to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot is to use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="2f137-104">no admite la creación de instantáneas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f137-104">does not support the creation of database snapshots.</span></span>  
  
-   <span data-ttu-id="2f137-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2f137-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f137-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2f137-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="2f137-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2f137-107">Security</span></span>](#Security)  
  
     [<span data-ttu-id="2f137-108">Procedimiento recomendado: Asignar nombres a instantáneas de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-108">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   <span data-ttu-id="2f137-109">**Creación de una instantánea de base de datos utilizando lo siguiente:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="2f137-109">**To create a database snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f137-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2f137-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2f137-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2f137-111">Prerequisites</span></span>  
 <span data-ttu-id="2f137-112">La base de datos de origen, que puede usar cualquier modelo de recuperación, debe cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="2f137-112">The source database, which can use any recovery model, must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="2f137-113">La instancia del servidor debe ejecutarse en una edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que admita instantáneas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2f137-113">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports database snapshot.</span></span> <span data-ttu-id="2f137-114">Para obtener información sobre la compatibilidad con las instantáneas de base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , vea [características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="2f137-114">For information about support for database snapshots in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="2f137-115">La base de datos de origen debe estar en línea, a menos que sea una base de datos reflejada dentro de una sesión de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f137-115">The source database must be online, unless the database is a mirror database within a database mirroring session.</span></span>  
  
-   <span data-ttu-id="2f137-116">Para crear la instantánea de una base de datos en una base de datos reflejada, la base de datos debe encontrarse en el[estado de reflejo](../../database-engine/database-mirroring/mirroring-states-sql-server.md)sincronizado.</span><span class="sxs-lookup"><span data-stu-id="2f137-116">To create a database snapshot on a mirror database, the database must be in the synchronized[mirroring state](../../database-engine/database-mirroring/mirroring-states-sql-server.md).</span></span>  
  
-   <span data-ttu-id="2f137-117">La base de datos de origen no se puede configurar como una base de datos compartida escalable.</span><span class="sxs-lookup"><span data-stu-id="2f137-117">The source database cannot be configured as a scalable shared database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f137-118">Para obtener información sobre otras consideraciones importantes, vea [Instantáneas de base de datos &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2f137-118">For information about other significant considerations, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2f137-119">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="2f137-119">Recommendations</span></span>  
 <span data-ttu-id="2f137-120">En esta sección se describen los procedimientos recomendados siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f137-120">This section discusses the following best practices:</span></span>  
  
-   [<span data-ttu-id="2f137-121">Procedimiento recomendado: Asignar nombres a instantáneas de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-121">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   [<span data-ttu-id="2f137-122">Procedimiento recomendado: Limitar el número de instantáneas de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-122">Best Practice: Limiting the Number of Database Snapshots</span></span>](#Limiting_Number)  
  
-   [<span data-ttu-id="2f137-123">Procedimiento recomendado: Conexiones de cliente con una instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-123">Best Practice: Client Connections to a Database Snapshot</span></span>](#Client_Connections)  
  
####  <a name="best-practice-naming-database-snapshots"></a><a name="Naming"></a> <span data-ttu-id="2f137-124">Procedimiento recomendado: Asignar nombres a instantáneas de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-124">Best Practice: Naming Database Snapshots</span></span>  
 <span data-ttu-id="2f137-125">Antes de crear instantáneas, es importante pensar cómo asignarles un nombre.</span><span class="sxs-lookup"><span data-stu-id="2f137-125">Before creating snapshots, it is important to consider how to name them.</span></span> <span data-ttu-id="2f137-126">Cada instantánea de base de datos necesita un nombre de base de datos único.</span><span class="sxs-lookup"><span data-stu-id="2f137-126">Each database snapshot requires a unique database name.</span></span> <span data-ttu-id="2f137-127">Para facilitar la administración, el nombre de una instantánea puede incorporar información que identifique la base de datos, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f137-127">For administrative ease, the name of a snapshot can incorporate information that identifies the database, such as:</span></span>  
  
-   <span data-ttu-id="2f137-128">Nombre de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="2f137-128">The name of the source database.</span></span>  
  
-   <span data-ttu-id="2f137-129">Una indicación de que el nuevo nombre es para una instantánea.</span><span class="sxs-lookup"><span data-stu-id="2f137-129">An indication that the new name is for a snapshot.</span></span>  
  
-   <span data-ttu-id="2f137-130">La fecha y hora de creación de la instantánea, un número de secuencia o cualquier otra información, por ejemplo, la hora del día, para distinguir instantáneas secuenciales en una base de datos dada.</span><span class="sxs-lookup"><span data-stu-id="2f137-130">The creation date and time of the snapshot, a sequence number, or some other information, such as time of day, to distinguish sequential snapshots on a given database.</span></span>  
  
 <span data-ttu-id="2f137-131">Por ejemplo, piense en una serie de instantáneas de base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f137-131">For example, consider a series of snapshots for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="2f137-132">Se crean tres instantáneas diarias a intervalos de 6 horas entre las 06:00</span><span class="sxs-lookup"><span data-stu-id="2f137-132">Three daily snapshots are created at 6-hour intervals between 6 A.M.</span></span> <span data-ttu-id="2f137-133">y las 18:00, tomando como base un reloj de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="2f137-133">and 6 P.M., based on a 24-hour clock.</span></span> <span data-ttu-id="2f137-134">Cada instantánea diaria se conserva 24 horas antes de que se quite y sea reemplazada por una nueva instantánea con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="2f137-134">Each daily snapshot is kept for 24 hours before being dropped and replaced by a new snapshot of the same name.</span></span> <span data-ttu-id="2f137-135">Recuerde que cada nombre de instantánea indica la hora, pero no el día:</span><span class="sxs-lookup"><span data-stu-id="2f137-135">Note that each snapshot name indicates the hour, but not the day:</span></span>  
  
```  
AdventureWorks_snapshot_0600  
AdventureWorks_snapshot_1200  
AdventureWorks_snapshot_1800  
```  
  
 <span data-ttu-id="2f137-136">Como alternativa, si la hora de creación de estas instantáneas diarias varía cada día, es posible que sea preferible disponer de una convención de nomenclatura menos precisa, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f137-136">Alternatively, if the creation time of these daily snapshots varies from day to day, a less precise naming convention might be preferable, for example:</span></span>  
  
```  
AdventureWorks_snapshot_morning  
AdventureWorks_snapshot_noon  
AdventureWorks_snapshot_evening  
```  
  
####  <a name="best-practice-limiting-the-number-of-database-snapshots"></a><a name="Limiting_Number"></a> <span data-ttu-id="2f137-137">Procedimiento recomendado: Limitar el número de instantáneas de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-137">Best Practice: Limiting the Number of Database Snapshots</span></span>  
 <span data-ttu-id="2f137-138">La creación de una serie de instantáneas a lo largo del tiempo permite capturar instantáneas secuenciales de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="2f137-138">Creating a series of snapshots over time captures sequential snapshots of the source database.</span></span> <span data-ttu-id="2f137-139">Cada instantánea se conserva hasta que se quite de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="2f137-139">Each snapshot persists until it is explicitly dropped.</span></span> <span data-ttu-id="2f137-140">Las instantáneas siguen creciendo a medida que se actualizan las páginas originales, por lo que seguramente querrá ahorrar espacio en el disco eliminando una instantánea más antigua después de crear una nueva instantánea.</span><span class="sxs-lookup"><span data-stu-id="2f137-140">Because each snapshot will continue to grow as original pages are updated, you may want to conserve disk space by deleting an older snapshot after creating a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f137-141">Si desea volver a una instantánea de base de datos, debe eliminar cualquier otra instantánea de esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f137-141">If you want to revert to a database snapshot, you need to delete any other snapshots from that database.</span></span>  
  
####  <a name="best-practice-client-connections-to-a-database-snapshot"></a><a name="Client_Connections"></a> <span data-ttu-id="2f137-142">Procedimiento recomendado: Conexiones de cliente con una instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-142">Best Practice: Client Connections to a Database Snapshot</span></span>  
 <span data-ttu-id="2f137-143">Para usar una instantánea de base de datos, los clientes deben saber dónde encontrarla.</span><span class="sxs-lookup"><span data-stu-id="2f137-143">To use a database snapshot, clients need to know where to find it.</span></span> <span data-ttu-id="2f137-144">Los usuarios pueden leer de una instantánea de base de datos mientras se crea o elimina otra.</span><span class="sxs-lookup"><span data-stu-id="2f137-144">Users can read from one database snapshot while another is being created or deleted.</span></span> <span data-ttu-id="2f137-145">Sin embargo, si sustituye una nueva instantánea por otra ya existente, debe redirigir a los clientes a la nueva instantánea.</span><span class="sxs-lookup"><span data-stu-id="2f137-145">However, when you substitute a new snapshot for an existing one, you need to redirect clients to the new snapshot.</span></span> <span data-ttu-id="2f137-146">Los usuarios pueden conectarse manualmente a una instantánea de base de datos mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f137-146">Users can manually connect to a database snapshot by means of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2f137-147">Sin embargo, para admitir un entorno de producción, debe crear una solución programática que dirija de un modo transparente a los clientes de escritura de informes a la instantánea de base de datos más reciente de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f137-147">However, to support a production environment, you should create a programmatic solution that transparently directs report-writing clients to the latest database snapshot of the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f137-148">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2f137-148">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f137-149">Permisos</span><span class="sxs-lookup"><span data-stu-id="2f137-149">Permissions</span></span>  
 <span data-ttu-id="2f137-150">Todos los usuarios que pueden crear una base de datos pueden crear una instantánea de base de datos; sin embargo, para crear una instantánea de una base de datos reflejada, es necesario ser miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="2f137-150">Any user who can create a database can create a database snapshot; however, to create a snapshot of a mirror database, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="how-to-create-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2f137-151">Cómo crear una instantánea de base de datos (con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2f137-151">How to Create a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="2f137-152">**Para crear una instantánea de base de datos**</span><span class="sxs-lookup"><span data-stu-id="2f137-152">**To create a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f137-153">Para obtener un ejemplo de este procedimiento, vea [Ejemplos (Transact-SQL)](#TsqlExample), más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="2f137-153">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="2f137-154">Basándose en el tamaño actual de la base de datos de origen, asegúrese de que tiene suficiente espacio en disco para incluir la instantánea de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f137-154">Based on the current size of the source database, ensure that you have sufficient disk space to hold the database snapshot.</span></span> <span data-ttu-id="2f137-155">El tamaño máximo de una instantánea de base de datos es el tamaño de la base de datos de origen en el momento de la creación de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="2f137-155">The maximum size of a database snapshot is the size of the source database at snapshot creation.</span></span> <span data-ttu-id="2f137-156">Para obtener más información, vea [Ver el tamaño del archivo disperso de una instantánea de base de datos &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2f137-156">For more information, see [View the Size of the Sparse File of a Database Snapshot &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="2f137-157">Emita una instrucción CREATE DATABASE en los archivos que usen la cláusula AS SNAPSHOT OF.</span><span class="sxs-lookup"><span data-stu-id="2f137-157">Issue a CREATE DATABASE statement on the files using the AS SNAPSHOT OF clause.</span></span> <span data-ttu-id="2f137-158">Para crear una instantánea, se debe especificar el nombre lógico de cada archivo de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="2f137-158">Creating a snapshot requires specifying the logical name of every database file of the source database.</span></span> <span data-ttu-id="2f137-159">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f137-159">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="2f137-160">CREATE DATABASE *nombre_de_instantánea_de_base_de_datos*</span><span class="sxs-lookup"><span data-stu-id="2f137-160">CREATE DATABASE *database_snapshot_name*</span></span>  
  
     <span data-ttu-id="2f137-161">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="2f137-161">ON</span></span>  
  
     <span data-ttu-id="2f137-162">(</span><span class="sxs-lookup"><span data-stu-id="2f137-162">(</span></span>  
  
     <span data-ttu-id="2f137-163">NAME =*nombre_de_archivo_lógico*,</span><span class="sxs-lookup"><span data-stu-id="2f137-163">NAME =*logical_file_name*,</span></span>  
  
     <span data-ttu-id="2f137-164">FILENAME ='*nombre_de_archivo_de_sistema_operativo*'</span><span class="sxs-lookup"><span data-stu-id="2f137-164">FILENAME ='*os_file_name*'</span></span>  
  
     <span data-ttu-id="2f137-165">) [ ,...*n* ]</span><span class="sxs-lookup"><span data-stu-id="2f137-165">) [ ,...*n* ]</span></span>  
  
     <span data-ttu-id="2f137-166">AS SNAPSHOT OF *nombre_de_base_de_datos_de_origen*</span><span class="sxs-lookup"><span data-stu-id="2f137-166">AS SNAPSHOT OF *source_database_name*</span></span>  
  
     <span data-ttu-id="2f137-167">[;]</span><span class="sxs-lookup"><span data-stu-id="2f137-167">[;]</span></span>  
  
     <span data-ttu-id="2f137-168">Donde *nombre_base_de_datos\*\*_origen* es la base de datos de origen, *nombre_de_archivo_lógico* es el nombre lógico que se usa en SQL Server cuando se hace referencia al archivo, *nombre_de_archivo_de_sistema_operativo* es la ruta de acceso y el nombre de archivo que usa el sistema operativo cuando se crea el archivo y *nombre_de_instantánea_de_base_de_datos* es el nombre de la instantánea a la que quiere revertir la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f137-168">Where *source_\*\*database_name* is the source database, *logical_file_name i*s the logical name used in SQL Server when referencing the file, *os_file_name* is the path and file name used by the operating system when you create the file, and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="2f137-169">Para obtener una descripción completa de esta sintaxis, vea [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2f137-169">For a full description of this syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f137-170">Cuando se crea una instantánea de base de datos, no se permite la presencia de archivos de registro, archivos sin conexión, archivos de restauración e inactivos en la instrucción CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="2f137-170">When you create a database snapshot, log files, offline files, restoring files, and defunct files are not allowed in the CREATE DATABASE statement.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="2f137-171">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2f137-171">Examples (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f137-172">La extensión `.ss` que se usa en los ejemplos es arbitraria.</span><span class="sxs-lookup"><span data-stu-id="2f137-172">The `.ss` extension used in the examples is arbitrary.</span></span>  
  
 <span data-ttu-id="2f137-173">En esta sección se incluyen los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f137-173">This section contains the following examples:</span></span>  
  
-   <span data-ttu-id="2f137-174">A.</span><span class="sxs-lookup"><span data-stu-id="2f137-174">A.</span></span> [<span data-ttu-id="2f137-175">Crear una instantánea de la base datos AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="2f137-175">Creating a snapshot on the AdventureWorks database</span></span>](#Creating_on_AW)  
  
-   <span data-ttu-id="2f137-176">B.</span><span class="sxs-lookup"><span data-stu-id="2f137-176">B.</span></span> [<span data-ttu-id="2f137-177">Crear una instantánea de la base datos Sales</span><span class="sxs-lookup"><span data-stu-id="2f137-177">Creating a snapshot on the Sales database</span></span>](#Creating_on_Sales)  
  
####  <a name="a-creating-a-snapshot-on-the-adventureworks-database"></a><a name="Creating_on_AW"></a> <span data-ttu-id="2f137-178">A.</span><span class="sxs-lookup"><span data-stu-id="2f137-178">A.</span></span> <span data-ttu-id="2f137-179">Crear una instantánea de la base datos AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="2f137-179">Creating a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="2f137-180">En este ejemplo se crea una instantánea de base datos `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="2f137-180">This example creates a database snapshot on the `AdventureWorks` database.</span></span> <span data-ttu-id="2f137-181">El nombre de la instantánea, `AdventureWorks_dbss_1800`, y el nombre de archivo de su archivo disperso, `AdventureWorks_data_1800.ss`, indican la hora de creación: 6 P.M (1800 horas).</span><span class="sxs-lookup"><span data-stu-id="2f137-181">The snapshot name, `AdventureWorks_dbss_1800`, and the file name of its sparse file, `AdventureWorks_data_1800.ss`, indicate the creation time, 6 P.M (1800 hours).</span></span>  
  
```  
CREATE DATABASE AdventureWorks_dbss1800 ON  
( NAME = AdventureWorks_Data, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data\AdventureWorks_data_1800.ss' )  
AS SNAPSHOT OF AdventureWorks;  
GO  
```  
  
####  <a name="b-creating-a-snapshot-on-the-sales-database"></a><a name="Creating_on_Sales"></a> <span data-ttu-id="2f137-182">B.</span><span class="sxs-lookup"><span data-stu-id="2f137-182">B.</span></span> <span data-ttu-id="2f137-183">Crear una instantánea de la base datos Sales</span><span class="sxs-lookup"><span data-stu-id="2f137-183">Creating a snapshot on the Sales database</span></span>  
 <span data-ttu-id="2f137-184">En este ejemplo se crea una instantánea de base datos, `sales_snapshot1200`, en la base de datos `Sales` .</span><span class="sxs-lookup"><span data-stu-id="2f137-184">This example creates a database snapshot, `sales_snapshot1200`, on the `Sales` database.</span></span> <span data-ttu-id="2f137-185">Esta base de datos se creó en el ejemplo "crear una base de datos que tiene grupos de archivos" en [Create database &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2f137-185">This database was created in the example, "Creating a database that has filegroups," in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
```  
--Creating sales_snapshot1200 as snapshot of the  
--Sales database:  
CREATE DATABASE sales_snapshot1200 ON  
( NAME = SPri1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri1dat_1200.ss'),  
( NAME = SPri2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri2dt_1200.ss'),  
( NAME = SGrp1Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\mssql\data\SG1Fi1dt_1200.ss'),  
( NAME = SGrp1Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG1Fi2dt_1200.ss'),  
( NAME = SGrp2Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi1dt_1200.ss'),  
( NAME = SGrp2Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi2dt_1200.ss')  
AS SNAPSHOT OF Sales;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2f137-186">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="2f137-186">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2f137-187">Ver una instantánea de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2f137-187">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="2f137-188">Revertir una base de datos a una instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="2f137-188">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="2f137-189">Eliminar una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f137-189">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f137-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f137-190">See Also</span></span>  
 <span data-ttu-id="2f137-191">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f137-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="2f137-192">Instantáneas de bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2f137-192">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
