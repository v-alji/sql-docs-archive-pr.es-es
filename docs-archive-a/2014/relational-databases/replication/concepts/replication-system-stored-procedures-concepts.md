---
title: Conceptos sobre los procedimientos almacenados del sistema de replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- stored procedures [SQL Server replication], programming
- programming [SQL Server replication], system stored procedures
- programming interfaces [SQL Server replication]
- system stored procedures [SQL Server replication]
- replication [SQL Server], how-to topics
ms.assetid: 816d2bda-ed72-43ec-aa4d-7ee3dc25fd8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 50536e5b6816c84dff26c9c9f99c46d02272b7de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750750"
---
# <a name="replication-system-stored-procedures-concepts"></a><span data-ttu-id="4e7c4-102">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="4e7c4-102">Replication System Stored Procedures Concepts</span></span>
  <span data-ttu-id="4e7c4-103">En [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], el acceso mediante programación a toda la funcionalidad configurable por el usuario en una topología de replicación se proporciona mediante procedimientos almacenados del sistema.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], programmatic access to all of the user-configurable functionality in a replication topology is provided by system stored procedures.</span></span> <span data-ttu-id="4e7c4-104">Aunque los procedimientos almacenados se pueden ejecutar individualmente utilizando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o el programa de línea de comandos sqlcmd, puede ser beneficioso escribir archivos de script de [!INCLUDE[tsql](../../../includes/tsql-md.md)] que se pueden ejecutar para realizar una secuencia lógica de tareas de replicación.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-104">While stored procedures may be executed individually using the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or the sqlcmd command-line utility, it may be beneficial to write [!INCLUDE[tsql](../../../includes/tsql-md.md)] script files that can be executed to perform a logical sequence of replication tasks.</span></span>  
  
 <span data-ttu-id="4e7c4-105">Las tareas de replicación para scripting proporcionan las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e7c4-105">Scripting replication tasks provides the following benefits:</span></span>  
  
-   <span data-ttu-id="4e7c4-106">Se mantiene una copia permanente de los pasos que se usan para implementar la topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-106">Keeps a permanent copy of the steps used to deploy your replication topology.</span></span>  
  
-   <span data-ttu-id="4e7c4-107">Se usa un único script para configurar varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-107">Uses a single script to configure multiple Subscribers.</span></span>  
  
-   <span data-ttu-id="4e7c4-108">Se instruye rápidamente a los nuevos administradores de bases de datos permitiéndoles evaluar, entender, cambiar o solucionar problemas del código.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-108">Quickly educates new database administrators by enabling them to evaluate, understand, change, or troubleshoot the code.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4e7c4-109">Los scripts pueden ser fuente de vulnerabilidades de la seguridad, ya que pueden invocar funciones del sistema sin la intervención ni el conocimiento del usuario y contener credenciales de seguridad en texto simple.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-109">Scripts can be the source of security vulnerabilities; they can invoke system functions without user knowledge or intervention and may contain security credentials in plain text.</span></span> <span data-ttu-id="4e7c4-110">Antes de usarlos, compruebe los aspectos siguientes de la seguridad de los scripts.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-110">Review scripts for security issues before you use them.</span></span>  
  
## <a name="creating-replication-scripts"></a><span data-ttu-id="4e7c4-111">Crear scripts de replicación</span><span class="sxs-lookup"><span data-stu-id="4e7c4-111">Creating Replication Scripts</span></span>  
 <span data-ttu-id="4e7c4-112">Desde el punto de vista de la replicación, un script es una serie de una o varias instrucciones de [!INCLUDE[tsql](../../../includes/tsql-md.md)] que cada una ejecuta un procedimiento almacenado de replicación.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-112">From the standpoint of replication, a script is a series of one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements where each statement executes a replication stored procedure.</span></span> <span data-ttu-id="4e7c4-113">Los scripts son archivos de texto, a menudo con la extensión .sql, que se pueden ejecutar utilizando la utilidad sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-113">Scripts are text files, often with a .sql file extension, that can be run using the sqlcmd utility.</span></span> <span data-ttu-id="4e7c4-114">Cuando se ejecuta un archivo de script, la utilidad ejecuta las instrucciones de SQL almacenadas en él.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-114">When a script file is run, the utility executes the SQL statements stored in the file.</span></span> <span data-ttu-id="4e7c4-115">De igual forma, un script puede almacenarse como un objeto de consulta en un proyecto de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e7c4-115">Similarly, a script can be stored as a query object in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span>  
  
 <span data-ttu-id="4e7c4-116">Los scripts de replicación se pueden crear de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e7c4-116">Replication scripts can be created in the following ways:</span></span>  
  
-   <span data-ttu-id="4e7c4-117">Cree el script manualmente.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-117">Manually create the script.</span></span>  
  
-   <span data-ttu-id="4e7c4-118">Use las características de generación de script que se proporcionan en los asistentes de replicación o</span><span class="sxs-lookup"><span data-stu-id="4e7c4-118">Use the script generation features that are provided in the replication wizards or</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="4e7c4-119">.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-119">.</span></span> <span data-ttu-id="4e7c4-120">Para más información, consulte [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4e7c4-120">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
-   <span data-ttu-id="4e7c4-121">Utilice Replication Management Objects (RMO) para generar mediante programación el script y crear un objeto RMO.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-121">Use Replication Management Objects (RMOs) to programmatically generate the script to create an RMO object.</span></span>  
  
 <span data-ttu-id="4e7c4-122">Al crear manualmente los scripts de replicación, tenga presente las consideraciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e7c4-122">When you manually create replication scripts, keep the following considerations in mind:</span></span>  
  
-   <span data-ttu-id="4e7c4-123">Los scripts [!INCLUDE[tsql](../../../includes/tsql-md.md)] constan de uno o varios lotes.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-123">[!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts have one or more batches.</span></span> <span data-ttu-id="4e7c4-124">El comando GO señala el final de un lote.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-124">The GO command signals the end of a batch.</span></span> <span data-ttu-id="4e7c4-125">Si un script de [!INCLUDE[tsql](../../../includes/tsql-md.md)] no contiene ningún comando GO, se ejecutará como un único lote.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-125">If a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script does not have any GO commands, it is executed as a single batch.</span></span>  
  
-   <span data-ttu-id="4e7c4-126">Al ejecutar varios procedimientos almacenados de la replicación en un único lote, después del primer procedimiento, la palabra clave EXECUTE debe preceder todos a los procedimientos subsiguientes en el lote.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-126">When executing multiple replication stored procedures in a single batch, after the first procedure, all subsequent procedures in the batch must be preceded by the EXECUTE keyword.</span></span>  
  
-   <span data-ttu-id="4e7c4-127">Todos los procedimientos almacenados en un lote deben compilarse antes de que se ejecute un lote.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-127">All stored procedures in a batch must compile before a batch will execute.</span></span> <span data-ttu-id="4e7c4-128">Sin embargo, una vez compilado el lote y creado un plan de ejecución, un error de tiempo de ejecución puede aparecer o no.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-128">However, once the batch has been compiled, and an execution plan has been created, a run-time error may or may not occur.</span></span>  
  
-   <span data-ttu-id="4e7c4-129">Al crear scripts para configurar la replicación, debería utilizar la autenticación de Windows para evitar almacenar las credenciales de seguridad en el archivo de script.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-129">When creating scripts to configure replication, you should use Windows Authentication to avoid storing security credentials in the script file.</span></span> <span data-ttu-id="4e7c4-130">Si debe almacenar las credenciales en un archivo de script, proteja el archivo para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-130">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
## <a name="sample-replication-script"></a><span data-ttu-id="4e7c4-131">Ejemplo de script de replicación</span><span class="sxs-lookup"><span data-stu-id="4e7c4-131">Sample Replication Script</span></span>  
 <span data-ttu-id="4e7c4-132">El script siguiente se puede ejecutar para configurar la publicación y distribución en un servidor.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-132">The following script can be executed to setup publishing and distribution on a server.</span></span>  
  
```  
-- This script uses sqlcmd scripting variables. They are in the form  
-- $(MyVariable). For information about how to use scripting variables    
-- on the command line and in SQL Server Management Studio, see the   
-- "Executing Replication Scripts" section in the topic  
-- "Programming Replication Using System Stored Procedures".  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
-- Specify the replication working directory.  
SET @directory = N'\\' + $(DistPubServer) + '\repldata';  
-- Specify the publication database.  
SET @publicationDB = N'AdventureWorks2012';   
  
-- Install the server MYDISTPUB as a Distributor using the defaults,  
-- including autogenerating the distributor password.  
USE master  
EXEC sp_adddistributor @distributor = @distributor;  
  
-- Create a new distribution database using the defaults, including  
-- using Windows Authentication.  
USE master  
EXEC sp_adddistributiondb @database = @distributionDB,   
    @security_mode = 1;  
GO  
  
-- Create a Publisher and enable AdventureWorks2012 for replication.  
-- Add MYDISTPUB as a publisher with MYDISTPUB as a local distributor  
-- and use Windows Authentication.  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
USE [distribution]  
EXEC sp_adddistpublisher @publisher=@publisher,   
    @distribution_db=@distributionDB,   
    @security_mode = 1;  
GO  
  
```  
  
 <span data-ttu-id="4e7c4-133">Este script puede guardarse entonces localmente como `instdistpub.sql` para que se pueda ejecutar o volver a ejecutar cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-133">This script can then be saved locally as `instdistpub.sql` so that it can be run or rerun when needed.</span></span>  
  
 <span data-ttu-id="4e7c4-134">El script anterior incluye variables de scripting de **sqlcmd**, que se usan en muchos de los ejemplos de código de replicación de los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e7c4-134">The previous script includes **sqlcmd** scripting variables, which are used in many of the replication code samples in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="4e7c4-135">Las variables de scripting se definen con la sintaxis `$(MyVariable)`.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-135">Scripting variables are defined by using `$(MyVariable)` syntax.</span></span> <span data-ttu-id="4e7c4-136">Los valores para las variables se pueden pasar a un script en la línea de comandos o en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e7c4-136">Values for variables can be passed to a script at the command line or in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4e7c4-137">Para obtener más información, consulte la sección siguiente en este tema, "Ejecutar scripts de replicación".</span><span class="sxs-lookup"><span data-stu-id="4e7c4-137">For more information, see the next section in this topic, "Executing Replication Scripts."</span></span>  
  
## <a name="executing-replication-scripts"></a><span data-ttu-id="4e7c4-138">Ejecutar scripts de replicación</span><span class="sxs-lookup"><span data-stu-id="4e7c4-138">Executing Replication Scripts</span></span>  
 <span data-ttu-id="4e7c4-139">Una vez creado, un script de replicación se puede ejecutar de alguna de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e7c4-139">Once created, a replication script can be executed in one of the following ways:</span></span>  
  
### <a name="creating-a-sql-query-file-in-sql-server-management-studio"></a><span data-ttu-id="4e7c4-140">Crear un archivo de SQL Query en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e7c4-140">Creating a SQL Query File in SQL Server Management Studio</span></span>  
 <span data-ttu-id="4e7c4-141">Un archivo de script de [!INCLUDE[tsql](../../../includes/tsql-md.md)] de replicación se puede crear como un archivo SQL de SQL Query en un proyecto de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e7c4-141">A replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] script file can be created as a SQL Query file in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span> <span data-ttu-id="4e7c4-142">Una vez escrito el script, se puede realizar una conexión a la base de datos para este archivo de consulta y se puede ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-142">After the script is written, a connection can be made to the database for this query file and the script can be executed.</span></span> <span data-ttu-id="4e7c4-143">Para obtener más información sobre cómo crear [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , vea [editores de consultas y texto &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span><span class="sxs-lookup"><span data-stu-id="4e7c4-143">For more information about how to create [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], see [Query and Text Editors &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span></span>  
  
 <span data-ttu-id="4e7c4-144">Para usar un script que incluya variables de scripting, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] debe estar ejecutándose en modo **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-144">To use a script that includes scripting variables, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] must be running in **sqlcmd** mode.</span></span> <span data-ttu-id="4e7c4-145">En el modo **sqlcmd**, el Editor de consultas acepta una sintaxis adicional concreta de **sqlcmd**, como `:setvar`, que se usa como valor de una variable.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-145">In **sqlcmd** mode, the Query Editor accepts additional syntax specific to **sqlcmd**, such as `:setvar`, which is used to a value for a variable.</span></span> <span data-ttu-id="4e7c4-146">Para obtener más información sobre el modo **sqlcmd**, vea [Modificar scripts SQLCMD con el Editor de consultas](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4e7c4-146">For more information about **sqlcmd** mode, see [Edit SQLCMD Scripts with Query Editor](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span> <span data-ttu-id="4e7c4-147">En el script siguiente se usa `:setvar` para proporcionar un valor para la variable `$(DistPubServer)`.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-147">In the following script, `:setvar` is used to provide a value for the `$(DistPubServer)` variable.</span></span>  
  
```  
:setvar DistPubServer N'MyPublisherAndDistributor';  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
--  
-- Additional code goes here  
--  
```  
  
### <a name="using-the-sqlcmd-utility-from-the-command-line"></a><span data-ttu-id="4e7c4-148">Usar la utilidad sqlcmd desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="4e7c4-148">Using the sqlcmd Utility from the Command Line</span></span>  
 <span data-ttu-id="4e7c4-149">El ejemplo siguiente muestra cómo se usa la línea de comandos para ejecutar el archivo de script `instdistpub.sql` mediante la [utilidad sqlcmd](../../../tools/sqlcmd-utility.md):</span><span class="sxs-lookup"><span data-stu-id="4e7c4-149">The following example shows how the command line is used to execute the `instdistpub.sql` script file using the [sqlcmd utility](../../../tools/sqlcmd-utility.md):</span></span>  
  
```  
sqlcmd.exe -E -S sqlserverinstance -i C:\instdistpub.sql -o C:\output.log -v DistPubServer="N'MyDistributorAndPublisher'"  
```  
  
 <span data-ttu-id="4e7c4-150">En este ejemplo, el modificador `-E` indica que al conectarse a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se utiliza la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-150">In this example, the `-E` switch indicates that Windows Authentication is used when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4e7c4-151">Al usar la autenticación de Windows, no hay necesidad de almacenar un nombre de usuario y una contraseña en el archivo de script.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-151">When using Windows Authentication, there is no need to store a username and password in the script file.</span></span> <span data-ttu-id="4e7c4-152">El modificador `-i` especifica el nombre y la ruta de acceso del archivo de script y el modificador `-o` especifica el nombre del archivo de salida (cuando se utiliza este modificador, la salida de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se escribe en este archivo en lugar de en la consola).</span><span class="sxs-lookup"><span data-stu-id="4e7c4-152">The name and path of the script file is specified by the `-i` switch and the name of the output file is specified by the `-o` switch (output from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is written to this file instead of the console when this switch is used).</span></span> <span data-ttu-id="4e7c4-153">La utilidad `sqlcmd` le permite pasar las variables de scripting a un script de [!INCLUDE[tsql](../../../includes/tsql-md.md)] en tiempo de ejecución utilizando el modificador `-v`.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-153">The `sqlcmd` utility enables you to pass scripting variables to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script at runtime using the `-v` switch.</span></span> <span data-ttu-id="4e7c4-154">En este ejemplo, `sqlcmd` reemplaza cada instancia de `$(DistPubServer)` en el script con el valor `N'MyDistributorAndPublisher'` antes de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-154">In this example, `sqlcmd` replaces every instance of `$(DistPubServer)` in the script with the value `N'MyDistributorAndPublisher'` before execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e7c4-155">El modificador `-X` deshabilita las variables de scripting.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-155">The `-X` switch disables scripting variables.</span></span>  
  
### <a name="automating-tasks-in-a-batch-file"></a><span data-ttu-id="4e7c4-156">Automatizar tareas en un archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="4e7c4-156">Automating Tasks in a Batch File</span></span>  
 <span data-ttu-id="4e7c4-157">Mediante un archivo por lotes, las tareas de administración de replicación, las tareas de sincronización de replicación y otras diversas se pueden automatizar en el mismo archivo por lotes.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-157">By using a batch file, replication administration tasks, replication synchronization tasks, and other tasks can be automated in the same batch file.</span></span> <span data-ttu-id="4e7c4-158">El archivo por lotes siguiente usa la utilidad **sqlcmd** para quitar y volver a crear la base de datos de suscripciones y agregar una suscripción de extracción de mezcla.</span><span class="sxs-lookup"><span data-stu-id="4e7c4-158">The following batch file uses the **sqlcmd** utility to drop and recreate the subscription database and add a merge pull subscription.</span></span> <span data-ttu-id="4e7c4-159">A continuación, el archivo invoca al agente de mezcla para sincronizar la nueva suscripción:</span><span class="sxs-lookup"><span data-stu-id="4e7c4-159">Then the file invokes the merge agent to synchronize the new subscription:</span></span>  
  
```  
REM ----------------------Script to synchronize merge subscription ----------------------  
REM -- Creates subscription database and   
REM -- synchronizes the subscription to MergeSalesPerson.  
REM -- Current computer acts as both Publisher and Subscriber.  
REM -------------------------------------------------------------------------------------  
  
SET Publisher=%computername%  
SET Subscriber=%computername%  
SET PubDb=AdventureWorks  
SET SubDb=AdventureWorksReplica  
SET PubName=AdvWorksSalesOrdersMerge  
  
REM -- Drop and recreate the subscription database at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE master IF EXISTS (SELECT * FROM sysdatabases WHERE name='%SubDb%' ) DROP DATABASE %SubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE master CREATE DATABASE %SubDb%"  
  
REM -- Add a pull subscription at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb% EXEC sp_addmergepullsubscription @publisher = %Publisher%, @publication = %PubName%, @publisher_db = %PubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb%  EXEC sp_addmergepullsubscription_agent @publisher = %Publisher%, @publisher_db = %PubDb%, @publication = %PubName%, @subscriber = %Subscriber%, @subscriber_db = %SubDb%, @distributor = %Publisher%"  
  
REM -- This batch file starts the merge agent at the Subscriber to   
REM -- synchronize a pull subscription to a merge publication.  
REM -- The following must be supplied on one line.  
"\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher  %Publisher% -Subscriber  %Subscriber%  -Distributor %Publisher%  -PublisherDB  %PubDb% -SubscriberDB %SubDb% -Publication %PubName% -PublisherSecurityMode 1 -OutputVerboseLevel 1  -Output  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1 -Validate 3  
  
```  
  
## <a name="scripting-common-replication-tasks"></a><span data-ttu-id="4e7c4-160">Incluir en script tareas de replicación comunes</span><span class="sxs-lookup"><span data-stu-id="4e7c4-160">Scripting Common Replication Tasks</span></span>  
 <span data-ttu-id="4e7c4-161">Las siguientes son algunas de las tareas de replicación más comunes que se pueden incluir en scripts utilizando procedimientos almacenados del sistema:</span><span class="sxs-lookup"><span data-stu-id="4e7c4-161">The following are some of the most common replication tasks can be scripted using system stored procedures:</span></span>  
  
-   <span data-ttu-id="4e7c4-162">Configurar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="4e7c4-162">Configuring publishing and distribution</span></span>  
  
-   <span data-ttu-id="4e7c4-163">Modificar las propiedades del distribuidor y del publicador</span><span class="sxs-lookup"><span data-stu-id="4e7c4-163">Modifying Publisher and Distributor properties</span></span>  
  
-   <span data-ttu-id="4e7c4-164">Deshabilitar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="4e7c4-164">Disabling publishing and distribution</span></span>  
  
-   <span data-ttu-id="4e7c4-165">Crear publicaciones y definir artículos</span><span class="sxs-lookup"><span data-stu-id="4e7c4-165">Creating publications and defining articles</span></span>  
  
-   <span data-ttu-id="4e7c4-166">Eliminar publicaciones y artículos</span><span class="sxs-lookup"><span data-stu-id="4e7c4-166">Deleting publications and articles</span></span>  
  
-   <span data-ttu-id="4e7c4-167">Crear una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="4e7c4-167">Creating a pull subscription</span></span>  
  
-   <span data-ttu-id="4e7c4-168">Modificar una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="4e7c4-168">Modifying a pull subscription</span></span>  
  
-   <span data-ttu-id="4e7c4-169">Eliminar una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="4e7c4-169">Deleting a pull subscription</span></span>  
  
-   <span data-ttu-id="4e7c4-170">Crear una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="4e7c4-170">Creating a push subscription</span></span>  
  
-   <span data-ttu-id="4e7c4-171">Modificar una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="4e7c4-171">Modifying a push subscription</span></span>  
  
-   <span data-ttu-id="4e7c4-172">Eliminar una suscripción de inserción</span><span class="sxs-lookup"><span data-stu-id="4e7c4-172">Deleting a push subscription</span></span>  
  
-   <span data-ttu-id="4e7c4-173">Sincronizar una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="4e7c4-173">Synchronizing a pull subscription</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e7c4-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e7c4-174">See Also</span></span>  
 <span data-ttu-id="4e7c4-175">[Conceptos de la programación de replicación](replication-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="4e7c4-175">[Replication Programming Concepts](replication-programming-concepts.md) </span></span>  
 <span data-ttu-id="4e7c4-176">[Procedimientos almacenados de replicación &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4e7c4-176">[Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="4e7c4-177">Crear script para la replicación</span><span class="sxs-lookup"><span data-stu-id="4e7c4-177">Scripting Replication</span></span>](../scripting-replication.md)  
  
  
