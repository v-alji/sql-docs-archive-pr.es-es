---
title: Separar y adjuntar bases de datos de DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 830e33bc-dd15-4f8e-a4ac-d8634b78fe45
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bcac9d1f53b10cf6356b878ce4006f66c198d99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669857"
---
# <a name="detaching-and-attaching-dqs-databases"></a><span data-ttu-id="1cfdd-102">Separar y adjuntar bases de datos de DQS</span><span class="sxs-lookup"><span data-stu-id="1cfdd-102">Detaching and Attaching DQS Databases</span></span>
  <span data-ttu-id="1cfdd-103">En este tema se describe cómo adjuntar y separar las bases de datos de DQS.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-103">This topic describes how to detach and attach the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1cfdd-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1cfdd-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="1cfdd-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="1cfdd-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1cfdd-106">Para obtener una lista de las limitaciones y restricciones, vea [Adjuntar y separar bases de datos &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1cfdd-106">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](../relational-databases/databases/database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1cfdd-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1cfdd-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="1cfdd-108">Asegúrese de que no haya actividades o procesos de DQS en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-108">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="1cfdd-109">Utilice la pantalla **Supervisión de actividades** para comprobarlo.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-109">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="1cfdd-110">Para obtener información detallada sobre cómo utilizar esta pantalla, vea [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="1cfdd-110">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="1cfdd-111">Asegúrese de que ningún usuario haya iniciado sesión en el [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cfdd-111">Ensure that there are no users logged on the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1cfdd-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1cfdd-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1cfdd-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="1cfdd-113">Permissions</span></span>  
  
-   <span data-ttu-id="1cfdd-114">La cuenta de usuario de Windows debe ser miembro del rol fijo de servidor db_owner en la instancia de SQL Server para separar bases de datos de DQS.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-114">Your Windows user account must be a member of the db_owner fixed server role in the SQL Server instance to detach DQS databases.</span></span>  
  
-   <span data-ttu-id="1cfdd-115">La cuenta de usuario de Windows debe tener el permiso CREATE DATABASE, CREATE ANY DATABASE o ALTER ANY DATABASE para adjuntar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-115">Your Windows user account must have CREATE DATABASE, CREATE ANY DATABASE, or ALTER ANY DATABASE permission to attach a database.</span></span>  
  
-   <span data-ttu-id="1cfdd-116">Debe disponer del rol dqs_administrator en la base de datos DQS_MAIN para terminar las actividades o detener los procesos en ejecución en DQS.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-116">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="detach-dqs-databases"></a><a name="Detach"></a><span data-ttu-id="1cfdd-117">Desasociar bases de datos de DQS</span><span class="sxs-lookup"><span data-stu-id="1cfdd-117">Detach DQS Databases</span></span>  
 <span data-ttu-id="1cfdd-118">Cuando se separa una base de datos de DQS mediante SQL Server Management Studio, los archivos separados permanecen en el equipo, y se pueden volver a adjuntar a la misma instancia de SQL Server o mover a otro servidor y adjuntarlos allí.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-118">When you detach a DQS database using SQL Server Management Studio, the detached files remain on your computer, and can be reattached to the same SQL Server instance or can be can be moved to another server and attached there.</span></span> <span data-ttu-id="1cfdd-119">Normalmente, los archivos de base de datos de DQS están disponibles en la siguiente ubicación en el equipo de Data Quality Services: C:\Archivos de Programa\microsoft SQL Server\MSSQL12. *<Instance_Name>* \MSSQL\DATA.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-119">The DQS database files are typically available at the following location on your Data Quality Services computer: C:\Program Files\Microsoft SQL Server\MSSQL12.*<Instance_Name>* \MSSQL\DATA.</span></span>  
  
1.  <span data-ttu-id="1cfdd-120">Inicie Microsoft SQL Server Management Studio y conéctese a la instancia adecuada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-120">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="1cfdd-121">En el Explorador de objetos, expanda el nodo **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="1cfdd-121">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="1cfdd-122">Haga clic con el botón secundario en la base de datos **DQS_MAIN** , seleccione **Tareas**y, a continuación, haga clic en **Separar**.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-122">Right-click the **DQS_MAIN** database, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="1cfdd-123">Aparecerá el cuadro de diálogo **Separar base de datos** .</span><span class="sxs-lookup"><span data-stu-id="1cfdd-123">The **Detach Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="1cfdd-124">Seleccione la casilla bajo la columna **Quitar** y haga clic en **Aceptar** para separar la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-124">Select the check box under the **Drop** column, and click **OK** to detach the DQS_MAIN database.</span></span>  
  
5.  <span data-ttu-id="1cfdd-125">Repita los pasos 3 y 4 con las bases de datos DQS_PROJECTS y DQS_STAGING_DATA para separarlas.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-125">Repeat steps 3 and 4 with the DQS_PROJECTS and DQS_STAGING_DATA databases to detach them.</span></span>  
  
 <span data-ttu-id="1cfdd-126">También puede separar bases de datos de DQS mediante instrucciones Transact-SQL; para ello, utilice el procedimiento almacenado sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-126">You can also detach DQS databases using the Transact-SQL statements by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="1cfdd-127">Para obtener más información sobre cómo separar bases de datos mediante instrucciones Transact-SQL, vea [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) en [Detach a Database](../relational-databases/databases/detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="1cfdd-127">For more information about detaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/detach-a-database.md#TsqlProcedure) in [Detach a Database](../relational-databases/databases/detach-a-database.md).</span></span>  
  
##  <a name="attach-dqs-databases"></a><a name="Attach"></a><span data-ttu-id="1cfdd-128">Adjuntar bases de datos de DQS</span><span class="sxs-lookup"><span data-stu-id="1cfdd-128">Attach DQS Databases</span></span>  
 <span data-ttu-id="1cfdd-129">Utilice las instrucciones siguientes para adjuntar una base de datos de DQS a la misma instancia de SQL Server (de la que se separó) o a una instancia de SQL Server diferente donde se ha instalado [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cfdd-129">Use the following instructions to attach a DQS database to the same SQL Server instance (from where you detached) or a different SQL Server instance where [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
1.  <span data-ttu-id="1cfdd-130">Inicie Microsoft SQL Server Management Studio y conéctese a la instancia adecuada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-130">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="1cfdd-131">En el Explorador de objetos, haga clic con el botón secundario del mouse en **Bases de datos**y, a continuación, haga clic en **Adjuntar**.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-131">In Object Explorer, right-click **Databases**, and then click **Attach**.</span></span> <span data-ttu-id="1cfdd-132">Aparecerá el cuadro de diálogo **Adjuntar bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="1cfdd-132">The **Attach Databases** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="1cfdd-133">Para especificar la base de datos que se va a adjuntar, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-133">To specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="1cfdd-134">Aparecerá el cuadro de diálogo **Buscar archivos de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="1cfdd-134">The **Locate Database Files** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="1cfdd-135">Seleccione la unidad de disco en la que se halla la base de datos y expanda el árbol de directorios para buscar y seleccionar el archivo .mdf de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-135">Select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database.</span></span> <span data-ttu-id="1cfdd-136">Por ejemplo, para la base de datos DQS_MAIN:</span><span class="sxs-lookup"><span data-stu-id="1cfdd-136">For example, for the DQS_MAIN database:</span></span>  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\DQS_MAIN.mdf  
    ```  
  
5.  <span data-ttu-id="1cfdd-137">El panel inferior, **Detalles de la base de datos** , muestra los nombres de los archivos que se van a adjuntar.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-137">The **database details** (lower) pane displays the names of the files to be attached.</span></span> <span data-ttu-id="1cfdd-138">Para comprobar o cambiar el nombre de la ruta de acceso de un archivo, haga clic en el botón **Examinar** ( ... ).</span><span class="sxs-lookup"><span data-stu-id="1cfdd-138">To verify or change the pathname of a file, click the **Browse** button (...).</span></span>  
  
6.  <span data-ttu-id="1cfdd-139">Para adjuntar la base de datos DQS_MAIN, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="1cfdd-139">Click **OK** to attach the DQS_MAIN database.</span></span>  
  
7.  <span data-ttu-id="1cfdd-140">Repita los pasos 2 a 6 con las bases de datos DQS_PROJECTS y DQS_STAGING_DATA para adjuntarlas.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-140">Repeat steps 2-6 for the DQS_PROJECTS and DQS_STAGING_DATA databases to attach them.</span></span>  
  
8.  <span data-ttu-id="1cfdd-141">También se deben ejecutar las instrucciones Transact-SQL del paso siguiente después de restaurar la base de datos DQS_MAIN; de lo contrario, se mostrará un mensaje de error al intentar conectar con el servidor Data Quality Server mediante la aplicación Data Quality Client, y no se podrá conectar.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-141">You must also run the Transact-SQL statements in the next step after restoring the DQS_MAIN database otherwise an error message is displayed when you try to connect to Data Quality Server by using the Data Quality Client application, and you cannot connect.</span></span> <span data-ttu-id="1cfdd-142">Sin embargo, no es necesario realizar los pasos 9 y 10 si acaba de adjuntar la base de datos DQS_PROJECTS o DQS_STAGING_DATA, no la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-142">However, you do not need to perform steps 9 and 10 if you have just attached the DQS_PROJECTS or DQS_STAGING_DATA database, and not DQS_MAIN.</span></span>  
  
     <span data-ttu-id="1cfdd-143">En el Explorador de objetos, haga clic con el botón secundario en el servidor y, a continuación, haga clic en **Nueva consulta**para ejecutar las instrucciones Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-143">To run the Transact-SQL statements, in Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
9. <span data-ttu-id="1cfdd-144">En la ventana del editor de consultas, copie las instrucciones SQL siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cfdd-144">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    ALTER DATABASE [DQS_MAIN] SET TRUSTWORTHY ON;  
    EXEC sp_configure 'clr enabled', 1;  
    RECONFIGURE WITH OVERRIDE  
    ALTER DATABASE [DQS_MAIN] SET ENABLE_BROKER  
    ALTER AUTHORIZATION ON DATABASE::[DQS_MAIN] TO [##MS_dqs_db_owner_login##]  
    ALTER AUTHORIZATION ON DATABASE::[DQS_PROJECTS] TO [##MS_dqs_db_owner_login##]  
    ```  
  
10. <span data-ttu-id="1cfdd-145">Presione F5 para ejecutar las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-145">Press F5 to execute the statements.</span></span> <span data-ttu-id="1cfdd-146">Vea el panel Resultados para comprobar que las instrucciones se han ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-146">Check the Results pane to verify that the statements have executed successfully.</span></span> <span data-ttu-id="1cfdd-147">Aparecerá el mensaje siguiente: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span><span class="sxs-lookup"><span data-stu-id="1cfdd-147">You will see the following message: `Configuration option 'clr enabled' changed from 1 to 1. Run the RECONFIGURE statement to install.`</span></span>  
  
11. <span data-ttu-id="1cfdd-148">Conéctese con el servidor Data Quality Server mediante Data Quality Client para comprobar si la conexión funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-148">Connect to the Data Quality Server using the Data Quality Client to verify if you can connect successfully.</span></span>  
  
 <span data-ttu-id="1cfdd-149">También se pueden adjuntar bases de datos de DQS utilizando las instrucciones Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="1cfdd-149">You can also attach DQS databases using the Transact-SQL statements.</span></span> <span data-ttu-id="1cfdd-150">Para obtener más información sobre cómo adjuntar bases de datos mediante instrucciones Transact-SQL, vea [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) en [Attach a Database](../relational-databases/databases/attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="1cfdd-150">For more information about attaching databases using Transact-SQL statements, see [Using Transact-SQL](../relational-databases/databases/attach-a-database.md#TsqlProcedure) in [Attach a Database](../relational-databases/databases/attach-a-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfdd-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1cfdd-151">See Also</span></span>  
 [<span data-ttu-id="1cfdd-152">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="1cfdd-152">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
