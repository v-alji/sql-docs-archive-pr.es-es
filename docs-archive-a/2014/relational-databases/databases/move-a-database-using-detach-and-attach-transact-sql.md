---
title: Movimiento de una base de datos mediante Separar y Adjuntar (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database attaching [SQL Server]
- moving databases [SQL Server]
- database detaching [SQL Server]
- relocating databases [SQL Server]
- detaching databases [SQL Server]
- attaching databases [SQL Server]
ms.assetid: 6732a431-cdef-4f1e-9262-4ac3b77c275e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 768a70dfe94af6f8d65f7c76fa08d3dff650fe7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677659"
---
# <a name="move-a-database-using-detach-and-attach-transact-sql"></a><span data-ttu-id="9e447-102">Mover una base de datos mediante Separar y Adjuntar (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9e447-102">Move a Database Using Detach and Attach (Transact-SQL)</span></span>
  <span data-ttu-id="9e447-103">En este tema se describe cómo mover una base de datos separada a otra ubicación y volver a adjuntarla a la misma instancia de servidor o a otra en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e447-103">This topic describes how to move a detached database to another location and re-attach it to the same or a different server instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="9e447-104">No obstante, se recomienda mover las bases de datos mediante el procedimiento de reubicación programada ALTER DATABASE, en lugar usar las operaciones de separar y adjuntar.</span><span class="sxs-lookup"><span data-stu-id="9e447-104">However, we recommend that you move databases by using the ALTER DATABASE planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="9e447-105">Para más información, consulte [Move User Databases](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9e447-105">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9e447-106">Se recomienda no adjuntar ni restaurar bases de datos de orígenes desconocidos o que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="9e447-106">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="9e447-107">Es posible que dichas bases de datos contengan código malintencionado que podría ejecutar código [!INCLUDE[tsql](../../includes/tsql-md.md)] no deseado o provocar errores al modificar el esquema o la estructura de la base de datos física.</span><span class="sxs-lookup"><span data-stu-id="9e447-107">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="9e447-108">Para usar una base de datos desde un origen desconocido o que no sea de confianza, ejecute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) en la base de datos de un servidor que no sea de producción y examine también el código, como procedimientos almacenados u otro código definido por el usuario, en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e447-108">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="9e447-109">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="9e447-109">Procedure</span></span>  
  
#### <a name="to-move-a-database-by-using-detach-and-attach"></a><span data-ttu-id="9e447-110">Para mover una base de datos mediante la operación de separar y adjuntar</span><span class="sxs-lookup"><span data-stu-id="9e447-110">To move a database by using detach and attach</span></span>  
  
1.  <span data-ttu-id="9e447-111">Separe la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e447-111">Detach the database.</span></span> <span data-ttu-id="9e447-112">Para obtener más información, vea [Separar una base de datos](detach-a-database.md)</span><span class="sxs-lookup"><span data-stu-id="9e447-112">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
2.  <span data-ttu-id="9e447-113">En el Explorador de Windows o en una ventana del símbolo del sistema de Windows, mueva el archivo o archivos de la base de datos separada y el archivo o archivos de registro a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="9e447-113">In a Windows Explorer or Windows Command Prompt window, move the detached database file or files and log file or files to the new location.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9e447-114">Para mover una base de datos de un solo archivo, puede usar el correo electrónico si el tamaño del archivo es lo suficientemente pequeño para acomodar el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e447-114">To move a single-file database, you can use email if the file size is small enough for email to accommodate.</span></span>  
  
     <span data-ttu-id="9e447-115">Debe mover los archivos de registro, incluso si piensa crear nuevos archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="9e447-115">You should move the log files even if you intend to create new log files.</span></span> <span data-ttu-id="9e447-116">En algunos casos, para volver a adjuntar una base de datos son necesarios sus archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="9e447-116">In some cases, reattaching a database requires its existing log files.</span></span> <span data-ttu-id="9e447-117">Por tanto, mantenga siempre todos los archivos de registro separados hasta que la base de datos se haya adjuntado correctamente sin ellos.</span><span class="sxs-lookup"><span data-stu-id="9e447-117">Therefore, always keep all the detached log files until the database has been successfully attached without them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9e447-118">Si intenta adjuntar la base de datos sin especificar el archivo de registro, la operación de adjuntar buscará el archivo de registro en su ubicación original.</span><span class="sxs-lookup"><span data-stu-id="9e447-118">If you try to attach the database without specifying the log file, the attach operation will look for the log file in its original location.</span></span> <span data-ttu-id="9e447-119">Si aún hay una copia del registro en la ubicación original, se adjunta esa copia.</span><span class="sxs-lookup"><span data-stu-id="9e447-119">If a copy of the log still exists in the original location, that copy is attached.</span></span> <span data-ttu-id="9e447-120">Para evitar que se utilice el archivo de registro original, especifique la ruta de acceso del nuevo archivo de registro o elimine la copia original del archivo de registro (después de copiarlo en la nueva ubicación).</span><span class="sxs-lookup"><span data-stu-id="9e447-120">To avoid using the original log file, either specify the path of the new log file or remove the original copy of the log file (after copying it to the new location).</span></span>  
  
3.  <span data-ttu-id="9e447-121">Adjunte los archivos copiados.</span><span class="sxs-lookup"><span data-stu-id="9e447-121">Attach the copied files.</span></span> <span data-ttu-id="9e447-122">Para obtener más información, consulte [Attach a Database](attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="9e447-122">For more information, see [Attach a Database](attach-a-database.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e447-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e447-123">Example</span></span>  
 <span data-ttu-id="9e447-124">En el ejemplo siguiente se crea una copia de las [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] instrucciones que se ejecutan en una ventana del editor de consultas que está conectada a la instancia del servidor a la que está asociada.</span><span class="sxs-lookup"><span data-stu-id="9e447-124">The following example creates a copy of the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements are executed in a Query Editor window that is connected to the server instance to which is attached.</span></span>  
  
1.  <span data-ttu-id="9e447-125">Desasocie las [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] instrucciones:</span><span class="sxs-lookup"><span data-stu-id="9e447-125">Detach the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sp_detach_db @dbname = N'AdventureWorks2012';  
    GO  
    ```  
  
2.  <span data-ttu-id="9e447-126">Mediante el método que elija, copie los archivos de la base de datos (AdventureWorks208R2_Data.mdf y AdventureWorks208R2_log) a: C:\MySQLServer\AdventureWorks208R2_Data.mdf y C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9e447-126">Using the method of your choice, copy the database files (AdventureWorks208R2_Data.mdf and AdventureWorks208R2_log) to: C:\MySQLServer\AdventureWorks208R2_Data.mdf and C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectively.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9e447-127">En el caso de una base de datos de producción, coloque la base de datos y el registro de transacciones en discos independientes.</span><span class="sxs-lookup"><span data-stu-id="9e447-127">For a production database, place the database and transaction log on separate disks.</span></span>  
  
     <span data-ttu-id="9e447-128">Para copiar archivos a través de la red en un disco de un equipo remoto, use el nombre UNC (Convención de nomenclatura universal) de la ubicación remota.</span><span class="sxs-lookup"><span data-stu-id="9e447-128">To copy files over the network to a disk on a remote computer, use the universal naming convention (UNC) name of the remote location.</span></span> <span data-ttu-id="9e447-129">Un nombre UNC toma la forma **\\\\** _nombreDeServidor_ **\\** _nombreDelRecursoCompartido_ **\\** _rutaDeAcceso_ **\\** _nombreDeArchivo_.</span><span class="sxs-lookup"><span data-stu-id="9e447-129">A UNC name takes the form **\\\\**_Servername_**\\**_Sharename_**\\**_Path_**\\**_Filename_.</span></span> <span data-ttu-id="9e447-130">De la misma forma que al escribir archivos en el disco duro local, se debe conceder a la cuenta de usuario que usa la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]los permisos necesarios para leer o escribir en archivos del disco remoto.</span><span class="sxs-lookup"><span data-stu-id="9e447-130">As with writing files to the local hard disk, the appropriate permissions that are required to read or write to a file on the remote disk must be granted to the user account used by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="9e447-131">Adjunte la base de datos movida y, opcionalmente, su registro ejecutando las siguientes instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e447-131">Attach the moved database and, optionally, its log by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Data.mdf'),  
        (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Log.ldf')  
        FOR ATTACH;  
    GO  
    ```  
  
     <span data-ttu-id="9e447-132">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], una base de datos recién adjuntada no es inmediatamente visible en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="9e447-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a newly attached database is not immediately visible in Object Explorer.</span></span> <span data-ttu-id="9e447-133">Para ver la base de datos, en el Explorador de objetos, haga clic en **Ver** y, a continuación, en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="9e447-133">To view the database, in Object Explorer, click **View,** and then **Refresh**.</span></span> <span data-ttu-id="9e447-134">Cuando se expande el nodo **Bases de datos** en el Explorador de objetos, la base de datos recién adjuntada aparecerá en la lista de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="9e447-134">When the **Databases** node is expanded in Object Explorer, the newly attached database now appears in the list of databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e447-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e447-135">See Also</span></span>  
 [<span data-ttu-id="9e447-136">Adjuntar y separar bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9e447-136">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
